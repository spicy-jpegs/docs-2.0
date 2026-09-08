# Prizes & Packs

Every prize in a StarBurst pool was put there by the creator before the draw. Prize NFTs are transferred into the pool's **vault**, where the contract holds them until they are won and claimed.

A pool can only ever draw from its own vault. Pools are isolated from one another.

## Tiers

Each prize NFT carries a tier: **epic**, **rare** or **common**.

A tier is a probability bucket, not a quality grade. The creator decides which NFTs go in which tier. What the tier controls is how often the draw reaches for it.

The creator sets the odds as percentages. Epic and rare are given explicitly, and whatever is left over is common:

| Setting | Example |
| --- | --- |
| Epic odds | 2% |
| Rare odds | 10% |
| Common | the remaining 88% |

A creator can also cap the number of epic prizes a single round may award, so a lucky streak cannot empty the top tier in one draw.

If a tier runs out mid-draw, the prize moves to a tier that still has stock rather than being skipped. See [Rounds & Draws](rounds-and-draws.md).

## Packs

A **pack** is several things won together as a single prize by a single wallet.

A pack can hold NFTs, ATOM or STARS, or a combination. It is awarded to one winner before the individual prizes are drawn, and it counts as exactly one win against that wallet's limit for the round.

{% hint style="warning" %}
A pack of 44 NFTs goes to **one** wallet, not to 44 winners. This is the point of a pack, and it is worth being explicit about it when a pool advertises a large one.
{% endhint %}

There are three kinds:

<table><thead><tr><th width="200">Kind</th><th>What the winner receives</th></tr></thead><tbody><tr><td><strong>Specific</strong></td><td>Exactly the NFTs the creator hand-picked. Those NFTs are reserved when the pack is built and cannot be drawn as individual prizes.</td></tr><tr><td><strong>Random</strong></td><td>A set number of NFTs, drawn from the vault at draw time by the pack's own tier odds. The contents are not known until the round is drawn.</td></tr><tr><td><strong>Cash only</strong></td><td>ATOM or STARS and no NFTs.</td></tr></tbody></table>

Any pack can also carry coins on top of its NFTs, so "1,000 STARS and 2 NFTs" is one pack.

Coins in a pack are deposited by the creator when the pack is built and held by the contract in escrow until the pack is claimed or removed. They are not spendable by anyone else in the meantime.

{% hint style="info" %}
A pack's own epic / rare / common label is a display badge. The NFTs inside it keep their own tiers, and a pack labelled epic may contain NFTs of any tier.
{% endhint %}

## Prize pools per round

By default every round in a pool draws from the same shared vault. A creator running a pool with mint-count rounds can instead give **each round its own prize pool**: its own hand-picked NFTs, its own tier odds, its own prize count and its own win limit.

That turns one event into a series of separate mini-raffles, for example a modest round one, a larger round two, and a headline prize in the final round.

When a pool is set up this way the pool page shows a **PRIZES BY ROUND** breakdown so entrants can see what each round is actually offering before they mint.

## Reading the prize numbers

* The **prize count** on a pool card and in the pool header is the number of prize **NFTs** on offer, including every NFT sitting inside a pack.
* **Max prizes per round** is a different number: how many separate prizes a single round is allowed to award. A round with one 44-NFT pack awards one prize.
* A drawn round's prizes have left the vault, so a pool's remaining vault count falls as the event runs.

## Next steps

* [Winning & Claiming](winning-and-claiming.md): getting a prize into your wallet
* [Running a Pool](running-a-pool.md): depositing prizes and building packs
