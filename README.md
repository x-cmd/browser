# x-cmd/browser — web browser topic library

Articles, comparisons, and deep dives on web browsers. Published
as a topic library at <https://x-cmd.com/browser>.

> 🌐 **中文版：[README.cn.md](./README.cn.md)** — same content,
> Chinese front matter.

This repo holds the canonical English / Chinese articles that
back the **Browser** section of the x-cmd website. The articles
are content-only, factual, and open for **modification PRs**
from anyone — see [`CONTRIBUTING.md`](./CONTRIBUTING.md) for
the article workflow and frontmatter spec.

## What's in this repo

```
x-cmd/browser/
├── README.md                 # this file (English)
├── README.cn.md              # Chinese version
├── CONTRIBUTING.md           # article workflow + frontmatter spec + FAQ schema
├── SKILL.md                  # AI-agent recipe for using the topic library
├── LICENSE                   # Apache-2.0
└── docs/
    ├── 0-latest-browsers.{en,cn}.md          # what's new in browsers
    ├── 0-latest-browsers.llms.md
    ├── 0-latest-browsers.faq.yml
    ├── 1-browser-overview.{en,cn}.md         # overview + horizontal comparison
    ├── 1-browser-overview.llms.md
    ├── 1-browser-overview.faq.yml
    ├── 2-browser-security-privacy.{en,cn}.md  # security: tracker protection, fingerprinting, sandboxing
    ├── 2-browser-security-privacy.llms.md
    ├── 2-browser-security-privacy.faq.yml
    ├── 3-browser-engine-diversity.{en,cn}.md  # engine diversity: Gecko / WebKit / Blink and the monoculture
    ├── 3-browser-engine-diversity.llms.md
    ├── 3-browser-engine-diversity.faq.yml
    └── 4-browser-ai-overview.{en,cn}.md      # AI integration: Gemini / Copilot / Leo / DuckAssist
        ├── 4-browser-ai-overview.llms.md
        └── 4-browser-ai-overview.faq.yml
```

The leading integer in the filename is the reading order.
Articles are kept in sync across all four files per slot:
`.en.md`, `.cn.md`, `.llms.md`, `.faq.yml`.

## Article slots

| Slot | Article | Purpose |
| --- | --- | --- |
| `0-` | Latest browsers | What's new in web browsers — recent releases, AI integration, deprecations. Newsletter-style. |
| `1-` | Browser overview | Big-picture map of the browser space; one comparison table across the main alternatives. |
| `2-…` | Angle / perspective analysis | One article per **angle** — security & privacy, engine diversity, AI overview. Not per-browser tutorials; install / config live at `x-cmd.com/install/<slug>` and `x-cmd.com/doc-2026/install/<slug>`. |

## Sister repos

- [`x-cmd/cve`](https://github.com/x-cmd/cve) — CVE / CWE intelligence (topic library pattern reference).
- [`x-cmd/gpg`](https://github.com/x-cmd/gpg) — team GPG keyring (topic library pattern reference).
- [`x-cmd/terminal`](https://github.com/x-cmd/terminal) — terminal emulator topic library (parallel structure).
- [`x-cmd/install`](https://github.com/x-cmd/install) — install database (drives `x install <name>`).
- [`x-cmd/x-cmd`](https://github.com/x-cmd/x-cmd) — module source (`mod/`).
- [`x-cmd/doc-2026`](https://github.com/x-cmd/doc-2026) — main site docs (per-tool articles at `data/install/<slug>/<name>.*`).

## License

Apache License 2.0 — see [`LICENSE`](./LICENSE).