# Renewing a Name

A Stargaze Name is leased, not owned forever. Renewing is how you keep it. It takes about thirty seconds and one transaction.

## The short version

* Your name has an **expiry date**. Find it in your profile's **Names** tab.
* Renew any time before that date — **renewing early costs you nothing extra**, because the new term is added on top of your existing one.
* If you miss it, you get **90 days of grace** to renew. Your name stops working during those 90 days, but nobody else can take it.
* After the grace period, the name is released. Someone else can register it, and it's gone.

## Where to find your expiry date

1. Connect your wallet.
2. Open **Profile → Names** (or the **Names** menu in the navbar → **My Names**).
3. The **Expires** column shows the date for every name you own. Sort by **Expiring Soonest** to put the urgent ones on top.

A red badge appears when something needs attention:

| Badge | Meaning |
| --- | --- |
| *(none)* | Registered and working normally |
| **Grace** | Expired. Still yours, but it has stopped resolving. Renew now. |
| **Expired** | Past the grace period. It can no longer be renewed and may already be gone. |

{% hint style="warning" %}
Stargaze does not email or message you before a name expires. Nothing will chase you. Check the **Names** tab now and then, or put a reminder in your calendar a month before the date.
{% endhint %}

## How to renew, step by step

### 1. Open your Names tab

Connect your wallet, then go to **Profile → Names**.

### 2. Click Renew

Each name you own has **Edit** and **Renew** buttons on the right of its row. Click **Renew**.

{% hint style="info" %}
If a name is currently **listed** or in a **live auction**, the Edit button is disabled — but Renew still works. You never have to delist a name to keep it alive.
{% endhint %}

### 3. Choose how many years to add

Use the **Years** stepper. You can add anywhere from 1 year up to the point where the total lease would exceed the 10-year cap.

For example, a name that expires in 3 years can be extended by up to 7 more.

### 4. Check the summary

The panel shows exactly what will happen:

* **Name** — the name being renewed
* **Renewal** — how many years you're adding
* **Current expiry** — today's expiry date
* **New expiry** — the date after this renewal
* **Total** — the price in ATOM

Read the **New expiry** line. That is the whole point of the transaction.

### 5. Renew and sign

Click **Renew** and approve in Keplr. You'll get a **Renewal Successful** confirmation showing the new expiry date.

## Renewing before time

**Renewing early is always safe, and it is the right habit.**

When you renew, the new years are added to your **existing expiry date**, not to today. Renew a name eleven months early and you keep those eleven months — they are added to, not replaced by, the term you just bought.

So there is no reason to wait, and no reward for cutting it fine:

* You can renew the day after you register.
* You can renew on any day of the lease.
* You can renew several times; each renewal stacks on the last.
* The only limit is the **10-year cap** — the lease can never extend more than 10 years past today.

### If the Years stepper is missing

If a name is already at the 10-year cap, the panel hides the stepper and says:

> This name is already at its maximum lease term and cannot be renewed right now.

That's not a problem. It means the name is safe for a decade. Come back later and you'll be able to top it up again as the cap moves forward with time.

## What renewal costs

Renewal is charged at the **standard length-based price**, the same as registration:

| Name length | Price per year |
| --- | --- |
| 3 characters | 100 ATOM |
| 4 characters | 10 ATOM |
| 5 or more characters | 1 ATOM |

Two things to know:

* **Presale and whitelist discounts never apply to renewals.** Those covered the first year of a registration only.
* **There is no late fee.** Renewing during the grace period costs exactly the same as renewing early.

## The lifecycle of a name

Every name moves through the same four states. They are worked out purely from the expiry date and the clock — there's no queue and no manual review.

| State | When | Does it resolve? | Who can act |
| --- | --- | --- | --- |
| **Registered** | Up to the expiry date | ✅ Yes | Anyone can renew it |
| **Grace** | 90 days after expiry | ❌ No | Anyone can renew it. Nobody can register it. |
| **Premium** | The next 21 days | ❌ No | Anyone can register it, at the normal price plus a surcharge that decays from 100 ATOM to zero |
| **Available** | After that | ❌ No | Anyone can register it, at the normal price |

```
 registered            expiry           +90 days          +21 days
      │  Registered       │    Grace        │   Premium      │   Available
      ▼───────────────────▼─────────────────▼────────────────▼──────────────▶
        works normally      stops working     someone else     someone else
        renew any time      renew any time    can take it      can take it
```

### Renewing during the grace period

You keep the right to renew for **90 full days** after expiry, and it costs the normal price. But two things are true during grace:

1. **Your name stops working.** It no longer resolves to your address. Your profile falls back to showing `cosmos1…`, and anyone sending to your name will find nothing there.
2. **You lose the lapsed time.** The renewal still extends from your **original expiry date**, so any days spent in grace come out of the new term. Lapse for 60 days and renew for a year, and you get roughly 305 usable days.

The renewal panel says this directly when it applies:

> This name is in its grace period and has stopped resolving. Renewing extends from the original expiry date, not from today.

### After the grace period

Once the 90 days are up, renewal is no longer possible. The panel will tell you:

> This name is past its grace period and can no longer be renewed. It must be registered again.

At that point the name enters the 21-day **premium** window and then becomes fully available. You can still get it back by **registering** it again — but so can anybody else, and during the premium window the price carries a surcharge that starts at 100 ATOM and falls to zero over the 21 days.

## Renewing someone else's name

Renewal is permissionless: **anyone can renew any name**, and the name stays with its current owner. You cannot take a name by renewing it.

That's useful in practice:

* A project can renew the names of its team or community members.
* A DAO can renew a name held in a multisig from any member's wallet.
* You can renew a friend's name as a gift.

To do it, open the owner's profile, go to their **Names** tab, and use the name's page — or renew it directly from your own wallet against that name.

## If you bought a name from someone else

Buying a name **does not reset its lease**. You inherit whatever term was left when you bought it, which could be years or could be days.

Check the expiry the moment the name lands in your wallet, and renew if it's close. See [Buying & Selling Names](buying-and-selling-names.md#check-the-expiry-before-you-buy).

## Next steps

* [Managing Your Name](managing-your-name.md) — profile picture, banner, links
* [Buying & Selling Names](buying-and-selling-names.md) — trading, and what to check first
* [Names FAQ](faq.md)
