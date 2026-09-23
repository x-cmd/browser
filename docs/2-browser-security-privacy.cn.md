---
x-title: 浏览器安全与隐私 — 跟踪保护、指纹识别与沙箱化
x-desc: >-
  浏览器安全与隐私的角度文章 —— 跟踪保护（第三方 cookie、指纹识别、
  supercookie）、各引擎默认行为（Firefox ETP、Safari ITP、Brave Shields、
  Chrome Privacy Sandbox）、沙箱模型（Chromium 多进程、Firefox 站点隔离）、
  以及新兴威胁（AI 驱动钓鱼）。
x-sidebar: 浏览器安全
x-keywords: 浏览器安全, 跟踪保护, 指纹识别, itp, etp, brave shields, privacy sandbox, 沙箱化
x-json-ld:
  '@context': https://schema.org
  '@graph':
    - '@type': TechArticle
      headline: '浏览器安全与隐私'
      inLanguage: 'cn'
      about: '浏览器安全与隐私分析'
---

# 浏览器安全与隐私 — 跟踪保护、指纹识别与沙箱化

每个现代浏览器对隐私都有自己的立场。立场在精神上相似（跟踪越少越好）
但细节不同——什么算"跟踪器"、是否默认屏蔽第三方 cookie、指纹识别防御
有多激进、引擎对沙箱的依赖程度。

