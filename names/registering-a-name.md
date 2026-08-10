# Registering a Name

Everything happens on one page: [stargaze.zone/names](https://stargaze.zone/names).

## Before you start

You need:

* A **Keplr** wallet connected to Stargaze. See [Creating a Wallet](../start-here/creating-a-wallet.md) and [Connecting to Stargaze](../start-here/connecting-to-stargaze.md).
* **ATOM** on the Cosmos Hub for the registration price, plus a fraction of a cent for gas. See [Getting ATOM](../start-here/getting-atom.md).

## What a name costs

Names are priced by **length**, per year, in ATOM. Shorter names are rarer, so they cost more.

| Name length | Price per year |
| --- | --- |
| 3 characters | 100 ATOM |
| 4 characters | 10 ATOM |
| 5 or more characters | 1 ATOM |

The term you choose is anywhere from **1 to 10 years**, and pricing is linear — a 5-year registration of a 6-character name costs 5 ATOM. There is no bulk discount for registering longer, but there is no penalty either, and it means you can't forget to renew for a decade.

{% hint style="info" %}
The price you see in the search bar is the price for **one year**. The full total for your chosen term is shown in the registration panel before you sign anything.
{% endhint %}

## Step by step

### 1. Search for your name

Go to [stargaze.zone/names](https://stargaze.zone/names) and type the name you want into the search box. You don't need to connect a wallet to search.

As you type, Stargaze checks the name against the chain and shows one of:

* A green tick and a price → **available**, you can register it
* **Not available** → someone already owns it (see [Already taken?](#already-taken) below)
* A red validation message → the name breaks one of the format rules

### 2. Check the format rules

A name must be:

* **3 to 62 characters**
* Made only of **lowercase letters, digits, and hyphens**
* Not starting or ending with a hyphen, and without hyphens in the 3rd and 4th position together

Typing an uppercase letter, a space, or a dot will show an error rather than silently correcting it — there is no `.stars` suffix on the Cosmos Hub.

### 3. Connect your wallet

If you aren't connected, the button reads **Connect Wallet**. Connect, and it becomes **Register**.

### 4. Choose your term

Click **Register** to open the registration panel. Set **Years** with the stepper — anywhere from 1 to 10.

The summary updates live and shows:

* **Name** — what you're registering
* **Registration** — the number of years
* **Total** — the full price in ATOM

### 5. Decide whether to point the name at your wallet

Below the summary there's a checkbox: **Associate with your wallet address**.

Tick it if you want this name to become your identity right away — your address will resolve to it, and Stargaze will start showing `@yourname` instead of `cosmos1…` everywhere.

Leave it unticked if you're registering a name to hold, gift, or resell. You can associate it later at any time from [Managing Your Name](managing-your-name.md).

{% hint style="warning" %}
If your wallet already resolves to a different name, a note tells you so. Ticking the box repoints your address to the new name — one address can point at only one name at a time. The old name stays yours; it just stops being your display name.
{% endhint %}

### 6. Register and sign

Click **Register** and approve the transaction in Keplr. When it confirms you'll see a **Registration Successful** screen with your new name, and a share button if you want to post it.

The name is now an NFT in your wallet.

### 7. Set up your profile

Open your profile, go to the **Names** tab, and click **Edit** on your new name to add a profile picture, a banner, and your links. See [Managing Your Name](managing-your-name.md).

## Presale (whitelist) registration

Before public registration opened, Stargaze ran a three-stage **presale** for whitelisted wallets. If a stage is live, the Names page shows it as a **Presale** panel with a tab per stage, a live countdown, and an **Eligible** / **Not Eligible** badge once your wallet is connected.

During a presale stage:

* **5+ character names are free** for the first year
* **3–4 character names are half price** for the first year
* Each stage has its own **per-wallet allowance** — the panel shows how many you have left
* Registration is **limited to whitelisted wallets** while a stage is live; everyone else waits for public registration

{% hint style="info" %}
The discount only ever covers the **first year**. If you pick a longer term during a presale, the extra years are added at the normal price in the same transaction, and the panel breaks that out as "1st year — whitelist" and "Years 2–N — full price".
{% endhint %}

**Public registration opened on 11 August 2026, 19:00 UTC.** From then on, anyone can register any available name at the normal price.

## Recently expired names carry a premium

If a name lapsed recently, it enters a 21-day **premium window** before it becomes ordinary again. It's registerable, but the price is the normal price plus a surcharge that starts at **100 ATOM** and falls steadily to zero across those 21 days.

When that applies, the page tells you: *"This name recently expired and carries a temporary premium that decreases over time."* Wait, and it gets cheaper. See [Renewing a Name](renewals.md#the-lifecycle-of-a-name) for the full lifecycle.

## Already taken?

If the name you want is owned, you have four options:

1. **Buy it.** Check whether it's listed on [the Names collection](https://stargaze.zone/m/names) — see [Buying & Selling Names](buying-and-selling-names.md).
2. **Make an offer.** Even an unlisted name can receive an offer on its page; the owner can accept it.
3. **Try a variation.** Hyphens and digits are valid characters.
4. **Wait for it to lapse.** Names expire. A name that isn't renewed becomes registerable again after its grace and premium windows — roughly 111 days after its expiry date.

## Next steps

* [Managing Your Name](managing-your-name.md) — point it somewhere, set your picture and links
* [Renewing a Name](renewals.md) — don't lose it
* [Names FAQ](faq.md)
