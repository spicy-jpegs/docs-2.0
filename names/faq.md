# Names FAQ

## The basics

<details>

<summary>Does my name end in <code>.stars</code>?</summary>

No. Stargaze Names on the Cosmos Hub are **bare** — the name is just the word, with no suffix at all. Stargaze displays it with an `@` in front (`@starty`) the way a social handle is shown, but the `@` isn't part of the name either. Typing a dot into the search box will fail validation, because dots aren't a valid character.

</details>

<details>

<summary>What characters can a name contain?</summary>

Lowercase letters `a–z`, digits `0–9`, and hyphens. Between 3 and 62 characters long. A hyphen can't be the first or last character, and hyphens can't sit in the 3rd and 4th position together.

Uppercase isn't converted, it's rejected — the valid form of `Starty` is `starty`.

</details>

<details>

<summary>What does a name cost?</summary>

Per year, in ATOM: **100** for a 3-character name, **10** for 4 characters, **1** for 5 or more. You choose a term of 1 to 10 years and pay for all of it up front. See [Registering a Name](registering-a-name.md).

</details>

<details>

<summary>Can I own more than one name?</summary>

Yes, as many as you like. Only one of them can be the name your address resolves to at any moment — that's the one shown as your identity across Stargaze. The rest sit in your wallet and can be traded, gifted, or pointed at collections.

</details>

<details>

<summary>Can I change my name after registering?</summary>

Not the name itself — a name is fixed once minted. What you change is which name your address points at. Register the new name, tick **Associate with your wallet address**, and your identity moves. The old name stays yours until you sell it or let it lapse.

</details>

## Renewals and expiry

<details>

<summary>How do I know when my name expires?</summary>

**Profile → Names**, the **Expires** column. Sort by *Expiring Soonest* to bring the urgent ones to the top. There are no email or push reminders, so set a calendar reminder yourself.

</details>

<details>

<summary>Do I lose time if I renew early?</summary>

No. The years you buy are added to your **existing expiry date**, not to today. Renewing early is free of any penalty and is the safest habit. See [Renewing a Name](renewals.md#renewing-before-time).

</details>

<details>

<summary>Is renewing more expensive than registering?</summary>

No — it's the same length-based price. There's no late fee either. The one difference is that presale and whitelist discounts never apply to renewals; those covered the first year of a registration only.

</details>

<details>

<summary>What happens the day my name expires?</summary>

It stops resolving — your profile falls back to your raw address and the name no longer points anywhere. But it stays yours for **90 more days** (the grace period), during which you can renew it at the normal price and nobody else can register it.

</details>

<details>

<summary>I let my name lapse. Can I get it back?</summary>

Within 90 days of expiry, yes — just renew it. After that the name is released and anyone can register it. For the following 21 days it carries a **premium** surcharge that starts at 100 ATOM and decays to zero, then it becomes an ordinary available name. You can re-register it yourself, but so can anyone else.

</details>

<details>

<summary>Can someone else renew my name and steal it?</summary>

No. Renewal is permissionless — **anyone** can renew **any** name — but renewing never changes who owns it. Paying to renew a name you don't own is simply a gift to its owner.

</details>

<details>

<summary>Why does renewing during grace give me less than a full year?</summary>

Because the renewal extends from your **original expiry date**, not from today. Days spent lapsed come out of the new term. Lapse for 60 days and renew for a year, and roughly 305 days remain.

</details>

<details>

<summary>The Years stepper is missing from the renewal panel.</summary>

That means the name is already at its 10-year maximum lease and can't be extended further right now. Nothing is wrong — come back later, as the cap moves forward with time.

</details>

## Using your name

<details>

<summary>How do I get my name to show up instead of my address?</summary>

Point it at your wallet. Either tick **Associate with your wallet address** while registering, or afterwards open **Profile → Names → Edit** and choose **Wallet Address**. See [Managing Your Name](managing-your-name.md).

</details>

<details>

<summary>Can I set a profile picture and banner?</summary>

Yes — both come from NFTs you own, chosen in the name's **Edit** panel. You must own the NFT when you save. See [Managing Your Name](managing-your-name.md).

</details>

<details>

<summary>Can I point a name at my collection instead of my wallet?</summary>

Yes. In the **Edit** panel choose **Collection Address** and pick one of the collections your wallet created. The collection then gets a readable URL and shows the name on Stargaze.

</details>

<details>

<summary>Why is the Edit button greyed out?</summary>

The name is listed for sale or in a live auction, so the marketplace is holding it and the chain won't accept edits from your wallet. Cancel the listing or auction to edit again. **Renew** stays available the whole time.

</details>

## Buying and selling

<details>

<summary>Do my links and picture transfer with the name when I sell it?</summary>

No, and that's deliberate. Any move of the name — sale, transfer, or being placed into marketplace escrow — clears the address it points at, all five text records, the profile picture and the banner. The buyer receives a clean name.

The catch: **listing a name is a move**. Listing and then cancelling gets the name back but not your settings. See [Managing Your Name](managing-your-name.md#two-things-that-wipe-your-settings).

</details>

<details>

<summary>Does buying a name reset its expiry date?</summary>

No. You inherit whatever time is left on the lease. Check the expiry immediately after buying and renew if it's close.

</details>

<details>

<summary>Can I buy an expired name safely?</summary>

Be careful. An expired name is still a tradeable NFT, but anyone can register it out from under the buyer, with no refund. Buying a name in its **grace** period is workable if you renew immediately. Buying one that's past grace is not — register it directly instead. See [Buying & Selling Names](buying-and-selling-names.md#check-the-expiry-before-you-buy).

</details>

<details>

<summary>What are the fees on a name sale?</summary>

2% marketplace fee plus a 5% royalty, both paid by the seller, plus gas. A 100 ATOM sale nets the seller 93 ATOM.

</details>

## Migrating from the Stargaze chain

<details>

<summary>I had a name on the old Stargaze chain. Do I need to register it again?</summary>

No. Names from the Stargaze chain were migrated to the Cosmos Hub for you. They arrived with a **one-year lease** from the August 2026 migration, so check **Profile → Names** for the expiry date and renew before then.

</details>

<details>

<summary>Do my old text records still work?</summary>

Records were carried over where possible. Open **Edit** once to confirm your links and profile picture are what you want.

</details>

## Still stuck?

See [Community & Support](../help/community-and-support.md).
