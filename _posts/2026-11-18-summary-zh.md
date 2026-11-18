---
layout: default
title: "Horizon Summary: 2026-11-18 (ZH)"
date: 2026-11-18
lang: zh
---

> 从 43 条内容中筛选出 14 条重要资讯。

---

**科技新闻**
1. [Java4Shell：OpenJDK Base64 处理被曝远程代码执行漏洞](#item-tech-news-1) ⭐️ 8.0/10
2. [OpenAI 发布 GPT-6.2 Astra 和 Sol，Astra 降价 20%](#item-tech-news-2) ⭐️ 8.0/10
3. [Solid 2.0 发布：服务端 RPC、实时广播与诊断改进](#item-tech-news-3) ⭐️ 8.0/10
4. [面向编码代理的外部沙箱模式与三种实现](#item-tech-news-4) ⭐️ 8.0/10
5. [Datasette Lite 重写：用 Service Worker 在浏览器运行 Datasette](#item-tech-news-5) ⭐️ 8.0/10
6. [微软 ONNX Runtime 的 GitHub 仓库疑似下线](#item-tech-news-6) ⭐️ 7.0/10
7. [Quad9 退出法国：Cloudflare 称其为 DNS 监管警示信号](#item-tech-news-7) ⭐️ 7.0/10
8. [英伟达停披新加坡销售 实体收入达 1040 亿美元](#item-tech-news-8) ⭐️ 7.0/10
9. [Phrack 第 73 期发布，含 Docker 逃逸与 SSH1 漏洞历史](#item-tech-news-9) ⭐️ 7.0/10
10. [中国完成 Q/V 频段双向 27Gbps 无线通信实验](#item-tech-news-10) ⭐️ 7.0/10
11. [Telegram 据报要求 Bot 与小程序数字商品仅用 Stars 支付](#item-tech-news-11) ⭐️ 7.0/10

**财经新闻**
1. [美国收紧芯片远程访问限制，科技企业面临中国市场取舍](#item-finance-news-1) ⭐️ 7.0/10
2. [英国法庭驳回索尼 PlayStation 商店约 19.7 亿英镑集体诉讼](#item-finance-news-2) ⭐️ 7.0/10
3. [工信部委托中汽协评估 17 家车企 60 天供应商账期](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Java4Shell：OpenJDK Base64 处理被曝远程代码执行漏洞](https://calif.io/java4shell/) ⭐️ 8.0/10

安全研究报道称，OpenJDK 在处理 Base64 时存在未经身份验证的远程代码执行漏洞，编号为 CVE-2026-114938，CVSS 4.0 评分为 9.2，且据称已潜伏近四年。受影响版本包括 Java 17（17.0.6 及之后的整个 17 系列）、21、25 和 27；标准 Java 8/11 通常不受影响，但 Oracle Java 8 Performance Pack 例外。利用条件限定为支持 AVX-512 VBMI 的 x86-64 服务器处理器（约 2021 年起的 Intel Ice Lake 及更新 Xeon、2022 年起的 AMD Zen 4 及更新 EPYC/Ryzen），ARM64 不受影响，并且远程堆布局对 RTT 和抖动敏感。

hackernews · werrett · 11月17日 21:11 · [社区讨论](https://news.ycombinator.com/item?id=50538240)

**「背景」** 该漏洞（CVE-2026-114938）出在 OpenJDK 的优化版 Base64 解码器：在支持 AVX-512 VBMI 的 x86-64 处理器上，解码会进入一条向量化实现，Datadog 安全实验室将其描述为越界写（out-of-bounds write）。该实验室同时指出，拒绝服务是更容易达成的后果，可靠远程代码执行还需针对具体应用和 JVM 环境做额外利用；Tenable 的 FAQ 则记录 Oracle 在 CVSS 3.1 下给出的评分为 8.1。

**「修复与处置」** 对仍运行受影响 OpenJDK 17.0.6 及以后版本、且部署在支持 AVX-512 VBMI 的 x86-64 服务器上的组织，实际影响是必须尽快升级到厂商修复版本；Oracle 已为 Java 17、21、25、27 发布修复构建，Amazon 也发布了修复后的 Corretto 17。资产盘点时还应把 Oracle Java 8 Performance Pack 纳入例外范围，因为标准 Java 8/11 通常不受影响，但该打包版本被列为受影响。

**「社区讨论」** Semgrep 的 ievans 表示已发布免费检测脚本，用于检查 HotSpot VM 等五项条件；他认为利用条件虽然具体，仍会有大量主机受影响。另有评论引用 Twitter 上尚未确认的说法，称漏洞与 Base64 解码的 AVX-512 实现有关，并可用 -XX:UseAVX=2 规避；这属于待验证的社区信息。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://securitylabs.datadoghq.com/articles/java4shell-remote-code-execution-in-openjdk-cve-2026-114938/">Java4Shell: Remote Code Execution in OpenJDK (CVE-2026-114938)</a></li>
<li><a href="https://www.tenable.com/blog/java4shell-cve-2026-114938-frequently-asked-questions-about-openjdk-rce-vulnerability">Java4Shell (CVE-2026-114938): OpenJDK RCE Vulnerability FAQ</a></li>
<li><a href="https://www.cyberkendra.com/2026/11/cve-2026-114938-pre-auth-rce-flaw-in-java-17-puts-servers-at-risk.html">Java 4 Shell (CVE-2026-114938): Java Base 64 Flaw... - Cyber Kendra</a></li>

</ul>
</details>

**标签**: `#Java`, `#OpenJDK`, `#RCE`, `#security vulnerability`, `#Base64`

---

<a id="item-tech-news-2"></a>
### [OpenAI 发布 GPT-6.2 Astra 和 Sol，Astra 降价 20%](https://openai.com/index/introducing-gpt-6-2-astra-sol/) ⭐️ 8.0/10

OpenAI 推出 GPT-6.2 Astra 和 GPT-6.2 Sol，API 模型名分别为 \`gpt-6.2-astra\` 和 \`gpt-6.2-sol\`；Simon Willison 的 LLM 0.38 已支持这两个模型。Astra 定位高难度任务，定价为每百万 token 输入 8 美元、输出 40 美元，是 GPT-6 Astra 的 80%，缓存输入为每百万 0.40 美元；Sol 定位日常任务，维持每百万输入 2 美元、输出 10 美元。Willison 的 pelican 绘图和 Yonkers 动画测试显示两模型可用，但 Yonkers 变形效果不如 Claude Fable 5.2 和 Gemini 4 Carbon；他同时提到 Astra 在部分基准上低于 Fable 5.2，且沟通风格有抱怨。

hackernews · jasondavies · 11月17日 17:46 · [社区讨论](https://news.ycombinator.com/item?id=50535230)

**「背景」** GPT-6.2 延续了 OpenAI 的 Astra/Sol 双线：Astra 面向高难度项目，Sol 面向日常高效工作；此前的 6 Astra 和 6.1 Sol 是同一产品线的上一代版本。此次 API 模型名分别为 gpt-6.2-astra 和 gpt-6.2-sol，LLM 0.38 已加入对这些模型的支持。

**「对开发者的影响」** 对需要长上下文、多轮工具调用的开发者，Astra 的缓存输入价格从每百万 1 美元降到 0.40 美元，直接降低重复上下文的 agent 会话成本；但 HN 评论者 chriddyp 也报告新模型有时“提前结束”并漏掉答案，采用时需把成本节省与任务可靠性一起评估。

**「社区反馈」** HN 评论中，chriddyp 报告其数据分析考试任务里 Astra 成本从约 20 美元降到约 4 美元、Sol 从 2.6 美元降到 1.2 美元，准确率相近，原因包括 token 减少约 20% 和更少工具调用，但也出现提前结束、漏答；Topfi 则批评 OpenAI 展示的 Slideshow、Workbook 和备忘录示例质量差，认为办公任务仍是其弱项。

**标签**: `#OpenAI`, `#GPT-6.2`, `#LLM release`, `#model benchmarks`, `#cost efficiency`

---

<a id="item-tech-news-3"></a>
### [Solid 2.0 发布：服务端 RPC、实时广播与诊断改进](https://www.solidjs.com/blog/solid-2-0-the-long-hold/) ⭐️ 8.0/10

Solid 2.0 已发布，这是一次面向 JavaScript 开发者的重大框架更新，新增服务端 RPC、live 与 broadcast 实时能力，并改进调试诊断。官方博客还设有“Built to Be Written by Agents”部分，但评论者认为其中的诊断改进对手写代码同样有用，并非只服务于代理式开发。当前材料未给出具体迁移细节或独立性能数据。

hackernews · pier25 · 11月17日 18:56 · [社区讨论](https://news.ycombinator.com/item?id=50536387)

**「背景」** Solid 1.0 发布于五年前，其响应式核心是同步的，服务端函数等能力此前由独立的元框架 SolidStart 承担。搜索结果中的报道显示，2.0 的候选版本（RC）于 2026 年 8 月发布，当时 Solid Primitives、Kobalte、Solid Testing Library 等生态库已宣称跟进兼容；此次稳定版则把异步数据纳入响应式图，并将服务端函数并入核心库、不再把 SolidStart 作为独立元框架。

**「影响」** 使用 Solid 的开发者可以直接采用框架内置的服务端 RPC 与 live/broadcast 能力，而不必像评论者所说在 Remix、LiveView 或 htmx/datastar 等方案之间自行拼合前后端中间层；升级现有项目前仍需核对迁移与兼容性说明，因为当前材料未列出具体破坏性变更。

**「社区讨论」** 评论者 pwmglenn 认为 Solid 的服务端 RPC、live 和 broadcast 比 LiveView 或 htmx/datastar 更自然，填补了 Remix 曾试图解决的前后端中间层；wk\_end 则指出“Built to Be Written by Agents”下的改进本质上是更好的调试诊断，对手写代码同样有益。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.solidjs.com/">Solid: Fine-grained reactive UI</a></li>
<li><a href="https://www.solidjs.com/blog/solid-2-0-rc-the-big-reveal">Solid 2.0 RC: The Big | SolidJS</a></li>
<li><a href="https://codingislove.com/solid-2-0/">Solid 2.0 released: async reactivity, server functions, no ...</a></li>

</ul>
</details>

**标签**: `#SolidJS`, `#JavaScript frameworks`, `#frontend development`, `#server RPC`, `#software releases`

---

<a id="item-tech-news-4"></a>
### [面向编码代理的外部沙箱模式与三种实现](https://simonwillison.net/2026/Nov/17/external-sandboxes-for-coding-agents/) ⭐️ 8.0/10

Simon Willison 与 Prime Radiant 公布了面向编码代理的“外部沙箱”模式：代理本身运行在沙箱之外，代理执行的代码则进入专用沙箱。该项目旨在降低试用本地模型时，误操作或提示注入对机器造成破坏的风险。随附发布的三个沙箱服务器实现分别是：用 Node.js 服务和 v86 在 WebAssembly 中运行 Alpine Linux 的 external-sandbox-v86；用 Python 服务在 Apple Containers 中运行 Alpine Linux 的 external-sandbox-container；以及用 Python 服务调用 Microsoft Quicksand（打包了 QEMU 与 Alpine Linux）的 external-sandbox-quicksand。三者提供相同的 localhost API，可让 Pi、Claude Code 或 Codex 将代码执行请求发送到沙箱，并包含可选的 HTTP/HTTPS 允许列表代理和凭据替换机制。

rss · Simon Willison · 11月17日 22:52

**「背景」** 编码代理通常需要执行 shell 命令或运行生成的代码；如果这些代码与代理运行在同一环境中，提示注入或误操作可能直接影响本机。外部沙箱模式将代码执行环境与代理本身隔离，代理只能通过接口调用沙箱中的代码，从而限制代码可访问的资源和网络。

**「影响」** 三个实现共用同一 localhost API，开发者在 v86、Apple Containers 与 Quicksand 后端之间切换时，Pi、Claude Code 或 Codex 的调用方式可以保持一致；允许列表代理限制代理代码可通信的主机，凭据替换机制则让需要认证的 API 调用无需把密钥交给代理。

**标签**: `#AI coding agents`, `#sandboxing`, `#security`, `#prompt injection`, `#developer tools`

---

<a id="item-tech-news-5"></a>
### [Datasette Lite 重写：用 Service Worker 在浏览器运行 Datasette](https://simonwillison.net/2026/Nov/17/datasette-lite/) ⭐️ 8.0/10

Simon Willison 发布了 Datasette Lite 的完整重写版：它通过 Service Worker 配合 WebAssembly 与 Pyodide，把 Datasette Python 应用直接放到浏览器中运行，作者称效果已接近真实的服务端版本。用户可在 lite.datasette.io 上通过 URL 参数加载 SQLite 数据库、JSON、CSV 或 SQL 脚本，从 PyPI 选择已发布的 Datasette 版本，或从 GitHub 指定提交、标签和分支，还可从 100 多个 SQLite 版本中选择。它支持从 PyPI 或 wheel 文件 URL 安装 Datasette 插件，包括 JavaScript 可视化插件；所引用的远程数据库 URL 需要提供开放的 CORS 响应头。

rss · Simon Willison · 11月17日 16:48

**「背景」** Datasette Lite 并非新项目：作者在 2022 年就发布过第一版，当时是在 Pyodide 的 Web Worker 中运行 Datasette，模拟请求后把生成的 HTML 用 \`innerHTML\` 注入顶层页面。由于 \`innerHTML\` 不会执行其中的 \`&lt;script&gt;\` 标签，这一版无法支持依赖 JavaScript 的 Datasette 功能，这也构成了此次改用 service worker 重写的直接背景。

**「影响」** 对插件和 Datasette 本身的开发者而言，这意味着可以把尚未发布的 GitHub 提交或特定 SQLite 版本固化成一条可分享的 lite.datasette.io 链接，用于复现缺陷或演示实验性功能，而无需部署 Web 服务器；代价是所引用的远程数据库文件必须允许跨域访问。

**标签**: `#Datasette`, `#Pyodide`, `#WebAssembly`, `#service workers`, `#SQLite`

---

<a id="item-tech-news-6"></a>
### [微软 ONNX Runtime 的 GitHub 仓库疑似下线](https://github.com/microsoft/onnxruntime) ⭐️ 7.0/10

2026 年 11 月 17 日，Hacker News 上的一则讨论称，微软的 ONNX Runtime GitHub 仓库（microsoft/onnxruntime）已经无法访问。发帖者表示，他们当天早上发现评估流水线开始失败，并称此前没有收到任何预警；该仓库约有 2.2 万个 star。目前没有微软的官方说明，仓库消失的原因也未得到确认，讨论中的安全或供应链猜测均属推测。

hackernews · nvader · 11月17日 23:18 · [社区讨论](https://news.ycombinator.com/item?id=50539610)

**「背景」** ONNX Runtime 是微软提供的跨平台推理与训练机器学习加速器，开发者可在不同平台上运行 ONNX 模型。该项目的 GitHub 仓库此前承载代码和版本发布说明，例如发布说明涉及 WebGPU 插件 EP 的变更。

**「对构建流水线的直接影响」** 对直接从该仓库拉取源码或依赖其构建流程的团队，影响是即时的：有用户在讨论中称当天上午评估任务开始失败，且此前没有任何预警。在官方说明缺失的情况下，可行的应对是改用已发布的包版本，或使用 Intel 的 onnxruntime 分支，但后者带有 OpenVINO 修改，不能当作等价替代。

**「社区讨论」** 有评论者猜测，这可能与微软某个软件包被入侵后的清理有关，也有人提到 ONNX 的遥测行为，或担心被后门的模型可能利用新攻击面，但这些说法都没有证据支持。另有用户指出，目前最接近的上游替代是带有 Intel OpenVINO 修改的 intel/onnxruntime 分支。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/microsoft/onnxruntime">GitHub - microsoft/onnxruntime: ONNX Runtime: cross-platform ...</a></li>
<li><a href="https://github.com/microsoft/onnxruntime/releases">Releases · microsoft/onnxruntime · GitHub</a></li>
<li><a href="https://news.ycombinator.com/item?id=50539610">Microsoft &#x27;s ONNX Runtime has disappeared from GitHub</a></li>

</ul>
</details>

**标签**: `#ONNX Runtime`, `#Microsoft`, `#GitHub`, `#open-source supply chain`, `#AI infrastructure`

---

<a id="item-tech-news-7"></a>
### [Quad9 退出法国：Cloudflare 称其为 DNS 监管警示信号](https://blog.cloudflare.com/quad9-withdrawal-from-france/) ⭐️ 7.0/10

Cloudflare 发布博客文章，将 Quad9 撤出法国定性为 DNS 过滤与互联网监管的“煤矿里的金丝雀”，认为该事件对整个 DNS 生态具有预示意义。文章在技术社区引发讨论，Quad9 首席技术官在评论中谈及此事，称在 IETF 127 现场其立场获得与会者一致支持，且业界对 DNS 相关案件的走向普遍感到忧虑。现有材料不含博客原文，因此 Quad9 撤出所依据的具体法律裁决、时间表与适用范围均未得到说明。

hackernews · subset · 11月17日 22:13 · [社区讨论](https://news.ycombinator.com/item?id=50538994)

**「背景」** Quad9 是面向全球的免费公共递归 DNS 解析服务，会在解析阶段拦截与恶意软件和钓鱼相关的域名。由于它位于用户与目标网站之间的解析环节，DNS 解析器是否应承担内容屏蔽和监管过滤，成为理解此次法国争议的关键背景。

**「实际影响」** 对法国境内使用 Quad9 公共解析服务的用户与机构而言，此次撤出意味着需要改用其他解析器，并重新评估所依赖 DNS 服务在可用性与司法管辖上的风险。Cloudflare 与部分评论者将此案视为先例：在其他司法辖区运营公共 DNS 解析器的机构，可能面临同类要求其进行域名过滤的命令。

**「社区讨论」** 评论者 driverdan 认可文章立场，但批评 Cloudflare 没有作出任何具体承诺，追问其若上诉失败是否也会像 Quad9 一样从受影响国家撤出，而非停留在含糊表态。Quad9 首席技术官 johnhtodd 则表示，IETF 127 上尚未遇到支持“权利方行业”立场的人，并形容现场对 DNS 现状存在一种普遍的担忧情绪。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Quad9">Quad 9 - Wikipedia</a></li>
<li><a href="https://quad9.net/">Quad 9 | A public and free DNS service for a better security and privacy</a></li>

</ul>
</details>

**标签**: `#DNS`, `#internet regulation`, `#privacy`, `#France`, `#Cloudflare`

---

<a id="item-tech-news-8"></a>
### [英伟达停披新加坡销售 实体收入达 1040 亿美元](https://www.ft.com/content/dbde7a30-548c-4f9d-a4be-7898a0c24dcf) ⭐️ 7.0/10

据《金融时报》报道，英伟达已停止单独披露新加坡销售额，而其新加坡实体的对外收入达到 1040 亿美元。该数字是新加坡子公司的对外收入，并非英伟达全球总收入；披露变化发生在外界审视 AI 芯片是否经新加坡转运至中国之际。

hackernews · louiereederson · 11月17日 17:12 · [社区讨论](https://news.ycombinator.com/item?id=50534631)

**「背景」** Nvidia 对新加坡的销售披露之所以受关注，是因为其收入按开票实体归属，而非按芯片最终运往地归属；此前披露显示，记在新加坡名下的收入远高于实际运往新加坡的产品价值。围绕新加坡公司 Megaspeed 的调查在 2025 年推进：CNBC 报道称，调查人员于 2025 年 5 月向 Nvidia 索取与 Megaspeed 直接或间接销售有关的记录，Nvidia 同年 6 月将 Megaspeed 列入“no sell”名单；《海峡时报》称该公司正接受新加坡和美国扩大调查。

**「影响」** 对依赖财报分项追踪英伟达销售流向的投资者和合规团队而言，失去新加坡销售单列数据后，将更难直接评估经新加坡实体流转的规模，需改用其他地区收入拆分或公司评论。

**「社区讨论」** 评论区的核心分歧在于 1040 亿美元应如何解读：有评论者强调这是新加坡子公司的对外收入，包含经该实体下单的 GPU 订单，终端客户通常通过 OEM/ODM 和经销商采购，因此这属于会计归属问题，不能说明芯片最终去向。也有人据此推测芯片经新加坡流入中国，但未提供证据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/17/nvidia-nvda-earnings-report-q3-2027.html">Nvidia (NVDA) Q3 2027 earnings report: Live updates</a></li>
<li><a href="https://www.straitstimes.com/business/the-megaspeed-mystery-whos-the-singaporean-behind-firm-at-centre-of-nvidia-chips-probe">The Megaspeed mystery: Who’s the Singaporean ... | The Straits Times</a></li>
<li><a href="https://www.youtube.com/watch?v=I8Yhx5U_hiQ">NVIDIA ’s $24B Singapore Mystery — What It Means for... - YouTube</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#export controls`, `#AI hardware`, `#Singapore`, `#semiconductor supply chain`

---

<a id="item-tech-news-9"></a>
### [Phrack 第 73 期发布，含 Docker 逃逸与 SSH1 漏洞历史](https://phrack.org/issues/73/introduction_md) ⭐️ 7.0/10

Phrack 第 73 期已在 phrack.org 发布，面向安全研究和技术读者。社区讨论提到本期包含 Docker 逃逸相关文章，以及回顾 2000 年 SSH1 漏洞利用历史的文章。源材料未提供正文，因此这些文章的具体技术细节、漏洞披露状态和是否分配 CVE 暂无法核实。

hackernews · notmine1337 · 11月17日 18:31 · [社区讨论](https://news.ycombinator.com/item?id=50535992)

**「背景」** 据 Zeli 汇总的本期目录，Phrack 第 73 期由新编辑团队策划，是该团队策划的第三期，收录 23 篇主文章和 8 篇 Line Noise 短文。Phrack 官网导言还列出四篇“Phrack World History”文章，其中包括 SSH1 CRC32 漏洞的历史。

**「影响」** 对运行容器的团队来说，本期提到的 Docker 逃逸文章值得对照自查：逃逸通常经由特权容器或内核缺陷突破隔离、触及宿主机，因此应复核是否仍在使用特权容器，并及时跟进内核补丁。不过评论中关于该利用是否已负责任披露、是否分配 CVE 的疑问在讨论里没有得到回答，读者无法仅凭杂志判断其针对的版本与修复状态，宜先核实再据此评估自身风险。

**「社区讨论」** 有评论者询问，Phrack 刊登的 Docker 逃逸等漏洞利用是否已经过负责任披露或分配 CVE，还是直接公开；这一问题在讨论中未被明确回答。另有读者怀念早期安全杂志较不修饰、表达更自由的风格，并将其与当前技术社区中类似简历的发言方式作对比。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://zeli.app/story/50535992">Phrack 73 Arrives With 23 Papers · 28 HN comments | Zeli</a></li>
<li><a href="https://phrack.org/issues/73/introduction_md">Introduction - phrack.org</a></li>
<li><a href="https://www.startupdefense.io/cyberattacks/docker-escape">Docker Escape : A Technical Guide to Container Security Risks</a></li>

</ul>
</details>

**标签**: `#computer security`, `#exploits`, `#Phrack`, `#vulnerability disclosure`, `#technical writing`

---

<a id="item-tech-news-10"></a>
### [中国完成 Q/V 频段双向 27Gbps 无线通信实验](https://www.news.cn/tech/20261117/d6323540dccf4e2a976c48a762795956/c.html) ⭐️ 7.0/10

中科院空天信息创新研究院等单位在丽江中国遥感卫星地面站完成 Q/V 频段高阶体制高码速率双向通信实验，实现我国该频段最高码速率无线通信验证。实验首次系统测试 64QAM 至 512QAM 多种调制模式，512QAM 下单通道双向速率达 6.75 Gbps，结合双载频和极化复用提升至 27 Gbps，刷新国内纪录。团队称关键指标达国内领先、国际先进水平，后续争取超过 50 Gbps；这仍是实验验证，并非已商用的通信系统。

telegram · zaihuapd · 11月17日 08:45

**「背景」** Q/V 频段指毫米波中的 Q 波段和 V 波段，是 6G 与卫星通信关注的高频资源；512QAM 属于高阶正交幅度调制，能在单位符号内承载更多比特，但对链路质量要求更高。此次验证把这些调制方式与双载频、极化复用结合，才达到双向 27 Gbps。

**「对卫星链路的意义」** 这次验证在丽江中国遥感卫星地面站完成，直接对应 Q/V 频段卫星链路的场景；实验首次系统测试了 64QAM 至 512QAM 多种调制模式，为按信道条件选择调制阶数提供了实测依据。不过，27 Gbps 是国内纪录，来自单次地面实验，并非已部署系统；团队仅表示后续争取超过 50 Gbps，未给出时间表，因此现阶段不宜把它当作可用的卫星互联容量。

**标签**: `#6G`, `#Q/V band`, `#satellite communications`, `#wireless communications`, `#512QAM`

---

<a id="item-tech-news-11"></a>
### [Telegram 据报要求 Bot 与小程序数字商品仅用 Stars 支付](https://telegram.me/zaihuapd/45189) ⭐️ 7.0/10

Telegram 据报已通知开发者，Bot 和小程序内的数字商品只能通过 Telegram Stars 销售，以符合苹果和谷歌的应用内购买规则。覆盖范围包括 Bot 订阅、付费工具、第三方 AI 模型访问权限以及积分或代币；涉及加密货币的交易则只能使用 GRAM。本周起官方将主动排查，违规者可能被直接封禁且不再另行警告；该消息来自单一 Telegram 频道投稿，尚未获得独立佐证。

telegram · zaihuapd · 11月17日 14:46

**「背景」** Telegram Stars 是 Telegram 自有的虚拟货币，用户可通过苹果或谷歌的应用内购买，或通过 PremiumBot 充值，再用于在 Bot 中购买电子书、在线课程和游戏道具等数字商品。

**「影响」** 若该政策按通知执行，依赖外部支付、第三方 AI 模型或积分的 Bot 与小程序开发者将需要把收费迁移到 Telegram Stars，或改用 GRAM 处理加密货币交易，否则面临封禁风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://meduza.io/en/news/2026/11/18/telegram-to-bar-in-app-card-payments-for-digital-services-exempting-vpn-bots-in-authoritarian-countries">Telegram to bar in - app card payments for digital services... — Meduza</a></li>
<li><a href="https://telegram.org/blog/telegram-stars">Telegram Stars : Pay for Digital Goods and More</a></li>

</ul>
</details>

**标签**: `#Telegram`, `#platform policy`, `#payments`, `#bots`, `#app store rules`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美国收紧芯片远程访问限制，科技企业面临中国市场取舍](https://www.cnbc.com/2026/11/17/us-tech-firms-china-ties-political-pressure.html) ⭐️ 7.0/10

特朗普政府于周一收紧限制，禁止中国公司远程使用美国先进芯片，以阻止它们通过海外数据中心绕过出口管制。此前一天，包括新加坡和英国在内的九个国家签署了美国国务院的《旧金山宣言》，承诺保护敏感技术。

rss · CNBC Finance · 11月17日 08:52

**「背景」** 上周，英伟达 CEO 黄仁勋因外遇报道辞职，其中涉及一名被美国情报部门怀疑为中国间谍的女性；本周一，特朗普政府收紧规定，限制中国企业通过海外数据中心远程使用先进美国芯片；周日，包括新加坡和英国在内的九国签署了美国国务院的《旧金山宣言》，承诺保护敏感技术。

**「影响」** 英伟达、苹果等美国科技公司因此需要在继续留在中国市场与规避供应链及政治风险之间权衡：大中华区约占苹果销售额的 15%，而中国在稀土等关键矿产供应链上占据主导地位，一旦北京采取反制，这些企业将直接承受冲击。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://apnews.com/article/nvidia-jensen-huang-resigns-ceo-affairs-314714d463cf578cbb0dbd49de903107">What we know after Jensen Huang resigns as Nvidia CEO</a></li>
<li><a href="https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/">US to curb China&#x27;s access to AI chips as Trump heads to Asia</a></li>
<li><a href="https://www.industry.gov.au/publications/san-francisco-declaration-secure-foundations-enduring-prosperity-signed-countries-attending-pax-silica-summit-15-november-2026">The San Francisco Declaration on the Secure Foundations of ...</a></li>

</ul>
</details>

**标签**: `#US-China relations`, `#semiconductor export controls`, `#Nvidia`, `#Apple`, `#rare earths`

---

<a id="item-finance-news-2"></a>
### [英国法庭驳回索尼 PlayStation 商店约 19.7 亿英镑集体诉讼](https://www.reuters.com/world/sony-defeats-2-billion-uk-claim-over-playstation-store-pricing-2026-11-17/) ⭐️ 7.0/10

11 月 17 日，英国竞争上诉法庭驳回了一项针对索尼的约 19.7 亿英镑集体诉讼；该案指控索尼滥用市场支配地位，抬高 PlayStation 商店数字内容价格，代表约 1220 万英国消费者。法庭认定，游戏主机之间的竞争已限制索尼的定价空间。

telegram · zaihuapd · 11月17日 16:02

**「背景」** 该案由 Alex Neill Class Representative Limited 代表约 1220 万英国消费者提起，是英国竞争上诉法庭审理的“选择退出”式集体诉讼：符合条件的消费者默认被纳入，除非主动退出。

**「影响」** 这起诉讼被驳回后，约 1220 万名潜在集体成员目前无法通过该案获得赔偿。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.brickcourt.co.uk/news/detail/competition-appeal-tribunal-dismisses-2-billion-playstation-class-action-against-sony">Competition Appeal Tribunal dismisses £2 billion PlayStation ...</a></li>

</ul>
</details>

**标签**: `#Sony`, `#PlayStation Store`, `#UK competition law`, `#class action`, `#digital platforms`

---

<a id="item-finance-news-3"></a>
### [工信部委托中汽协评估 17 家车企 60 天供应商账期](http://www.caam.org.cn/chn/5/cate_68/con_5237404.html) ⭐️ 7.0/10

中国汽车工业协会 11 月 16 日发布通知称，受工信部委托作为第三方机构，对 17 家重点车企的供应商账款支付情况开展调研评估，核查 60 天账期是否落地。评估内容包括中小企业账期是否不超过 60 天，以及非中小企业现金和银行承兑汇票支付比例不低于 80%等，名单包括一汽、上汽、比亚迪、理想、蔚来、小鹏、小米汽车、零跑等。

telegram · zaihuapd · 11月18日 01:15

**「背景」** 此前，17 家重点车企曾公开承诺供应商支付账期不超过 60 天，中汽协随后明确账期自验收合格之日起算；此次受工信部委托的评估，正是核查这一承诺是否落地。

**「影响」** 对为这 17 家车企供货的中小零部件企业来说，评估结果公开发布可能形成回款压力，从而缩短其应收账款周期、改善现金流；但据 14 家上市公司财报估算，车企承诺 60 天账期一年后无一家达标，最长账期达 280 天，实际改善仍待观察。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bjnews.com.cn/detail/1757908524168188.html">多 家 车 企 响应 中 汽 协 “ 60 天 账 期 ”倡议 — 新京报</a></li>
<li><a href="https://news.qq.com/rain/a/20260907A0CGJS00">厘清关键要素、引入第三方调研 评 估 汽 车 行业 账 期 进入“强监管”_腾讯新闻</a></li>
<li><a href="https://www.huxiu.com/article/4891734.html">汽车公司承诺&#x27;60天账期&#x27;一年后，财报显示没有一家能够达标</a></li>

</ul>
</details>

**标签**: `#China auto industry`, `#supply chain finance`, `#payment terms`, `#regulatory oversight`, `#SME suppliers`

---