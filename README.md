# data scraping proxies: how to choose between per-IP and per-GB plans, and stop paying twice for failed requests

Most people shopping for data scraping proxies spend their first hour comparing pool sizes. "Ours is bigger" is the easiest thing for a vendor to put on a landing page, and the hardest thing for you to verify before you've spent money. What actually decides whether your pipeline runs smoothly is duller than that: which billing axis you bought on, and whether your workload matches it.

There's a second thing worth knowing before you commit. Vendor pages advertise 95–99% success rates. Independent benchmarks that run requests against genuinely protected targets — the AIMultiple benchmark cycles through roughly 17,000 different URLs across Amazon, Bing, eBay and YouTube — put most residential networks somewhere in the 50–67% range on a given day. The gap isn't dishonesty so much as different definitions: a CAPTCHA page served with an HTTP 200 counts as a success in some vendor reporting and a failure in most benchmarks.

Which means the number that should drive your purchase isn't the headline price per GB. It's cost per *successful* page, and that number depends heavily on how you're billed when things fail.

## The decision that actually changes your bill

Residential proxy pricing comes in two shapes, and they're not interchangeable.

**Per-GB (bandwidth) billing** charges you for traffic. Every request that goes out — including the ones that come back as a block page, a CAPTCHA, or a timeout — consumes your balance. Run a job over image-heavy pages and you'll feel it.

**Per-IP billing** charges you for access to a fixed set of residential addresses, usually with bandwidth unmetered while an IP is active. A retry costs you nothing extra in traffic. A 5 MB product page costs the same as a 200 KB one.

The practical rule most teams converge on: if your target pages are heavy or your bandwidth is unpredictable, per-IP is the safer structure. If your workload is high-rotation and each request is small — SERP snapshots, price checks, API polling — per-GB is usually cheaper, because you're paying for exactly what you use and nothing for idle IPs.

That's the fork in the road. Everything else is detail.

## Where 9Proxy sits in this

9Proxy is a residential-only provider: 20M+ residential IPs across 90+ countries, HTTP/HTTPS and SOCKS5 support, country-, state-, city-, ZIP- and ISP-level targeting, and a claimed 99.95% uptime. According to 9Proxy's own documentation, the platform offers exactly two residential models — by IPs and by GB — which is worth flagging up front if you were hoping for datacenter proxies in the same dashboard. You'd need a different provider for those.

The two models are built differently enough that picking the wrong one is genuinely annoying.

### Residential Proxy by IPs

You buy a block of IPs and each one gives you unlimited traffic while it's alive. A residential IP typically stays active anywhere from a few hours to around 24 hours, so "unlimited" means unlimited *during that window*, not unlimited forever.

Setup runs through the 9Proxy desktop app with local port forwarding. There's no natural rotation — you either let IPs expire or configure Auto Rotation on selected ports at intervals you choose. Other pieces that matter in practice: Auto Refresh to swap an IP on demand, port configuration for parallel sessions, and a "Today List" that lets you re-forward an IP you already used within the last 24 hours without spending a second one from your balance. That last one quietly cuts IP consumption for jobs that run across multiple days.

Unused IPs don't expire. If you buy 5,000 and burn 1,200 this month, the rest is still sitting there.

### Residential Proxy by GB

You buy traffic instead of addresses, and the platform generates unlimited endpoints against that traffic. Only the GB you actually consume gets deducted. Sessions can run sticky or rotating, and authentication works through username/password or IP whitelisting — the latter matters a lot if you're running from a cloud server, because you skip the app entirely and work straight from the dashboard.

Purchased GB stays valid for 180 days. Targeting goes down to ZIP and ISP level. Sub-users let you hand traffic to specific projects or teammates, and share codes cover the ad-hoc cases.

