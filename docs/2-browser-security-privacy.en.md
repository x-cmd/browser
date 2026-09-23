---
x-title: Browser Security & Privacy — Tracker Protection, Fingerprinting, and Sandboxing
x-desc: >-
  An angle article on browser security and privacy — tracking
  protection (3P cookies, fingerprinting, supercookies), per-engine
  default behavior (Firefox ETP, Safari ITP, Brave Shields, Chrome
  Privacy Sandbox), sandboxing models (Chromium multi-process,
  Firefox site isolation), and emerging threats (AI-driven phishing).
x-sidebar: Browser security
x-keywords: browser security, tracker protection, fingerprinting, itp, etp, brave shields, privacy sandbox, sandboxing
x-json-ld:
  '@context': https://schema.org
  '@graph':
    - '@type': TechArticle
      headline: 'Browser security and privacy'
      inLanguage: 'en'
      about: 'browser security and privacy analysis'
---

# Browser Security & Privacy — Tracker Protection, Fingerprinting, and Sandboxing

Every modern browser takes a position on privacy. The
positions are similar in spirit (less tracking is better) but
differ in detail — what counts as a "tracker", whether 3P
cookies are blocked by default, how aggressively fingerprint
defenses are applied, and how much the engine relies on a
sandbox.

This page is an angle article — security / privacy analysis,
not a per-tool tutorial. Install / config live at
[x-cmd.com/install/<browser>](https://x-cmd.com/install/).

> **TL;DR.** All modern browsers block cross-site tracking
> by default in 2026. The differences are in **how
> aggressive** — Firefox's Total Cookie Protection is the
> strictest; Brave's Shields adds a built-in VPN + firewall;
> Chrome's Privacy Sandbox is the slowest to fully replace
> 3P cookies. On sandboxing: Chromium has multi-process
> site isolation since 2018; Firefox matched with Fission
> (default since 2024); Safari uses WebKit's sandbox.

## Tracker protection — what's blocked

A 2026 audit:

| Engine | Browser | 3P cookies | Fingerprinting | Supercookies | Network tracking |
| --- | --- | --- | --- | --- | --- |
| **Gecko** | **Firefox** | Blocked (ETP) | Blocked (strict) | Blocked (resistFingerprinting) | DoH + ECH |
| **Gecko (Tor)** | **Tor Browser** | Blocked | Blocked (uniform) | Blocked | Tor network |
| **Gecko (fork)** | **LibreWolf** | Blocked | Blocked | Blocked | DoH |
| **WebKit** | **Safari** | Blocked (ITP) | Blocked | Blocked | iCloud Private Relay (optional) |
| **Blink** | **Chrome** | Phasing out (Privacy Sandbox) | Limited | Limited | IP Protection (US rollout) |
| **Blink** | **Edge** | Phasing out (Tracking Prevention) | Limited | Limited | SmartScreen + DoH |
| **Blink** | **Brave** | Blocked (Shields default) | Blocked (randomization) | Blocked | Built-in VPN + Firewall |
| **Blink** | **Arc** | Limited | Limited | Limited | Standard |
| **Blink** | **Vivaldi** | Blocked (optional) | Limited | Limited | DoH |
| **Blink** | **Opera** | Blocked (optional) | Limited | Limited | Built-in VPN |
| **Servo (niche)** | **Falkon / Ladybird (in dev)** | Limited | Limited | Limited | — |

### What each engine protects against

**Gecko (Firefox / Tor Browser / LibreWolf):**

- **Enhanced Tracking Protection (ETP)** — blocks trackers,
  fingerprinters, cryptominers. Three levels: Standard,
  Strict, Custom.
- **Total Cookie Protection** — cookies partitioned per
  first-party domain. Cookie set on Site A by Tracker X
  can't be read on Site B even if both embed Tracker X.
- **Resist Fingerprinting** — uniform User-Agent, time
  zone, canvas; harder to fingerprint.
- **DoH + ECH** — encrypted DNS.

**WebKit (Safari):**

- **Intelligent Tracking Prevention (ITP)** — ML-driven
  cross-site tracker blocking.
- **Fingerprint protection** — browser fingerprint
  blocking.
- **iCloud Private Relay** (iCloud+ subscribers) — hides
  IP from trackers.

**Blink (Chrome / Edge / Brave / Arc / Vivaldi / Opera):**

- **Privacy Sandbox** — Topics API + FLEDGE + Attribution
  API (Chrome); phasing out 3P cookies through 2024-2026.
- **Shields (Brave only)** — block trackers, fingerprint
  randomization, cookie blocking, HTTPS upgrades.
- **Built-in VPN / Firewall (Brave, Opera)** — VPN on
  demand.

### How strict is "strict"?

A rough ordering (most → least strict, 2026):

1. **Tor Browser** — uniform, no JS by default, Tor
   network. (Most strict.)
2. **LibreWolf** — strict ETP, telemetry-free.
3. **Firefox (Strict)** — strict ETP.
4. **Brave (Aggressive)** — Shields default aggressive.
5. **Safari** — ITP default.
6. **Firefox (Standard)** — moderate.
7. **Vivaldi / Opera** — opt-in blocking.
8. **Arc** — minimal blocking.
9. **Chrome** — Privacy Sandbox (incomplete).
10. **Edge** — Tracking Prevention at default level.

(Least strict.)

## Sandbox and site isolation

A browser's **sandbox** is what protects the OS from a
compromised renderer process. Three approaches in 2026:

### Chromium multi-process (Chrome / Edge / Brave / Arc / Vivaldi / Opera)

Chromium has a **multi-process architecture** with separate
processes for browser, renderers, GPU, network, extensions,
and utility. **Site isolation** (each origin in its own
process) has been default since Chrome 67 (2018).

- Pros: Defends against Spectre-style attacks; one
  compromised site can't read another site's cookies or
  storage.
- Cons: Higher memory use (~50-200 MB more than
  Firefox for the same tab count).

### Firefox site isolation (Project Fission)

Firefox introduced Project Fission in 2020; **default for
all users since 2024**. Each origin in its own process.

- Pros: Matches Chromium's defense in depth.
- Cons: Slightly higher memory use than pre-Fission
  Firefox.

### WebKit sandbox (Safari)

WebKit sandboxing is OS-level: on macOS, sandboxed processes
via Sandbox; on iOS, even stricter.

- Pros: Mature, low memory.
- Cons: Different sandbox model per platform.

## Phishing protection

Every modern browser has a phishing/malware protection
system. Most use Google's Safe Browsing API or a similar
service:

| Engine | Browser | Service | URL check | Download check |
| --- | --- | --- | --- | --- |
| **Blink** | Chrome | Google Safe Browsing (Enhanced) | ✅ | ✅ |
| **Blink** | Edge | Microsoft Defender SmartScreen | ✅ | ✅ |
| **Blink** | Brave | Google Safe Browsing + Local lists | ✅ | ✅ |
| **Blink** | Arc | Google Safe Browsing | ✅ | ✅ |
| **Gecko** | Firefox | Google Safe Browsing | ✅ | ✅ |
| **WebKit** | Safari | Tencent + Apple proxy (China), Google Safe Browsing (elsewhere) | ✅ | ✅ |

Note: **Google Safe Browsing is the dominant backend** —
even non-Chromium browsers (Firefox) use it. Privacy-
conscious browsers (Brave) also use it but try to limit
data sent.

## AI-driven phishing — the 2026 threat

A new class of phishing attack: **AI-generated phishing
pages**. An attacker uses an LLM to clone a bank's login
page in real time, with personalized content (target's name,
account number from a leaked dataset). The page is hosted
on a domain that's only been registered for hours.

Defense:

- **Phishing detection** — heuristic ML in the browser
  (Chrome's Enhanced Safe Browsing; Edge's SmartScreen).
- **Passkeys / WebAuthn** — phishing-resistant login;
  doesn't transmit credentials to the (fake) server.
- **Tracked block lists** — Google's Safe Browsing updates
  within minutes.

No browser yet ships a fully AI-resistant phishing defense
— that's an open research area.

## What about "private browsing" / Incognito?

Private browsing modes (Chrome Incognito, Firefox Private
Window, Safari Private Window, Brave Private Window with
Tor) **block local tracking**:

- Don't save history / cookies / cache after the window
  closes.
- Don't share cookies with the regular session.

But **do not** make you anonymous to the websites you
visit, your employer, or your ISP. For real anonymity, use
**Tor Browser**.

## Practical recommendations

1. **Default browser for most users:** Firefox (Strong
   privacy defaults, broad extension ecosystem).
2. **Maximum privacy:** Tor Browser or Brave with Shields
   at Aggressive.
3. **Avoid the weakest defaults:** Arc, Opera (no
   tracking protection by default in 2026), Edge
   (SmartScreen is good, but less privacy than Brave).
4. **Use Passkeys / WebAuthn** where supported — phishing-
   resistant.
5. **Enable DNS over HTTPS (DoH)** in any browser that
   supports it.
6. **Enable Encrypted Client Hello (ECH)** for SNI
   privacy.

## What's next?

- **3-browser-engine-diversity** — why the monoculture
  matters.
- **4-browser-ai-overview** — how AI features change
  the privacy story.

## Related

- [Firefox ETP](https://support.mozilla.org/en-US/kb/enhanced-tracking-protection-firefox)
- [Safari ITP](https://webkit.org/tracking-prevention/)
- [Brave Shields](https://www.brave.com/shields)
- [Chrome Privacy Sandbox](https://privacysandbox.com/)
- [Tor Browser](https://www.torproject.org/)

> For per-tool install / config: `x-cmd.com/install/
> <browser>` or `x-cmd.com/doc-2026/install/<browser>`. This
> page is angle / analysis only.