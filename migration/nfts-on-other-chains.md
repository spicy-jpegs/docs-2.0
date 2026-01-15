# NFTs on Other Chains / DAOs

Special cases for NFTs that weren't in a standard wallet on Stargaze L1.

## NFTs in DAO Treasuries

If your DAO's treasury holds NFTs, they must be moved before the migration snapshot.

### Why This Matters

DAO contract addresses cannot be reconstructed on the Cosmos Hub. Treasury NFTs will **not** migrate automatically.

### What's Affected

* **Treasury-held NFTs** - Must be moved to a multisig or single wallet
* **Staked NFTs** - NOT affected, claimable by the staker

Only treasury-held NFTs need action.

### What to Do

1. Move NFTs out of DAO treasuries to a multisig or single wallet
2. Deadline: January 31st
3. After moving, NFTs can be claimed normally on the Hub

### After the Snapshot

If NFTs were still in a DAO treasury at snapshot:
* They cannot be claimed on the Hub
* Check your DAO's treasury on daodao.zone
* Contact the DAO creator if needed

## NFTs on Other Chains (ICS-721)

Some NFTs were transferred to other chains via ICS-721 (interchain NFT standard).

### Stargaze NFTs on Osmosis/Neutron

If you had Stargaze-native NFTs on another chain:
* They're being pushed back to their home chains
* You may need to claim them separately
* Check the original chain for your NFTs

### Non-Stargaze NFTs on Stargaze

Collections like Mad Scientists (home chain: Osmosis):
* Migrating to their home chain
* Can be bridged to Hub via ICS-721 if desired
* Check with the collection for specific instructions

We've contacted all ICS-721 collection creators to coordinate the migration.

### Affected Collections

| Collection | Home Chain | Status |
|------------|------------|--------|
| Mad Scientists | Osmosis | Migrates to Osmosis, can bridge to Hub via ICS-721 |
| Other ICS-721 | Various | Check collection announcements |

## NFTs in Multisig Wallets

Good news: Multisig wallets work!

* Same members can recreate the multisig on Hub
* The derived address is the same
* Claim NFTs to the multisig address

### How to Claim with Multisig

1. Recreate your multisig on Cosmos Hub (same members)
2. The address will match your L1 multisig
3. Initiate claim from the multisig
4. Collect required signatures
5. NFTs transfer to the multisig

## Edge Cases

### Lost Access

If you lost wallet access:
* Cannot claim without private keys
* No recovery mechanism exists
* Standard crypto self-custody applies

### Disputed Ownership

If there's a dispute:
* Snapshot is the source of truth
* On-chain ownership at snapshot block
* Contact support with transaction evidence

## Getting Help

These situations can be complex:
* Join Discord #support
* Provide wallet addresses and context
* Team members can investigate

## Summary

| Situation | Action |
|-----------|--------|
| NFTs in regular wallet | Claim normally |
| NFTs in DAO treasury | Check daodao.zone, contact DAO creator |
| NFTs on other chains | Check home chain |
| NFTs in multisig | Recreate multisig, claim |