If you want a concrete side-by-side of what each model gives you, 👉 [see 9Proxy's residential proxy options and current package list](https://bit.ly/9-Proxy).

## Every 9Proxy package, at current prices

9Proxy raised prices on IP-based and bundle packages on 1 June 2026 — the first adjustment in the company's history. GB-based pricing was left alone. The table below reflects post-adjustment rates.

| Model | Package | Price | Effective rate | Validity |
| --- | --- | --- | --- | --- |
| By IPs | 100 IPs | $24 | $0.24/IP | Unused IPs never expire |
| By IPs | 500 IPs | $72 | $0.144/IP | Unused IPs never expire |
| By IPs | 1,000 IPs + 500 bonus | $126 | $0.084/IP | Unused IPs never expire |
| By IPs | 2,500 IPs | $210 | $0.084/IP | Unused IPs never expire |
| By IPs | 5,000 IPs | $360 | $0.072/IP | Unused IPs never expire |
| By IPs | 15,000 IPs | $720 | $0.048/IP | Unused IPs never expire |
| By IPs | 25,000 IPs | $863 | $0.035/IP | Unused IPs never expire |
| By IPs | 50,000 IPs | $1,438 | $0.029/IP | Unused IPs never expire |
| Business IPs | 100,000 IPs | $2,300 | $0.023/IP | Unused IPs never expire |
| Business IPs | 200,000 IPs | $4,140 | $0.021/IP | Unused IPs never expire |
| Business IPs | 500,000 IPs | $8,625 | $0.018/IP | Unused IPs never expire |
| By GB | 5 GB | $15 | $3.00/GB | 180 days |
| By GB | 50 GB + 5 GB bonus | $105 | $2.10/GB | 180 days |
| By GB | 100 GB | $150 | $1.50/GB | 180 days |
| By GB | 200 GB | $200 | $1.00/GB | 180 days |
| By GB | 1,000 GB | $800 | $0.80/GB | 180 days |
| By GB | 2,000 GB | $1,500 | $0.75/GB | 180 days |
| Enterprise GB | 3,000 GB | $2,160 | $0.72/GB | No expiry |
| Enterprise GB | 6,000 GB | $4,200 | $0.70/GB | No expiry |
| Enterprise GB | 10,000 GB | $6,800 | $0.68/GB | No expiry |
| Bundle | 100 IPs + 5 GB — Starter | $30 | — | GB valid 180 days |
| Bundle | 1,500 IPs + 50 GB | $180 | — | GB valid 180 days |
| Bundle | 5,000 IPs + 500 GB — Pro | $720 | — | GB valid 180 days |

Purchase links, package by package:

- 👉 [Buy 100 IPs for $24](https://bit.ly/9-Proxy) · 👉 [Buy 500 IPs for $72](https://bit.ly/9-Proxy) · 👉 [Buy the 1,000 IP + 500 bonus pack](https://bit.ly/9-Proxy)
- 👉 [Buy 5,000 IPs for $360](https://bit.ly/9-Proxy) · 👉 [Buy 15,000 IPs for $720](https://bit.ly/9-Proxy) · 👉 [Buy the 50,000 IP bulk tier](https://bit.ly/9-Proxy)
- 👉 [Buy the 5 GB starter pack](https://bit.ly/9-Proxy) · 👉 [Buy the 200 GB pack](https://bit.ly/9-Proxy) · 👉 [Buy the 1,000 GB pack](https://bit.ly/9-Proxy)
- 👉 [Pick a Starter, mid-tier or Pro bundle](https://bit.ly/9-Proxy)

Two things jump out from that table. The per-IP rate only becomes genuinely cheap past 5,000 IPs — below that, you're paying $0.084–$0.24 per address, which is fine for session-based work but not for spraying requests. And the GB ladder is steep: going from the 5 GB pack to the 1,000 GB pack cuts the effective rate from $3.00 to $0.80 per GB, a 73% drop. If you're confident about monthly volume, buying one tier up is usually the better trade.

## Bundle plans and the Enterprise tier

Bundles exist for mixed workloads where one part of the job wants session stability and another just wants to rotate through the pool. The Starter bundle at $30 gives you 100 IPs plus 5 GB — enough to load-test a pipeline against your actual targets before committing. The Pro bundle at $720 pairs 5,000 IPs with 500 GB, which covers agencies running several clients off one procurement.

Enterprise GB packages drop the 180-day clock entirely. Traffic never expires, and the tier adds team functionality: one owner plus up to five members, per-member traffic controls, activity logs, unlimited share-code creation, and shared bandwidth inside the team that doesn't run down a validity timer. External shares still follow the 180-day rule.

For a scraping team, that team-layer is the part that matters. Passing traffic to a specific project or person without handing over the whole account balance is the difference between an agency setup and a shared login that everyone abuses.

## What a month of scraping actually costs

Numbers make this concrete, so here's arithmetic with the assumptions stated — this is cost modeling, not a benchmark result.

Say you need **3 million page fetches a month**, and you've blocked images and CSS, so each response averages about **300 KB**.

That's roughly **900 GB** of traffic. On the GB model you'd buy the 1,000 GB pack at $800, an effective $0.80/GB. Cost per thousand successful requests: about **$0.27**.

Now assume the same volume spread across the IP model. If you buy 5,000 IPs at $360 and each address handles a few hundred requests before it goes offline, 5,000 IPs covers the month. Cost per thousand requests: about **$0.12**. The IP model wins here — and it wins by more than the sticker math suggests, because a request that returns a block page consumes bandwidth on the GB model and nothing extra on the IP model.

Flip one variable and the answer flips with it. Leave images enabled and those same 3 million pages average 1.5 MB each — **4,500 GB**. You're now stepping into the 6,000 GB Enterprise pack at $4,200. Per-IP billing doesn't care about that at all.

> The hidden line item is retries. If 30% of your requests fail and you retry them, you're paying for roughly 1.4 requests per usable page. On per-GB billing that's a straight 40% surcharge. On per-IP billing, retries cost you time and maybe an extra IP, but not traffic.

## Setup choices that quietly change your bill

A few configuration decisions move real money, and none of them are in the marketing copy.

**Turn off assets you don't need.** Blocking images, fonts and CSS is the single biggest lever on a per-GB plan. If you're extracting text or structured data, you have no reason to download a hero image.

**Keep concurrency sane.** Pushing 50 parallel workers at one host gets you blocked faster than any pool size can fix, and every block is a wasted request. A handful of workers per domain is a more realistic ceiling than most people assume.

**Use sticky sessions when you're mid-flow, rotating when you're not.** A job that clicks from search results into a detail page and then a checkout flow should hold one IP with its cookies intact. A job pulling 10,000 independent product pages doesn't need that — rotating gives you more spread and lower per-IP pressure.

**Check the Today List before you buy more IPs.** IP-based users can re-forward an address used in the last 24 hours without consuming a fresh one. Multi-day jobs that would otherwise chew through balance can run noticeably leaner.

**Match your authentication to your infrastructure.** GB-based proxies work with username/password or IP whitelisting from a cloud server, no app involved. IP-based proxies need the desktop app. That difference decides whether your headless VPS can use the product at all.

If you're running from a cloud box and don't want to touch a desktop client, 👉 [set up a 9Proxy GB-based account here](https://bit.ly/9-Proxy) and authenticate by IP whitelist instead.

## Trial, payment, and the honest gaps

9Proxy offers a limited trial for new users, subject to availability, and you have to tell them which kind you want — an IP-based trial or a GB-based one. It's not an instant self-serve button, so ask support before you assume it's gone.

Payment covers credit cards, crypto (USDT, BTC, ETH, LTC, DOGE and others), bank cards, Alipay, Apple Pay and Google Pay. Some payment methods carry an additional 5% discount or a 5% product bonus, and referred users get 5% off through the referral program — worth checking at checkout, since it's a real reduction on a $126 or $360 order.

The gaps, stated plainly: there are no datacenter proxies in the documented lineup, so if your targets are lightly protected and you'd rather pay datacenter prices, this isn't the tool. The per-IP model has no built-in rotation, so you configure it yourself. And IP-based usage requires the desktop app — a genuine constraint for headless deployments.

Against that, an IP-based package with no expiry and unlimited traffic is a fairly forgiving thing to buy, because a slow month doesn't burn your balance. On the GB side, 180-day validity on 5 GB at $15 is a cheap way to test whether the network handles your specific targets before you commit to anything larger.

## FAQ

**Are residential proxies necessary for scraping?**
Not always. On lightly protected sites, datacenter IPs often get through more than half the time and cost less. Escalate to residential when your targets block cloud IP ranges or serve location-specific content you need to see accurately.

**How many IPs do I actually need?**
Divide your monthly request count by how many requests an IP realistically handles before it ages out, then add headroom. If you're unsure, start small — an unused IP doesn't expire, so a small first order isn't wasted money.

**Do 9Proxy packages expire?**
Unused IPs don't expire. GB-based packages are valid 180 days, and Enterprise GB packages have no expiry at all.

**Does it work with Scrapy, Playwright, Selenium and Puppeteer?**
HTTP/HTTPS and SOCKS5 are both supported, so any client that accepts a proxy string will work. GB-based proxies can be authenticated without the desktop app.

**Can I share traffic with my team?**
Yes. Sub-users and share codes are available on GB-based accounts, and the Enterprise tier adds a structured team mode with five members and per-member traffic controls.

## The short version

If your scraping job touches heavy pages or unpredictable bandwidth, buy IPs — unlimited traffic per address turns the retry problem into a non-issue, and unused balance doesn't rot. If your job is high-rotation and lightweight, buy GB and stop paying for idle addresses.

What you shouldn't do is pick a model because its headline number looked smaller on a comparison page. Per-IP and per-GB pricing aren't two prices for the same thing. They're two different products, and the gap between them shows up in your bill the first time a third of your requests come back blocked.

👉 [Check the current 9Proxy packages and pick the model that matches your workload](https://bit.ly/9-Proxy)
