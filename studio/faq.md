# FAQ & Troubleshooting

Common questions about Studio 2.0. Still stuck? See [Community & Support](../help/community-and-support.md).

## General

**What's different about Studio 2.0?**
It stores your art and metadata **permanently on Arweave** — pay once, kept forever — instead of on IPFS, which needs ongoing pinning. It also adds a full collection manager, built-in creator tools, and a testnet-first workflow. See [What is Arweave?](what-is-arweave.md).

**Do I need to know how to code?**
No. The creation and management flows are fully guided. The [Developer Tools](developer-tools.md) are optional extras for advanced users.

**Which wallet do I need?**
Keplr — your normal Cosmos wallet, the same one you use to collect on Stargaze.

## Testnet & mainnet

**Do I have to use testnet?**
It's strongly recommended. You rehearse the on-chain steps for free on testnet — the app tops up your testnet ATOM automatically — so you can get everything right before going live. Storage is the exception: Arweave has no testnet, so that upload is real and permanent, but you pay for it once and it carries over to mainnet.

**If I test on testnet, do I re-upload for mainnet?**
No. Your Arweave files are permanent and network-agnostic, so mainnet reuses the exact files from testnet. You only pay the on-chain creation fee and gas to go live — never a second storage charge.

## Storage & costs

**Are my files really permanent?**
Yes. Once uploaded to Arweave, they're stored forever with no renewals — and because the address is content-based, the file can't be swapped or lost.

**Why is storage paid in ATOM?**
Studio 2.0 quotes and charges Arweave storage in Cosmos-native ATOM, right in the app — no credit card or separate storage account needed. See [Costs & Fees](costs-and-fees.md).

**How do I keep my storage cost low?**
Shrink your files before uploading with the [Image & Video Resizer](creator-tools.md). Storage is priced by size, so smaller files cost less.

**Can my collection be minted in STARS?**
Yes — you can price your mint in ATOM or STARS. Network fees (creation, gas, storage) are always in ATOM.

## After launch

**What can I change after launching?**
Pricing, per-wallet limits, mint start/end, trading start, royalties, whitelist, and (where allowed) metadata — all from the [Collection Manager](managing-your-collection.md).

**What can't I change?**
Total supply (for fixed-supply collections), the contract address, and your permanent Arweave art.

## Troubleshooting

**My collection's images aren't showing on the marketplace yet.**
Freshly uploaded Arweave files can take a little time to propagate across gateways before every image resolves everywhere. This usually settles on its own shortly after upload. If images are still missing well after launch, reach out in [Community & Support](../help/community-and-support.md).

**A transaction failed with an "out of gas" error.**
Make sure your wallet is on the right network and has enough ATOM for gas, then retry. If it persists, hard-refresh the page to load the latest version of Studio and try again.

**The manager says "connect your wallet to broadcast actions."**
Loading a collection to view it doesn't require a wallet, but making changes does — and only the collection's creator wallet can perform admin actions. Connect the wallet you launched with.

**My whitelist members aren't showing on another device.**
Studio keeps a readable copy of your member list on the device you built it on. To move it, use **Download CSV** on the [Whitelists](whitelists.md) page and re-import it where you need it. The whitelist itself still works — minting isn't affected.
