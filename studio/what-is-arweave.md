# What is Arweave?

Arweave is a network for **permanent file storage**. You pay once, and your files are stored forever — there's no monthly bill, no renewal, and no service that can quietly drop your data. Studio 2.0 uses Arweave to store your NFT artwork and metadata, so a collection you launch today is still fully intact years from now.

<figure><img src="../.gitbook/assets/studio2-vending-create.png" alt="Arweave permanent storage and launch cost panel in Studio 2.0"><figcaption>Studio 2.0 shows your permanent-storage and launch costs up front, before you upload.</figcaption></figure>

## Why it matters for your NFTs

An NFT is really two parts:

1. **The token** — an entry on the blockchain that says who owns it. This lives on Stargaze forever.
2. **The artwork and metadata** — the image, animation, name, and traits. These are usually stored *off-chain*, and the token just points to them.

If that off-chain storage ever becomes unavailable, the token still exists on-chain — but the artwork it points to can't load. Permanent storage removes that risk entirely: your art is guaranteed to stay exactly where it is, for good.

{% hint style="info" %}
An NFT is only as permanent as the place its art is stored. Arweave makes that place permanent by design.
{% endhint %}

## Arweave vs. IPFS pinning

Another common way to store NFT files is **IPFS**, which keeps files available only as long as someone keeps "pinning" them. Pinning is an ongoing job — usually a paid service — so it depends on that service continuing. Studio 2.0 uses Arweave instead: you pay once, and there's nothing to keep renewing or maintaining.

| | IPFS pinning | Arweave (Studio 2.0) |
|---|---|---|
| **How long it's stored** | As long as it's actively pinned | Permanently, guaranteed at upload |
| **Ongoing cost** | Recurring pinning fees | None — pay once |
| **What you pay** | Subscription to a pinning service | A one-time fee in ATOM, shown up front |

## What an `ar://` link is

When Studio 2.0 uploads your files, each one gets a permanent address that looks like this:

```
ar://GRYCsHU7yF5jJ0P9K1e1Yb...
```

That `ar://` address is baked into your collection's on-chain records. Anyone — Stargaze, a marketplace, or a wallet — can resolve it through any Arweave gateway to load your art. Because the address is permanent and content-addressed, the file it points to can never be swapped or lost.

## How you pay for it

You don't need an Arweave account or a separate wallet. Studio 2.0 handles it for you:

1. Studio calculates the exact storage cost from your files' total size and shows it **before** you upload.
2. You pay that amount in **ATOM**, signed from your normal Stargaze wallet.
3. Studio uploads your files to Arweave and writes the permanent `ar://` addresses into your collection.

{% hint style="info" %}
**Storage is priced by size.** Arweave charges by how much data you store (a set rate per gigabyte), so a small, well-optimized collection is inexpensive while a large one with heavy media costs more. Run your files through the built-in [Resizer](creator-tools.md) first to bring the size — and the cost — down.
{% endhint %}

## Arweave has no testnet

Arweave storage is always permanent — there's no throwaway "test" version. So the art you upload while rehearsing your collection on the Cosmos Hub testnet is the **same** art your mainnet collection uses. You pay to store it once, and when you promote from testnet to mainnet, Studio reuses those exact uploads with no second storage charge.

Next: [Getting Started](getting-started.md) →
