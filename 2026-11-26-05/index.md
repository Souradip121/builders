---
title: "Cloudflare for students: the Minecraft trick + the free plan"
---

# Cloudflare for students: the Minecraft trick + the free plan

## The repo that's trending
**sshkeda/minecraft-server-on-orange-cloud** (MIT licence) — https://github.com/sshkeda/minecraft-server-on-orange-cloud

It runs a Paper server for Minecraft Java entirely on Cloudflare:
1. Spectrum takes the player's TCP connection on port 25565 and hands it to a Worker.
2. The Worker passes it to a Durable Object, which starts the Paper server in a Cloudflare Container.
3. After 10 minutes with nobody online, it saves the world and sleeps. The next player wakes it in about 30 seconds.
4. While awake, it backs the world up to R2 about every 5 minutes.

**The honest part: it is not free.** It needs the Workers Paid plan (from $5/month, the only plan with Containers) and a domain on Cloudflare's Pro plan or higher, because Spectrum doesn't work on Free zones (Pro: $25/month, or $20/month billed yearly). The README puts the fixed cost at $25–30/month, plus container time only while it's awake (its estimate: about $5/month for 2 hours of play a day). Setup needs macOS or Linux, Bun, Node.js 22.12+ and Docker.

## What the FREE plan actually gives you ($0)
| Product | Free allowance | Use it for |
|---|---|---|
| Workers | 100,000 requests/day, 10 ms CPU per request | APIs, bots, cron jobs |
| Pages | Static asset requests free and unlimited; 500 builds/month; 1 build at a time; 20,000 files/site | Portfolio, project sites |
| R2 | 10 GB-month storage, 1M Class A + 10M Class B ops/month, **no egress fees** | Images, uploads, backups |
| D1 (SQLite) | 5 GB total, 5M rows read/day, 100K rows written/day, 10 databases | Your app's database |
| Workers KV | 1 GB stored, 100K reads/day, 1K writes/day | Config, caching, sessions |
| Durable Objects | Free with the SQLite backend: 100K requests/day, 13,000 GB-s/day | Chat rooms, live counters |
| Workers AI | 10,000 Neurons/day | Small AI features |
| Quick Tunnels | No account or domain needed | Share localhost for a demo |

## A student stack for Rs 0
- Portfolio on **Pages** (connect your GitHub repo, every push deploys).
- API on **Workers**: `npm create cloudflare@latest`, then `npx wrangler deploy`.
- Database on **D1**, files on **R2**.
- Demo your local app to a friend: `cloudflared tunnel --url http://localhost:8080` gives you a temporary trycloudflare.com link (testing only, no uptime guarantee, 200 in-flight requests).

## Sources (checked 25 Nov 2026)
- https://github.com/sshkeda/minecraft-server-on-orange-cloud
- https://developers.cloudflare.com/workers/platform/pricing/
- https://developers.cloudflare.com/containers/pricing/
- https://www.cloudflare.com/plans/
- https://developers.cloudflare.com/pages/platform/limits/
- https://developers.cloudflare.com/pages/functions/pricing/
- https://developers.cloudflare.com/r2/pricing/
- https://developers.cloudflare.com/workers-ai/platform/pricing/
- https://developers.cloudflare.com/cloudflare-one/networks/connectors/cloudflare-tunnel/do-more-with-tunnels/trycloudflare/

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
