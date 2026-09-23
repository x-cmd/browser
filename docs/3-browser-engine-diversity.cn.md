---
x-title: 浏览器引擎多样性 — 为何 Gecko、WebKit、Blink 都重要
x-desc: >-
  浏览器引擎多样性的角度文章 —— 三个存活的引擎（Gecko / WebKit / Blink），
  为何单一化对开放网络危险，一家主导时赌注是什么，如何支持三者，以及新兴引擎
  （Servo、Ladybird）。
x-sidebar: 浏览器引擎多样性
x-keywords: 浏览器引擎, gecko, webkit, blink, 单一化, servo, ladybird, 网页兼容
x-json-ld:
  '@context': https://schema.org
  '@graph':
    - '@type': TechArticle
      headline: '浏览器引擎多样性'
      inLanguage: 'cn'
      about: '浏览器引擎生态分析'
---

# 浏览器引擎多样性 — 为何 Gecko、WebKit、Blink 都重要

2026 年三个引擎渲染网页：

- **Gecko** —— Mozilla Firefox、LibreWolf、Tor Browser、Zen、Waterfox。
- **WebKit** —— Safari，加上每个 iOS 浏览器（Apple 政策）。
- **Blink** —— Chrome、Edge、Brave、Arc、Vivaldi、Opera，加上所有基于
  Chromium 的浏览器。

Blink 份额是**约 76% 桌面**（StatCounter 2026 Q2）。那是**单一化**。
本文讨论它为何重要以及如何保持另外两个存活。