本页是角度文章——安全 / 隐私分析，而非 per-tool 教程。安装 / 配置见
[x-cmd.com/install/<browser>](https://x-cmd.com/install/)。

> **TL;DR。** 2026 年所有现代浏览器默认屏蔽跨站跟踪。差异在**激进
> 程度**——Firefox 的总 Cookie 保护最严；Brave Shields 加内置 VPN + 防火墙；
> Chrome Privacy Sandbox 是最慢完成取代 3P cookie 的。沙箱化：Chromium
> 自 2018 多进程站点隔离；Firefox 与 Project Fission（自 2024 默认）持平；
> Safari 用 WebKit 沙箱。

## 跟踪保护——屏蔽什么

2026 年审计：

| 引擎 | 浏览器 | 第三方 cookie | 指纹识别 | Supercookie | 网络跟踪 |
| --- | --- | --- | --- | --- | --- |
| **Gecko** | **Firefox** | 屏蔽（ETP） | 屏蔽（严格） | 屏蔽（resistFingerprinting） | DoH + ECH |
| **Gecko (Tor)** | **Tor Browser** | 屏蔽 | 屏蔽（统一） | 屏蔽 | Tor 网络 |
| **Gecko (fork)** | **LibreWolf** | 屏蔽 | 屏蔽 | 屏蔽 | DoH |
| **WebKit** | **Safari** | 屏蔽（ITP） | 屏蔽 | 屏蔽 | iCloud Private Relay（可选） |
| **Blink** | **Chrome** | 逐步淘汰（Privacy Sandbox） | 有限 | 有限 | IP 保护（美国铺开） |
| **Blink** | **Edge** | 逐步淘汰（Tracking Prevention） | 有限 | 有限 | SmartScreen + DoH |
| **Blink** | **Brave** | 屏蔽（Shields 默认） | 屏蔽（随机化） | 屏蔽 | 内置 VPN + 防火墙 |
| **Blink** | **Arc** | 有限 | 有限 | 有限 | 标准 |
| **Blink** | **Vivaldi** | 屏蔽（可选） | 有限 | 有限 | DoH |
| **Blink** | **Opera** | 屏蔽（可选） | 有限 | 有限 | 内置 VPN |
| **Servo（利基）** | **Falkon / Ladybird（开发中）** | 有限 | 有限 | 有限 | — |

### 每个引擎屏蔽什么

**Gecko（Firefox / Tor Browser / LibreWolf）：**

- **增强跟踪保护（ETP）** —— 屏蔽跟踪器、指纹识别器、加密货币挖矿。
  三级：标准、严格、自定义。
- **总 Cookie 保护** —— Cookie 按第一方域分区。Tracker X 在站点 A 设置的
  Cookie 在访问站点 B 时无法被读取，即使两个站点都嵌入 Tracker X。
- **抵抗指纹识别** —— 统一的 User-Agent、时区、canvas；更难指纹化。
- **DoH + ECH** —— 加密 DNS。

**WebKit（Safari）：**

- **智能跟踪预防（ITP）** —— 机器学习驱动的跨站跟踪器屏蔽。
- **指纹保护** —— 浏览器指纹屏蔽。
- **iCloud Private Relay**（iCloud+ 订阅者）—— 对跟踪器隐藏 IP。

**Blink（Chrome / Edge / Brave / Arc / Vivaldi / Opera）：**

- **Privacy Sandbox** —— Topics API + FLEDGE + Attribution API
  （Chrome）；通过 2024–2026 逐步淘汰 3P cookie。
- **Shields（仅 Brave）** —— 屏蔽跟踪器、指纹随机化、cookie 屏蔽、
  HTTPS 升级。
- **内置 VPN / 防火墙（Brave、Opera）** —— 按需 VPN。

### "严格"有多严？

大致排序（最严 → 最松，2026）：

1. **Tor Browser** —— 统一，默认无 JS，Tor 网络。（最严。）
2. **LibreWolf** —— 严格 ETP，无遥测。
3. **Firefox（Strict）** —— 严格 ETP。
4. **Brave（Aggressive）** —— Shields 默认 Aggressive。
5. **Safari** —— ITP 默认。
6. **Firefox（Standard）** —— 中等。
7. **Vivaldi / Opera** —— 可选屏蔽。
8. **Arc** —— 最小屏蔽。
9. **Chrome** —— Privacy Sandbox（不完整）。
10. **Edge** —— Tracking Prevention 在默认级。

（最松。）

## 沙箱与站点隔离

浏览器的**沙箱**保护操作系统免受已攻破渲染器进程的侵害。2026 年
三种方法：

### Chromium 多进程（Chrome / Edge / Brave / Arc / Vivaldi / Opera）

Chromium 有**多进程架构**，为 browser、renderer、GPU、网络、扩展、工具
分别有进程。**站点隔离**（每个源跑在自己的进程里）自 Chrome 67（2018）
起默认。

- 优点：防御 Spectre 类攻击；一个被攻破的站点读不到另一个站点的
  cookie 或存储。
- 缺点：内存占用更高（同一 tab 数比 Firefox 多约 50-200 MB）。

### Firefox 站点隔离（Project Fission）

Firefox 在 2020 年引入 Project Fission；**自 2024 年起对所有用户默认**。
每个源在自己的进程里。

- 优点：与 Chromium 的纵深防御持平。
- 缺点：内存占用比 Fission 之前的 Firefox 略高。

### WebKit 沙箱（Safari）

WebKit 沙箱是 OS 级：在 macOS 上，通过 Sandbox 沙箱化进程；在 iOS 上，
更严。

- 优点：成熟，内存低。
- 缺点：每个平台沙箱模型不同。

## 钓鱼保护

每个现代浏览器都有钓鱼 / 恶意软件保护系统。大多数用 Google Safe Browsing
API 或类似服务：

| 引擎 | 浏览器 | 服务 | URL 检查 | 下载检查 |
| --- | --- | --- | --- | --- |
| **Blink** | Chrome | Google Safe Browsing（增强） | ✅ | ✅ |
| **Blink** | Edge | Microsoft Defender SmartScreen | ✅ | ✅ |
| **Blink** | Brave | Google Safe Browsing + 本地列表 | ✅ | ✅ |
| **Blink** | Arc | Google Safe Browsing | ✅ | ✅ |
| **Gecko** | Firefox | Google Safe Browsing | ✅ | ✅ |
| **WebKit** | Safari | 腾讯 + Apple 代理（中国），Google Safe Browsing（其他） | ✅ | ✅ |

注意：**Google Safe Browsing 是主流后端**——甚至非 Chromium 浏览器
（Firefox）也用它。注重隐私的浏览器（Brave）也用它但试图限制发送的数据。

## AI 驱动钓鱼——2026 年威胁

新型钓鱼攻击：**AI 生成的钓鱼页面**。攻击者用 LLM 实时克隆银行登录页，
带个性化内容（目标的姓名、来自泄露数据集的账号）。页面托管在一个
仅注册了几小时的域名上。

防御：

- **钓鱼检测** —— 浏览器内的启发式 ML（Chrome 增强 Safe Browsing；
  Edge SmartScreen）。
- **Passkey / WebAuthn** —— 抗钓鱼登录；不向（假）服务器传凭据。
- **跟踪的屏蔽列表** —— Google Safe Browsing 在数分钟内更新。

尚无浏览器提供完全 AI 抗钓鱼的防御——这是开放的研究领域。

## "私密浏览" / 隐身模式呢？

私密浏览模式（Chrome Incognito、Firefox 私密窗口、Safari 私密窗口、
带 Tor 的 Brave 私密窗口）**屏蔽本地跟踪**：

- 窗口关闭后不保存历史 / cookie / 缓存。
- 不与常规会话共享 cookie。

但**不**让你对你访问的网站、雇主或 ISP 匿名。需要真正匿名，请用
**Tor Browser**。

## 实用建议

1. **大多数用户的默认浏览器：** Firefox（强隐私默认，广泛的扩展
   生态）。
2. **最大隐私：** Tor Browser 或 Brave 带 Shields 设 Aggressive。
3. **避开最弱默认：** Arc、Opera（2026 默认无跟踪保护）、Edge
   （SmartScreen 不错，但隐私不如 Brave）。
4. **用 Passkey / WebAuthn** —— 抗钓鱼。
5. **启用 DNS over HTTPS（DoH）** 在任何支持的浏览器里。
6. **启用 Encrypted Client Hello（ECH）** —— SNI 隐私。

## 下一步？

- **3-browser-engine-diversity** —— 为何单一化重要。
- **4-browser-ai-overview** —— AI 功能如何改变隐私故事。

## 相关

- [Firefox ETP](https://support.mozilla.org/en-US/kb/enhanced-tracking-protection-firefox)
- [Safari ITP](https://webkit.org/tracking-prevention/)
- [Brave Shields](https://www.brave.com/shields)
- [Chrome Privacy Sandbox](https://privacysandbox.com/)
- [Tor Browser](https://www.torproject.org/)

> per-tool 安装 / 配置：`x-cmd.com/install/<browser>` 或
> `x-cmd.com/doc-2026/install/<browser>` 的 per-tool 文章。本页
> 仅为角度 / 分析。