---
title: "Vibe-coded to production: the 6-folder roadmap"
---

# Vibe-coded to production: the 6-folder roadmap

A demo works once, for you. A product works every day, for strangers. Do one folder a day.

```
production-ready/
├── 01-version-control/   git, .gitignore for .env, PRs, Dependabot
├── 02-tests/             Vitest unit tests, 1 Playwright E2E test, CI on every PR
├── 03-data-security/     RLS on every table, per-user policies, service key server-side
├── 04-secrets/           env vars, separate prod/preview values, redeploy after changes
├── 05-monitoring/        Sentry + source maps, alerts, 1 uptime monitor
└── 06-rollback/          preview deploys, Instant Rollback, db dumps, a rollback drill
```

## 01-version-control
Free resource: the Pro Git book — https://git-scm.com/book/en/v2. Dependabot alerts are included in all GitHub plans. **Done when:** the app is on GitHub, main is clean and no secrets are in history.

## 02-tests
Free resources: https://vitest.dev/guide/ and https://playwright.dev/docs/intro. GitHub Actions: public repos are free on standard runners; the Free plan includes $12/month of compute for private repos (GitHub no longer quotes a fixed minute count). **Done when:** CI is green on every PR and your main user flow has an E2E test.

## 03-data-security
Free resource: https://supabase.com/docs/guides/database/postgres/row-level-security — "Enable RLS on every table in an exposed schema." Don't assume it's on: check every table. **Done when:** a logged-in user can't read or change another user's rows.

## 04-secrets
Free resource: https://vercel.com/docs/environment-variables (Netlify: https://docs.netlify.com/build/environment-variables/overview/). Changes apply only to new deployments, so redeploy. **Done when:** no keys in the repo or client bundle, and production has its own keys.

## 05-monitoring
Free resource: https://docs.sentry.io. Sentry's free Developer plan: 1 user, 5k errors, 5M spans, 50 replays, 1 uptime monitor, 1 cron monitor, 30-day lookback. **Done when:** a test error shows up and triggers an alert.

## 06-rollback
Free resource: https://vercel.com/docs/instant-rollback — Hobby can roll back to the immediately previous deployment (Pro: any eligible one). After a rollback, run `vercel promote` to re-enable auto-assignment. Supabase daily backups are **Pro/Team/Enterprise only**; on Free, export regularly with `supabase db dump` (https://supabase.com/docs/guides/platform/backups). **Done when:** you've rolled back once on purpose and have a recent database dump.

## Sources (checked 2026-11-24)
All links above, plus https://sentry.io/pricing/ and https://docs.github.com/en/billing/concepts/product-billing/github-actions

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
