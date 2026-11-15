---
layout: default
title: "Horizon Summary: 2026-11-15 (ZH)"
date: 2026-11-15
lang: zh
---

> 从 39 条内容中筛选出 7 条重要资讯。

---

**科技新闻**
1. [Lovable 应用因 RLS 不足泄露护照信息与逾 20 万条私信](#item-tech-news-1) ⭐️ 8.0/10
2. [PyPI 项目页改版上线，强化安全与来源信号](#item-tech-news-2) ⭐️ 7.0/10
3. [用约 200 行纯 JAX 复现 DeepSeek V3](#item-tech-news-3) ⭐️ 7.0/10
4. [Project Zero 将漏洞披露期限设为 90 天并计划缩短](#item-tech-news-4) ⭐️ 7.0/10
5. [Cloudflare 开源无状态 AI 代理浏览器 Kitesurf](#item-tech-news-5) ⭐️ 7.0/10
6. [意大利因违规读取相册对 Meta 罚款 8.05 亿欧元](#item-tech-news-6) ⭐️ 7.0/10
7. [特斯拉 Cybercab 被曝月租 299 美元才能开动](#item-tech-news-7) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Lovable 应用因 RLS 不足泄露护照信息与逾 20 万条私信](https://www.crissyfield.de/research/lovable-en/) ⭐️ 8.0/10

安全研究人员报告称，部分由 Lovable 构建的应用因 Row-Level Security（RLS）配置不足，暴露了用户敏感数据，包括护照信息和超过 20 万条私信。Lovable 安全负责人 Igor Andri 在讨论中回应称，根因正是 RLS 不足，并称平台会在发布前自动扫描每个应用，还提供更深入的 SAST 扫描，均对所有用户免费；发现问题后可选择“Fix”，也可启用自动修复或在问题未解决时阻止发布。上述扫描与修复能力是 Lovable 的说法，现有信息未说明受影响应用的具体数量或修复进展。

hackernews · armcat · 11月14日 17:43 · [社区讨论](https://news.ycombinator.com/item?id=50499017)

**「背景」** Row-Level Security（RLS）是 Postgres 的行级访问控制机制：当 Lovable 生成的应用把数据放在 Supabase 后端、由客户端直接查询时，RLS 策略决定客户端能读到哪些行。此次暴露的核心正是这些策略缺失或过宽，使本应受保护的数据可通过应用接口被读取。有评论还提到，Supabase 过去为降低接入门槛而采用较宽松的默认配置，相关默认值据称已在 10 月 30 日调整，但既有项目是否沿用旧配置仍存疑。

**「对开发者的影响」** 对使用 Lovable 发布应用的人来说，关键风险是“发现严重问题时阻止发布”在所有套餐中默认关闭；如果未手动开启并处理扫描结果，应用仍可能带着 RLS 缺陷上线。Lovable 提供免费的 SAST/Quick scan，以及针对符合条件的发现项的自动修复；开发者应开启发布阻断、运行扫描并修复发现项，同时复查已上线应用的 Supabase 行级权限。

**「社区讨论」** 评论者 SOLAR\_FIELDS 认为 Supabase 也应承担部分责任，称其默认设置是多年前为降低接入门槛而做的取舍，并提到相关讨论称问题已在 10 月 30 日修复，但有报告称现有项目仍沿用旧默认值。另有评论者主张平台应采用默认拒绝的数据库权限、最小权限 API 和自动化认证测试，使 AI 生成代码更难造成不安全部署；Oras 则指出这类 AI 生成应用数量多、攻击门槛低，普通用户往往不知道自己在使用什么。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.lovable.dev/features/security">Security overview - Lovable Documentation</a></li>
<li><a href="https://latchdog.com/guides/is-my-lovable-app-secure">Is my Lovable app secure ? What Lovable checks, and... | LatchDog</a></li>

</ul>
</details>

**标签**: `#security vulnerability`, `#Row-Level Security`, `#Supabase`, `#AI-generated code`, `#data exposure`

---

<a id="item-tech-news-2"></a>
### [PyPI 项目页改版上线，强化安全与来源信号](https://blog.pypi.org/posts/2026-11-06-ui-updates-complete/) ⭐️ 7.0/10

PyPI 已上线重新设计的项目页面，面向 Python 包维护者和使用者，更清晰地展示安全与来源（provenance）信息。此次是已完成的界面更新，而非仅宣布计划；但现有材料没有说明具体展示哪些检查项、判定规则或覆盖范围。对依赖 PyPI 的团队来说，项目页因此成为查看包来源信号的入口，不过页面上的信号本身并不等同于对包安全性的保证。

hackernews · rbanffy · 11月14日 15:40 · [社区讨论](https://news.ycombinator.com/item?id=50497892)

**「背景」** PyPI 的来源证明（provenance）由 Trusted Publishing 发布流程生成，随文件记录源码仓库、提交等构建来源信息。第三方分析指出，这类有效证明只能说明文件由何处构建，并不能证明包本身没有恶意——2026 年 5 月就曾出现带有有效 SLSA Level 3 证明的恶意 npm 和 PyPI 包。

**「影响」** 使用者在挑选依赖时可以直接在项目页查看来源信号，维护者若要让项目显示这类信号，则需要让发布流程产出可验证的来源信息。审查依赖时，缺少来源信号应促使团队进一步核实发布流程，而不是单独作为拒绝该包的依据。

**「社区讨论」** 评论中，time4tea 担心把信任建立在集中式“大云”服务上会带来锁定效应；samhclark 则支持推广 Sigstore 式无密钥短期签名，并希望第三方 CI/CD 服务补齐安全 OIDC 能力。cowlevel 提醒，来源信息主要有助于发现原本正常、后来被入侵的项目，并不能识别从一开始就恶意的项目。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.pypi.org/using-pypi/package-security/provenance/">Checking Provenance (package origin) - PyPI User Documentation</a></li>
<li><a href="https://matrixgard.com/blog/npm-pypi-provenance-attestation-supply-chain-2026/">Valid Provenance , Malicious Package: What Attestations Buy You</a></li>

</ul>
</details>

**标签**: `#PyPI`, `#Python packaging`, `#supply chain security`, `#software provenance`, `#open source infrastructure`

---

<a id="item-tech-news-3"></a>
### [用约 200 行纯 JAX 复现 DeepSeek V3](https://github.com/Vaibhaav-Tiwari/deepseek-v3-jax) ⭐️ 7.0/10

开发者 VaibhaavTiwari 在 Show HN 发布了一个用约 200 行纯 JAX 复现 DeepSeek V3 的开源项目，面向学习推理实现和本地实验。项目本身没有提供正确性或完整性的验证证据，因此更适合作为教学和动手实验的起点，而不是可直接用于生产的实现。

hackernews · VaibhaavTiwari · 11月14日 15:04 · [社区讨论](https://news.ycombinator.com/item?id=50497589)

**「背景」** JAX 是支持自动微分与加速器编译的 Python 数值计算库，常被用来从零实现和试验模型推理。DeepSeek V3 是大型语言模型，而这个 Show HN 项目把其推理核心压缩到约 200 行纯 JAX，定位更接近可阅读、可本地动手实验的教学实现，而非经过独立验证的完整生产版本。

**「实际影响」** 对使用 AMD ROCm、没有 CUDA 的本地实验者，这个项目已经显示出可操作性：一位 RX 7600 XT 16GB 用户报告它在 Fedora 上端到端跑通，但需要设置两个环境变量，其中包括 HSA\_OVERRIDE\_GFX\_VERSION=11.0.0。

**「社区讨论」** 评论者普遍赞赏从第一性原理重建模型的做法，有人表示会照着复现用于学习，也有人询问系统学习推理实现的路线图。上述 ROCm 成功案例是单个用户报告，不能视为项目在各类硬件上的普遍兼容性证明。

**标签**: `#JAX`, `#DeepSeek V3`, `#LLM inference`, `#open-source implementation`, `#ROCm`

---

<a id="item-tech-news-4"></a>
### [Project Zero 将漏洞披露期限设为 90 天并计划缩短](https://projectzero.google/2026/11/disclosure-policy.html) ⭐️ 7.0/10

Google Project Zero 将把漏洞披露政策改为在向厂商报告后 90 天公开，适用于该团队发现的漏洞。评论中引述的政策文本还称，这一窗口将在 2027 年 2 月 2 日缩短至 60 天，并在 2028 年 1 月 3 日进一步缩短至 30 天；由于帖子未提供完整原文，这些后续日期和阶段只能视为评论转述，尚不能独立核实。

hackernews · hacb · 11月14日 11:13 · [社区讨论](https://news.ycombinator.com/item?id=50496051)

**「背景：协调披露时限」** 漏洞协调披露通常指先向厂商报告并留出修复时间，期限届满后再公开技术细节，以兼顾修复压力和用户防护。评论中引述的 Project Zero 政策文本显示，当前规则为“Full 90”，即报告后 90 天公开；60 天和 30 天则是分别计划于 2027 年 2 月 2 日和 2028 年 1 月 3 日生效的后续阶段。

**「影响」** 对厂商和开源维护者而言，可用的修复窗口将分两步压缩：从当前的 90 天先缩短到 60 天（2027 年 2 月 2 日起），再缩短到 30 天（2028 年 1 月 3 日起）。这意味着依赖 Project Zero 报告来安排补丁节奏的团队，需要在此之前把从收到报告到发布修复的流程压缩到一个月以内，否则就要面对漏洞细节先于补丁公开的局面。评论中也有观点认为，像 Ubuntu 这类涉及大量下游软件包的项目，很难在如此短的期限内完成修复与分发。

**「社区讨论」** 有评论认为 90 天、60 天乃至 30 天的窗口对 Ubuntu 等大型项目仍远远不够，也有评论主张应更早甚至立即公开，因为只有公开压力才会迫使厂商修复。另有评论提出，发现漏洞的公司也应向厂商或开源项目提供类似的产品访问权限，以免披露政策被用作推广自家 LLM 工具的手段。

**标签**: `#vulnerability disclosure`, `#Project Zero`, `#cybersecurity policy`, `#coordinated disclosure`, `#software security`

---

<a id="item-tech-news-5"></a>
### [Cloudflare 开源无状态 AI 代理浏览器 Kitesurf](https://www.phoronix.com/news/Cloudflare-Kitesurf-Open-Source) ⭐️ 7.0/10

Cloudflare 已以 Apache 2.0 许可证在 GitHub 开源 Kitesurf——一个面向 AI 代理的无状态浏览器。它运行在 Cloudflare Workers 上，可解析 HTML、处理 CSS 并执行 JavaScript，无需浏览器容器。Cloudflare 称其目标是提供比 Chromium 更省 CPU 和内存、并能在全球 Workers 网络上按需扩展的轻量方案，但尚未提供独立基准或架构细节来验证这些性能对比。

telegram · zaihuapd · 11月14日 09:33

**「背景」** Cloudflare 将 Kitesurf 定位为面向 AI 代理的实验性浏览器引擎，开发者可以检查代码、在本地运行，或部署到 Cloudflare Workers。其页面隔离依赖 Cloudflare Dynamic Workers，而 Dynamic Workers 属于 Workers 付费计划；同时，它为代理等客户端提供 CDP 端点。

**「影响」** 对在 Workers 上构建代理的开发者而言，Kitesurf 提供了一条不依赖 Chromium 容器的网页处理路径；但公开信息未说明其与 Chromium 的功能兼容范围，开发者在依赖它执行复杂网页 JavaScript 或 CSS 处理前需自行验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.cloudflare.com/kitesurf-open-source/">Kitesurf is now open source | Cloudflare Blog</a></li>
<li><a href="https://github.com/cloudflare/kitesurf">GitHub - cloudflare / kitesurf : Kitesurf is an experimental browser ...</a></li>

</ul>
</details>

**标签**: `#Cloudflare`, `#AI agents`, `#open source`, `#browsers`, `#serverless`

---

<a id="item-tech-news-6"></a>
### [意大利因违规读取相册对 Meta 罚款 8.05 亿欧元](https://www.garanteprivacy.it/home/docweb/-/docweb-display/docweb/10321080) ⭐️ 7.0/10

意大利隐私监管机构 Garante Privacy 对 Meta 处以 8.05 亿欧元罚款，认定 Facebook Android 应用在未取得具体同意的情况下读取了约 2000 万意大利用户的相册照片、视频及元数据。涉事功能是 2023 年上线的相册推荐，默认开启且授权提示笼统；监管机构要求 Meta 在 60 天内改为默认关闭并单独征得用户同意，否则不得向未有效授权的用户启用该功能。

telegram · zaihuapd · 11月14日 14:37

**「背景」** 此案的关键在于 Android 相册权限的授权粒度：据 BBC 报道，Facebook 通过一次应用级授权请求访问用户相册，而意大利监管机构认定，事先提示没有清楚说明该授权还会让 Facebook 根据相册中的照片生成推荐。监管机构据此认为，笼统的一次性授权不足以构成针对相册推荐功能的“具体同意”。

**「影响」** 对意大利的 Facebook Android 用户而言，最直接的变化是相册推荐不能再依靠默认开启获得授权，需单独同意后才能使用；若 Meta 未在 60 天内完成整改，该功能将对未有效授权的用户停用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bbc.com/news/articles/cwn83gxemk35o">Italy fines Meta € 805 m over accessing users&#x27; photos</a></li>

</ul>
</details>

**标签**: `#隐私监管`, `#Meta`, `#移动应用权限`, `#平台合规`, `#意大利`

---

<a id="item-tech-news-7"></a>
### [特斯拉 Cybercab 被曝月租 299 美元才能开动](https://www.tesla.com/configurator/api/v4/terms?category=autonomy_subs&amp;amp;locale=en_US&amp;amp;model=cc&amp;amp;saleType=Sale) ⭐️ 7.0/10

一个 Telegram 频道转述特斯拉条款页面称，Cybercab 售价 29,990 美元，车主必须每月支付 299 美元自主驾驶订阅费，否则车辆无法运行。据该转述，特斯拉可提前一个月通知调价，欠费或违规使用会导致订阅暂停或取消，累计三次警告则停用自动驾驶一周。车辆还被限定在指定区域内运行，未经授权不得接入网约车、配送或租赁平台。上述内容来自二手转述，未经独立核实；Electrek 指出 Cybercab 与用于 Robotaxi 的 Model Y 采用相同的 AI4 硬件并运行相同自动驾驶软件，但面向普通车主的 FSD 仍需人类监督。

telegram · zaihuapd · 11月15日 01:10

**「背景」** 据 Electrek 报道，特斯拉已在得克萨斯州和佛罗里达州运营 Robotaxi 服务，并划定了相应的地理围栏；面向个人销售的 Cybercab 只能在同类服务区域内自动驾驶。该报道还称，这些实际围栏范围明显小于特斯拉对外宣传的范围，因此车主可用的自动行驶区域可能比宣传所示更窄。

**「影响」** 按转述的条款，购车者除支付 29,990 美元车价外，还需持续承担每月 299 美元订阅费，而且订阅被暂停或取消时车辆在条款层面即不可使用，并不存在转为人工驾驶的降级选项。打算将车辆投入网约车、配送或租赁的车主则需先取得授权，否则可能触发停用处罚。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://electrek.co/">Electrek | EV and Tesla News, Green Energy, Ebikes, and more</a></li>

</ul>
</details>

**标签**: `#Tesla`, `#Cybercab`, `#autonomous driving`, `#subscription`, `#robotaxi`

---