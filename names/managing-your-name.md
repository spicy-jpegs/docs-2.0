# Managing Your Name

Once you own a name you can decide what it points at, what picture and banner it shows, and which links it carries. All of it lives in one place.

## Opening the editor

1. Connect your wallet.
2. Go to **Profile → Names** (or the **Names** menu → **My Names**).
3. Click **Edit** on the name you want to change.

Everything below is edited in that one panel, and saved with a **single transaction** — change five things at once and you sign once.

{% hint style="info" %}
Viewing someone else's profile shows a **View** button instead, which opens the same panel read-only. It's a quick way to see who a name points at and what links it carries.
{% endhint %}

## Associated address — what the name points at

The **Associated Address** is the address people reach when they resolve your name. Pick one of three modes:

<table><thead><tr><th width="220">Mode</th><th>What it does</th></tr></thead><tbody><tr><td><strong>Wallet Address</strong></td><td>Points the name at your own connected wallet. This is what makes <code>@yourname</code> appear instead of your address across Stargaze.</td></tr><tr><td><strong>Collection Address</strong></td><td>Points the name at a collection contract you created. The collection then gets a readable URL and shows the name on the site.</td></tr><tr><td><strong>No Association</strong></td><td>The name resolves to nothing. Use this for names you hold to trade or gift.</td></tr></tbody></table>

For **Collection Address**, a dropdown lists the collections your wallet created — pick one and the address fills itself in. You can also paste a contract address directly; it must be a valid Cosmos Hub **contract** address, and you must be its admin.

{% hint style="warning" %}
**One address, one name.** An address can resolve to only one name at a time. Pointing a second name at the same wallet moves the association — the first name stays yours, it just stops being your display name.
{% endhint %}

## Profile picture and banner

Two pickers let you choose NFTs you already own:

* **Profile Image NFT** — becomes your avatar on Stargaze
* **Banner NFT** — becomes the banner across the top of your profile

Click the picker, choose a collection, then choose a token. You must **own the NFT** at the moment you save; the chain checks it.

If you later sell that NFT, the pointer stays where it is — it just points at something you no longer own. Update it when that happens.

## Links and records

Five records can be attached to a name:

| Record | Format |
| --- | --- |
| **X (Twitter)** | handle only, 2–15 characters (letters, numbers, underscores) |
| **Discord** | username, 2–32 lowercase characters (letters, numbers, dots, underscores) |
| **Telegram** | username, 5–32 characters (letters, numbers, underscores) |
| **Website** | a full URL, e.g. `https://example.com` |
| **EVM Address** | `0x` followed by 40 hex characters |

Type the value, leave the rest blank, and hit **Save Changes**. Clearing a field removes that record.

### Verified records

An X handle can carry a **Verified** badge. If you edit a record that is currently verified, a note appears under the field:

> Saving a change to this record removes its verification.

That's expected — verification is tied to the exact value that was checked, so changing the value invalidates it.

## Saving

**Save Changes** builds one transaction containing only what you actually changed, and Keplr shows it for approval. Fields you didn't touch are left alone.

The button stays disabled until there's a real change to save, so if nothing happens when you click it, nothing has changed yet.

## Two things that wipe your settings

This is the part worth reading twice.

{% hint style="danger" %}
**Moving a name erases everything attached to it.** Whenever a name changes hands — a transfer, a sale, or simply being placed into marketplace escrow — its associated address, its reverse link, all five text records, its profile picture and its banner are cleared.
{% endhint %}

That means:

1. **Transferring or selling a name** hands the buyer a completely clean name. Nothing of yours travels with it. That's by design — you don't want your Discord handle following a name you sold.
2. **Listing a name for sale escrows it**, which counts as a move. Listing and then cancelling the listing gets the name back, but **your records will be gone** and you'll have to set them up again.

So: don't list the name you use as your identity on a whim. If you're testing the waters on price, be ready to redo your profile.

Renewing a name does **not** touch any of this — renewals never move the NFT.

## When editing is blocked

The **Edit** button is greyed out in two cases, with a tooltip explaining why:

* *Listed names cannot be edited until they are delisted*
* *Auctioned names cannot be edited while the auction is live*

While a name sits in marketplace or auction escrow, your wallet isn't holding it, so the chain won't accept edits from you. Cancel the listing or auction to get it back.

**Renew** remains available the whole time.

## Next steps

* [Renewing a Name](renewals.md) — keep it alive
* [Buying & Selling Names](buying-and-selling-names.md) — what a listing actually does
* [Names FAQ](faq.md)
