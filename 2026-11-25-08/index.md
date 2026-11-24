---
title: "GPT-6.2 Astra and Sol: the builder's cheat sheet"
---

# GPT-6.2 Astra and Sol: the builder's cheat sheet

Announced by OpenAI on 17 Nov 2026 ("Introducing GPT-6.2 Astra and Sol").

## The two models
- **GPT-6.2 Astra** — OpenAI's "new frontier model for your hardest projects".
- **GPT-6.2 Sol** — the efficient everyday model, an upgrade over GPT-6.1 Sol.

## API pricing (per 1M tokens)
| Model | Input | Cached input | Output |
|---|---|---|---|
| gpt-6.2-astra | $8 | $0.40 | $40 |
| gpt-6.2-sol | $2 | $0.10 | $10 |
| Astra, prompts over 272K input tokens | $16 | $0.80 | $60 |
| Sol, prompts over 272K input tokens | $4 | $0.20 | $15 |

## Context (Astra, from the model docs)
1,050,000-token context window, 922,000 max input, 128,000 max output tokens, knowledge cutoff 18 May 2026.

## Availability
- ChatGPT: Plus, Pro, Enterprise and Edu, in ChatGPT Work and Codex.
- Ultrafast mode: Pro 500 (both models), Pro 200 (Sol only), Enterprise/Edu when an admin enables it.
- API model ids: `gpt-6.2-astra`, `gpt-6.2-sol`.

## OpenAI's benchmark claims (their numbers)
- Agents' Last Exam: Astra +5.2 points over GPT-6 Astra at under a third of the cost.
- Terminal-Bench-Science 0.1: Astra +9 points over GPT-6 Astra.
- GDPval v2 (internal): Astra +6.2 points with 22% fewer output tokens; Sol +5.3 over GPT-6.1 Sol.
- FrontierCode 2.0: Sol within 0.5 points of Astra at about one-fifth the cost.

## For developers
- Both models are in Codex; OpenAI says Astra is better at complex changes in existing codebases.
- Keep prompt prefixes unchanged so prompt caching applies (cached input is 20× cheaper).
- A simple routing rule: Sol by default, Astra for the hard 10% (large refactors, long multi-step agent runs). Re-check costs on your own traffic.

## Sources (checked 2026-11-24)
- https://openai.com/index/introducing-gpt-6-2-astra-sol/
- https://developers.openai.com/api/docs/pricing
- https://developers.openai.com/api/docs/models/gpt-6.2-astra

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
