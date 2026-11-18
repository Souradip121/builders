---
title: "AI wrote more code. Review became the bottleneck."
---

# AI wrote more code. Review became the bottleneck.

## The study
"Artificial Intelligence in the Firm: Bottlenecks in Software Production" is a working paper by two Harvard PhD candidates (current version dated Aug 4, 2026; not yet peer-reviewed). It covers **718 firms** and 725,938 workers from **January 2021 to March 2026**, using engineering-analytics data (49.1M pull requests, 200.9M commits). It compares firms that adopted coding agents with firms that hadn't yet, and measures the added effect of agents at firms that already had AI coding assistants.

| Metric | Change |
|---|---|
| Lines of code added per worker-month | +30% (+1,494 on a 5,017 baseline) |
| Commits | +20% |
| Pull requests | +23% |
| Finished work (issues resolved and deployed) | no measurable rise |
| Time from PR to merge | +49% (7.03 → 10.48 days) |
| Review comments per PR | +35% |
| Share of PRs with change requests | about +12 points from 13% (nearly doubled) |

PRs didn't get bigger. AI wrote only 23.3% of review comments by March 2026. Summary: ComplexDiscovery, Oct 13, 2026.

## The fix: verification before review
From "How the Claude Code team thinks about verification" (claude.dev, Nov 16, 2026):

1. **End-to-end tests first.** "If you have to focus on one test type, pick end-to-end." Give the agent a way to boot, drive and inspect the running app.
2. **Fast, reliable tests.** Flaky tests teach an agent to rerun instead of fixing code.
3. **Cheap checks before the PR.** Tests, build and linter run locally before a pull request opens; hooks can enforce it.
4. **Escalate.** If a check still fails after three rounds, a human steps in.
5. **Keep checks out of reach.** "If a change can modify the check that judges it, the check is broken." Review rules are read from the base branch, not the PR.
6. **Turn misses into rules.** Repeated issues become rules in REVIEW.md or CLAUDE.md, pruned now and then.
7. **Measure the checks.** Track reverts and rejections.

## Your checklist
- [ ] One end-to-end test for your most important user flow
- [ ] A pre-PR hook that runs tests, build and lint
- [ ] CI that reads review rules from the main branch
- [ ] A CLAUDE.md (or REVIEW.md) with your top 10 repeated review comments
- [ ] A weekly look at time-to-merge

## Sources (checked 2026-11-19)
- https://complexdiscovery.com/harvard-researchers-find-ai-coding-agents-shifted-the-bottleneck-to-code-review/
- https://claude.dev/blog/how-the-claude-code-team-thinks-about-verification/

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
