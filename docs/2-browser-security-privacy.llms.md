---
name: 2-browser-security-privacy
description: Security and privacy angle on browsers — per-engine tracker protection (3P cookies, fingerprinting, supercookies), sandboxing models (Chromium multi-process, Firefox Fission, WebKit sandbox), AI-driven phishing defenses, Passkeys / WebAuthn.
type: summary
---

# Core Content

core_features:
  - All modern browsers block cross-site tracking by default in 2026
  - Firefox ETP / Total Cookie Protection — strictest among major engines
  - Safari ITP — ML-driven cross-site blocking + iCloud Private Relay
  - Brave Shields — strictest among Blink browsers; built-in VPN + firewall
  - Chrome Privacy Sandbox — slowest to fully replace 3P cookies
  - Tor Browser — most strict; uniform fingerprinting + Tor network
  - Chromium site isolation since 2018; Firefox Fission default since 2024
  - Google Safe Browsing is the dominant phishing backend across all engines

# Key Information

highlights:
  - Strictness ordering (2026): Tor Browser > LibreWolf > Firefox Strict > Brave Aggressive > Safari > Firefox Standard > Vivaldi/Opera > Arc > Chrome > Edge
  - Sandbox models: Chromium multi-process (default since 2018), Firefox Fission (default since 2024), WebKit (OS-level)
  - All major browsers use Google Safe Browsing for phishing detection
  - Private browsing blocks local tracking but does NOT make you anonymous to websites/ISP
  - AI-generated phishing pages are a 2026 emerging threat
  - Passkeys / WebAuthn is phishing-resistant login
  - DoH + ECH for encrypted DNS + SNI

# Use Cases

use_cases:
  - Choosing a browser for privacy-focused users
  - Auditing browser defaults for tracking protection
  - Setting up Passkeys / WebAuthn
  - Configuring DoH + ECH
  - Defending against AI-driven phishing

# Related Resources

related:
  - name: Firefox ETP
    url: https://support.mozilla.org/en-US/kb/enhanced-tracking-protection-firefox
  - name: Safari ITP
    url: https://webkit.org/tracking-prevention/
  - name: Brave Shields
    url: https://www.brave.com/shields
  - name: Chrome Privacy Sandbox
    url: https://privacysandbox.com/
  - name: Tor Browser
    url: https://www.torproject.org/

# Summary

Browser security and privacy in 2026 is mostly about default tracking-protection defaults. All modern browsers block cross-site tracking, but strictness varies: Tor Browser (uniform fingerprinting + Tor network) > LibreWolf > Firefox Strict > Brave Aggressive > Safari ITP > Firefox Standard > Vivaldi/Opera > Arc > Chrome Privacy Sandbox > Edge. Sandboxing: Chromium multi-process site isolation since 2018; Firefox Project Fission default since 2024; WebKit OS-level sandbox. Phishing: Google Safe Browsing is the dominant backend used by all major browsers (even non-Chromium ones). AI-driven phishing pages are an emerging 2026 threat; Passkeys / WebAuthn is the strongest defense. Private browsing blocks local tracking but does NOT make you anonymous to websites / ISP / employer — for that, use Tor Browser. Practical recommendations: Firefox for default users; Brave Aggressive or Tor Browser for max privacy; Passkeys + DoH + ECH everywhere.