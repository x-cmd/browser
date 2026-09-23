---
x-title: Browser AI Overview — Gemini Nano, Copilot, Apple Intelligence, Leo, DuckAssist
x-desc: >-
  An angle article on browser AI features in 2026 — Gemini Nano
  (Chrome), Microsoft Copilot (Edge), Apple Intelligence (Safari),
  Brave Leo, DuckDuckGo DuckAssist, Arc AI Boosts, and the privacy
  implications of local vs cloud inference.
x-sidebar: Browser AI overview
x-keywords: browser ai, gemini nano, copilot, apple intelligence, brave leo, duckassist, local llm, on-device
x-json-ld:
  '@context': https://schema.org
  '@graph':
    - '@type': TechArticle
      headline: 'Browser AI overview'
      inLanguage: 'en'
      about: 'browser AI feature comparison'
---

# Browser AI Overview — Gemini Nano, Copilot, Apple Intelligence, Leo, DuckAssist

Every major browser shipped some form of AI integration by
2025. By 2026, AI features are **table stakes** — the
question isn't "does this browser have AI?" but **"which AI,
where does it run, and what does it see?"**

This page is an angle article — AI feature comparison, not
a per-tool tutorial. Install / config live at
[x-cmd.com/install/<browser>](https://x-cmd.com/install/).

> **TL;DR.** Browser AI falls into two buckets: **cloud
> inference** (Copilot, Gemini Pro, Safari Apple
> Intelligence cloud) and **local / on-device** (Gemini
> Nano on Chrome for Pro, Brave Leo local mode, Apple
> Intelligence on-device, DuckAssist on-device). Local is
> more private but limited in capability; cloud is more
> capable but sees your inputs. Choose by threat model.

## The two inference models

### Cloud inference (most browsers)

The browser sends your prompt to a cloud LLM (OpenAI,
Anthropic, Google's Gemini Pro, etc.). The cloud runs the
inference and sends the response back.

Pros:

- Most capable (frontier models).
- Fast on big queries.
- No hardware constraints.

Cons:

- The cloud sees your prompt (search queries, page
  contents, AI Chat messages).
- Cloud-side logging may persist.
- Latency: network round-trip.
- Bandwidth / data costs to the provider.

### Local / on-device inference

The browser runs a small LLM on your device (CPU, GPU, or
NPU). No data leaves the device.

Pros:

- Privacy — data stays local.
- Latency — no network.
- Works offline.

Cons:

- Limited capability (smaller models).
- Battery / thermal impact.
- Requires modern hardware (Apple silicon M1+, recent
  Intel / AMD CPUs with NPUs).

## Per-browser AI features (2026)

### Chrome — Gemini Nano (on-device) + Gemini Pro (cloud)

- **Gemini Nano** — on-device LLM, available to **Pro
  subscribers** on machines that meet hardware requirements.
  Used for translate, summarize, draft.
- **Gemini Pro** — cloud inference. Powers Chrome's
  AI-augmented search results and AI Overview summaries.
- **AI Overview** — AI-generated summary at top of search
  results. Backed by Gemini Pro.

Privacy: cloud inference by default; Nano is opt-in for Pro.

### Edge — Microsoft Copilot (cloud)

- **Copilot** — Microsoft 365 Copilot, deeply integrated
  with Edge. Translate, summarize, draft, browse, code.
- **Bing Chat** (now Copilot) — chat interface.
- **Bing Image Creator** — DALL-E integration.

Privacy: cloud inference; data sent to Microsoft. Enterprise
tier has private-mode options.

### Safari — Apple Intelligence (on-device + cloud)

- **Writing Tools** — proofread, rewrite, summarize. All
  on-device.
- **Image Playground** — image generation (cloud for the
  higher-quality models).
- **Siri integration** — cross-app context.
- **Reader translate** — on-device translation via
  Bergamot.

Privacy: **on-device by default** for most features.
Apple silicon M1+ required for full features. Cloud
inference is opt-in and privacy-preserving (Apple claims no
data retention).

### Brave — Leo (cloud + local option)

- **Leo** — built-in AI assistant. Multiple model options:
  - Cloud: Claude / Llama / others (paid tier).
  - **Local** — runs models locally (Llama, Mistral).
- **Privacy focus** — Leo claims not to use conversations
  for model training.

Privacy: local mode available on supported hardware.

### DuckDuckGo — DuckAssist + AI Chat (cloud)

- **DuckAssist** — AI Overview equivalent. Cites sources.
- **AI Chat** — chat interface backed by OpenAI / Anthropic
  / Mistral. **Privacy claims**: not used for model training;
  DDG proxies and strips identifying headers.

Privacy: cloud inference; DDG proxies for privacy. Not as
private as local.

### Arc — Boosts + Easels + AI Search (cloud)

- **Boosts** — user-defined AI prompts that apply to every
  page (e.g. "summarize in 3 bullet points", "translate to
  Spanish").
- **Easels** — collaborative whiteboards with AI.
- **AI Search** — Perplexity integration.

Privacy: cloud inference.

### Vivaldi — minimal AI

- Vivaldi's stance: AI should be a **user choice**, not a
  browser default.
- Optional integration with chatbots; no built-in AI.

Privacy: user-controlled.

## Local inference — what's possible in 2026?

Three device classes support local LLM inference:

### Apple silicon (M1+)

- **Unified memory** between CPU / GPU / NPU makes local
  LLMs efficient.
- Apple Intelligence is on-device by default for most
  features.
- 7B models (Llama, Mistral) run smoothly on M1 Pro / Max.

### Modern Intel / AMD with NPUs

- Snapdragon X / Intel Core Ultra / AMD Ryzen AI — NPUs
  accelerate local inference.
- Windows Copilot+ PCs ship with NPUs for on-device AI.
- Performance varies; not all NPUs are equal.

### Older hardware

- No NPU.
- Local LLMs run on CPU / GPU; 7B models are slow
  (>10s / token).
- Cloud is the practical choice.

## Privacy comparison matrix

| Browser | Default | Local option | Cloud | Data retention |
| --- | --- | --- | --- | --- |
| **Chrome** | Cloud (Gemini Pro) | Nano (Pro only) | Yes | Google's privacy policy |
| **Edge** | Cloud (Copilot) | ❌ | Yes | Microsoft's privacy policy |
| **Safari** | Local (Apple Intelligence) | Yes (default) | Optional | Apple's privacy policy |
| **Brave** | Local (Leo) | Yes (default) | Paid tier | Leo claims no training |
| **DuckDuckGo** | Cloud (DuckAssist + AI Chat) | ❌ | Yes (proxied) | DDG privacy policy |
| **Arc** | Cloud (Boosts + Easels) | ❌ | Yes | Arc privacy policy |
| **Vivaldi** | None (user opt-in) | Optional | User opt-in | Per-provider |

## The threat-model question

Choose AI features by threat model:

- **Maximum privacy** — Apple Intelligence (Safari on
  Apple silicon) or Brave Leo local. No data leaves device.
- **Balance privacy / capability** — DuckDuckGo (proxied
  cloud) or Brave Leo cloud.
- **Maximum capability** — Chrome with Pro subscription
  (Gemini Nano + Pro) or Edge Copilot.
- **No AI** — Vivaldi (user opt-in).

## AI Overview — the citation question

All major browsers ship an "AI Overview" feature at the top
of search results. The question is: **how do you get
cited?**

What works:

- **Long-form first-hand content.** AI Overview cites
  primary sources.
- **Original data / research.** Unique data points get
  cited.
- **Clear expertise signals.** Author bio, credentials,
  citations.
- **Structured data.** Schema.org helps the LLM parse.

What doesn't:

- **SEO-optimized fluff.** AI Overviews skip fluff.
- **Unverified claims.** LLMs prefer sources with
  citations.
- **Outdated content.** Freshness matters.

## What's next?

Topic-library articles in `0-latest-browsers` /
`1-browser-overview` for cross-references. Per-tool install
at `x-cmd.com/install/<browser>`.

## Related

- [Chrome AI features](https://developer.chrome.com/docs/ai)
- [Apple Intelligence](https://www.apple.com/apple-intelligence/)
- [Brave Leo](https://brave.com/leo/)
- [DuckDuckGo DuckAssist](https://duckduckgo.com/?q=DuckAssist)
- [Microsoft Copilot](https://copilot.microsoft.com/)

> For per-tool install / config: `x-cmd.com/install/
> <browser>` or `x-cmd.com/doc-2026/install/<browser>`. This
> page is angle / analysis only.