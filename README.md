# pay as you go residential proxies: how per-GB billing works, what a fair rate looks like, and how to test one for $5

People searching this phrase usually want one of three things. Residential IPs for a project that runs three weeks instead of twelve months. A way out of a monthly plan they used at 40% capacity. Or confirmation that the $1/GB figure on a provider's homepage survives contact with the checkout page.

All three questions reduce to the same two variables: what you pay per gigabyte and what happens to the gigabytes you never use. Most comparison pages cover the first one and stay quiet about the second, which is where the real money sits.

## The billing model matters more than the headline rate

Pay-as-you-go in residential proxies means you load credit into an account and spend it against traffic. No renewal date, no card on file, no minimum monthly commitment. Subscription plans bundle a fixed allowance per month, usually at a discount per GB, and the allowance resets whether you used it or not.

That difference is only cheap in one direction. If you burn a steady terabyte every month, a subscription tier usually wins on rate. If your usage is lumpy — a big scrape in March, nothing in April — the subscription discount is arithmetic you never collect.

Here is the part that trips people up. "Pay as you go" describes the billing mechanic, not the expiry policy. A provider can bill you by the gigabyte and still put a clock on the balance. Databay, for example, publishes a 186-day validity window on its pay-as-you-go residential data and 31 days on its volume packages, after which unused gigabytes expire. IPRoyal runs the opposite trade: its pay-as-you-go residential traffic costs about 5% more per GB than the subscription equivalent, but the balance does not expire.

So the question to ask any provider is not "do you have pay-as-you-go?" but "does the balance survive a quarter I don't use?"

## What residential traffic costs per gigabyte

Entry rates across the market, taken from provider pricing pages through 2026. Treat them as a range rather than a quote — every one of these has moved at least once this year.

| Provider | Published residential entry | Model |
| --- | --- | --- |
| DataImpulse | $1/GB | Pay-as-you-go, no expiry, $5 minimum |
| Decodo | ~$3.75/GB entry, ~$4/GB pay-as-you-go | PAYG plus monthly tiers, ~$2/GB at volume |
| SOAX | $3.60/GB (no monthly fee on the Sandbox tier) | Credit-based |
| IPRoyal | ~$7.35/GB pay-as-you-go | PAYG, non-expiring balance |
| Oxylabs | ~$8/GB standard, ~$4/GB during promos | PAYG plus commitment tiers |
| Bright Data | ~$8/GB list, ~$4/GB promotional | PAYG plus committed plans |
| Webshare | Bundled bandwidth, per-GB rate above the budget tier | Subscription-first |

The spread between $1 and $8 for what sounds like the same product is not marketing noise. It reflects pool size, how the IPs were sourced, targeting depth, and whether managed anti-bot tooling is bundled. Oxylabs and Bright Data charge for infrastructure most small scraping operations never touch — enterprise SLAs, compliance documentation, managed unlockers, 175M+ and 400M+ IP pools respectively.

If you are running your own scraper and just need clean exit IPs, that stack is overhead. If procurement needs SOC 2 paperwork and you're crawling LinkedIn at scale, it isn't.

## Cost per gigabyte is not cost per useful request

A $1/GB pool that returns data 99% of the time is cheaper than a $0.50/GB pool that works 60% of the time, and the gap is bigger than it looks because failures still burn bandwidth. Retries, CAPTCHAs, and blocked responses all meter.

The rough arithmetic: divide your nominal rate by the success rate to get an effective cost per usable request. A $1/GB pool at 0.99 lands near $1.01. A $0.50/GB pool at 0.60 lands above $0.83 before you count the engineering time you spent debugging why Amazon stopped responding. Add an expiry window on top and the cheap option can end up 20–40% more expensive than the rate you thought you bought.

This is why success rate matters as much as price, and why the useful thing to check before scaling is how a pool performs against *your* targets, not against a benchmark page.

## Where DataImpulse's pay-as-you-go model actually lands

DataImpulse is the provider currently sitting at the low end of that table, and the model is worth examining because it is unusually pure about the pay-as-you-go idea.

The pitch is $1/GB on residential traffic with no subscription, no monthly minimum, and a $5 minimum deposit. Purchased gigabytes do not expire on any tier, which means the balance from a February test is still there in November. The pool is advertised as 90M+ ethically sourced IPs across 195 countries, sourced first-party through DataImpulse's own opt-in participant app rather than resold from third-party aggregators. DataImpulse publishes a 99.51% success rate and a 4.8/5 G2 rating on its own product pages.

The minimum spend is $5 across all four proxy types, which buys 5GB of residential, 10GB of datacenter, or 2.5GB of mobile. That is enough traffic to run a few thousand real requests against your actual targets and see what the success rate looks like.

