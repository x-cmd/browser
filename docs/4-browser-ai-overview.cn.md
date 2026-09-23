---
x-title: 浏览器 AI 概览 — Gemini Nano、Copilot、Apple Intelligence、Leo、DuckAssist
x-desc: >-
  2026 年浏览器 AI 功能的角文章 —— Gemini Nano（Chrome）、Microsoft Copilot（Edge）、
  Apple Intelligence（Safari）、Brave Leo、DuckDuckGo DuckAssist、Arc AI Boosts，
  以及本地 vs 云推理的隐私含义。
x-sidebar: 浏览器 AI 概览
x-keywords: 浏览器 ai, gemini nano, copilot, apple intelligence, brave leo, duckassist, 本地 llm, 端侧
x-json-ld:
  '@context': https://schema.org
  '@graph':
    - '@type': TechArticle
      headline: '浏览器 AI 概览'
      inLanguage: 'cn'
      about: '浏览器 AI 功能对比'
---

# 浏览器 AI 概览 — Gemini Nano、Copilot、Apple Intelligence、Leo、DuckAssist

每个主流浏览器到 2025 年都发布了某种 AI 集成。到 2026 年，AI 功能是
**基本盘**——问题不是"这个浏览器有 AI 吗？"而是**"哪种 AI，
跑在哪里，它看到什么？"**。

