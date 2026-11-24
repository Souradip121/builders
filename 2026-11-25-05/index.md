---
title: "neonclipping: the free, local clipping engine (setup guide)"
---

# neonclipping: the free, local clipping engine

**Repo:** https://github.com/iamajmeena/neonclipping (2.4k stars, 153 forks on 2026-11-24)
"Paste a link, get captioned 9:16 clips in ~2 min. Free, local, open-source clipping engine."

## Licence
The LICENSE file is now **AGPL-3.0** (changed 24 Nov 2026). Versions released before that stay under MIT.

## What it does
- **Fast mode** (audio-first + YouTube captions) and **Deep mode** (adds optical-flow motion analysis)
- 1080×1920 export with burned-in captions in 52 languages
- 11 gaming layouts with facecam detection
- Live clipping from Twitch and YouTube Live, a creator watch mode, clip editing and a transcript explorer
- Optional publishing to YouTube, Instagram and TikTok

## Requirements
- Python 3.10–3.13 and FFmpeg on your PATH
- Optional but recommended: [Ollama](https://ollama.com) with `ollama pull llama3.2:3b` (without it, clips are picked from audio and motion scores only)
- Optional GPU: NVIDIA (NVENC / faster-whisper) speeds things up; Mac and Linux use VideoToolbox or x264
- Optional cloud AI key

## Setup
1. Windows: run `NeonClipping-Setup.bat`. Mac/Linux: run `install.sh` (README: not yet tested on a real Mac). Or clone the repo and use `run.ps1` / `run.sh`.
2. Open http://127.0.0.1:8770
3. Paste a video link and press **Make clips**.

## Speed (the author's numbers)
One machine (RTX 2060), Fast mode, 3 clips: an 85-min YouTube video took 97 s, a 3-hour Twitch VOD 136 s, a 90-second trailer 21 s. Yours will differ.

## vs OpusClip
OpusClip lists Free $0, Starter $15/mo, Pro $29/mo and Business (custom). The free plan adds a watermark and files expire after 3 days. https://www.opus.pro/pricing

## Caveats from the README
Highlight picking is heuristic, so review clips before posting. YouTube may show a bot check.

## Sources (checked 2026-11-24)
- https://github.com/iamajmeena/neonclipping
- https://www.opus.pro/pricing

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
