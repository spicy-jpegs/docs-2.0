# Integrating Names (Developers)

Technical reference for resolving, registering, and displaying Stargaze Names from your own app, wallet, or indexer.

Everything below is on-chain and permissionless — no API key, no allowlist.

## Contracts

| Contract | Role | Mainnet (`cosmoshub-4`) |
| --- | --- | --- |
| **name-collection** | The NFT + resolver. Owner, records, avatar, banner, forward and reverse resolution. | `cosmos1pq7vpw5k3ad4jlaskuhm66gjapump23zz69ut9fck2p5k5p4sq9s79da69` |
| **name-registrar** | The controller. Pricing, the lease clock, lifecycle, fee routing. Sole minter of the collection. | `cosmos1agnzrv9mwkufzjwux2yy3ff077x6phetdzgd2tffsr72ah33eunqt5pmnq` |
| **marketplace v2** | Secondary sales. Escrows the NFT while listed. | `cosmos1tl0ptdmlz422z5pj20zujzyt3c96qp2g9vp83uj9pyj8q994tzhsl77adr` |
| **reserve auction** | Auctions. Escrows the NFT *and* the high bid. | `cosmos1jyx8zpvjxq2vdmquvrw6cwl2qp9slmnyy8dnpj3cgyvava2x7lmqhj3mmy` |

Testnet (`provider`):

| Contract | Address |
| --- | --- |
| name-collection | `cosmos1hl6dx3yepsm8tjz80jxp6c6tchm4mqljk6yp63gxj7h8n7xj3rgsjns5rc` |
| name-registrar | `cosmos1af8xd3ctlahs3ccdweyvd6pmwsxmkjv76jfkef6f3hs6dsv9646snkfrq0` |

Mainnet and testnet hold completely independent state — a name registered on one does not exist on the other.

{% hint style="info" %}
Never hardcode the collection address if you can avoid it. Query the registrar's `{"config":{}}` and read `collection` from the response.
{% endhint %}

## The model in one paragraph

A name is a **CW721 v0.22 NFT whose `token_id` is the name string**. Owning the NFT is owning the name. The **collection** holds ownership, records, and both directions of resolution. The **registrar** holds the lease clock (`EXPIRY[name]`), prices registrations, and is the only address allowed to mint or reclaim. Lifecycle status is not stored anywhere — it is derived from `expiry` plus the current block time.

## Five things that will bite you

Read these before writing any code.

1. **The registrar does not resolve names.** It has exactly six queries — `expiry`, `status`, `price`, `is_available`, `config`, `whitelist_usage` — and none of them turn a name into an address. Resolution lives on the **collection**, behind the CW721 `extension` wrapper.
2. **A name that doesn't exist returns an error, not `null`.** Over LCD you get an HTTP 500 with `"Name not found"`. Most wallets are unnamed, so this is the *common* path — treat it as "no name" and don't log, retry, or surface it as a failure.
3. **`associated_address` is not `owner_of`.** A name owned by wallet A can point at wallet B, or at a contract. `owner_of` returns a plausible-looking wrong answer, and the two coincide for most names, so the bug is invisible in testing. Never substitute one for the other.
4. **Resolution is expiry-gated.** Forward and reverse resolution return a result **only while the lease is current**. The moment a name enters grace, both queries start erroring — even though the NFT is still owned and still tradeable.
5. **Prices are in `uatom`.** Not `ustars`. The registrar's `price` query also validates nothing about availability — it will happily quote a name that is already taken. Always pair it with `status`.

## Resolving a name

### Forward — name → address

```bash
COL=cosmos1pq7vpw5k3ad4jlaskuhm66gjapump23zz69ut9fck2p5k5p4sq9s79da69
Q=$(echo -n '{"extension":{"msg":{"associated_address":{"name":"starty"}}}}' | base64)
curl -s "https://hub-rest.stargaze-apis.com/cosmwasm/wasm/v1/contract/$COL/smart/$Q"
# {"data":"cosmos1dt8sxe4yhmt742aq78unyaglhmqy59pnhap96w3mdszzc7t2g0yqu2as4l"}
```

### Reverse — address → name

```bash
Q=$(echo -n '{"extension":{"msg":{"name":{"address":"cosmos1dt8..."}}}}' | base64)
curl -s "https://hub-rest.stargaze-apis.com/cosmwasm/wasm/v1/contract/$COL/smart/$Q"
# {"data":"starty"}
```

An address resolves to **at most one** name — the contract clears any previous association when a new one is set.

### With CosmJS

```ts
import { CosmWasmClient } from '@cosmjs/cosmwasm-stargate';

const client = await CosmWasmClient.connect(RPC);

/** name -> address, or null when unregistered/expired */
async function resolveName(name: string): Promise<string | null> {
  try {
    return await client.queryContractSmart(COLLECTION, {
      extension: { msg: { associated_address: { name } } },
    });
  } catch {
    return null; // "Name not found" is the common case, not an error condition
  }
}

/** address -> name, or null when the address has no current name */
async function reverseLookup(address: string): Promise<string | null> {
  try {
    return await client.queryContractSmart(COLLECTION, {
      extension: { msg: { name: { address } } },
    });
  } catch {
    return null;
  }
}
```

