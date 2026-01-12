# NFTs on Other Chains / DAOs

Special cases for NFTs that weren't in a standard wallet on Stargaze L1.

## NFTs in DAOs

If your NFTs were held by a DAO contract:

### The Challenge

DAO contracts on Stargaze L1 cannot be recreated on the Cosmos Hub. NFTs in DAOs needed special handling.

### What Happened

* DAOs were notified before migration
* NFTs needed to be moved to regular wallets
* NFTs remaining in DAOs may not be claimable

### What to Do

If your NFTs were in a DAO:
1. Check if the DAO distributed NFTs before snapshot
2. If moved to your wallet, claim normally
3. If still in DAO, contact the DAO administrators

### DAO DAO Specific

DAO DAO on Stargaze is not migrating. NFTs in DAO DAO vaults:
* Should have been withdrawn before snapshot
* Contact your DAO's leadership for status

## NFTs on Other Chains (ICS-721)

Some NFTs were transferred to other chains via ICS-721 (interchain NFT standard).

### Stargaze NFTs on Osmosis/Neutron

If you had Stargaze-native NFTs on another chain:
* They're being pushed back to their home chains
* You may need to claim them separately
* Check the original chain for your NFTs

### Non-Stargaze NFTs on Stargaze

Collections like Mad Scientists (from Osmosis):
* Being returned to their home chain
* Claim on Osmosis, not Cosmos Hub
* Check with the collection for specific instructions

### Affected Collections

| Collection | Home Chain | Status |
|------------|------------|--------|
| Mad Scientists | Osmosis | Returns to Osmosis |
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

## Liquid Staking (stSTARS)

If you held stSTARS or other liquid staking derivatives:

### Unwinding

* LST protocols are unwinding positions
* Watch announcements from Stride/etc.
* Claim underlying STARS, then claim on Hub

### Timeline

LST unwinding happens before the claim period. Make sure to:
1. Unwind your stSTARS
2. Receive STARS in your wallet
3. Claim STARS on Hub

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
* Join Discord #migration-help
* Provide wallet addresses and context
* Team members can investigate

## Summary

| Situation | Action |
|-----------|--------|
| NFTs in regular wallet | Claim normally |
| NFTs in DAO | Contact DAO leadership |
| NFTs on other chains | Check home chain |
| NFTs in multisig | Recreate multisig, claim |
| stSTARS/LST | Unwind first, then claim |
