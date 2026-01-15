# Developer Overview

Technical information for developers integrating with Stargaze on the Cosmos Hub.

## Architecture

Stargaze runs on the **Cosmos Hub** using CosmWasm smart contracts. All NFT collections use the **CW721** standard.

## Contract Standard

Stargaze uses CW721 (Cosmos NFT standard) with extensions for:
- Royalty payments
- Collection metadata
- Migration support

See [CW721 Contract Reference](cw721-reference.md) for message specs.

## Chain Information

| Property | Value |
|----------|-------|
| Chain | Cosmos Hub |
| Chain ID | cosmoshub-4 |
| Token | ATOM |
| Contract Standard | CW721 |

## Querying NFT Data

To query NFT data on-chain, use standard CosmWasm contract queries against the collection contract address.

For indexed data (listings, sales history, etc.), contact the Stargaze team for API access.

## Building on Stargaze

Stargaze operates on the Cosmos Hub. For general Cosmos development:
- [Cosmos SDK Documentation](https://docs.cosmos.network)
- [CosmWasm Documentation](https://docs.cosmwasm.com)
- [CW721 Spec](https://github.com/CosmWasm/cw-nfts)

## API Access

Stargaze APIs and indexer access are not publicly available. For integration partnerships, contact the team via Discord.