Cache reverse lookups aggressively — they change rarely and you will call them on every address you render.

## Records, avatar, and banner

All on the collection, all behind the same `extension` wrapper, and — unlike resolution — **not** expiry-gated.

| Query | Returns |
| --- | --- |
| `{"text_records":{"name":"starty"}}` | `[{ name, value, verified }]` |
| `{"image_nft":{"name":"starty"}}` | `{ collection, token_id }` or `null` |
| `{"banner_nft":{"name":"starty"}}` | `{ collection, token_id }` or `null` |
| `{"is_twitter_verified":{"name":"starty"}}` | `bool` |

```json
[
  { "name": "twitter",  "value": "startynft",             "verified": true },
  { "name": "discord",  "value": "f79DAyfEdA",            "verified": null },
  { "name": "website",  "value": "https://startynft.com", "verified": null }
]
```

Record keys used by Stargaze: `twitter`, `discord`, `telegram`, `website`, `evm_address`. The contract doesn't restrict the key set, so treat unknown keys as opaque. `verified` is set by a verifier oracle and resets to `null` whenever the value changes.

Avatar and banner are **pointers**, not images — resolve `{collection, token_id}` through the CW721 the usual way. The owner is checked when the pointer is set, not when it's read, so a pointer can outlive the owner's holding of that NFT.

## The lease

### State machine

Status is a pure function of `expiry`, the config windows, and the clock. There is no status field on-chain and no cron job.

| State | Condition | Resolves | Registerable by | Renewable |
| --- | --- | --- | --- | --- |
| **Registered** | `now ≤ expiry` | ✅ | nobody | anyone |
| **Grace** | `≤ expiry + 90d` | ❌ | nobody | anyone |
| **Premium** | `≤ expiry + 90d + 21d` | ❌ | anyone, at `base·years + surcharge(t)` | — |
| **Available** | after that | ❌ | anyone, at `base·years` | — |

```
status(name, t):
  e = expiry(name)
  if e is null:                    Available
  elif t <= e:                     Registered
  elif t <= e + GRACE:             Grace
  elif t <= e + GRACE + PREMIUM:   Premium
  else:                            Available
```

The premium surcharge decays **linearly** to zero across the 21-day window, measured from `expiry + GRACE`.

### Registrar queries

| Query | Returns |
| --- | --- |
| `{"config":{}}` | `{ collection, config }` — the collection address plus every parameter below |
| `{"expiry":{"name":"…"}}` | `{ expiry }` — nanosecond timestamp, `null` if never registered |
| `{"status":{"name":"…"}}` | `{ status: registered\|grace\|premium\|available, expiry }` |
| `{"is_available":{"name":"…"}}` | `bool` |
| `{"price":{"name":"…","years":1}}` | `{ price, denom }` — includes the premium surcharge when applicable |
| `{"whitelist_usage":{"address":"…"}}` | discounted-registration usage under the live whitelist stage, or `null` |

`price` also accepts `sender`, `stage`, `proof_hashes`, and `allocation` to quote the whitelist-member price — it errors in exactly the cases `register` would.

### Live config (mainnet)

```json
{
  "denom": "uatom",
  "base_price": "1000000",
  "min_chars": 3,
  "max_chars": 63,
  "min_years": 1,
  "max_years": 10,
  "grace_period_secs": 7776000,
  "premium_period_secs": 1814400,
  "release_surcharge": "100000000"
}
```

Read these from the chain rather than hardcoding them — they are governance-adjustable.

### Pricing

Per year, derived from `base_price` and the name's length. The multipliers are compiled into the contract; only `base_price` is configurable.

| Length | Price / year |
| --- | --- |
| 3 chars | `base_price × 100` (100 ATOM) |
| 4 chars | `base_price × 10` (10 ATOM) |
| 5+ chars | `base_price × 1` (1 ATOM) |

Whitelist-member pricing halves the 3–4 char tiers and makes 5+ free, **for one year only**, and never discounts the premium surcharge.

## Executes

### Register

```json
{
  "register": {
    "name": "alice",
    "years": 1,
    "max_price": "1000000",
    "stage": null,
    "proof_hashes": null,
    "allocation": null
  }
}
```

Attach `funds ≥ price` in `uatom`; overpayment is refunded. `max_price` is a slippage guard against the decaying premium — the tx reverts rather than overpaying. The NFT is minted (or reclaimed) to the sender and `EXPIRY` is set to `now + years·YEAR`.

