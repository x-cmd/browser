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
    ├── 2-firefox.{en,cn}.md                  # Firefox deep dive
    ├── 2-firefox.llms.md
    └── 2-firefox.faq.yml
```

The leading integer in the filename is the reading order.
Articles are kept in sync across all four files per slot:
`.en.md`, `.cn.md`, `.llms.md`, `.faq.yml`.

## Article slots

| Slot | Article | Purpose |
| --- | --- | --- |
| `0-` | Latest browsers | What's new in web browsers — recent releases, AI integration, deprecations. Newsletter-style. |
| `1-` | Browser overview | Big-picture map of the browser space; one comparison table across the main alternatives. |
| `2-…` | Per-browser deep dives | One article per notable browser — engine, install, extension model, when to use / not use. |

## Sister repos

- [`x-cmd/cve`](https://github.com/x-cmd/cve) — CVE / CWE intelligence (topic library pattern reference).
- [`x-cmd/gpg`](https://github.com/x-cmd/gpg) — team GPG keyring (topic library pattern reference).
- [`x-cmd/terminal`](https://github.com/x-cmd/terminal) — terminal emulator topic library (parallel structure).
- [`x-cmd/install`](https://github.com/x-cmd/install) — install database (drives `x install <name>`).
- [`x-cmd/x-cmd`](https://github.com/x-cmd/x-cmd) — module source (`mod/`).

## License

Apache License 2.0 — see [`LICENSE`](./LICENSE).