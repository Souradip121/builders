---
title: "Anthropic's free agent playbook on GitHub"
---

# Anthropic's free agent playbook on GitHub

Six official repos under https://github.com/anthropics, in the order I'd open them. Star counts are what GitHub showed on 2026-11-19.

## 1. claude-cookbooks (~55k stars)
https://github.com/anthropics/claude-cookbooks (the old `anthropic-cookbook` URL redirects here)
- "A collection of notebooks/recipes showcasing some fun and effective ways of using Claude."
- Open first: `patterns/agents` (basic_workflows, orchestrator_workers, evaluator_optimizer), then `tool_use/customer_service_agent.ipynb`.
- Also has `claude_agent_sdk` and `managed_agents` folders.

## 2. claude-quickstarts (~21k stars)
https://github.com/anthropics/claude-quickstarts
- Deployable projects built on the Claude API: Customer Support Agent, Computer Use Demo, Autonomous Coding Agent, Managed Agents examples (Slack, Linear, Sentry).
- Fork one, swap in your own data, deploy it.

## 3. Claude Agent SDK (Python ~8.6k stars, TypeScript ~1.9k)
- https://github.com/anthropics/claude-agent-sdk-python ("Python SDK for Claude Agent")
- https://github.com/anthropics/claude-agent-sdk-typescript (npm `@anthropic-ai/claude-agent-sdk`)
- Docs: https://code.claude.com/docs/en/agent-sdk/overview ("Build production AI agents with Claude Code as a library")
- Look for `query()`, `ClaudeSDKClient`, custom tools with `@tool`, and hooks.

## 4. claude-agent-sdk-demos (~2.8k stars)
https://github.com/anthropics/claude-agent-sdk-demos
- Working agents to read: email-agent, research-agent, excel-demo, resume-generator.

## 5. skills (~197k stars)
https://github.com/anthropics/skills ("Public repository for Agent Skills")
- `skills/` has docx, pdf, pptx and xlsx skills; `spec/` and `template/` show how to write your own.

## 6. prompt-eng-interactive-tutorial (~39.5k stars)
https://github.com/anthropics/prompt-eng-interactive-tutorial
- 9 chapters (e.g. Ch. 6 "Precognition", Ch. 8 "Avoiding Hallucinations"); the appendix covers prompt chaining and tool use.

## The theory behind it
Anthropic's engineering post "Building effective agents" (Dec 19, 2024) explains prompt chaining, routing, parallelization, orchestrator-workers and evaluator-optimizer. The cookbooks' `patterns/agents` folder is the code for it.
https://www.anthropic.com/engineering/building-effective-agents

## Skip
`anthropics/courses` has been archived (read-only) since Sep 15, 2026.

## A 1-week plan
1. Day 1: prompt tutorial, chapters 1 to 5.
2. Day 2: read "Building effective agents".
3. Days 3 and 4: run the `patterns/agents` notebooks.
4. Days 5 to 7: fork a quickstart or an SDK demo and make it do one job for you.

## Sources (checked 2026-11-19)
- https://github.com/anthropics (each repo page above)
- https://code.claude.com/docs/en/agent-sdk/overview
- https://www.anthropic.com/engineering/building-effective-agents

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
