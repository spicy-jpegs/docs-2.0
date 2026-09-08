# StarBurst FAQ

## Entering

**Does every Stargaze mint earn raffle tickets?**\
No. Tickets are only earned by minting a collection whose creator has attached it to a StarBurst pool, and only while one of that pool's rounds is open. Minting any other collection earns nothing. The pools on [starburst.stargaze.zone](https://starburst.stargaze.zone) are where to find the collections that have one.

**Does entering cost anything beyond the mint?**\
No. You pay the collection's mint price and the Cosmos Hub transaction fee. There is currently no entry fee.

**Do I have to do anything after minting?**\
No. The mint transaction carries the ticket claim with it, whether you mint on the pool page or on stargaze.zone.

**I minted but my tickets are not showing.**\
Use **Already minted? Claim entries** on the pool page. It credits every mint the pool has not yet counted. If the count still looks short, check whether the pool counts only mints made after it opened; earlier mints are excluded in that case by design.

**Do more mints really improve my odds?**\
Yes. Tickets are the weight in the draw, so ten times the tickets is ten times the chance. It does not guarantee a win.

**Are tickets used up when I win?**\
No. They stay counted for the rest of that round's draw, subject to the round's limit on wins per person.

**Do tickets carry over to the next round?**\
No. Each round is counted separately and everyone starts the next one from zero.

**Can I enter a raffle for a collection I did not mint?**\
No. Tickets come from minting the collection the pool is attached to.

**Can a creator enter their own raffle?**\
No. The contract blocks pool admins from earning tickets in their own pool.

## Rounds and draws

**The round ended but there are no winners yet.**\
It is waiting for its draw. Draws are run by the Stargaze team rather than by the creator, so a wait between a round closing and its winners appearing is expected.

**Why did a round award fewer prizes than the pool advertises?**\
A round awards at most one prize per participating wallet. With 3 wallets entered, a round awards 3 prizes even if its cap is much higher. The remaining prizes stay in the vault for later rounds.

**How is the winner chosen?**\
The contract picks each prize's tier against the pool's odds, then picks a wallet at random weighted by tickets, then picks an NFT from that tier. It runs in a single transaction and the result is recorded on-chain.

**What happens if a tier runs out of NFTs?**\
The prize is drawn from a tier that still has stock rather than being skipped.

**Can one wallet win everything?**\
No. Each round has a limit on how many prizes one wallet can win. It is 5 by default, and creators often set 1. A wallet also cannot win more prizes in a round than it holds tickets.

**Can a draw be undone?**\
The Stargaze team can cancel and re-run a draw in exceptional circumstances. Prizes already claimed stay with their winners; unclaimed ones go back to the vault.

## Prizes and claiming

**How do I know if I won?**\
The landing page shows a pop-up with your unclaimed prizes across every pool, and the pool page has a **Your wins** section. There are no email or push notifications.

**Is there a deadline to claim?**\
No. An unclaimed prize stays assigned to your wallet.

**I won a pack. Why is there a separate claim button?**\
Packs are claimed on their own, one claim per pack, separately from a round's individual prizes.

**A pack says it has 44 NFTs. Do 44 people win?**\
No. A pack is one prize for one wallet, however many NFTs it holds.

**What does the epic label on a pack mean?**\
It is a display badge chosen by the creator. The NFTs inside keep their own tiers.

**Can I win ATOM or STARS?**\
Yes, if the creator built a pack that carries coins. They are paid out when the pack is claimed.

**Where do my prizes go?**\
Straight to the wallet that won them. They show up on your Stargaze profile at `stargaze.zone/p/<your address>`.

## Creators

**How do I get a pool?**\
Apply at [starburst.stargaze.zone/create-pool](https://starburst.stargaze.zone/create-pool), or open a ticket in the [Stargaze Discord](https://discord.gg/stargaze).

**What does it cost?**\
2.5 ATOM or 50,000 STARS, once, when the pool is created.

**Why is my pool not on the landing page?**\
New pools are hidden until published. Submit it for review from the pool page and the Stargaze team publishes it. Direct links work the whole time.

**My deposit failed and the error mentions message index 0.**\
One of the selected NFTs cannot be transferred. A listed token is the usual cause, because listing puts it in marketplace escrow. Delist it, or deselect it, and deposit again.

**Can I change the ticket rate after launch?**\
Yes. You can update the rate per ATOM, set per-whitelist-stage rates, or pin a fixed rate per mint at any time. Changes apply to mints credited after that point.

**Can I take prizes back out?**\
Unwon NFTs can be withdrawn from the vault. Anything already won belongs to its winner.

**Do I run my own draws?**\
No. Draws are run by the Stargaze team. You can close a round early in a mint-count pool, and pause the pool, from the admin page.

## Further help

* [Community & Support](../help/community-and-support.md)
* [Troubleshooting](../help/troubleshooting.md)
