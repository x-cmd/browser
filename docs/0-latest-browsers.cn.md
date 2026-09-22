---
x-title: 最新浏览器 — 2026 年动态
x-desc: >-
  浏览器领域的最新发布、趋势与破坏性变更 —— Firefox 138、Chrome 138、Safari 19、
  Brave 1.80、Arc 2.0、Zen 1.14，以及 AI 集成浪潮。
x-sidebar: 最新浏览器
x-keywords: 浏览器, firefox, chrome, safari, brave, arc, zen, 2026
x-json-ld:
  '@context': https://schema.org
  '@graph':
    - '@type': TechArticle
      headline: '最新浏览器 — 2026'
      inLanguage: 'cn'
      about: '网页浏览器新闻与发布'
---

# 最新浏览器 — 2026 年动态

2026 年网页浏览器领域的新发布、新变化与新方向快照。每季度更新。

## 近期发布

| 日期 | 浏览器 | 版本 | 主要变化 |
| --- | --- | --- | --- |
| 2026-08 | **Firefox** | 138 | Manifest V3 扩展支持落地；AI 驱动的标签页分组；CSS 的 speculative rules。 |
| 2026-07 | **Chrome** | 138 | 所有标签页基于 GPU 合成；为 Pro 用户提供页面级 LLM 助手（Gemini Nano）。 |
| 2026-06 | **Safari** | 19 | 默认启用 WebGPU；阅读器视图重新设计；标准化声明式 shadow DOM。 |
| 2026-05 | **Brave** | 1.80 | AI 助手 "Leo" 提供本地模型选项；通过 Brave Search 提供 Web3 搜索。 |
| 2026-04 | **Arc** | 2.0 | 首个 Windows 稳定版；跨设备同步；AI "Boosts" 趋于成熟。 |
| 2026-03 | **Zen** | 1.14 | 基于 Firefox；经过数月预发布后的首个主要稳定版。 |
| 2026-02 | **Vivaldi** | 7.5 | 标签平铺改进；内置 Mastodon 客户端刷新。 |

## 趋势

### AI 集成已成基本盘

每个主流浏览器都自带某种 AI 助手：

- **Chrome** —— Gemini Nano（页面级 LLM，Pro 用户）。
- **Firefox** —— 标签页分组（AI 辅助）+ 可选 AI 插件。
- **Safari** —— Apple 的设备端 Intelligence 与 Safari 的阅读 / 写作工具集成。
- **Edge** —— Copilot 深度集成。
- **Brave** —— Leo，提供本地模型选项。
- **Arc** —— Boosts、Easels、AI 搜索。

2026 年的转变是尽可能 **本地 / 设备端**。Brave 与 Arc 都提供本地模型选项；Chrome 的 Gemini Nano 为 Pro 用户在设备端运行。

### Chromium 单一化

2026 年的数字相比 2024 年变化不大：

- **基于 Chromium**（Chrome、Edge、Brave、Arc、Opera、Vivaldi）：桌面份额约 76%（StatCounter 2026 Q2）。
- **Safari（WebKit）** 约 17%。
- **Firefox（Gecko）** 约 6%。
- **其他**（基于 Servo、小众）约 1%。

趋势平稳 —— Firefox 自 2024 年起下降趋稳，得益于 Manifest V3 过渡和对隐私的重新聚焦。WebKit 份额大致不变。Chromium 仍是事实标准。

### Manifest V3 无处不在

Chrome 在 Chrome 100+ 中发布 Manifest V3 稳定版；实际铺开发生在 2024–2025 年。**Firefox 138（2026 年 8 月）终于在稳定版中落地 Manifest V3**。大多数扩展开发者现在优先写 Manifest V3 代码，仅对遗留需求用 V2 polyfill。

### 隐私特性持续分化

- **Firefox** —— 默认开启增强跟踪保护；总 Cookie 保护；容器标签页。
- **Safari** —— 智能跟踪防护；指纹保护。
- **Brave** —— 默认开启 Shields；内置 VPN + 防火墙。
- **Chrome** —— Privacy Sandbox 取代第三方 Cookie（2024–2026 逐步淘汰）。

### WebGPU 无处不在

WebGPU（新一代网页 GPU API）在 **所有主流浏览器** 于 2025–2026 年达到稳定。Chrome 113+、Firefox 141+（计划中）、Safari 19+。WebGPU 如今是浏览器内计算密集型工作负载（LLM 推理、3D、视频处理）的推荐路径。

## 值得关注的破坏性变更

- **Firefox 138** 携带 Manifest V3 正式版；一些仅 V2 的遗留扩展会停止工作或需要 V3 polyfill。
- **Chrome 138** 停止支持较老的 Linux 发行版（要求 glibc 2.28+）；请检查你的发行版。
- **Safari 19** 停止支持 macOS 12 Monterey；最低要求 macOS 13 Ventura。
- **Edge** 改为季度大版本周期（旧为年度）；变更更频繁。

## 值得关注的动向

- **Firefox 141**（2026 年 9 月）—— 默认对所有用户启用 WebGPU；最后一个主流引擎。
- **Chrome 140+** —— Privacy Sandbox 的 "Topics" API 渐进推出；第三方 Cookie 的替代持续推进。
- **Servo** —— Rust 编写、由 Linux Foundation Europe 资助的浏览器引擎。非消费级，但嵌入式 / IoT 方向值得关注。
- **Arc 的 "Dia"** —— 据报道 Arc 的母公司（The Browser Company）正在做一个聚焦 AI 优先浏览的独立浏览器。暂无公开时间表。

## 相关

- [`docs/1-browser-overview.cn.md`](./1-browser-overview.cn.md) — 概览与对比表。
- [`docs/2-firefox.cn.md`](./2-firefox.cn.md) — Firefox 深度介绍。