---
name: 2-firefox
description: Modern, independent web browser built by Mozilla. Gecko layout engine, MPL-2.0, strong privacy defaults. Cross-platform: Windows, macOS, Linux, BSD, Android, iOS. Quantum and Project Fission define the modern Firefox architecture.
type: summary
---

# Core Content

core_features:
  - Independent Gecko layout engine (last major non-Blink, non-WebKit)
  - Strong privacy defaults: Enhanced Tracking Protection, Total Cookie Protection
  - Cross-platform: Windows, macOS, Linux, BSD, Android, iOS (iOS uses WebKit due to Apple policy)
  - WebExtensions API with both MV2 and MV3 (MV3 stable since Firefox 138)
  - Container tabs (Multi-Account Containers add-on) — unique to Firefox
  - MPL-2.0 licensed

# Key Information

highlights:
  - Only major independent-engine browser (Gecko)
  - Quantum project (2017) brought multi-process + parallel CSS + GPU compositing
  - Project Fission (2024 default) — per-origin site isolation
  - Stylo CSS engine written in Rust
  - Manifest V3 stable since Firefox 138 (Aug 2026)
  - On iOS, Firefox uses WebKit due to Apple policy

# Use Cases

use_cases:
  - Privacy-conscious browsing with strong defaults
  - Multi-account workflows (container tabs per identity)
  - Cross-platform sync via Mozilla account
  - Supporting engine diversity (independent web)
  - Developer workflows with built-in dev tools + container tabs

# Related Resources

official:
  website: https://www.mozilla.org/firefox/
  source: https://hg.mozilla.org/mozilla-central/
related:
  - name: Chrome
    url: https://www.google.com/chrome/
  - name: Safari
    url: https://www.apple.com/safari/
  - name: Brave
    url: https://brave.com/
  - name: LibreWolf
    url: https://librewolf.net/
  - name: Tor Browser
    url: https://www.torproject.org/

# Summary

Firefox is the canonical independent-engine web browser — Mozilla-built, Gecko-rendered, MPL-2.0 licensed. It's the only major browser not based on Blink or WebKit, ships strong privacy defaults (ETP, Total Cookie Protection, container tabs), and runs on every major platform (iOS uses WebKit due to Apple policy). The Quantum project (2017) brought multi-process + parallel CSS + GPU compositing; Project Fission (default 2024) added per-origin site isolation. Manifest V3 finally landed stable in Firefox 138 (Aug 2026). Verdict: recommended for engine independence and privacy; skip if tightly locked into Google's ecosystem.