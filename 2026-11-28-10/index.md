---
title: "Fix your GitHub profile in one evening: 6 tells + free fixes"
---

# Fix your GitHub profile in one evening: 6 tells + free fixes

For students whose GitHub is their resume. Every tool here is free and open source (checked 27 Nov 2026).

## 1. Make a profile README
GitHub shows it at the top of your profile only if: the repo name **matches your username**, the repo is **public**, it has **README.md in the root**, and the file has any content.
1. **+ → New repository**, name it exactly your username.
2. Set it to Public, tick **Add README**, create.
3. Edit README.md. A starter:

```md
# Hi, I'm <name> 👋
2nd-year CS student · building <project> · learning <topic>

- 🔭 Working on: <project + live link>
- 📫 Reach me: <email or LinkedIn>
```
Docs: https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/managing-your-profile-readme

## 2. Pin real projects
You can pin up to **6** repositories and gists combined (Profile → Customize your pins). Pin things a stranger can run, each with a README: what it does, a screenshot, how to run it, a live link.
Docs: https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/pinning-items-to-your-profile

## 3. Show private contributions
Most work in private or college repos? Profile → **Contribution settings** (above the graph) → **Private contributions**. It shows as anonymized activity.
Docs: https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/managing-contribution-settings-on-your-profile/showing-your-private-contributions-and-achievements-on-your-profile

## 4. A stats card that loads
**github-readme-stats** (https://github.com/anuraghazra/github-readme-stats, MIT) now says it is **no longer maintained** and points to its successor. Its public instance is "best-effort", because the GitHub API allows 5k requests per hour; it recommends self-hosting or its GitHub Actions workflow.
Successor, **GitHub Stats Extended** (https://github.com/stats-organization/github-stats-extended, MIT), with a card wizard at https://github-stats-extended.vercel.app/frontend:

```md
![My GitHub stats](https://github-stats-extended.vercel.app/api?username=YOUR_USERNAME)
```

## 5. Skills as icons, not a text list
**skill-icons** (https://github.com/tandpfun/skill-icons, MIT): one image, many icons.

```md
[![My Skills](https://skillicons.dev/icons?i=js,react,py,cpp,git)](https://skillicons.dev)
```
Add `&theme=light` or `&perline=5`.
Or **Shields.io** badges: `logo=` takes **Simple Icons** slugs (https://github.com/simple-icons/simple-icons, CC0, 3,400+ brand icons):

```md
![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
```

## 6. Extras that move
- **readme-typing-svg** (https://github.com/DenverCoder1/readme-typing-svg, MIT): a typing animation. It suggests self-hosting for better uptime.

```md
![Typing SVG](https://readme-typing-svg.demolab.com/?lines=2nd-year+CS+student;I+build+web+apps)
```
- **lowlighter/metrics** (https://github.com/lowlighter/metrics, MIT): an infographic with 47 plugins. Use the GitHub Action for all features; the shared instance at metrics.lecoq.io turns off compute-heavy ones.

## Sources (checked 27 Nov 2026)
- https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/managing-your-profile-readme
- https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/pinning-items-to-your-profile
- https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/managing-contribution-settings-on-your-profile/showing-your-private-contributions-and-achievements-on-your-profile
- https://github.com/anuraghazra/github-readme-stats
- https://github.com/stats-organization/github-stats-extended
- https://github.com/tandpfun/skill-icons
- https://github.com/simple-icons/simple-icons
- https://shields.io/docs/logos
- https://github.com/DenverCoder1/readme-typing-svg
- https://github.com/lowlighter/metrics

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
