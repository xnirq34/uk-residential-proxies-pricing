# UK residential proxies: what they cost, how UK targeting actually works, and which plan fits your workload

Most people typing "uk residential proxies" into Google are trying to solve one of four things: getting data that only exists behind a UK IP, checking what UK users actually see, keeping a UK-facing account alive, or watching google.co.uk results from a British address. The provider list is easy to find. The harder part is deciding between two billing models that behave nothing alike — and figuring out whether you need one UK IP for three months or 400 UK IPs for one afternoon.

This is a walkthrough of that decision, using 9Proxy's current plans as the concrete example, because its pricing exposes the trade-off more clearly than most: you can pay per IP with unlimited bandwidth, or pay per GB with unlimited endpoints. Picking wrong costs real money in either direction.

## Why "UK" is a specific requirement, not just a geography label

Plenty of sites geo-gate by country and stop there. The UK is worse than that. A lot of the commercially interesting data is region-locked at the domain level and priced per market:

- Retail pricing on Amazon UK, Currys, John Lewis, Argos, ASOS and Tesco differs from the EU and US storefronts, and some pages simply won't render for non-UK IPs.
- Property and jobs data — Rightmove, Zoopla, Indeed UK, Reed — is gated by IP geography.
- Ad verification for Sky, ITV and Channel 4 campaigns only means anything if the request comes from a British residential connection.
- Streaming is its own category: BBC iPlayer, ITVX and Netflix UK are the usual reasons people start looking at UK IPs in the first place.
- google.co.uk SERP tracking needs a UK exit IP, or your rank data is somebody else's country's results.

Datacenter IPs from a UK range get flagged quickly on most of these. That's the entire reason the word "residential" is in the search query — you need an IP that looks like a home broadband connection in Britain, not a leased server.

One honest caveat worth knowing before you buy anything: UK residential proxies are good at retail, SERP, ad and account work, and inconsistent at streaming. A 2025 review of 9Proxy on iTWire found it worked well for e-commerce targets but could still get detected on services like Netflix [1]. That's a category-wide problem with consumer residential pools, not a 9Proxy-specific one. If iPlayer is your only goal, test before you commit to a large package.

## The two models, and why they're not interchangeable

This is the part most provider comparison pages flatten into a single "from $X/GB" line. It matters more than the headline price.

**Residential Proxy by IPs** — you buy a fixed number of residential IPs. An IP is only deducted from your balance when you forward it to a local port, unused IPs never expire, and each activated proxy has unlimited bandwidth for as long as it stays online (a few hours, up to around 24 hours, depending on the address) [2]. Because it's a real household connection, it won't hold forever — 9Proxy provides Auto Refresh Proxy to swap dead ones automatically and Auto Rotation Proxy to rotate on a schedule [2].

The catch: IP-based proxies run through the 9Proxy desktop app (Windows, macOS, Linux) using local port forwarding. There's no dashboard-only path, which is awkward on headless cloud servers [2][1].

**Residential Proxy by GB** — you buy a traffic allowance and generate as many endpoints as you want from it. Rotating by default, sticky sessions configurable by minutes, targeting embedded directly in the proxy username, and authentication via username/password or IP whitelist. Everything runs from the dashboard, no app required [3]. Traffic is valid for 180 days on standard GB plans, and never expires on Enterprise plans [2][3].

For UK work specifically, the target string looks like this:


subaccount-country-uk-city-london-sst-15


That's a London IP held for 15 minutes. Swap `sst-15` for nothing and every request gets a fresh UK IP; add `ssid-id1` and `ssid-id2` and you get parallel sticky sessions from the same configuration [3]. Country, state, city, ZIP and ISP filters are all available.

If you're using IP-based proxies on Linux instead, the equivalent is a terminal command rather than a username string:


9proxy proxy -c UK -p 60000


That forwards a UK residential proxy to port 60000 [2].

|  | Residential by IPs | Residential by GB |
| --- | --- | --- |
| You pay for | Fixed number of IPs | Total bandwidth consumed |
| Bandwidth | Unlimited while the IP is active | Capped by purchased GB |
| Endpoints | 1 IP = 1 activation when forwarded | Unlimited endpoints, only GB deducted |
| Expiry | Unused IPs never expire | 180 days (unlimited on Enterprise) |
| IP lifetime | A few hours to ~24h | Rotates per request, or sticky by minute setting |
| Setup | Desktop app + local port forwarding | Dashboard, no app needed |
| Best for | Long sessions, account work, unpredictable data volume | High-rotation scraping, cloud automation, tight budget control |

## What UK residential proxies cost across the market

Rough ballpark from published provider pricing: DataImpulse advertises pay-as-you-go UK residential from around $1/GB, Decodo and Webshare sit nearer $3.50/GB, Bright Data around $4.00/GB, and Geonode quotes from $0.79/GB with cheaper tiers at scale [4][5]. Static UK ISP proxies — a different product, billed per IP per month with unmetered bandwidth — start around $2.50 per IP per month at volume [6].

