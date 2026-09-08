# Rounds & Draws

A pool is divided into **rounds**. Each round collects its own tickets and draws its own winners. When a round closes, everyone starts the next one from zero.

## The two ways a round can end

A creator picks one of these when the pool is created, and it applies to the whole pool.

### On a schedule

The creator sets an open and close date for each round. This is the classic raffle format: the round runs for a fixed stretch of time regardless of how many people mint.

The pool page shows a live countdown: **ENDS IN** for the open round, **STARTS IN** for one that has not opened yet.

### Every N mints

The round closes the moment the collection reaches the next mint milestone. The creator writes a **round plan**: a list of mint quotas, one per round, such as 500 · 1,000 · 500.

<table><thead><tr><th width="220">Property</th><th>Detail</th></tr></thead><tbody><tr><td>Round length</td><td>Measured in credited mints, not time. Each round can have a different quota.</td></tr><tr><td>End date</td><td>None. Only the pool's start time is set; every round after that closes on its count.</td></tr><tr><td>Number of rounds</td><td>Fixed by the plan. When the last round closes the pool is finished, and no extra round opens for stragglers.</td></tr><tr><td>Connected collections</td><td>Exactly one. A mint-count pool tracks a single collection so the count is unambiguous.</td></tr></tbody></table>

The mint counter starts at zero when the pool is connected to the collection, so a plan's first number is "close after this many new mints", not a position in the collection's total supply.

If minting stalls part-way through a round, the creator can close the round where it stands from the pool admin page.

## From closed to drawn

<table><thead><tr><th width="200">State</th><th>What it means</th></tr></thead><tbody><tr><td><strong>Open</strong></td><td>Mints are earning tickets for this round.</td></tr><tr><td><strong>Awaiting draw</strong></td><td>The round has closed. Tickets are final and the draw has not run yet.</td></tr><tr><td><strong>Drawn</strong></td><td>Winners are recorded on-chain and prizes are ready to claim.</td></tr></tbody></table>

Draws are run by the Stargaze team, not by the creator. A round sitting in **awaiting draw** is a normal state and does not mean anything is wrong. It resolves when the team runs the draw for it.

## How winners are picked

The draw runs entirely inside the contract, in one transaction, from a seed built out of the block the draw lands in, the round's full participant list, and a value supplied by the operator running it.

### How many prizes a round awards

The number of prizes is the **lower** of two figures:

* the number of distinct wallets that entered the round, and
* the **max prizes per round** the creator set.

So a round with 3 participants and a cap of 100 awards 3 prizes, not 100. The rest of the vault stays for later rounds.

### Picking each winner

For each prize, the contract:

1. **Rolls a tier** (epic, rare or common) against the odds the creator set for that round.
2. **Picks a wallet** at random, weighted by tickets. A wallet with 60 tickets out of 600 in the round has ten times the chance of one with 6.
3. **Picks an NFT** at random from that tier's remaining prizes and records the win.

Two limits apply while this runs:

* **Max wins per person.** A wallet can win at most this many prizes in one round, 5 unless the creator changed it. Setting it to 1 makes a round "one prize per wallet".
* **A wallet can never win more prizes than it holds tickets.** One ticket is one chance, so a single-ticket entrant can win once in that round.

If the rolled tier has run out of NFTs but the round still has prizes in another tier, the contract moves the prize to a tier that has stock rather than skipping it. Creators can also cap how many epic prizes a single round is allowed to award.

Packs are awarded before the individual prizes, each to a different wallet, and a pack counts toward that wallet's win limit for the round. See [Prizes & Packs](prizes-and-packs.md).

## Viewing the result

A drawn round shows **WINNERS & PRIZES** on the pool page: every winner, the prize they were assigned, and whether it has been claimed. Wallets that hold a Stargaze name are shown by name.

## Reversing a draw

The Stargaze team can cancel a draw in exceptional circumstances. Unclaimed prizes go back to the vault and the round returns to awaiting draw so it can be run again. Prizes that have already been claimed are in their winner's wallet and are not affected.

## Next steps

* [Prizes & Packs](prizes-and-packs.md): what is in the vault and how tiers work
* [Winning & Claiming](winning-and-claiming.md): claiming what you won
