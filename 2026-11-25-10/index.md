---
title: "Learn local AI in 4 weeks: the roadmap"
---

# Learn local AI in 4 weeks: the roadmap

Run open models on your own machine: private, offline, no per-token bill.

```
local-ai/
├── week-1-hardware/     RAM/VRAM, GGUF, quantization
├── week-2-run-one/      Ollama, LM Studio, llama.cpp
├── week-3-pick-models/  Qwen3.5, Gemma 4, Llama 3.2
├── week-4-build/        OpenAI-compatible API, embeddings, local RAG
└── bonus-fine-tune/     Unsloth
```

## Week 1: hardware
- GGUF is the file format used by llama.cpp, LM Studio and Ollama. Q4_K ≈ 4.5 bits per weight, Q5_K ≈ 5.5, Q6_K ≈ 6.56. https://huggingface.co/docs/hub/gguf
- LM Studio recommends 16 GB+ RAM; 8 GB Macs can work with smaller models and modest context. Windows GPU use: 4 GB+ VRAM. https://lmstudio.ai/docs/app/system-requirements
- A general guideline (not an official rule): ~8 GB RAM for small 3–4B models at Q4, ~16 GB for 7–9B.

## Week 2: run one
- **Ollama** (MIT; macOS, Windows, Linux, Docker): `ollama run qwen3.5:4b`. https://github.com/ollama/ollama
- **LM Studio**: desktop GUI, free for use at work since July 2025 (Apple Silicon Macs, Windows, Linux). https://lmstudio.ai
- **llama.cpp** (MIT): the C/C++ engine, with an OpenAI-compatible server. https://github.com/ggml-org/llama.cpp

## Week 3: pick models (Ollama library)
- qwen3.5: 0.8b, 2b, 4b, 9b, 27b, 35b, 122b — https://ollama.com/library/qwen3.5
- gemma4: e2b, e4b, 12b, 26b, 31b — https://ollama.com/library/gemma4
- llama3.2: 1b, 3b — small and fast on laptops
Test 3 models on the same 10 prompts from your own work and keep the smallest one that passes.

## Week 4: build
- Ollama's OpenAI-compatible API: base URL `http://localhost:11434/v1/` (chat completions, embeddings). Any API key string works; it's ignored. https://docs.ollama.com/api/openai-compatibility
- Embeddings: `ollama pull nomic-embed-text` (274 MB). https://ollama.com/library/nomic-embed-text
- Project: a RAG over your own notes that answers with Wi-Fi off.

## Bonus: fine-tune
**Unsloth** claims "2× faster with 70% less VRAM", with free Colab notebooks (Gemma 4 E2B, Qwen3.5 4B, Llama 3.1 8B and more). Core is Apache 2.0. https://github.com/unslothai/unsloth

## Going bigger
This week's widely shared beginner guide (gpupartner.com, HN) targets desktop GPUs: e.g. Qwen3.8-27B on a 32 GB card, and Thinking Machines Lab's new open-weight Inkling 2 Mini (released 20 Nov 2026, ~20 GB; Ollama support on Macs with 32 GB+). https://thinkingmachines.ai/news/inkling-2-mini/

## Sources (checked 2026-11-24)
All links above.

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
