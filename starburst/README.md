# What is StarBurst?

**StarBurst** is an NFT raffle protocol built by Stargaze and running on the Cosmos Hub. It lives at [starburst.stargaze.zone](https://starburst.stargaze.zone).

**Minting a collection that has a StarBurst raffle attached earns you raffle tickets, and those tickets can win you more NFTs.**

A creator opens a raffle, stocks it with prize NFTs, and connects it to their own mint. Everyone who mints that collection earns tickets automatically. At set points the raffle draws winners, and winners claim their prizes to their own wallet.

Raffles are set up per collection by the creator, so they are the exception rather than the rule. Minting a collection that has no pool attached to it earns nothing, and the pools listed on [starburst.stargaze.zone](https://starburst.stargaze.zone) are where to find the collections that are running one.

Everything that matters happens on-chain: tickets are credited by a contract that verifies your mints, prizes sit in a contract vault until they are won, and the draw result is recorded on the Cosmos Hub.

## The three steps

<table><thead><tr><th width="180">Step</th><th>What happens</th></tr></thead><tbody><tr><td><strong>1. Pick a pool</strong></td><td>Each raffle is its own "pool", run by one creator with its own prizes, rounds and rules.</td></tr><tr><td><strong>2. Mint to enter</strong></td><td>Mint the collection the pool is attached to. Tickets are credited in the same transaction, so there is nothing extra to sign.</td></tr><tr><td><strong>3. Win prizes</strong></td><td>When a round closes, winners are drawn from the ticket pool and claim their prizes from the pool page.</td></tr></tbody></table>

More mints means more tickets, and more tickets means better odds. Tickets are not spent when you win. They are a weight in the draw, not a currency.

## Who StarBurst is for

* **Collectors.** A raffle turns a mint into two chances at once: the NFT you mint, and whatever the pool is giving away. Entering costs nothing beyond the mint you were already making.
* **Creators.** A pool is a launch mechanic. It rewards early minters, gives a reason to mint more than one, and pays out in NFTs you already hold, with no new token and no external tooling.

## The words StarBurst uses

<table><thead><tr><th width="190">Term</th><th>Meaning</th></tr></thead><tbody><tr><td><strong>Pool</strong></td><td>One raffle event, run by one creator. Pools are fully isolated, so one pool's prizes can never be drawn by another.</td></tr><tr><td><strong>Round</strong></td><td>A slice of a pool that draws its own winners. A pool has one or more rounds.</td></tr><tr><td><strong>Ticket</strong> (or <strong>entry</strong>)</td><td>Your weight in a round's draw. Earned by minting the collection that pool is attached to.</td></tr><tr><td><strong>Vault</strong></td><td>The prize NFTs the creator has deposited into the pool. Held by the contract until claimed.</td></tr><tr><td><strong>Tier</strong></td><td>Prizes are labelled <strong>epic</strong>, <strong>rare</strong> or <strong>common</strong>. The tier decides how likely a prize is to be drawn.</td></tr><tr><td><strong>Pack</strong></td><td>A bundle of NFTs, ATOM or STARS awarded to a single winner as one prize.</td></tr><tr><td><strong>Draw</strong></td><td>The transaction that picks a round's winners and assigns each one a prize.</td></tr></tbody></table>

## What you need

* A **Keplr** wallet connected to the Cosmos Hub.
* **ATOM** for the mint price and transaction fees.

There is currently no separate fee to enter a raffle. You pay the mint price of the collection and normal Cosmos Hub gas, and nothing else.

## Past events

The original Stargaze raffle, the **Stargaze Arrival** event, predates the pool system and ran on its own contract. It appears under **Past Events** on the StarBurst landing page, and anyone who won a prize there can still claim it from that page.

## Next steps

* [Entering a Raffle](entering-a-raffle.md): connect, mint, and earn tickets
* [Rounds & Draws](rounds-and-draws.md): when a round closes and how winners are picked
* [Prizes & Packs](prizes-and-packs.md): tiers, odds, and bundled prizes
* [Winning & Claiming](winning-and-claiming.md): getting your prize into your wallet
* [Running a Pool](running-a-pool.md): the creator's guide
* [StarBurst FAQ](faq.md)
