---
title: "AI agents roadmap: the folder tree + free resources"
---

# AI agents roadmap: the folder tree + free resources

An agent is an LLM that calls tools in a loop until the task is done. Build one folder a week.

```
ai-agents/
├── 01-foundations/   Python or TypeScript, async, HTTP APIs + JSON, Git
├── 02-llm-basics/    tokens, context window, system prompts, structured outputs, streaming
├── 03-tools/         tool calling, MCP, retries/timeouts, human approval
├── 04-memory/        embeddings, pgvector, chunking + retrieval (RAG)
├── 05-patterns/      chaining, routing, parallelization, orchestrator-workers, evaluator-optimizer
└── 06-ship/          an agent SDK + tracing and evals
```

## 01-foundations
Pick one language and stay with it. Build a small CLI that calls a public API and prints JSON. That's 80% of what agent "tools" are.

## 02-llm-basics
Read your model provider's docs on prompts and structured outputs, then make the CLI return typed JSON every time.
- Anthropic's interactive prompt tutorial (9 chapters): https://github.com/anthropics/prompt-eng-interactive-tutorial

## 03-tools
- **Model Context Protocol (MCP)**: "an open-source standard for connecting AI applications to external systems". https://modelcontextprotocol.io
- Add a confirmation step before any tool that sends, pays or deletes.

## 04-memory
- **pgvector**: open-source vector similarity search for Postgres. https://github.com/pgvector/pgvector
- Start with plain retrieval over your own docs before adding "long-term memory".

## 05-patterns
Anthropic's engineering post "Building effective agents" (Dec 19, 2024) names the patterns: prompt chaining, routing, parallelization, orchestrator-workers, evaluator-optimizer, and autonomous agents.
- Post: https://www.anthropic.com/engineering/building-effective-agents
- Runnable notebooks: `patterns/agents` in https://github.com/anthropics/claude-cookbooks

## 06-ship: pick one SDK
| SDK | What its own page says | Link |
|---|---|---|
| Claude Agent SDK | "Build production AI agents with Claude Code as a library" (renamed from Claude Code SDK) | https://code.claude.com/docs/en/agent-sdk/overview |
| OpenAI Agents SDK | "a lightweight yet powerful framework for building multi-agent workflows" | https://github.com/openai/openai-agents-python |
| LangGraph | "Low-level orchestration framework for building stateful agents" | https://github.com/langchain-ai/langgraph |
| AI SDK (by Vercel) | "The AI Toolkit for TypeScript" | https://github.com/vercel/ai |
| Pydantic AI | "a typed, extensible agent loop" | https://github.com/pydantic/pydantic-ai |
| CrewAI | "orchestrating role-playing, autonomous AI agents" | https://github.com/crewAIInc/crewAI |

Tracing and evals: **Langfuse** is open source (MIT except `ee` folders) and can be self-hosted. https://github.com/langfuse/langfuse

## Your capstone
An agent that reads your GitHub issues through an MCP server, drafts a fix plan, and asks you before it touches anything.

## Sources (checked 2026-11-19)
- https://modelcontextprotocol.io
- https://code.claude.com/docs/en/agent-sdk/overview
- https://github.com/openai/openai-agents-python · https://github.com/langchain-ai/langgraph · https://github.com/vercel/ai
- https://github.com/pgvector/pgvector · https://github.com/langfuse/langfuse · https://github.com/pydantic/pydantic-ai · https://github.com/crewAIInc/crewAI
- https://www.anthropic.com/engineering/building-effective-agents · https://github.com/anthropics/claude-cookbooks

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
