# CW721 Contract Reference

Stargaze NFT collections use CW721 contracts on the Cosmos Hub.

## Instantiate

Create a new collection:

```json
{
  "name": "Collection Name",
  "symbol": "SYMBOL",
  "minter": "cosmos1...",
  "creator": "cosmos1...",
  "collection_info_extension": {
    "description": "Collection description",
    "image": "ipfs://...",
    "external_link": "https://...",
    "royalty_info": {
      "payment_address": "cosmos1...",
      "share": "0.05"
    }
  }
}
```

## Execute Messages

### Transfer NFT

```json
{
  "transfer_nft": {
    "recipient": "cosmos1...",
    "token_id": "1"
  }
}
```

### Send NFT (to contract)

```json
{
  "send_nft": {
    "contract": "cosmos1...",
    "token_id": "1",
    "msg": "<base64-encoded-message>"
  }
}
```

### Approve

```json
{
  "approve": {
    "spender": "cosmos1...",
    "token_id": "1",
    "expires": { "at_height": 12345678 }
  }
}
```

### Revoke

```json
{
  "revoke": {
    "spender": "cosmos1...",
    "token_id": "1"
  }
}
```

### Approve All

```json
{
  "approve_all": {
    "operator": "cosmos1...",
    "expires": { "at_time": "1234567890000000000" }
  }
}
```

### Revoke All

```json
{
  "revoke_all": {
    "operator": "cosmos1..."
  }
}
```

### Burn

```json
{
  "burn": {
    "token_id": "1"
  }
}
```

### Update Collection Info

```json
{
  "update_collection_info": {
    "collection_info": {
      "name": "New Name",
      "symbol": "NEW",
      "extension": {
        "description": "Updated description",
        "royalty_info": {
          "payment_address": "cosmos1...",
          "share": "0.10"
        }
      }
    }
  }
}
```

## Query Messages

### Owner Of

Get the owner of a token:

```json
{
  "owner_of": {
    "token_id": "1",
    "include_expired": false
  }
}
```

### NFT Info

Get token metadata:

```json
{
  "nft_info": {
    "token_id": "1"
  }
}
```

**Response:**
```json
{
  "token_uri": "ipfs://...",
  "extension": {}
}
```

### All NFT Info

Get owner and metadata:

```json
{
  "all_nft_info": {
    "token_id": "1",
    "include_expired": false
  }
}
```

### Tokens (by owner)

List tokens owned by an address:

```json
{
  "tokens": {
    "owner": "cosmos1...",
    "start_after": "0",
    "limit": 100
  }
}
```

### All Tokens

List all tokens in collection:

```json
{
  "all_tokens": {
    "start_after": "0",
    "limit": 100
  }
}
```

### Num Tokens

Get total supply:

```json
{
  "num_tokens": {}
}
```

### Collection Info

Get collection metadata:

```json
{
  "get_collection_info_and_extension": {}
}
```

### Approvals

Get approvals for a token:

```json
{
  "approvals": {
    "token_id": "1",
    "include_expired": false
  }
}
```

### All Operators

Get all operators for an owner:

```json
{
  "all_operators": {
    "owner": "cosmos1...",
    "include_expired": false,
    "start_after": null,
    "limit": 100
  }
}
```

## Royalties

Royalties are set in the collection extension:

```json
{
  "royalty_info": {
    "payment_address": "cosmos1...",
    "share": "0.05"
  }
}
```

- `share` is a decimal (0.05 = 5%)
- Maximum royalty: 10% (0.10)
- Royalties are enforced by the marketplace contract

## Expiration Types

Used for approvals:

```json
// Block height
{ "at_height": 12345678 }

// Timestamp (nanoseconds)
{ "at_time": "1234567890000000000" }

// Never expires
{ "never": {} }
```

## External Resources

- [CW721 Spec](https://github.com/CosmWasm/cw-nfts/tree/main/packages/cw721)
- [CosmWasm Documentation](https://docs.cosmwasm.com)
- [Cosmos Hub Documentation](https://hub.cosmos.network)
