---
title: "Pre-launch security audit: 4 tells + free checks"
---

# Pre-launch security audit: 4 tells + free checks

## 1. nginx HTTP/2 bugs (disclosed 18 Nov 2026)
- **CVE-2026-123007** (HTTP/2 send_window integer underflow): nginx 1.9.5–1.31.8. Wiz says it is exploitable in default configs with HTTP/2 on.
- **CVE-2026-123633** (HTTP/2 use-after-free): nginx 1.19.7–1.31.8, when nginx proxies over HTTP/2 and connection slots run low.
- **Fixed in:** 1.30.7 (stable) and 1.31.9 (mainline). NGINX Plus fixes are listed in F5 advisories K000163926 / K000163928.
- **Severity:** Wiz rates both CVSS 9.2; nginx.org rates them "major" and "medium".
- **Workaround until you upgrade:** `http2 off;` (nginx 1.25.1+) or remove `http2` from `listen`, then reload.
- Check your version: `nginx -v`.

## 2. Ruby2Shell (CVE-2026-132825)
A one-byte heap overflow when changing letter case in single-byte encodings. Veria Labs marks Rails "affected in default configuration", reachable before login.
- **Affected:** Ruby 4.0.0–4.0.9, 3.4.0–3.4.12, 3.3.13 and earlier (3.2 and older are end of life).
- **Fixed:** Ruby 4.0.10, 3.4.13, 3.3.14. Upgrade Ruby itself; updating Rails gems doesn't fix it.
- Check: `ruby -v`.

## 3. Supabase Row Level Security
"Enable RLS on every table in an exposed schema." A table without RLS is readable and writable by any role with a grant on it. Write per-user policies with `auth.uid()`, keep the service_role key on the server, and log in as a second account to test.

## 4. Secrets in git
GitHub secret scanning runs automatically and free on public repos, across all history. Dependabot alerts are included in all plans. If a key ever hit git, rotate it — deleting the file isn't enough.

## Free checks
- **Mozilla HTTP Observatory** — scores your HTTP headers (CSP, HTTPS redirect, Referrer-Policy). https://developer.mozilla.org/en-US/observatory
- **ZAP baseline scan** — spiders for a minute, passive checks only: `docker run -t ghcr.io/zaproxy/zaproxy:stable zap-baseline.py -t https://yoursite`
- **npm audit** — known vulnerabilities in dependencies; `npm audit fix` to patch.
- **Supabase Security Advisor** — flags RLS gaps (also `supabase db advisors`).

## Sources (checked 2026-11-24)
- https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities · https://nginx.org/en/security_advisories.html
- https://verialabs.com/ruby2shell/ · https://www.ruby-lang.org/en/news/2026/11/18/multiple-vulnerabilities-in-regexp-and-string/
- https://supabase.com/docs/guides/database/postgres/row-level-security
- https://docs.github.com/en/code-security/secret-scanning/introduction/about-secret-scanning
- https://www.zaproxy.org/docs/docker/baseline-scan/ · https://docs.npmjs.com/cli/v11/commands/npm-audit

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
