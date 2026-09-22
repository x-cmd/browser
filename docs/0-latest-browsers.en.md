---
x-title: Latest Web Browsers — What's New in 2026
x-desc: >-
  Recent releases, trends, and breaking changes in web browsers —
  Firefox 138, Chrome 138, Safari 19, Brave 1.80, Arc 2.0, Zen 1.14,
  and the AI integration wave.
x-sidebar: Latest browsers
x-keywords: browser, firefox, chrome, safari, brave, arc, zen, 2026
x-json-ld:
  '@context': https://schema.org
  '@graph':
    - '@type': TechArticle
      headline: 'Latest web browsers — 2026'
      inLanguage: 'en'
      about: 'web browser news and releases'
---

# Latest Web Browsers — What's New in 2026

A snapshot of what shipped, what changed, and where the
web-browser space is heading in 2026. Updated quarterly.

## Recent releases

| Date | Browser | Version | Headline change |
| --- | --- | --- | --- |
| 2026-08 | **Firefox** | 138 | Manifest V3 extension support lands; AI-powered Tab Groups; speculative rules for CSS. |
| 2026-07 | **Chrome** | 138 | GPU-based compositing for all tabs; on-page LLM assistant (Gemini Nano) for Pro users. |
| 2026-06 | **Safari** | 19 | WebGPU enabled by default; redesigned reader view; declarative shadow DOM standardized. |
| 2026-05 | **Brave** | 1.80 | AI assistant "Leo" gets a local model option; Web3 search via Brave Search. |
| 2026-04 | **Arc** | 2.0 | First stable Windows release; cross-device sync; AI "Boosts" mature. |
| 2026-03 | **Zen** | 1.14 | Firefox-based; first major stable after several months of pre-release. |
| 2026-02 | **Vivaldi** | 7.5 | Tab tiling improvements; built-in Mastodon client refresh. |

## Trends

### AI integration is now table stakes

Every major browser ships an AI assistant of some kind:

- **Chrome** — Gemini Nano (on-page LLM, Pro users).
- **Firefox** — Tab Groups (AI-assisted) + optional AI add-ons.
- **Safari** — Apple's on-device Intelligence integrates with
  Safari's reader / writing tools.
- **Edge** — Copilot deeply integrated.
- **Brave** — Leo, with a local model option.
- **Arc** — Boosts, Easels, and AI search.

The shift in 2026 is **local / on-device** where possible. Brave
and Arc both ship local-model options; Chrome's Gemini Nano runs
on-device for Pro users.

### The Chromium monoculture

The 2026 numbers haven't shifted much from 2024:

- **Chromium-based** (Chrome, Edge, Brave, Arc, Opera, Vivaldi):
  ~76% desktop share (per StatCounter Q2 2026).
- **Safari (WebKit)** ~17%.
- **Firefox (Gecko)** ~6%.
- **Other** (Servo-based, niche) ~1%.

The trend is flat — Firefox's decline has stabilized since 2024
on the back of the Manifest V3 transition and renewed focus on
privacy. The WebKit share is roughly constant. Chromium remains
the de facto standard.

### Manifest V3 everywhere

Chrome shipped Manifest V3 stable in Chrome 100+; the practical
rollout happened through 2024–2025. **Firefox 138 (Aug 2026)
finally lands Manifest V3 in stable**. Most extension developers
now write Manifest V3 code first, with V2 polyfills only for
legacy needs.

### Privacy features continue to diverge

- **Firefox** — Enhanced Tracking Protection on by default;
  Total Cookie Protection; container tabs.
- **Safari** — Intelligent Tracking Prevention; fingerprint
  protection.
- **Brave** — Shields by default; built-in VPN + Firewall.
- **Chrome** — Privacy Sandbox replacing third-party cookies
  (Phasing out 2024-2026).

### WebGPU everywhere

WebGPU (the next-generation GPU API for the web) hit stable in
**all major browsers** in 2025–2026. Chrome 113+, Firefox
141+ (planned), Safari 19+. WebGPU is now the recommended path
for in-browser compute-intensive workloads (LLM inference, 3D,
video processing).

## Breaking changes worth knowing

- **Firefox 138** ships Manifest V3; some legacy V2-only
  extensions stop working or need V3 polyfills.
- **Chrome 138** drops support for older Linux distros (glibc
  2.28+ required); check your distro.
- **Safari 19** drops support for macOS 12 Monterey; macOS 13
  Ventura is the minimum.
- **Edge** moved to a quarterly major cycle (was yearly);
  expect more frequent changes.

## What to watch

- **Firefox 141** (Sep 2026) — WebGPU enabled by default for
  all users; the last of the major engines.
- **Chrome 140+** — incremental rollout of the Privacy
  Sandbox's "Topics" API; replacement for third-party cookies
  continues.
- **Servo** — Rust-based browser engine funded by Linux
  Foundation Europe. Not consumer-ready but interesting for
  embedded / IoT.
- **Arc's "Dia"** — Arc's makers (The Browser Company) are
  reportedly working on a separate browser focused on AI-first
  browsing. No public timeline yet.

## Related

- [`docs/1-browser-overview.en.md`](./1-browser-overview.en.md) — overview and comparison table.
- [`docs/2-firefox.en.md`](./2-firefox.en.md) — Firefox deep dive.