本页是角度文章——生态分析，而非 per-tool 教程。安装 / 配置见
[x-cmd.com/install/<browser>](https://x-cmd.com/install/)。

> **TL;DR。** 三个引擎是必要的，因为：（1）每个都能捕捉其他两个漏掉的
> bug；（2）任何一个都可能被所有者放弃（Google / Apple / Mozilla 可能
> 停止资助）；（3）web 标准在多厂商反馈下变得更好；（4）当只有一家公
> 司塑造浏览器中跑的内容时，web 变得更小。**日常用 Gecko**且**如果有
> 能力则资助 Mozilla 或做贡献**。

## 2026 年的三个引擎

### Gecko

- **所有者：** Mozilla 基金会（美国，非营利）。
- **浏览器份额：** 约 6% 桌面，约 2% 移动。
- **优势：** 独立、强的隐私默认、容器标签、使命是保持替代引擎存活。
- **Fork：** LibreWolf（无遥测）、Tor Browser（隐私）、Waterfox、Zen。
- **资金：** 主要靠 Mozilla 基金会捐赠 + Google 搜索协议收入（有争议）。

### WebKit

- **所有者：** Apple（公司）。
- **浏览器份额：** 约 17% 桌面，约 30%+ 移动（因为 Apple 强制所有
  iOS 浏览器用 WebKit）。
- **优势：** Apple silicon 上的电池续航、端侧 AI 集成、深 OS 集成。
- **Fork：** 有限 —— Apple 控制 WebKit；只有 Apple 平台浏览器能用它。

### Blink

- **所有者：** Google（公司），有 Microsoft、Brave、Arc、Vivaldi、Opera
  的 fork。
- **浏览器份额：** 约 76% 桌面，约 63% 移动。
- **优势：** 兼容性、生态、Sync、DevTools、Gemini Nano 端侧 AI。
- **Fork：** 每个非 Gecko 非 WebKit 的主流浏览器都基于 Blink。

## 单一化为何危险

### 论点 1：bug

每个引擎都有 bug。如果只有一个引擎渲染网页，**一个坏设计**影响所有人。
三个引擎是相互捕捉错误的多元性。

真实例子：**Apple iOS Safari 跟踪保护 bug**（2024）—— ITP 中的一个 bug
破坏了 iOS Safari 上的一些登录流。Firefox / Chrome 有类似 bug（更早捕捉）；
桌面常那个 bug 只在生产中表现出来，因为 iOS Safari 是 iOS 用户唯一能用的
浏览器。

### 论点 2：放弃

引擎可以被放弃。真实例子：

- **EdgeHTML**（Microsoft 的 Chromium 前引擎）在 2018 年 Microsoft 把
  Edge 切换到 Blink 时被放弃。16+ 年的投资消失。
- **Presto**（Opera）在 2013 年 Opera 切换到 Blink 时被放弃。
- **Trident / EdgeHTML**（Microsoft）—— 放弃。

如果 Google 决定放弃 Blink，web 将变成**两个引擎**（WebKit + Gecko）。
长远来看这是真实的可能性。

### 论点 3：标准

web 标准在**多厂商投入**下变得更好。CSS 特性、JS API、可访问性原语——
都受益于被多于一个团队实现。WHATWG（HTML living standard）明确要求多
厂商签署。

### 论点 4：市场力量

当一个引擎有 76%+ 份额时，**Google 塑造浏览器中跑的内容**。不为
Chrome 的怪癖发货的站点被降级。为 Chrome 怪癖发货的站点有时在其他
地方坏掉。即使在今天这也是真实的张力。

## Gecko 消失的话赌注是什么

如果 Mozilla 资金崩塌、Gecko 死了，web 变成：

- 约 76% Blink
- 约 17-30% WebKit（仅 Apple）
- 0% Gecko

所有 web 标准工作在 Google + Apple 处完成。web 变得更统一——但也更容易受
单一公司选择影响。

Mozilla 的角色：

- **先实现标准** —— 许多 web 特性先在 Gecko 上发布（CSS Grid、WebExtensions
  API）。
- **明确的隐私立场** —— Mozilla 游说反对有害 web 实践。
- **替代 UI 模式** —— Firefox 的容器标签影响了 Chrome 对 profile 的思考。
- **标准反馈** —— Mozilla 在 WHATWG / W3C 中的声音独立于 Google。

如果 Gecko 消失，所有这些都消失。

## 如何支持引擎多样性

按影响力排序的实用行动：

1. **以 Firefox 作为你的主浏览器。** Gecko 份额的每个百分点都支持
   Mozilla 的持续存在。
2. **在 Apple 设备上用 Safari。** Apple 是第二个引擎所有者；如果你用
   Safari，你支持 WebKit 的持续投资。
3. **捐给 Mozilla。** 直接支持他们工作。
4. **向所有浏览器报告 webcompat bug。** 如果站点在 Firefox 上坏，提交
   bug。Mozilla 的 webcompat 团队会分类。
5. **在 Firefox 上测试你的站。** 发布特性前，验证它在 Gecko 上能跑。
   用 Playwright 或 Selenium 测试三个。
6. **避免仅 WebKit / 仅 Blink 的特性。** 用标准（CSS、JS、HTML）而非
   厂商前缀。

## 新兴引擎

两个开发中的新引擎：

- **Servo** —— Rust 编写的实验引擎，最初由 Mozilla 资助。现在由 Linux
  Foundation Europe 接手。非消费级，但嵌入式 / IoT 方向有趣。
- **Ladybird** —— 来自 SerenityOS 项目。纯 pre-1.0；目标是无现有引擎
  依赖的完整 web 浏览器。尚未生产就绪。

两个都未生产就绪。如果任一成功，引擎生态可能增至 5 个。

## iOS 呢？

Apple App Store 政策：**iOS 上的每个浏览器底层必须用 WebKit**。
Chrome for iOS、Firefox for iOS、Brave for iOS —— 都通过 WebKit 渲染，
不是 Blink 或 Gecko。

这意味着：

- **iOS** = 仅 WebKit（无引擎选择）。
- **macOS** = Safari（WebKit）+ Chrome / Firefox / Brave（Blink / Gecko）。
- **Windows** = Edge（Blink）+ Firefox / Brave（Gecko / Blink）。
- **Linux** = Firefox（Gecko）+ 基于 Chromium 的（Blink）。

引擎选择在**桌面上最有意义**。

## 下一步？

- **4-browser-ai-overview** —— AI 功能如何改变引擎故事。

## 相关

- [Mozilla 基金会](https://foundation.mozilla.org/)
- [Apple WebKit](https://webkit.org/)
- [Chromium 项目](https://www.chromium.org/)
- [Servo 引擎](https://servo.org/)
- [Ladybird 浏览器](https://ladybird.org/)
- [WHATWG](https://whatwg.org/)

> per-tool 安装 / 配置：`x-cmd.com/install/<browser>` 或
> `x-cmd.com/doc-2026/install/<browser>` 的 per-tool 文章。本页
> 仅为角度 / 分析。