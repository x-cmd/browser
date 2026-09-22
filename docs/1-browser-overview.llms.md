---
name: 1-browser-overview
description: Horizontal comparison of web browsers in 2026 across engine (Gecko/WebKit/Blink), platforms, extension API, privacy defaults, AI integration, and best-for. Covers 12 browsers including Firefox, Chrome, Safari, Brave, Arc, Edge, Vivaldi, Opera, Zen, Tor Browser, LibreWolf, DuckDuckGo.
type: summary
---

# Core Content

core_features:
  - Side-by-side comparison of 12 widely-used web browsers
  - Dimensions: engine, platforms, extension API, privacy, AI integration, best-for
  - Decision tree for picking the right browser
  - Per-platform notes (Windows, macOS, Linux, iOS, Android, BSD)
  - Disambiguation: what is and isn't a web browser

# Key Information

highlights:
  - Three engines: Gecko (Firefox family), WebKit (Safari + all iOS browsers), Blink (Chromium family, ~76% share)
  - Manifest V3 has landed in all major browsers (Firefox 138 finally, Aug 2026)
  - AI integration is table stakes: Chrome Gemini Nano, Firefox Tab Groups, Safari Apple Intelligence, Edge Copilot, Brave Leo
  - Firefox is the only major independent-engine browser; everything else is Chromium or WebKit
  - iOS policy: every browser uses WebKit (Safari is the only one with full Apple WebKit APIs)

# Use Cases

use_cases:
  - Picking a browser for a new machine
  - Comparing two browsers side-by-side
  - Understanding the engine / extension / privacy trade-offs
  - Knowing what's Linux-native vs iOS-restricted vs cross-platform

# Related Resources

official:
  repo: https://github.com/x-cmd/browser
related:
  - name: 0-latest-browsers
    url: https://github.com/x-cmd/browser/blob/main/docs/0-latest-browsers.en.md
  - name: 2-firefox
    url: https://github.com/x-cmd/browser/blob/main/docs/2-firefox.en.md

# Summary

A practical comparison of the web browsers people actually pick in 2026. The headline: three engines (Gecko, WebKit, Blink) with Chromium's Blink holding ~76% desktop share; AI integration is now table stakes across all major browsers; Firefox is the only major independent-engine option. The decision tree picks Firefox for privacy + independence, Chrome for ecosystem + compatibility, Safari for Apple users, Edge for Microsoft environments, Brave for ad blocking + Web3, Arc for power users, Tor Browser for anonymity. iOS is WebKit-only by Apple policy; Linux supports Firefox and Chromium-based browsers fully.