---
title: "Anthropic's Agent Skills: the repo + how to write your own"
---

# Anthropic's Agent Skills: the repo + how to write your own

A **skill** is a folder with a `SKILL.md` file (YAML frontmatter with `name` + `description`, then instructions) plus optional scripts, reference files and templates. Claude keeps only each skill's name and description in context (~100 tokens per skill), reads `SKILL.md` when a task matches, and opens the other files or runs the scripts only when needed. Anthropic calls this progressive disclosure.

## The repo: github.com/anthropics/skills
- https://github.com/anthropics/skills ("Public repository for Agent Skills"), ~200k stars and 23.4k forks on 25 Nov 2026.
- `skills/` has 19 skills, `template/` a starter `SKILL.md`, `spec/` a pointer to the open standard at https://agentskills.io/specification.
- Licence: per the README, many skills are open source under **Apache 2.0**, including the `docx`, `pdf`, `pptx` and `xlsx` skills behind Claude's file creation. Check each skill's `LICENSE.txt`.
- The README says they're for demonstration and education: test before you rely on them.

**Open these first**
- `skill-creator`: creates, edits and tests new skills.
- `pdf`: forms, merging, extraction; ships a `scripts/` folder of Python helpers. Good model of a complex skill.
- `webapp-testing`: tests local web apps with Playwright.
- `mcp-builder`: a guide to building good MCP servers.
- `frontend-design`: steers Claude to deliberate, less generic UI.

## Where skills work (official docs)
- **Claude Code**: custom skills in `~/.claude/skills/` (personal) or `.claude/skills/` (project). No upload. Install the repo's skills as plugins:
  ```
  /plugin marketplace add anthropics/skills
  /plugin install document-skills@anthropic-agent-skills
  /plugin install example-skills@anthropic-agent-skills
  ```
  Then just ask, e.g. "Use the PDF skill to extract the form fields from file.pdf".
- **Claude apps (claude.ai)**: pre-built document skills run automatically; upload your own as a zip on Pro, Max, Ultra, Team and Enterprise plans with code execution enabled.
- **Claude API**: pre-built `pptx`, `xlsx`, `docx`, `pdf` skills by `skill_id`, or upload yours through `/v1/skills`. Needs the code execution tool; the container has no network access.
- Custom skills don't sync between these surfaces: add them to each one separately.

## Write your own in 10 minutes
1. `mkdir -p ~/.claude/skills/commit-notes`
2. Create `SKILL.md`:
   ```markdown
   ---
   name: commit-notes
   description: Writes release notes from git log. Use when the user asks for release notes or a changelog.
   ---
   # Commit notes
   1. Run `git log --oneline` since the last tag.
   2. Group commits into Added / Fixed / Changed.
   3. Keep each line under 80 characters.
   ```
3. Rules: `name` is lowercase letters, numbers and hyphens, max 64 characters, and can't contain "anthropic" or "claude". `description` is max 1,024 characters and must say **what it does and when to use it**: that's what Claude matches against.
4. Ask Claude Code for release notes and watch it load the skill.

**Safety:** only install skills from sources you trust, and read the scripts first. A skill can run code.

## Sources (checked 25 Nov 2026)
- https://github.com/anthropics/skills
- https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview
- https://code.claude.com/docs/en/skills
- https://support.claude.com/en/articles/12512180-using-skills-in-claude
- https://agentskills.io/specification

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
