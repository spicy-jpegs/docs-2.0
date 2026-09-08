# Entering a Raffle

Entering a StarBurst pool means minting the collection that pool is attached to. There is no separate sign-up, no deposit, and no ticket purchase.

## Before you start

* A **Keplr** wallet connected to the Cosmos Hub.
* Enough **ATOM** for the mint price plus transaction fees.

## Pick a pool

Open [starburst.stargaze.zone](https://starburst.stargaze.zone). The landing page lists every published pool with its prize count, round count and status.

<table><thead><tr><th width="170">Badge</th><th>What it means</th></tr></thead><tbody><tr><td><strong>LIVE</strong></td><td>A round is open and mints are earning tickets right now.</td></tr><tr><td><strong>UPCOMING</strong></td><td>The pool is published but its first round has not opened yet.</td></tr><tr><td><strong>PENDING DRAW</strong></td><td>A round has closed and its winners have not been drawn yet.</td></tr><tr><td><strong>PAUSED</strong></td><td>The creator has paused the pool. Ticket earning and claiming are on hold.</td></tr><tr><td><strong>ENDED</strong></td><td>Every round has finished.</td></tr></tbody></table>

Open a pool to see its prizes, its rounds, the collection it is attached to, and how many tickets each mint earns.

## Mint to enter

On the pool page, the **MINT TO ENTER** card shows the connected collection, its price, and the tickets you will earn per mint. Choose a quantity and mint.

The mint transaction carries the ticket claim with it, so one signature does both. When it confirms you will see how many NFTs you minted and how many tickets were added.

{% hint style="info" %}
You can also mint the collection on [stargaze.zone](https://stargaze.zone) as you normally would. That mint credits your tickets too, because the raffle claim is bundled into the same transaction there as well.
{% endhint %}

## Crediting mints made elsewhere

If you minted the collection before the pool was connected, or through another interface that did not bundle the claim, your mints are not lost. The pool page has an **Already minted? Claim entries** link that credits everything you have minted and not yet been credited for, in one transaction.

This is safe to run at any time and safe to repeat. The contract tracks how many of your mints it has already credited and only ever awards the difference.

{% hint style="warning" %}
Some pools are set to count only mints made **after** the pool opened. In that case earlier mints are deliberately excluded and claiming will not credit them. The pool page says which setting is in use.
{% endhint %}

## How many tickets a mint earns

The creator sets the rate, and the pool page always shows the live figure as **PER MINT**. There are three ways a rate can be set, and StarBurst uses the most specific one that applies:

<table><thead><tr><th width="240">How the rate is set</th><th>How it works</th></tr></thead><tbody><tr><td><strong>A fixed number per mint</strong></td><td>The creator pins an exact ticket count per mint, whatever the price is.</td></tr><tr><td><strong>A rate per whitelist stage</strong></td><td>A collection with tiered whitelist stages can pay a different number of tickets in each stage, for example more tickets during an early access stage than at public mint.</td></tr><tr><td><strong>A rate per ATOM spent</strong></td><td>The default. The creator sets tickets per 1 ATOM of mint spend, so a more expensive mint earns proportionally more tickets.</td></tr></tbody></table>

Because the last one is based on what you spend, minting more in one transaction earns more tickets. The card shows the running total as you change the quantity.

## Checking your entries and odds

The pool page has a **Your Entries** panel showing your tickets in the open round next to the round's total, with your live odds. Those odds move as other people mint, so they are a snapshot rather than a promise.

If a round can award more prizes than it has participants, the panel says so. That is the situation where entering effectively guarantees a prize.

## Ticket rules and costs

* **Tickets belong to a round, not to the pool.** When a round closes, its tickets are used for that round's draw and the next round starts everyone from zero.
* **A mint can be split across rounds.** In a pool where rounds close on a mint count, minting a quantity that crosses the boundary puts some of your tickets in the closing round and the rest in the next one, in the order they were minted.
* **Tickets are not spent when you win.** They stay counted for the rest of that round's draw.
* **Pool admins cannot earn tickets in their own pool.** The contract blocks it, so a creator cannot enter their own raffle.
* **There is no entry fee today.** You pay the collection's mint price and Cosmos Hub gas.

## Next steps

* [Rounds & Draws](rounds-and-draws.md): when a round closes and how winners are picked
* [Winning & Claiming](winning-and-claiming.md): what to do when you win
