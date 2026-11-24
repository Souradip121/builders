---
title: "5 more FREE vs PAID swaps you can self-host"
---

# 5 more FREE vs PAID swaps you can self-host

Part 2 of the FREE vs PAID series. "$0" means no licence fee: you still pay for the server and your time.

| Paid plan (official price) | Free swap | Licence | Stars |
|---|---|---|---|
| Calendly Standard: $10/seat/mo (Teams $16) | [Cal.diy](https://github.com/calcom/cal.diy) | MIT | 50.4k |
| Mailchimp Essentials: from $13/mo (Free plan: 250 contacts) | [listmonk](https://github.com/knadh/listmonk) | AGPL-3.0 | 24.4k |
| Notion Plus: $10/member/mo | [AFFiNE](https://github.com/toeverything/AFFiNE) | MIT for self-hosting | 77.8k |
| Hotjar (now Contentsquare) Growth: $39/mo yearly, $49 monthly | [PostHog](https://github.com/PostHog/posthog) | MIT (except `ee/`) | 41.1k |
| 1Password Teams Starter Pack: $24.95/mo for up to 10 users, billed yearly | [Vaultwarden](https://github.com/dani-garcia/vaultwarden) | AGPL-3.0 | 71.3k |

## Notes on each
- **Cal.diy**: the cal.com repo now opens as Cal.diy, "a fork of Cal.com with all enterprise/commercial code removed", 100% MIT. Teams, Orgs, Workflows and SSO were removed, and there is no hosted version. Docker Compose is documented.
- **listmonk**: newsletter and mailing-list manager in a single binary. `docker compose up -d` from the README. Pair it with an SMTP provider.
- **AFFiNE**: docs, whiteboards and databases in one workspace; "free for self-hosting under the MIT license". Start with Docker.
- **PostHog**: product analytics with session replay and heatmaps. The README offers a one-line hobby deploy on Linux with Docker (4 GB RAM recommended) and says open-source deployments aren't supported by PostHog. The cloud version also has a free tier.
- **Vaultwarden**: a lightweight server compatible with Bitwarden apps; install via the container images. "This project is not associated with Bitwarden or Bitwarden, Inc."

## How to try one this weekend
1. Get a small Linux VPS (or reuse the Coolify box from part 1).
2. Deploy one swap at a time from its README.
3. Put it behind HTTPS and set up automatic database backups.
4. Run it next to the paid tool for a month before you cancel.

## Sources (checked 2026-11-24)
- https://calendly.com/pricing · https://github.com/calcom/cal.diy
- https://mailchimp.com/pricing/marketing/ · https://github.com/knadh/listmonk
- https://www.notion.com/pricing · https://github.com/toeverything/AFFiNE
- https://contentsquare.com/pricing/ · https://github.com/PostHog/posthog
- https://1password.com/business-pricing · https://github.com/dani-garcia/vaultwarden

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
