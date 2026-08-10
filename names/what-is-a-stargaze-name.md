# What is a Stargaze Name?

A **Stargaze Name** is a short, human-readable identity for your Cosmos Hub wallet.

Instead of this:

```
cosmos1h7vk2ycx8m4gq3n0dzp9awufe5s6tlr4jb2xdq7mve3n8ku0y9rs2pfw6c
```

people see this:

```
@stargazer
```

Same wallet. One is impossible to remember and easy to get wrong; the other is you.

## What you actually get

Registering a name gives you four things at once:

* **An identity.** Your name replaces your address everywhere on Stargaze — the navbar, your profile, activity feeds, notifications, search results, owner and buyer rows.
* **A profile.** Your name carries a profile picture, a banner, and links (X, Discord, Telegram, website, EVM address). Set them once and they follow you across the site.
* **An address it points to.** By default your own wallet — but a name can also point at a collection contract, which is how projects get a clean collection URL.
* **An NFT.** The name *is* a CW721 NFT in your wallet. You can hold it, transfer it, list it, or auction it like any other collectible.

## The format

Stargaze Names on the Cosmos Hub are **bare** — there is no `.stars`, `.cosmos`, or any other suffix. The name is just the word. Stargaze displays it with an `@` in front, the way a social handle is shown, but the `@` is not part of the name.

| Rule | Detail |
| --- | --- |
| Length | 3 to 62 characters |
| Allowed characters | lowercase letters `a–z`, digits `0–9`, and hyphens `-` |
| Not allowed | uppercase, spaces, dots, emoji, or any other symbol |
| Hyphens | cannot be the first or last character, and cannot sit in the 3rd and 4th position together |

Names are not case-sensitive because uppercase simply isn't valid — `Stargazer` is rejected, `stargazer` is the name.

## Names are leased, not bought forever

This is the one thing worth understanding before you register.

A name is registered for a **term of 1 to 10 years**, paid up front in ATOM. Before that term ends you renew it. If you never renew, the name eventually goes back to the public and someone else can take it.

That is deliberate. It keeps the namespace alive instead of letting it be permanently squatted by wallets that were abandoned years ago.

Selling or transferring a name does **not** reset the clock. The buyer inherits whatever time is left on the lease and has to renew it themselves.

See [Renewing a Name](renewals.md) for exactly how renewals, the grace period, and expiry work.

## Where names show up on Stargaze

<table><thead><tr><th width="230">Where</th><th>What you see</th></tr></thead><tbody><tr><td><strong>Names</strong> in the top navbar</td><td>Register, Trade, and My Names</td></tr><tr><td><a href="https://stargaze.zone/names">stargaze.zone/names</a></td><td>Search for a name and register it</td></tr><tr><td><a href="https://stargaze.zone/m/names">stargaze.zone/m/names</a></td><td>The Names collection on the marketplace — browse, buy, and sell names</td></tr><tr><td><code>/m/names/&lt;name&gt;</code></td><td>An individual name's page, like any other NFT</td></tr><tr><td>Profile → <strong>Names</strong> tab</td><td>Every name a wallet owns, its expiry date, and Edit / Renew buttons if it's yours</td></tr><tr><td>Your profile header</td><td>Your name as your display name, plus the profile picture and banner you set on it</td></tr><tr><td>Everywhere an address appears</td><td>Activity, notifications, search, offers, owner rows — the address is replaced by the name it resolves to</td></tr><tr><td>Collection URLs</td><td>A collection whose creator pointed a name at it gets a readable URL instead of a contract address</td></tr></tbody></table>

## Coming from the Stargaze chain?

Names that existed on the original Stargaze chain were migrated to the Cosmos Hub for you — you don't need to re-register them. They arrived with a **one-year lease** starting from the August 2026 migration, so they will need renewing like any other name.

Check yours: open your profile, go to the **Names** tab, and look at the **Expires** column.

{% hint style="info" %}
Migrated names kept their text records where possible, but it's worth opening **Edit** once to confirm your links and profile picture are the ones you want.
{% endhint %}

## Next steps

* [Registering a Name](registering-a-name.md) — check availability, pricing, and claim one
* [Renewing a Name](renewals.md) — keep it, step by step
* [Managing Your Name](managing-your-name.md) — profile picture, banner, links, and where it points
* [Buying & Selling Names](buying-and-selling-names.md) — trade names on the marketplace
