# Contributing — `x-cmd/browser`

This page covers how to add or modify an article in the
web-browser topic library.

**Looking to read?** See [`README.md`](./README.md) for the
overview, or [`SKILL.md`](./SKILL.md) for the AI-agent recipe.

## Article slots

| Slot | Article | Add a new one? |
| --- | --- | --- |
| `0-latest-browsers` | Latest news. | Refresh in place; do not add a second `0-` slot. |
| `1-browser-overview` | Overview + comparison. | Refresh in place. |
| `2-…`, `3-…`, … | One per notable browser. | **Yes** — add a new slot. Filename `n-<browser>.{en,cn,llms,faq}.md`. |

When you add a new per-browser deep dive, link it from the
overview's comparison table and from the latest-news article
(if it's relevant to recent activity).

## Per-slot file convention

Every article slot is **four files, kept in sync**:

| File | Purpose | Required? |
| --- | --- | --- |
| `n-<slug>.en.md` | Canonical English article. The one the GitHub social preview and search engines see. | ✅ |
| `n-<slug>.cn.md` | Chinese translation. Same structure, same anchors, same diagrams. | ✅ |
| `n-<slug>.llms.md` | LLM-friendly summary — YAML frontmatter + flat prose. One screen of structured text. | ✅ |
| `n-<slug>.faq.yml` | Structured Q&A used for the FAQ section and JSON-LD on the site. | ✅ |

If you change `.en.md`, change `.cn.md` in the same commit. If
you add a new FAQ entry, add it to both languages.

## English frontmatter

```yaml
---
x-title: Firefox — A Modern, Independent Web Browser
x-desc: >-
  Firefox is the last major browser engine (Gecko) independent of
  Chromium. Built by Mozilla, MPL-2.0 licensed, with strong privacy
  defaults and cross-platform support.
x-sidebar: Firefox
x-keywords: firefox, gecko, mozilla, browser, privacy
x-json-ld:
  '@context': https://schema.org
  '@graph':
    - '@type': TechArticle
      headline: 'Firefox'
      inLanguage: 'en'
      about: 'Firefox web browser'
---
```

`x-title` and `x-desc` are required; `x-sidebar`, `x-keywords`,
and `x-json-ld` are optional but recommended for SEO.

## `.llms.md` format

```markdown
---
name: firefox
description: Modern, independent web browser built by Mozilla. Gecko
  engine, MPL-2.0, strong privacy defaults, cross-platform.
type: summary
---

# Core Content

core_features:
  - Independent Gecko layout engine
  - Strong privacy defaults (Enhanced Tracking Protection)
  - Cross-platform: Windows, macOS, Linux, BSD, Android, iOS

# Key Information

highlights:
  - Last major independent browser engine
  - WebExtensions API (shared with Chromium-based browsers)
  - Quantum project boosted performance significantly since 2017

# Use Cases

use_cases:
  - Privacy-conscious browsing
  - Avoiding Chromium monoculture
  - Firefox Sync across devices

# Related Resources

official:
  website: https://www.mozilla.org/firefox/
  repo: https://hg.mozilla.org/mozilla-central/

# Summary

Short paragraph that an LLM can quote verbatim.
```

## `.faq.yml` format

```yaml
id: x-b-2-firefox

data:
  - name:
      en: overview
      cn: 概览
    qa:
      - id: what-is-firefox
        question:
          en: What is Firefox?
          cn: 什么是 Firefox？
        answer:
          en: A modern web browser built by Mozilla, using the independent Gecko engine. Available on Windows, macOS, Linux, BSD, Android, and iOS.
          cn: 由 Mozilla 构建的现代网页浏览器，使用独立的 Gecko 引擎。支持 Windows、macOS、Linux、BSD、Android 和 iOS。
        confidence: 9
        reference:
          - docs/2-firefox.en.md
          - docs/2-firefox.cn.md
```

Each FAQ entry has:

- `id` — kebab-case, unique within the file
- `question` — bilingual `en` + `cn`
- `answer` — bilingual `en` + `cn`, ≤ 4 sentences each
- `confidence` (1–9) — how confident the team is in the answer
- `reference` — list of article files that back the answer

## Editing rules

- **One slot per commit.** Don't mix the overview and a deep
  dive in the same commit.
- **Both languages in the same commit.** Don't open separate
  PRs for the `.en.md` and `.cn.md` of the same slot.
- **Quote from official sources only.** Don't paraphrase from
  Wikipedia / Reddit / random blogs without verifying against
  the upstream repo, the official website, or release notes.
- **Don't quote from `x-cmd-install/mneme`.** That repo is
  private and exists to keep things out of public view.
- **Don't discuss intent.** Articles are content-only — no
  "we're planning to add", no monetization framing, no
  internal-org context.

## CI

The site's build pipeline reads `docs/` and validates that:

1. Every `.en.md` has a matching `.cn.md` with the same
   filename stem.
2. Every slot has a `.llms.md` and a `.faq.yml`.
3. The `.faq.yml` is valid YAML and every `id` is unique.
4. The `.llms.md` frontmatter parses.

If CI fails, the article does not publish to
`x-cmd.com/browser` until the failure is fixed.

## What this repo is NOT

- **Not** a fork of any browser's source code.
- **Not** an install database — that's [`x-cmd/install`](https://github.com/x-cmd/install).
- **Not** an opinion piece on "which browser is best" — the
  articles are factual and let the reader compare.
- **Not** a substitute for the upstream docs — link to them
  for canonical install / config recipes.