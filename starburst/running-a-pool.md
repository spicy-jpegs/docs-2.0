# Running a Pool

A pool is your own raffle event: your prizes, your rounds, your rules, attached to your mint. This page covers setting one up and running it end to end.

## Getting access

Pool creation is allowlisted. Open [starburst.stargaze.zone/create-pool](https://starburst.stargaze.zone/create-pool) with your wallet connected:

* If your wallet is on the allowlist, the create form opens.
* If it is not, you get a short request form instead. Describe the event and leave a way to reach you, and the Stargaze team reviews it. You can also open a ticket in the [Stargaze Discord](https://discord.gg/stargaze).

## Creation fee

Creating a pool costs a one-time fee, payable in either token:

| Pay with | Amount |
| --- | --- |
| ATOM | 2.5 ATOM |
| STARS | 50,000 STARS |

The form lets you pick which one to attach. There is no per-entry fee charged to the people who enter your raffle.

## Creating the pool

<table><thead><tr><th width="290">Setting</th><th>What it does</th></tr></thead><tbody><tr><td><strong>Pool name</strong></td><td>The name shown on the landing page and the pool page.</td></tr><tr><td><strong>Extra admins</strong></td><td>Other wallets allowed to operate the pool. You cannot remove yourself.</td></tr><tr><td><strong>Raffle tickets per 1 ATOM spent on minting</strong></td><td>The default ticket rate. At 10, a 0.5 ATOM mint earns 5 tickets and a 2 ATOM mint earns 20.</td></tr><tr><td><strong>Max prizes / round</strong></td><td>The ceiling on prizes awarded in one round. The actual number is this or the participant count, whichever is lower.</td></tr><tr><td><strong>Max wins per person / round</strong></td><td>How many prizes one wallet can win in a round. Defaults to 5; set it to 1 for one prize per wallet.</td></tr><tr><td><strong>Epic odds / Rare odds</strong></td><td>The chance a given prize is drawn from each tier. Common takes the remainder.</td></tr><tr><td><strong>Pool card image</strong></td><td>Optional backdrop for the landing-page card. Left blank, an epic NFT from your vault is used.</td></tr></tbody></table>

You can edit all of these later from the pool admin page.

## Choosing how rounds end

<table><thead><tr><th width="200">Mode</th><th>Set up</th></tr></thead><tbody><tr><td><strong>On a schedule</strong></td><td>Give each round an open and close date. Rounds that have already drawn are locked; the rest stay editable.</td></tr><tr><td><strong>Every N mints</strong></td><td>Give a start time and a <strong>round plan</strong>: one mint quota per round, such as 500 · 1,000 · 500. There are no end dates; each round closes on its count and the pool finishes after the last one.</td></tr></tbody></table>

Two things to know about mint-count pools:

* They track **one** collection. The whitelist form closes after the first one; removing it frees the slot.
* The mint counter starts at zero when you connect the collection, so the first quota means "close after this many new mints", not "close when the collection reaches this supply".

You can retune quotas for rounds that have not drawn yet. Editing the **current** round's quota moves its draw target by the same amount; editing a future round's does not affect the one in progress.

## Connecting your mint collection

From the pool admin page, add the collection people will mint. StarBurst credits tickets by querying the minter for each wallet's mint count and awarding the difference since it last credited them, so it works with standard Stargaze collections, including whitelisted and merkle deploys.

### Do past mints earn tickets?

You choose this when adding the collection, and it cannot be changed afterwards for that collection.

<table><thead><tr><th width="250">Option</th><th>What happens</th></tr></thead><tbody><tr><td><strong>No, new mints only</strong></td><td>Only mints made after the pool goes live earn tickets. Requires a one-time setup step, below.</td></tr><tr><td><strong>Yes, holders claim themselves</strong></td><td>Everyone who has already minted can claim their tickets from the pool page.</td></tr><tr><td><strong>Yes, sent automatically</strong></td><td>You push the tickets out to existing minters in a batch. The admin page walks through it.</td></tr></tbody></table>

{% hint style="warning" %}
**New mints only: complete the setup before minting opens.** This option arms with a lock, and the step that unlocks it records everyone's current mint count as their starting point. Any mint made between adding the collection and finishing that step is folded into the starting point and cannot earn tickets afterwards. Do it before the mint is live. If minting is already open, finish it immediately and use **Admin add tickets** to compensate anyone who minted in the gap.
{% endhint %}

### Setting the ticket rate

The rate per ATOM you set at creation applies by default. Two overrides are available per collection:

* **A rate per whitelist stage.** If the collection uses tiered whitelist stages, you can set a different ticket count for each one, for example 50 in stage 1, 30 in stage 2, 20 at public. The stage is resolved on-chain at the moment of the mint.
* **A fixed rate per mint.** A single number that applies to every mint regardless of price or stage. This one wins over everything else.

{% hint style="info" %}
The rate shown on a collection row is calculated from the mint price when the collection was added. If you later change the pool's tickets-per-ATOM, refresh the collection or set a fixed rate. Otherwise the displayed number can drift from what is actually credited.
{% endhint %}

### Open editions

Open editions work as mint collections and as prizes. The one unsupported combination is **mint-count rounds together with counting past mints**, because an open edition has no fixed supply for the counter to work from. The form detects this and selects new-mints-only for you.

## Stocking the prize vault

Open the **Deposit** page, pick the NFTs, assign each one a tier, and send them. They transfer into the pool's vault in a single transaction.

* Prizes must come from a collection the raffle contract trusts, which in practice means collections created through Stargaze. Anything else is filtered out of the picker.
* **A listed NFT cannot be deposited.** Listed tokens are held in marketplace escrow, and including one fails the whole deposit. They are shown disabled with a **Listed** tag. Delist first, then deposit.
* Tiers can be changed later from the admin page, and NFTs can be withdrawn while they are still unwon.

Stock enough that a round can actually pay out what it advertises. The admin prize vault shows a fill bar per round against that round's prize count, so an under-stocked round is visible at a glance.

### Per-round prize pools

If you turned on **give each round its own prize pool**, deposited NFTs land on an unassigned shelf first. Assign them to rounds from the prize vault, and set each round's odds, prize count and win limit there. Rounds that have already drawn are locked.

## Building packs

A pack bundles NFTs and coins into one prize for one winner. Build packs from the pool admin page.

* **Specific**: hand-picked NFTs. In a per-round pool, a pack for round N can only contain NFTs already assigned to round N, so the working order is **deposit → assign to a round → build the pack**.
* **Random**: a size and its own tier odds. Contents are drawn from the vault when the round draws.
* **Cash only**: ATOM or STARS with no NFTs.

Coins are attached to the transaction that creates the pack and held in escrow until the pack is claimed. Removing an unawarded pack refunds them and returns its NFTs to the vault.

Remember that a pack goes to a single wallet however many NFTs it holds, and that it consumes one of that wallet's wins for the round.

## Publishing

New pools are hidden. Set everything up, then use **Submit for review** on the pool page. The Stargaze team is notified and publishes the pool to the landing page once they have looked at it. Direct links to the pool work throughout, which is useful for checking your own setup before it is public.

## Running the event

* **Draws are run by the Stargaze team**, not by pool admins. A round sitting in *awaiting draw* is normal; it resolves when the team runs it.
* **Closing a round early.** In a mint-count pool you can close the open round where it stands if minting stalls.
* **Pause.** Pausing halts ticket earning and claiming across the pool.
* **Admin add tickets.** Credits tickets to a specific wallet in a specific round. This is the tool for correcting a mistake.
* **Withdrawing prizes.** Unwon NFTs can be pulled back out of the vault. Anything already won belongs to its winner.

{% hint style="info" %}
In a mint-count pool, one large mint transaction can cross several boundaries at once, opening, filling and closing more than one round in a single block, with that wallet as the only participant in each. Take it into account when deciding how richly to stock the later rounds of a short plan.
{% endhint %}

## Next steps

* [Rounds & Draws](rounds-and-draws.md): the draw mechanics your settings feed into
* [Prizes & Packs](prizes-and-packs.md): tiers, odds and pack behaviour
* [StarBurst FAQ](faq.md)
