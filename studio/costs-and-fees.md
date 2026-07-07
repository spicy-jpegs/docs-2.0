# Costs & Fees

Studio 2.0 is transparent about cost: every fee is shown **live, before you confirm**, and testnet is completely free. This page explains what makes up the total so there are no surprises.

<figure><img src="../.gitbook/assets/studio2-vending-create.png" alt="Live launch cost panel in Studio 2.0"><figcaption>The launch panel breaks down storage, fees, and gas before you commit — and shows the free testnet path.</figcaption></figure>

## Testnet is free

Rehearsing on the Cosmos Hub testnet costs nothing — you use free faucet ATOM. Build, launch, and preview as many times as you like before spending anything real.

## What you pay on mainnet

A mainnet launch is made of a few parts, all shown in the app before you sign:

| Cost | What it's for | Notes |
|---|---|---|
| **Permanent storage** | Storing your art + metadata on Arweave, forever | One-time, priced by file size — often just cents. Paid in ATOM. |
| **Collection creation fee** | The on-chain fee to create your collection | Depends on the type and size (for example, a Vending drop is priced per 1,000 tokens). |
| **Whitelist fee** | Deploying a whitelist contract, if you add one | Small, optional. |
| **Network gas** | The blockchain transaction fee | A fraction of an ATOM per action. |

{% hint style="success" %}
**You never pay for storage twice.** Files uploaded during testnet are reused on mainnet, so promoting a collection only costs the on-chain creation fee and gas — not another storage charge.
{% endhint %}

## Keep storage cheap

Because permanent storage is priced by size, the single best way to lower your cost is to **shrink your files first**. Use the [Image & Video Resizer](creator-tools.md) to convert images to WebP and compress video before you upload — a whole collection of well-sized files often costs only a few cents to store forever.

## Ongoing costs

There are **none** for storage — that's the whole point of Arweave. You pay once at launch and your art is kept permanently, with no monthly bills or renewals. After launch, you only pay small network gas fees when you take an action in the [Collection Manager](managing-your-collection.md) (updating price, airdropping, withdrawing, etc.).

## A note on mint tokens

Your collection can be minted in **ATOM or STARS** — you choose. Note that this is separate from the fees above: creation fees, storage, whitelist deployment, and gas are always paid in **ATOM** by the network, even if your collection is minted in STARS.

## Next steps

* [What is Arweave?](what-is-arweave.md) — why storage is pay-once
* [Getting Started](getting-started.md) — the free testnet-first workflow