👉 [Start a DataImpulse balance from $5 and test the pool against your own targets](https://bit.ly/dataimPulse)

## All DataImpulse plans, side by side

DataImpulse sells traffic rather than named subscription tiers, and the same ladder structure repeats across four proxy products. Everything below is usage-based, non-expiring, and available without a subscription.

| Product and tier | Traffic | Price | Effective rate | Billing | Get it |
| --- | --- | --- | --- | --- | --- |
| Residential — Intro | 5 GB | $5 | $1.00/GB | One-time, no expiry | [Residential intro](https://bit.ly/dataimPulse) |
| Residential — Basic | 50 GB | $50 | $1.00/GB | One-time, no expiry | [Residential basic](https://bit.ly/dataimPulse) |
| Residential — Advanced | 1 TB | $800 | $0.80/GB (20% volume discount) | One-time, no expiry | [Residential advanced](https://bit.ly/dataimPulse) |
| Residential — Custom | 5 TB+ | From $4,000 | Negotiated | Quote | [Request residential pricing](https://bit.ly/dataimPulse) |
| Datacenter — Intro | 10 GB | $5 | $0.50/GB | One-time, no expiry | [Datacenter intro](https://bit.ly/dataimPulse) |
| Datacenter — Basic | 100 GB | $50 | $0.50/GB | One-time, no expiry | [Datacenter basic](https://bit.ly/dataimPulse) |
| Datacenter — Advanced | 1 TB | $450 | $0.45/GB | One-time, no expiry | [Datacenter advanced](https://bit.ly/dataimPulse) |
| Datacenter — Custom | 5 TB+ | From $2,250 | Negotiated | Quote | [Request datacenter pricing](https://bit.ly/dataimPulse) |
| Mobile — Intro | 2.5 GB | $5 | $2.00/GB | One-time, no expiry | [Mobile intro](https://bit.ly/dataimPulse) |
| Mobile — Basic | 25 GB | $50 | $2.00/GB | One-time, no expiry | [Mobile basic](https://bit.ly/dataimPulse) |
| Mobile — Advanced | 1 TB | $1,600 | $1.60/GB | One-time, no expiry | [Mobile advanced](https://bit.ly/dataimPulse) |
| Mobile — Custom | 5 TB+ | From $8,000 | Negotiated | Quote | [Request mobile pricing](https://bit.ly/dataimPulse) |
| Premium Residential — Intro | 1 GB | $5 | $5.00/GB | One-time, no expiry | [Premium residential intro](https://bit.ly/dataimPulse) |
| Premium Residential — Basic | 10 GB | $50 | $5.00/GB | One-time, no expiry | [Premium residential basic](https://bit.ly/dataimPulse) |
| Premium Residential — Custom | Larger volumes | Custom quote | Negotiated | Quote | [Request premium pricing](https://bit.ly/dataimPulse) |

Premium Residential is the odd one out. It runs at $5/GB, five times the standard residential rate, and buys a high-speed pool, a personal account manager, and all targeting options without the surcharge described below. That is a product for teams failing on hard targets, not a default upgrade.

## Which one you should actually buy

For most people reading a page about pay-as-you-go residential proxies, the answer is the $5 residential intro. It is the cheapest way to find out whether a pool works on your targets, and because the traffic does not expire, a failed experiment costs $5 of unused balance rather than a wasted month.

Datacenter traffic is half the price and genuinely worth testing if your targets do not actively block server IP ranges. The trade is detection: datacenter subnets are shared and cheap to block, so anything protected will flag you fast. Route the open pages to datacenter and the defended ones to residential, and you cut the bill without cutting success.

Mobile at $2/GB is the opposite case. It is the most expensive tier and the one to save for targets that residential genuinely cannot get through. Paying cellular rates for a job the $1 pool handles is the most common way a cheap proxy stack quietly becomes an expensive one.

## Rotating, sticky, and the settings that change your bill

Practical details you'll want before wiring anything up:

- **Rotating sessions** change the exit IP on every request. HTTP/HTTPS runs on port 823, SOCKS5 on port 824.
- **Sticky sessions** hold one IP to a specific port. Intervals are configurable from 1 to 120 minutes, with roughly 30 minutes being the realistic average. Sticky connections use ports between 10000 and 20000.
- **Protocols:** HTTP, HTTPS, and SOCKS5 are all supported on the same endpoint, with no protocol upcharge.
- **Authentication:** username/password or IP whitelisting.
- **Targeting:** country selection is included at no extra cost. State, city, ZIP, and specific ASN targeting is reported as billed at 2× the standard rate on standard residential plans, while DataImpulse's product page lists state/city/ZIP/ASN under datacenter features.

That last point deserves a note. Sticky sessions are not guaranteed to last the interval you set, because residential IPs come from real devices that go offline. When the underlying device disconnects, the session rotates to the next available IP automatically. A support agent confirmed this directly to HostAdvice's reviewer in a 2026 test, explaining the 120-minute ceiling as a configuration maximum rather than a promise. If your workflow assumes a fixed IP for two hours, build for early rotation.

> Advanced targeting charges are worth confirming with support before you budget. Third-party write-ups note that state/city/ZIP/ASN traffic is billed at double the base residential rate, while the product page presents some of that targeting as included. That difference matters at scale, and it takes one chat message to resolve.

## Where the $1/GB story has limits

Cheap and good are not opposites here, but they are not the same thing either.

The 90M+ pool is mid-tier by IP count. Bright Data advertises 400M+ and Oxylabs 175M+. For retail, e-commerce, SERP, and most marketing data work, volume is not the constraint. On the hardest social platforms and aggressively defended targets, a deeper pool with a managed unblocking layer on top tends to win. One independent review directory notes the pool is visibly thinner in tier-3 geographies such as sub-Saharan Africa and Central Asia, and flags the absence of published SOC 2 or ISO 27001 certification as a blocker for procurement-gated enterprise buyers.

There is no free tier. Every path starts at a $5 purchase. Intro plans carry a 7-day money-back guarantee on card payments, conditional on having consumed less than 80% of the traffic. Cryptocurrency purchases on Intro plans are not refundable even inside that window, which is worth knowing because DataImpulse accepts crypto through Cryptomus alongside cards via Stripe, PayPal, wire transfer, Alipay, Apple Pay, and Google Pay — availability varies by region.

HostAdvice's reviewer tested the live chat and had a named human agent answer a technical question about session behavior within seven minutes, with a complete answer about twelve minutes in. Support being human-staffed rather than bot-first is a real operational difference at this price point, and it is one of the few things you can verify in ten minutes for free before spending anything.

## A $5 test that tells you something

The point of pay-as-you-go is that you can evaluate a pool without a procurement conversation. Use it that way.

1. Buy the smallest residential balance and set up credentials with IP whitelisting or username/password.
2. Point a few hundred requests at your real targets, not a benchmark URL someone else measured.
3. Log success rate, average response time, and bytes consumed per successful page. That last number is the one that predicts your actual bill.
4. Repeat with datacenter traffic on the same targets to see how far down the price ladder you can go.
5. Compare effective cost per successful request, not headline rate. A $1/GB pool at 99% is not the same product as a $0.50/GB pool at 60%.

Then decide whether you need a commitment tier at all. For uneven workloads, the honest answer is usually no.

👉 [Run your own numbers with a $5 DataImpulse balance — traffic doesn't expire](https://bit.ly/dataimPulse)

## FAQ

**Does pay-as-you-go mean the traffic never expires?**
No, and this is the main reason two providers at the same rate can cost very differently. Non-expiring balances are the exception. Ask before buying.

**Is there a free trial for pay-as-you-go residential proxies?**
Rarely. DataImpulse has no free tier; access starts at a $5 purchase, with a 7-day money-back guarantee on Intro plans paid by card, provided less than 80% of the traffic was used. Crypto payments are excluded from that refund.

**How much traffic do 5GB actually buy?**
It depends entirely on page weight and how many requests fail. A typical HTML page runs 50–300KB through a proxy, so 5GB covers roughly tens of thousands of page loads on light pages and a fraction of that on JavaScript-heavy targets. Measure your own pages rather than trusting a generic estimate.

**Is $1/GB residential traffic legitimate?**
Yes, within limits. The rate is achievable because the provider sources IPs first-party through its own opt-in app instead of buying from aggregators, and because support and onboarding lean heavily on automation. What you give up is pool depth in less-common countries, enterprise compliance paperwork, and managed anti-bot tooling. For direct residential scraping with your own code, that trade usually makes sense.

**Can I start without a monthly commitment?**
That is the entire point of the model. Buy a balance, spend it at your own pace, top up when you need more. No renewal runs in the background, and nothing is charged unless you place an order.

## The short version

If you are here because you want residential IPs without a subscription, the market will happily sell you that. The decision that actually saves money is choosing a provider whose unused traffic survives, then measuring cost per successful request instead of cost per gigabyte.

DataImpulse sits at the aggressive end of that comparison at $1/GB with non-expiring traffic and a $5 entry point, which makes it a cheap way to find out whether the model fits your workload before you commit to anyone's annual plan.
