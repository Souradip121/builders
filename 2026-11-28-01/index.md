---
title: "System design in 30 days: the free folder-tree roadmap"
---

# System design in 30 days: the free folder-tree roadmap

AI now writes a lot of the code. What it can't do for you is decide how the pieces fit: where the cache goes, which database, what breaks at 10x traffic. That judgement is system design, and it's what interviewers test. Here's a 30-day plan using only free resources.

## The free resources
- **The System Design Primer** (https://github.com/donnemartin/system-design-primer): free, open source, ~379k stars. Covers scalability, latency vs throughput, CAP, DNS, CDNs, load balancers, SQL vs NoSQL, replication, sharding, caching, message queues, and "latency numbers every programmer should know". Has worked design questions (Pastebin/Bit.ly, Twitter timeline, web crawler) with solutions.
- **ByteByteGo system-design-101** (https://github.com/ByteByteGoHq/system-design-101): free repo of visual explainers (CC BY-NC-ND 4.0). Their **YouTube channel** (https://www.youtube.com/channel/UCZgt6AzoyjslHTC9dz0UoTw) is free; courses on bytebytego.com are paid (optional).
- **MIT 6.5840 Distributed Systems** (https://pdos.csail.mit.edu/6.824/): the Spring 2026 course site has public lecture notes, papers and labs (MapReduce, Raft, sharded key/value). Go here after day 30 if you want depth.
- **Company engineering blogs**: read one real architecture write-up a week (e.g. the "real-world architectures" list in the Primer).

## The plan
**Week 1 · fundamentals**: client-server, HTTP, DNS, latency vs throughput, latency numbers. Done when you can explain what happens when you type a URL.
**Week 2 · building blocks**: load balancers, caching, SQL vs NoSQL, indexes, replication, sharding. Done when you can say *why* you'd add each one.
**Week 3 · scale + trade-offs**: message queues, rate limiting, consistency patterns, CAP. Done when you can argue both sides of a trade-off.
**Week 4 · practice**: design a URL shortener, a chat app and a news feed (Primer's Pastebin/Bit.ly and Twitter timeline solutions help), then 2 mock interviews with a friend. Done when you can do one in 45 minutes out loud.

## 1-page interview answer template
1. **Requirements**: functional (what it does) + non-functional (scale, latency, availability). Ask questions first.
2. **Estimates**: users, requests/sec, storage per year (back-of-envelope).
3. **API**: 3-5 endpoints with inputs/outputs.
4. **Data model**: tables/collections, keys, SQL or NoSQL and why.
5. **High-level design**: client, load balancer, services, cache, DB, queue. Draw boxes and arrows.
6. **Bottlenecks**: what breaks first at 10x, and how you'd fix it (cache, replicas, sharding, async).

## Sources (checked 27 Nov 2026)
- https://github.com/donnemartin/system-design-primer
- https://github.com/ByteByteGoHq/system-design-101
- https://pdos.csail.mit.edu/6.824/
- https://pdos.csail.mit.edu/6.824/schedule.html

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
