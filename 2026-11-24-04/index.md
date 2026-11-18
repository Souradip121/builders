---
title: "The ₹0 SaaS stack: free tiers and their limits"
---

# The ₹0 SaaS stack: free tiers and their limits

Everything below is the free plan as stated on each official pricing page.

| Job | Tool | Free plan | First paid plan |
|---|---|---|---|
| Code + CI | [GitHub](https://github.com/pricing) | Unlimited public/private repos, 2,000 CI/CD minutes/month, 500 MB Packages | Team $4/user/mo |
| Database + auth | [Supabase](https://supabase.com/pricing) | 500 MB database, 50,000 monthly active users, 1 GB file storage, 5 GB egress, 2 active projects; paused after 1 week of inactivity | Pro $25/mo |
| Hosting / API | [Cloudflare Workers](https://developers.cloudflare.com/workers/platform/pricing/) | 100,000 requests/day, 10 ms CPU per invocation | Workers Paid from $5/mo |
| Static sites | [Cloudflare Pages](https://developers.cloudflare.com/pages/platform/limits/) | 500 builds/month, 1 build at a time, 100 projects | – |
| Email | [Resend](https://resend.com/pricing) | 3,000 emails/month, 100/day, 3 domains | Pro $20/mo (50,000 emails) |
| Analytics | [PostHog](https://posthog.com/pricing) | 1M events, 5,000 session recordings, 1M feature-flag requests/month; no card needed | Pay-as-you-go, $0 base |
| Errors | [Sentry](https://sentry.io/pricing/) | Developer: 5k errors/month, 1 user | Team $29/mo ($26 billed yearly) |
| Payments | [Stripe India](https://stripe.com/in/pricing) | No setup or monthly fees | 2% for Indian Visa/Mastercard cards, 3% international |

Optional extras: [Clerk](https://clerk.com/pricing) auth is free up to 50,000 monthly retained users per app; [Upstash Redis](https://upstash.com/pricing/redis) is free for 250 MB and 500K commands/month; [Neon](https://neon.com/pricing) Postgres has a free plan with 1 GB storage per project.

## The trap: Vercel Hobby
Vercel's terms say a Hobby plan is for personal or non-commercial use only. For a paid SaaS, use Vercel Pro ($20 per developer seat) or host on Cloudflare.

## Setup order
1. Create the GitHub repo and turn on Actions for tests.
2. Create a Supabase project. Turn on Row Level Security for every table before you add data.
3. Deploy the frontend and API on Cloudflare (Pages for static, Workers for functions).
4. Verify your domain in Resend and send the sign-up email from it.
5. Add PostHog for events and Sentry for errors.
6. Add Stripe last, in test mode first.

## Watch these limits
- Supabase free projects pause after a week with no activity, so keep a staging project busy or upgrade before launch.
- Resend's 100 emails a day can cap a launch-day sign-up spike.

## Sources (checked 2026-11-19)
- https://supabase.com/pricing
- https://developers.cloudflare.com/workers/platform/pricing/ and https://developers.cloudflare.com/pages/platform/limits/
- https://vercel.com/pricing, https://vercel.com/docs/plans/hobby, https://vercel.com/legal/terms
- https://resend.com/pricing · https://posthog.com/pricing · https://sentry.io/pricing/
- https://clerk.com/pricing · https://github.com/pricing · https://stripe.com/in/pricing
- https://neon.com/pricing · https://upstash.com/pricing/redis

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
