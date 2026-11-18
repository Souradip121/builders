---
title: "Pre-launch security checklist for vibe-coded apps"
---

# Pre-launch security checklist for vibe-coded apps

In November 2026 the security firm Crissy Field published a scan of **159,041 Lovable projects** (Dec 2025 to Sep 2026). 34,545 used Supabase. **24,664** sites sent Supabase database records on page load without a login, and **7,403** of them served tables containing email addresses. Data they found included passport details, 200,000+ chat messages, payment information and contracts. The researchers note the 30% figure is not a confirmed leak rate and the sample isn't representative of all Lovable apps.

Run these checks before real users sign up.

## 1. Run Supabase's Security Advisor
Dashboard → **Advisors → Security** (`https://supabase.com/dashboard/project/_/advisors/security`), or `supabase db advisors` in the CLI. Fix these first:
- `0013_rls_disabled_in_public` (ERROR): "Table publicly accessible"
- `0010_security_definer_view` (ERROR): a public view that ignores RLS
- `0002_auth_users_exposed` (ERROR): user data exposed through a view
- `0007_policy_exists_rls_disabled`: you wrote a policy but RLS is off, so it does nothing
- `0008_rls_enabled_no_policy`: RLS on, no access rules yet

## 2. Turn on RLS for every table in an exposed schema
```sql
alter table public.your_table enable row level security;
```
With RLS on and no policies, the publishable (public) key reads nothing through the API. Then add one policy per real use case, such as "a user can read their own rows". Supabase's RLS guide has policy examples.

## 3. Keep the secret key out of the browser
The secret (service role) key bypasses RLS. Supabase's docs: never use a secret key in the browser or expose it to customers. Search your deployed JavaScript bundle and your repo for it. If it ever shipped, treat it as leaked and replace it.

## 4. Test as a stranger
- Create a second account and try to load the first account's data by changing IDs in URLs and API calls.
- Log out, open DevTools → Network, reload, and read what data comes back.
- If anything private loads, fix the policy, then test again.

## 5. Repeat after big changes
The report recommends reviewing access permissions and the separation between user accounts before handling real data, repeating the checks after significant changes, and getting an expert review before handling confidential data. Automated checks don't replace a professional security assessment.

## Sources (checked 2026-11-19)
- Crissy Field report: https://www.crissyfield.de/research/lovable-en/
- Supabase RLS guide: https://supabase.com/docs/guides/database/postgres/row-level-security
- Supabase database advisors: https://supabase.com/docs/guides/database/database-advisors

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
