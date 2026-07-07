# What is Arweave?

Arweave is a network for **permanent file storage**. You pay once, and your files are stored forever — there's no monthly bill, no renewal, and no service that can quietly drop your data. Studio 2.0 uses Arweave to store your NFT artwork and metadata, so a collection you launch today is still fully intact years from now.

<figure><img src="../.gitbook/assets/studio2-vending-create.png" alt="Arweave permanent storage and launch cost panel in Studio 2.0"><figcaption>Studio 2.0 shows your permanent-storage and launch costs up front, before you upload.</figcaption></figure>

## Why it matters for your NFTs

An NFT is really two parts:

1. **The token** — an entry on the blockchain that says who owns it. This lives on Stargaze forever.
2. **The artwork and metadata** — the image, animation, name, and traits. These are usually stored *off-chain*, and the token just points to them.

If that off-chain storage goes away, your NFT still exists on-chain — but the picture is gone. This is the "broken image" problem you've probably seen on older collections.

{% hint style="warning" %}
An NFT is only as permanent as the place its art is stored. If the storage disappears, so does the image — even though the token itself is safe on-chain.
{% endhint %}

## Arweave vs. IPFS pinning

The original Studio used **IPFS**, which stores files as long as someone keeps "pinning" them. Pinning is an ongoing job — usually a paid service — and if the pin lapses, the file can become unreachable.

| | IPFS (old Studio) | Arweave (Studio 2.0) |
|---|---|---|
| **How long it's stored** | As long as it's actively pinned | Permanently, guaranteed at upload |
| **Ongoing cost** | Monthly pinning fees | None — pay once |
| **Risk of link rot** | Yes, if pinning stops | No |
| **What you pay** | Subscription to a pinning service | A one-time fee in ATOM, shown up front |

## What an `ar://` link is

When Studio 2.0 uploads your files, each one gets a permanent address that looks like this:

```
ar://GRYCsHU7yF5jJ0P9K1e1Yb... 
```

That `ar://` address is baked into your collection's on-chain records. Anyone — Stargaze, a marketplace, or a wallet — can resolve it through any Arweave gateway to load your art. Because the address is permanent and content-addressed, the file it points to can never be swapped or lost.

## How you pay for it

You don't need an Arweave account or a separate wallet. Studio 2.0 handles it for you:

1. Studio calculates the exact storage cost based on your files' size and shows it **before** you upload.
2. You pay that amount in **ATOM**, signed from your normal Stargaze wallet.
3. Studio uploads your files to Arweave and writes the permanent `ar://` addresses into your collection.

{% hint style="info" %}
**Tip:** smaller files cost less to store forever. Resizing images and using efficient formats (like WebP) before you upload keeps your storage cost low — often just a few cents for a whole collection.
{% endhint %}

## Testnet and mainnet share the same files

Because an `ar://` address is permanent and network-agnostic, files you upload while testing on testnet are the **same files** you use on mainnet. When you promote a collection from testnet to mainnet, Studio reuses those uploads — you don't pay to store them twice.

Next: [Getting Started](getting-started.md) →
