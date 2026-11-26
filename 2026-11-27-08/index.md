---
title: "6 signs your project was vibe-coded (and the fix for each)"
---

# 6 signs your project was vibe-coded (and the fix for each)

Using AI to build is fine. Shipping code you never understood is the problem, and it shows. Here are the six tells I look for in student portfolios, with the fix for each.

## 1. The default AI landing page
Purple gradients, glass cards, emoji in every heading, glowing buttons, a fake logo marquee.
- **Slopstrap** (https://slopstrap.mikelacher.com/) is a satirical front-end toolkit that adds this look *on purpose*: gradient text, frosted cards with cursor glow, decorative emoji, shimmering buttons, bento grids, animated stat counters, fake testimonials and placeholder copy. You add `slopstrap.css` + `slopstrap.js` and use classes like `slop-card`. Open it and you'll recognise half the projects on your feed.
- **Fix:** one font, one accent colour, real screenshots of your app instead of decoration.

## 2. A README nobody wrote
"Seamless, powerful, revolutionary" and no way to run the project.
- **Fix:** use the structure from https://www.makeareadme.com/: what it does, a screenshot or GIF, install + run steps, how to use it, what you'd improve next. Write it in your own words.

## 3. Zero tests
- **Fix:** write 3 tests for the core logic (not the UI). Then run them on every push with GitHub Actions: https://docs.github.com/en/actions/get-started/quickstart (Python example: https://docs.github.com/en/actions/tutorials/build-and-test-code/python). Free for public repos.

## 4. Secrets in the repo
A committed `.env` file or a hard-coded API key.
- **Fix, in this order:** 1) revoke or rotate the key (GitHub's docs say this is the first step, and it may be enough), 2) add `.env` to `.gitignore` (https://docs.github.com/en/get-started/git-basics/ignoring-files), 3) only if needed, rewrite history with git-filter-repo (https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository).
- GitHub push protection for users is on by default and blocks supported secrets from being pushed to public repos: https://docs.github.com/en/code-security/secret-scanning/introduction/about-push-protection

## 5. Dead buttons and placeholder links
"Learn more" goes to `#`, testimonials from people who don't exist, a pricing page for an app with no payments.
- **Fix:** click every link yourself. Delete anything that isn't real. A small app that fully works beats a big one that half works.

## 6. You can't explain your own code
This is the one that costs you in interviews: "why this database?" and silence.
- **Fix:** before you ship, walk through every file out loud (or to a friend). Any part you can't explain, rewrite yourself or ask the AI to explain it until you can.

## Quick checklist before you put a project on your resume
- [ ] README with run steps and a screenshot
- [ ] 3+ tests running in CI
- [ ] No secrets in the repo or its history
- [ ] Every link and button works
- [ ] You can explain each file in 1 minute

## Sources (checked 26 Nov 2026)
- https://slopstrap.mikelacher.com/
- https://www.makeareadme.com/
- https://docs.github.com/en/actions/get-started/quickstart
- https://docs.github.com/en/get-started/git-basics/ignoring-files
- https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository
- https://docs.github.com/en/code-security/secret-scanning/introduction/about-push-protection

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