本页是角度文章——AI 功能对比，而非 per-tool 教程。安装 / 配置见
[x-cmd.com/install/<browser>](https://x-cmd.com/install/)。

> **TL;DR。** 浏览器 AI 落入两个桶：**云推理**（Copilot、Gemini Pro、
> Safari Apple Intelligence 云）与**本地 / 端侧**（Chrome 的 Pro
> 用户用 Gemini Nano、Brave Leo 本地模式、Apple Intelligence 端侧、
> DuckAssist 端侧）。本地更隐私但能力有限；云更有能力但看到你的输入。
> 按威胁模型选择。

## 两种推理模型

### 云推理（大多数浏览器）

浏览器把你的提示送到云端 LLM（OpenAI、Anthropic、Google 的 Gemini Pro
等）。云运行推理并送回响应。

优点：

- 最有能力（前沿模型）。
- 大查询上快。
- 无硬件约束。

缺点：

- 云看到你的提示（搜索查询、页面内容、AI Chat 消息）。
- 云端日志可能持久。
- 延迟：网络往返。
- 提供商的带宽 / 数据成本。

### 本地 / 端侧推理

浏览器在你的设备（CPU、GPU 或 NPU）上跑小 LLM。数据不离开设备。

优点：

- 隐私——数据留在本地。
- 延迟——无网络。
- 离线工作。

缺点：

- 能力有限（更小的模型）。
- 电池 / 热影响。
- 需要现代硬件（Apple silicon M1+、最近带 NPU 的 Intel / AMD CPU）。

## 每浏览器 AI 功能（2026）

### Chrome —— Gemini Nano（端侧）+ Gemini Pro（云）

- **Gemini Nano** —— 端侧 LLM，**Pro 订阅者**在满足硬件要求的机器上可用。
  用于翻译、摘要、起草。
- **Gemini Pro** —— 云推理。支撑 Chrome 的 AI 增强搜索结果与 AI
  Overview 摘要。
- **AI Overview** —— 搜索结果顶部的 AI 生成摘要。由 Gemini Pro 支撑。

隐私：默认云推理；Nano 对 Pro 是可选开的。

### Edge —— Microsoft Copilot（云）

- **Copilot** —— Microsoft 365 Copilot，与 Edge 深度集成。翻译、摘要、
  起草、浏览、代码。
- **Bing Chat**（现 Copilot）—— 聊天界面。
- **Bing Image Creator** —— DALL-E 集成。

隐私：云推理；数据送到 Microsoft。企业层有私密模式选项。

### Safari —— Apple Intelligence（端侧 + 云）

- **写作工具** —— 校对、改写、摘要。全部端侧。
- **图像 Playground** —— 图像生成（云用于更高质量模型）。
- **Siri 集成** —— 跨 app 上下文。
- **阅读器翻译** —— 通过 Bergamot 的端侧翻译。

隐私：**默认端侧**覆盖大多数功能。Apple silicon M1+ 需要完整功能。云
推理可选且注重隐私（Apple 声明无数据保留）。

### Brave —— Leo（云 + 本地选项）

- **Leo** —— 内置 AI 助手。多种模型选项：
  - 云：Claude / Llama / 其他（付费层）。
  - **本地** —— 本地跑模型（Llama、Mistral）。
- **注重隐私** —— Leo 声称对话不用于模型训练。

隐私：本地模式在支持的硬件上可用。

### DuckDuckGo —— DuckAssist + AI Chat（云）

- **DuckAssist** —— AI Overview 对应物。引用来源。
- **AI Chat** —— 由 OpenAI / Anthropic / Mistral 支撑的聊天界面。**隐私
  声称**：不用于模型训练；DDG 代理并剥离标识头。

隐私：云推理；DDG 代理注重隐私。不如本地隐私。

### Arc —— Boosts + Easels + AI Search（云）

- **Boosts** —— 用户定义的 AI 提示，应用于每个页面（如"用 3 个要点摘要"、
  "翻译成西班牙语"）。
- **Easels** —— 带 AI 的协作白板。
- **AI Search** —— Perplexity 集成。

隐私：云推理。

### Vivaldi —— 极简 AI

- Vivaldi 立场：AI 应该是**用户选择**，不是浏览器默认。
- 可选与 chatbot 集成；无内置 AI。

隐私：用户控制。

## 本地推理——2026 年能做什么

三类设备支持本地 LLM 推理：

### Apple silicon（M1+）

- CPU / GPU / NPU 间的**统一内存**让本地 LLM 高效。
- Apple Intelligence 默认对大多数功能是端侧。
- 7B 模型（Llama、Mistral）在 M1 Pro / Max 上流畅运行。

### 现代 Intel / AMD 带 NPU

- Snapdragon X / Intel Core Ultra / AMD Ryzen AI —— NPU 加速本地推理。
- Windows Copilot+ PC 带 NPU 用于端侧 AI。
- 性能各异；NPU 不全相等。

### 较老硬件

- 无 NPU。
- 本地 LLM 跑在 CPU / GPU；7B 模型慢（>10s / token）。
- 云是实际选择。

## 隐私对比矩阵

| 浏览器 | 默认 | 本地选项 | 云 | 数据保留 |
| --- | --- | --- | --- | --- |
| **Chrome** | 云（Gemini Pro） | Nano（仅 Pro） | 是 | Google 隐私政策 |
| **Edge** | 云（Copilot） | ❌ | 是 | Microsoft 隐私政策 |
| **Safari** | 本地（Apple Intelligence） | 是（默认） | 可选 | Apple 隐私政策 |
| **Brave** | 本地（Leo） | 是（默认） | 付费层 | Leo 声称不训练 |
| **DuckDuckGo** | 云（DuckAssist + AI Chat） | ❌ | 是（代理） | DDG 隐私政策 |
| **Arc** | 云（Boosts + Easels） | ❌ | 是 | Arc 隐私政策 |
| **Vivaldi** | 无（用户自选） | 可选 | 用户自选 | 按提供商 |

## 威胁模型问题

按威胁模型选 AI 功能：

- **最大隐私** —— Apple Intelligence（Apple silicon 上的 Safari）或
  Brave Leo 本地。无数据离开设备。
- **隐私 / 能力平衡** —— DuckDuckGo（代理云）或 Brave Leo 云。
- **最大能力** —— 带 Pro 订阅的 Chrome（Gemini Nano + Pro）或 Edge
  Copilot。
- **不要 AI** —— Vivaldi（用户自选）。

## AI Overview——引用问题

所有主流浏览器在搜索结果顶部都发布"AI Overview"特性。问题是：**如何
被引用？**。

什么有效：

- **长篇一手内容。** AI Overview 引用主要来源。
- **原创数据 / 研究。** 独特数据点被引用。
- **明确的专业信号。** 作者简历、凭据、引用。
- **结构化数据。** Schema.org 帮助 LLM 解析。

什么无效：

- **SEO 优化的废话。** AI Overview 跳过废话。
- **未经核实的声称。** LLM 偏好带引用的来源。
- **过时的内容。** 时效性很重要。

## 下一步？

`0-latest-browsers` / `1-browser-overview` 中的交叉引用。
per-tool 安装见 `x-cmd.com/install/<browser>`。

## 相关

- [Chrome AI 功能](https://developer.chrome.com/docs/ai)
- [Apple Intelligence](https://www.apple.com/apple-intelligence/)
- [Brave Leo](https://brave.com/leo/)
- [DuckDuckGo DuckAssist](https://duckduckgo.com/?q=DuckAssist)
- [Microsoft Copilot](https://copilot.microsoft.com/)

> per-tool 安装 / 配置：`x-cmd.com/install/<browser>` 或
> `x-cmd.com/doc-2026/install/<browser>` 的 per-tool 文章。本页
> 仅为角度 / 分析。