Two things worth noticing there. First, per-GB pricing spans a 4x range for what looks like the same product category. Second, when a benchmark test ran UK proxy providers against hardened British domains at 15-minute intervals, measured daily success rates landed between roughly 57% and 81% — nobody hits 100% on the difficult UK targets [4]. Budget for retries regardless of who you buy from.

9Proxy plays at the low end of that per-GB range and prices IPs separately. Its floor rates are $0.018 per IP and $0.68 per GB at the top tiers [7][8].

One timing note: on 1 June 2026, 9Proxy raised prices on IP-based and bundle packages for the first time since launch, and explicitly left GB-based prices untouched [9]. So if you see older tables quoting $0.015/IP or a $20 entry package for 100 IPs, those numbers are pre-adjustment. The current ones are below.

## Full 9Proxy package list

All tiers currently shown, in USD. Every listing below is a one-off balance top-up, not a subscription.

| Package | Model | What you get | Price | Unit price | Validity |
| --- | --- | --- | --- | --- | --- |
| 100 IPs | Residential by IPs | 100 residential IPs, unlimited bandwidth while active | $24 | $0.24/IP | IPs don't expire |
| 500 IPs | Residential by IPs | 500 residential IPs | $72 | $0.144/IP | IPs don't expire |
| 1,000 + 500 IPs | Residential by IPs | 1,500 IPs (1,000 paid, 500 bonus) | $126 | $0.084/IP | IPs don't expire |
| 2,500 IPs | Residential by IPs | 2,500 residential IPs | $210 | $0.084/IP | IPs don't expire |
| 5,000 IPs | Residential by IPs | 5,000 residential IPs | $360 | $0.072/IP | IPs don't expire |
| 15,000 IPs | Residential by IPs | 15,000 residential IPs | $720 | $0.048/IP | IPs don't expire |
| 25,000 IPs | Residential by IPs | 25,000 residential IPs | $863 | $0.035/IP | IPs don't expire |
| 50,000 IPs | Residential by IPs | 50,000 residential IPs | $1,438 | $0.029/IP | IPs don't expire |
| 100,000 IPs (Business) | Business IP | 100,000 residential IPs | $2,300 | $0.023/IP | IPs don't expire |
| 200,000 IPs (Business) | Business IP | 200,000 residential IPs | $4,140 | $0.021/IP | IPs don't expire |
| 500,000 IPs (Business) | Business IP | 500,000 residential IPs | $8,625 | $0.018/IP | IPs don't expire |
| 5 GB | Residential by GB | 5 GB traffic, unlimited endpoints | $15 | $3.00/GB | 180 days |
| 50 + 5 GB | Residential by GB | 55 GB traffic (50 paid, 5 bonus) | $105 | $2.10/GB | 180 days |
| 100 GB | Residential by GB | 100 GB traffic | $150 | $1.50/GB | 180 days |
| 200 GB | Residential by GB | 200 GB traffic | $200 | $1.00/GB | 180 days |
| 1,000 GB | Residential by GB | 1,000 GB traffic | $800 | $0.80/GB | 180 days |
| 2,000 GB | Residential by GB | 2,000 GB traffic | $1,500 | $0.75/GB | 180 days |
| 3,000 GB (Enterprise) | Enterprise GB | 3,000 GB, team mode, no expiry | $2,160 | $0.72/GB | Unlimited |
| 6,000 GB (Enterprise) | Enterprise GB | 6,000 GB, team mode, no expiry | $4,200 | $0.70/GB | Unlimited |
| 10,000 GB (Enterprise) | Enterprise GB | 10,000 GB, team mode, no expiry | $6,800 | $0.68/GB | Unlimited |
| Starter bundle | Bundle | 100 IPs + 5 GB | $30 | — | Mixed (IPs don't expire, GB 180 days) |
| Popular bundle | Bundle | 1,500 IPs + 50 GB | $180 | — | Mixed |
| Pro bundle | Bundle | 5,000 IPs + 500 GB | $720 | — | Mixed |

Pricing as listed by 9Proxy following the June 2026 adjustment [7][9]. The bundles are the cheapest way in if you're not sure which model you need — the Starter bundle at $30 gets you both a fixed-IP allowance and traffic to burn, which is usually enough to find out whether UK sticky sessions or rotating requests suit your job.

👉 [Compare the UK-capable 9Proxy packages](https://bit.ly/9-Proxy)

## Reading those numbers like a buyer

The per-IP column is where the volume discount actually bites. Going from 100 IPs to 5,000 drops the unit cost from $0.24 to $0.072 — a third of the price for the same product. Below that, 25,000 and 50,000 IPs land at $0.035 and $0.029, and the Business tiers bottom out at $0.018. If you expect to need more than a few hundred UK IPs over the next year, buying them in a bigger block once is cheaper than topping up five times, since the IPs sit in your balance without expiring [2].

The GB side is the opposite shape. The 5 GB package is the worst value per gigabyte in the entire lineup at $3.00/GB, and jumping to 200 GB cuts that to $1.00/GB — a 3x difference. If you're doing anything ongoing, the 5 GB tier is a testing package, not a production one.

A worked example to make it concrete. Say you're tracking google.co.uk rankings for 2,000 keywords daily across several UK locations, plus pulling UK retail prices on a few thousand product pages. That's a rotation-heavy, bandwidth-light workload where you want a different IP frequently and each request is small. The 100 GB package at $150 gives you plenty of headroom, and because it's GB-based you can generate a fresh UK endpoint per request without burning through IP activations [3]. Same job on the IP-based model would mean buying and re-forwarding IPs constantly, which works but is more manual — and IP-based proxies require the desktop app anyway, so a cloud server is off the table [2].

Now flip it. You're running 30 UK social or marketplace accounts, each needing a stable British address for hours at a time, with heavy browsing. Rotation here is a liability, not a feature. Buy 500 IPs for $72, forward what you need, keep the rest in balance, and let Auto Refresh swap any that drop [2]. Unlimited bandwidth means a session that runs long doesn't cost extra.

There's a third case people underestimate: UK ad verification around a campaign launch. You need real British residential exits on Sky, ITV or Channel 4 properties at specific moments, then nothing for three weeks. GB-based works, but the 180-day clock means unused traffic eventually evaporates [2]. The bundle packages exist for exactly this shape of mixed usage.

For a team rather than a solo operator, Enterprise GB plans add unlimited validity, one owner plus up to five members, shared bandwidth that doesn't expire inside the team, per-member traffic controls and full activity logs [3]. Worth it if you're coordinating several people on the same UK data pipeline, overkill if it's just you.

## Limits worth knowing before you pay

Some friction points that don't make it into provider sales pages:

- **The desktop app requirement is real.** IP-based proxies need the 9Proxy App for local port forwarding. If your workload lives on a VPS or in a scheduled cloud job, GB-based is the practical choice [2][1].
- **Residential IPs don't live forever.** On the IP-based model you're looking at hours up to roughly a day per activation, with automatic replacement available. Plan for churn rather than assuming a permanent UK address [2].
- **Streaming is hit and miss.** As noted above, third-party testing found detection issues on services like Netflix even when e-commerce targets worked cleanly [1].
- **Residential only.** 9Proxy's lineup covers residential by IP and residential by GB; there's no datacenter product in the two models documented [2]. If you need cheap bulk datacenter IPs for a job where stealth doesn't matter, this isn't it.
- **Free trials come and go.** Trial allocation depends on availability and current promotions, and reviewers have flagged that you often need to ask support for a code [1]. Don't build a plan around an assumed free tier.

On the positive side, third-party trackers put 9Proxy around a 97% success rate with roughly 1.3-second response times — competitive for the price bracket, though nowhere near the top end of the market [8]. Payment options are broad: credit and bank cards, crypto including USDT, BTC, ETH, LTC and DOGE, Google Pay, Alipay, and the in-house 9Proxy wallet [2]. Support is 24/7 via live chat, email and Telegram [2].

👉 [Check current UK IP availability and pricing on 9Proxy](https://bit.ly/9-Proxy)

## Quick answers to the usual questions

**Do I need residential proxies over datacenter ones for UK sites?**
For Amazon UK, ASOS, Tesco, Rightmove, google.co.uk and ad platforms, yes. Datacenter ranges are pre-flagged on most of them. For plain content access where nobody is checking, datacenter IPs are cheaper and faster.

**Can I target a UK city rather than just the country?**
Yes. 9Proxy supports country, state, city, ZIP and ISP filtering, both through the desktop app's filter panel and through the GB-based username string [2][3]. Worth knowing that stacking state + city + ISP filters narrows the available pool, so target only what your task genuinely requires [3].

**Is 180-day validity enough?**
For project-based work, usually. For continuous pipelines, pick larger GB tiers or go Enterprise, where traffic never expires [2][3].

**What happens if a UK IP goes dead mid-session?**
On IP-based plans, Auto Refresh Proxy replaces it automatically, or Auto Rotation Proxy handles scheduled rotation [2]. iTWire's review also references a 60-second replacement policy for unusable IPs [1].

**Do the packages auto-renew?**
No. This is balance-based: you top up and draw down. Unused IP balance doesn't expire, and GB balance runs on the 180-day (or unlimited) clock [2].

## The short version

If your UK work is high-rotation and bandwidth-light — SERP tracking, price collection, ad verification, geo-checks — go GB-based, and skip the 5 GB tier in favour of 100 GB or 200 GB unless you're only testing.

If it's account-based with real browsing behind each UK identity, buy IPs instead. The 500 IP tier at $72 is the sensible first stop, and the 1,000 + 500 package at $126 is the better deal if you already know you'll use them, since nothing in that balance expires.

If you genuinely don't know yet, the $30 Starter bundle buys you both currencies and answers the question in an afternoon rather than after a month of guessing.

👉 [Start with 9Proxy's UK residential proxy packages](https://bit.ly/9-Proxy)

*Prices and package configurations reflect 9Proxy's published rates following the June 2026 pricing update and may change; verify on the pricing page before purchasing.*