Whitelist registrations supply `stage`, `proof_hashes`, and optionally `allocation`; the merkle leaf is `"{stage}{sender}{allocation}"` with `None` parts omitted. A proof that can't be validated **reverts** — it never silently falls back to full price. Free registrations must attach no funds. The discount is limited to 1-year terms; extend with a full-price `renew` in the same transaction.

Two gates apply to `register` and never to `renew`: nothing registers before `config.registration_start_time`, and while a whitelist stage is live, proof-less registration is rejected outright (no full-price fallback).

### Renew

```json
{ "renew": { "name": "alice", "years": 1 } }
```

Permissionless — any address may pay. Allowed while `now ≤ expiry + GRACE`; rejected past grace. Charged at the plain tier price (never discounted, no surcharge) and **extends from the existing expiry**, so renewing early loses nothing and renewing late loses the lapsed time. Rejected if the result would exceed `now + max_years·YEAR`.

### Name execute messages (on the collection)

Sent as `{"update_extension":{"msg": … }}`, owner-gated:

| Message | Effect |
| --- | --- |
| `{"associate_address":{"name":"…","address":"…"\|null}}` | Set or clear forward + reverse resolution. The address must be the sender's own, or a contract they admin. |
| `{"add_text_record":{…}}` / `update_text_record` / `remove_text_record` | Manage records. Each edit resets `verified` to `null`. |
| `{"update_image_nft":{"name":"…","nft":{…}\|null}}` | Set or clear the avatar pointer. Ownership of the referenced NFT is checked at set time. |
| `{"update_banner_nft":{…}}` | Same, for the banner. |

Batch several of these into one transaction — that's what the Stargaze UI does when you hit Save.

## Two invariants you must design around

### Moving a name wipes its state

Every `transfer_nft` / `send_nft` — **regardless of caller**, including the marketplace during escrow — clears the name's entire side-map: associated address, reverse entry, all text records, avatar, and banner. A transferred name arrives clean.

Because listing escrows the NFT, a **list-then-cancel round trip also clears the owner's records**. If your UI lets users list a name, warn them first.

`burn` is rejected on this collection; only the registrar destroys token state, via `reclaim` on the release path.

### Expiry is invisible to the marketplace

CW721 `owner_of` reflects NFT ownership, not the lease. So:

* A name in **grace, premium, or available** is still a normal, owned, tradeable and auctionable NFT.
* A buyer can purchase such a name and have it **re-registered out from under them** — the registrar reclaims the token on the next `register`.
* A bidder on such a name can have the auction cancelled at any moment. The high bid is refunded **in full**, so no funds are lost, but the bid never wins.

The contracts deliberately do not gate transfers on expiry — that would deadlock escrow. **The mitigation is entirely off-chain: any UI or indexer that shows a name listing or auction must surface `status`/`expiry` and warn or block on anything that isn't `registered`.** If you build a marketplace surface over this collection, this is your obligation, not the contract's.

## Indexing

If you're building an indexer rather than querying live:

* **Ingest** `wasm-register`, `wasm-renew`, `wasm-set-whitelist`, and `wasm-update-config` from the registrar (authoritative for expiry); `wasm` `action=transfer_nft`/`send_nft`/`mint`, `wasm-reclaim`, `wasm-associate-address`, the `*-text-record` events, `wasm-update-image-nft`, and `wasm-update-banner-nft` from the collection (authoritative for owner, records, resolution). Always disambiguate by `_contract_address`, and process events in `(height, tx_index, msg_index, event_index)` order.
* **Store `expiry`, compute `status`.** Lifecycle transitions emit **no event** — a name entering grace or being released happens silently as the clock passes a boundary. If you need status filters or user notifications, run a scheduler that re-materializes status near window boundaries.
* **Mirror the wipe rules.** `transfer_nft`, `send_nft`, and `reclaim` all clear associated address, reverse, records, avatar, and banner. Getting this wrong leaves stale records on sold names.
* **Gate cached resolution on `status == registered`**, or your answers will drift from the on-chain ones the moment a lease lapses.
* **Reconcile periodically.** Re-query `owner_of`, `expiry`, `associated_address`, and `text_records` for recently-touched names and correct drift. Cheap insurance against missed events.

## Displaying names well

A few conventions Stargaze follows, worth matching for consistency:

* Render a name as `@name`. The `@` is presentation only — never send it to the chain.
* Names are bare. Don't append `.stars`, `.cosmos`, or anything else.
* Fall back to a truncated address when reverse resolution returns nothing, which is most of the time.
* Never render an un-copyable truncated address as the only representation of an address.
* Validate client-side before quoting a price: 3–62 characters, `^[a-z0-9-]+$`, no leading or trailing hyphen, no hyphens in the 3rd and 4th positions together.

## Next steps

* [Developer Overview](../developers/overview.md) — chain info and CW721 basics
* [What is a Stargaze Name?](what-is-a-stargaze-name.md) — the product behaviour these contracts implement
