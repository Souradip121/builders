---
title: "Find and fix leaked API keys in your repo"
---

# Find and fix leaked API keys in your repo

Deleting a `.env` file in a new commit doesn't remove the key: every earlier commit still holds it. GitHub reports that more than 39 million secrets were leaked across GitHub in 2024.

## Step 0: scan (all free)

**Gitleaks** (MIT license) finds passwords, API keys and tokens in git repos, folders and stdin.
- Install: see https://github.com/gitleaks/gitleaks (latest release v8.30.1).
- Whole history: `gitleaks git -v .`
- A folder or file: `gitleaks dir -v path/`
- Note: the maintainer says Gitleaks is feature complete; new releases are security patches.

**TruffleHog** (open source, AGPL-3.0) covers 800+ secret types and verifies each finding against the provider's API, marking results verified, unverified or unknown.
- Repo: https://github.com/trufflesecurity/trufflehog
- Scan a repo, show only working keys: `trufflehog git https://github.com/you/repo --results=verified`

**GitHub secret scanning** runs automatically and free on public repositories, across the entire Git history on all branches. Private org repos need GitHub Secret Protection (GitHub Team or Enterprise Cloud).
- **Push protection for users** is on by default on GitHub.com and stops you pushing secrets to public repositories.
- Push protection for a repo: Settings → Advanced Security → Secret Protection → Push protection → Enable.

## Step 1: rotate the key first
GitHub's own guide says to revoke and/or rotate the secret first; that may be enough without rewriting history. Assume a leaked key is compromised.

## Step 2: clean history with git filter-repo
Needs git-filter-repo 2.47+ (git 2.36+, Python 3.6+): https://github.com/newren/git-filter-repo
- Remove a file from all history: `git-filter-repo --sensitive-data-removal --invert-paths --path .env`
- Replace a string everywhere: `git-filter-repo --sensitive-data-removal --replace-text ../passwords.txt`
- Push: `git push --force --mirror origin`
- Side effects: all later commit hashes change, signatures are dropped, and a collaborator who pulls then pushes can bring the key back. Merge or close open PRs first. Cached PR views need GitHub Support.

## Step 3: add a pre-commit hook
With the pre-commit framework (https://pre-commit.com), create `.pre-commit-config.yaml`:

```yaml
repos:
  - repo: https://github.com/gitleaks/gitleaks
    rev: v8.30.1
    hooks:
      - id: gitleaks
```

Then run `pre-commit install`. `pre-commit autoupdate` bumps the version.

## Sources (checked 25 Nov 2026)
- https://github.com/gitleaks/gitleaks
- https://github.com/trufflesecurity/trufflehog
- https://docs.github.com/en/code-security/secret-scanning/introduction/about-secret-scanning
- https://docs.github.com/en/code-security/secret-scanning/introduction/about-push-protection
- https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository
- https://github.com/newren/git-filter-repo
- https://github.blog/security/application-security/next-evolution-github-advanced-security/

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
