---
layout: default
title: "Horizon Summary: 2026-11-28 (ZH)"
date: 2026-11-28
lang: zh
---

> 从 31 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [OpenSec 披露 Linux nfsd 9.8 分预认证漏洞](#item-tech-news-1) ⭐️ 8.0/10
2. [谷歌 DeepCrossAttention 称质量相当下最高提速 3 倍](#item-tech-news-2) ⭐️ 7.0/10
3. [报道称 WebRTC 信用卡盗刷脚本现身购物网站](#item-tech-news-3) ⭐️ 7.0/10
4. [Convex 技能被指未经告知上传应用创意，CEO 回应](#item-tech-news-4) ⭐️ 7.0/10
5. [计算机检查证明的健全性风险](#item-tech-news-5) ⭐️ 7.0/10
6. [多州总检察长起诉 SpaceX，指 Grok 生成儿童性虐待与未经同意的私密图像](#item-tech-news-6) ⭐️ 7.0/10
7. [SemiAnalysis 深度解析 AWS Trainium3 推理与微架构](#item-tech-news-7) ⭐️ 7.0/10
8. [黑客借 AI 工具 Artex 攻击美情报机构](#item-tech-news-8) ⭐️ 7.0/10
9. [《我的世界》基岩版资源包漏洞影响 26.52–26.63，26.65 修复](#item-tech-news-9) ⭐️ 7.0/10
10. [微软拟用 Windows 内置驱动替代部分第三方驱动](#item-tech-news-10) ⭐️ 7.0/10

**财经新闻**
1. [国常会部署稳市：加力发挥“国家队”作用，优化中央汇金类“平准基金”功能](#item-finance-news-1) ⭐️ 8.0/10
2. [央行发布大额存单新规：个人认购起点降至 10 万元](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [OpenSec 披露 Linux nfsd 9.8 分预认证漏洞](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 8.0/10

据 OpenSec 披露，Linux 内核 NFS 服务器组件 nfsd 存在预认证堆溢出漏洞 CVE-2026-99362，CVSS 评分为 9.8，攻击者无需登录，仅通过一条发往 tcp/2049 的连接即可越界写入内核堆并获取 root shell。该漏洞自 2014 年的 Linux 3.16 起存在，影响启用 NFSv4.1 或 4.2 的文件服务器、NAS 和集群存储节点。修复已随 6.12.117、6.18.61、7.3.2 和 7.4-rc1 发布，需升级内核并重启；无法立即升级的环境应通过防火墙限制 tcp/2049 访问，CVE 于 2026 年 11 月 20 日公开。

telegram · zaihuapd · 11月27日 12:57

**「背景」** 该漏洞位于 Linux 内核 nfsd 的 NFSv4.1/4.2 会话回复缓存。Red Hat 的安全说明称，远程客户端可先协商一个极小的缓存回复大小，再发送带有 SEQUENCE 操作的构造复合请求，使服务器把完整回复写入过小的缓冲区，从而触发越界写；这一路径在认证前即可到达。

**「处置建议」** 对运行受影响 nfsd 的文件服务器、NAS 和存储节点而言，在打补丁前将 tcp/2049 暴露给不可信网络就可能被远程获取 root。应升级到 6.12.117、6.18.61、7.3.2 或 7.4-rc1 并重启；无法立即升级时，可用防火墙仅允许可信子网访问 2049，不需要 NFS 的主机可停止并禁用 nfs-server。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://access.redhat.com/security/cve/cve-2026-99362">CVE-2026-99362 - Red Hat Customer Portal</a></li>
<li><a href="https://computingforgeeks.com/nfs2root-cve-2026-99362/">NFS2ROOT (CVE-2026-99362): Check, Patch, Mitigate ...</a></li>
<li><a href="https://rokkhe.hashnode.dev/nfs2root-cve-2026-99362-linux-nfsd">NFS2ROOT (CVE-2026-99362): what it is, who is exposed, and ...</a></li>
<li><a href="https://opensec.in/blog/nfs2root-cve-2026-99362">NFS 2ROOT (CVE-2026-99362): pre-auth root in Linux nfsd | OpenSec</a></li>
<li><a href="https://1275.ru/vulnerability/nfs2root-v-yadre-linux-zakryli-zapis-za-granitsy-v-nfsd_53834">NFS 2ROOT: в ядре Linux закрыли запись за границы в nfsd</a></li>

</ul>
</details>

**标签**: `#Linux kernel`, `#NFS`, `#vulnerability`, `#security`, `#CVE`

---

<a id="item-tech-news-2"></a>
### [谷歌 DeepCrossAttention 称质量相当下最高提速 3 倍](https://research.google/blog/supercharging-transformer-residual-connections/) ⭐️ 7.0/10

Google Research 在博客中介绍了名为 DeepCrossAttention 的 transformer 残差连接方法，声称在模型质量相当的情况下最高可实现 3 倍加速。该性能数字来自谷歌研究自身的博客说明，尚未经过独立复现或第三方基准验证。

hackernews · ComputedCamp995 · 11月27日 23:06 · [社区讨论](https://news.ycombinator.com/item?id=50672565)

**「背景」** Transformer 的传统残差连接会把各层输出沿固定路径相加，Google Research 称这种做法的深层网络中会出现信息稀释。其提出的 DeepCrossAttention（DCA）改用可学习的、输入相关的权重，并通过跨层交叉注意力动态组合此前各层的输出，使模型能够按需关注更相关的历史层信息；arXiv 上 2025 年 2 月的论文已按这一机制描述 DCA。

**「实践影响」** 对希望降低训练成本的团队来说，DCA 提供了一个在不牺牲模型质量目标下提升吞吐的候选方案；但论文所称的“最高 3 倍”加速仍需在自有模型规模和任务上复现，采用前还要确认其跨层注意力实现能与现有残差连接和训练栈兼容。

**「社区讨论」** 评论区有人质疑图表形式，认为用折线连接没有时间关系的不同方法并不合适。另有评论者报告，MTP、Dflash 等衍生优化已在过去两年带来 10 倍 tokens/sec，并追问 DeepCrossAttention 能否叠加达到 30 倍。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://research.google/blog/supercharging-transformer-residual-connections/">Supercharging transformer residual connections - Google Research</a></li>
<li><a href="https://arxiv.org/abs/2502.06785">[2502.06785] DeepCrossAttention: Supercharging Transformer ...</a></li>
<li><a href="https://arxiv.org/abs/2502.06785">[2502.06785] DeepCrossAttention : Supercharging Transformer ...</a></li>
<li><a href="https://www.alphaxiv.org/overview/2502.06785v1">DeepCrossAttention : Supercharging Transformer Residual ...</a></li>

</ul>
</details>

**标签**: `#transformers`, `#model efficiency`, `#Google Research`, `#deep learning`, `#residual connections`

---

<a id="item-tech-news-3"></a>
### [报道称 WebRTC 信用卡盗刷脚本现身购物网站](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

据 Infohawk 报道，热门购物网站上发现了据称使用 WebRTC 的信用卡盗刷脚本，攻击目标是结账页面中的支付卡数据。现有材料没有给出受影响站点名称、脚本样本、感染规模或拦截数据，因此这仍是一则标题层面的安全报告，尚无法独立复核。对电商站点而言，风险指向第三方脚本：页面一旦嵌入外部代码，攻击者就可能借其读取或外传结账信息。

hackernews · scanr · 11月27日 15:40 · [社区讨论](https://news.ycombinator.com/item?id=50668145)

**「背景」** 信用卡盗刷脚本（常被称为 Magecart 类攻击）的典型手法，是在电商结账页面中注入恶意 JavaScript，在用户提交表单时读取卡号、有效期等信息并外传；由于这些脚本往往通过被攻陷的第三方组件（分析、客服、A/B 测试等）进入页面，商家自己的代码审查很难发现。WebRTC 是浏览器内置的实时音视频与点对点传输 API，其数据通道可以绕过部分依赖域名或请求特征的传统流量检测手段，这也是此类脚本被指用来外传数据的技术前提。需要说明的是，本次报道的细节仅来自标题与社区讨论层面，尚无公开的样本分析或受影响站点清单可供核实。

**「对电商站点的影响」** 对受影响的电商网站而言，这类 WebRTC 窃取脚本可绕过 CSP 等传统安全控制，在支付流程中把数据外传，因此仅依赖 CSP 或常规脚本监控不足以发现此类注入。站点运营方应审计并限制第三方脚本，重点监控支付页的脚本变更和 WebRTC 连接，以便在支付数据被大量外传前响应。

**「社区讨论」** 评论者 afavour 认为，问题不在 WebRTC 本身，而在于第三方脚本和检测盲区：同样的数据外传可以用普通 HTTP 请求完成，嵌入第三方脚本的站点始终有风险。jszymborski 则把这类事件视为拦截广告和第三方脚本的理由；另有评论提出广告沙箱、浏览器只渲染数据等方案，但这些是观点而非报道已证实的事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.linkedin.com/posts/chadbarr_webrtc-skimmer-bypasses-csp-to-steal-payment-activity-7442920958270562304-SdXp">WebRTC Skimmer Bypasses CSP to Steal Payment Data from...</a></li>
<li><a href="https://aviatrix.ai/threat-research-center/webrtc-skimmer-bypasses-csp-to-steal-payment-data-from-e-commerce-sites/">WebRTC Skimmer Bypasses CSP to Steal Payment Data from...</a></li>

</ul>
</details>

**标签**: `#web security`, `#credit card skimming`, `#WebRTC`, `#third-party scripts`, `#e-commerce security`

---

<a id="item-tech-news-4"></a>
### [Convex 技能被指未经告知上传应用创意，CEO 回应](https://github.com/convex/convex-backend-skill/issues/64) ⭐️ 7.0/10

一项 GitHub issue 指控 Convex 的 AI 编码技能会在未告知用户的情况下，把用户的应用创意发送到远程服务器；受影响的是使用该技能或插件进行开发的用户。Convex CEO Jamie 在 Hacker News 评论中回应称，该插件中的提示上传用于支撑 Convex 的“quickstart”功能，并称公司近期已关闭端到端 vibe-coding 产品 Convex Chef。现有材料没有给出上传的具体范围、服务器位置或关闭方式，也没有独立验证该指控，因此应将其视为待核实的隐私争议，而非已确认的数据处理事实。

hackernews · MickyTheMouse · 11月27日 18:02 · [社区讨论](https://news.ycombinator.com/item?id=50669765)

**「背景」** Convex 是响应式后端平台，其 AI 编码 skill 是供编程代理读取的 SKILL.md 指令集，用于生成类型安全的 Convex 后端。此次争议集中在 quickstart 与 add 两个 skill：前者被指在 SKILL.md 第 48–56 行把用户的一句话项目想法 POST 到 basic-anteater-667.convex.site，注释称其为 telemetry，且未告知用户想法会离开本机；后者在第 62、64 行从同一主机拉取脚本并直接交给 bash 执行。

**「对开发者的实际影响」** 对使用该 Convex skill 的开发者来说，最直接的后果是：在输入应用构想前，需要先确认是否会触发 quickstart 的提示上传；若不想让构想离开本地环境，就只能避开该功能或转向自托管方案。Convex CEO 的回应把这次上传描述为该功能的实现方式，并未承诺移除，因此这一隐私取舍目前仍由使用者自己承担。

**「社区讨论」** 评论者更关注信任与架构选择：有人主张长期看自托管开放权重模型更可靠，也有人指出提示注入比模型主动恶意调用工具更常见，但明确表示不能据此断定此次事件出于恶意。上述均为评论者观点，并非对事件的独立确认。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/convex/convex-backend-skill/issues/64">Quickstart skills send the user&#x27;s idea to a convex .site host and run...</a></li>
<li><a href="https://www.convex.dev/">Convex | All gas, no breakages</a></li>
<li><a href="https://mcpfield.com/en/skills/convex-backend">convex - backend · Skills · MCP Field</a></li>

</ul>
</details>

**标签**: `#AI coding tools`, `#privacy`, `#security`, `#developer tooling`, `#Convex`

---

<a id="item-tech-news-5"></a>
### [计算机检查证明的健全性风险](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

这篇分析文章讨论形式化证明中的一个风险：证明检查器自身的健全性（soundness）缺陷，可能让计算机“检查通过”的证明实际上为假。文章以 Lean、Metamath 等证明助手和验证器生态为背景，属于分析性论述而非新漏洞公告；评论者补充说，实际接受证明时往往要求多个独立检查器同时通过。

hackernews · \_tk\_ · 11月27日 15:26 · [社区讨论](https://news.ycombinator.com/item?id=50667989)

**「背景」** 所谓可靠性漏洞（soundness bug）是指证明检查器本身的实现缺陷，使它能接受实际上不成立的证明；D. J. Bernstein 的文章讨论的正是这类已报告案例。为降低单一检查器出错的影响，形式化项目会让导出的证明同时经过内核和多个独立检查器复核，有的检查器还附带相对于集合论的形式化可靠性证明。

**「影响」** 对依赖形式化证明的团队，实际影响是单一检查器的“通过”不能单独作为高保障依据；评论指出 Metamath 的 set.mm 和 iset.mm 要求 5 个用不同语言独立实现的验证器同时接受，Lean 生态也有多个检查器。若只部署一个检查器，健全性缺陷就会直接变成错误接受证明的风险。

**「社区讨论」** 评论区的核心分歧在于风险应被强调到什么程度：twotwotwo 和 dwheeler 认为文章低估了多检查器与独立实现的门槛，单个检查器出错并不等于能骗过数学界；gr\_norm 则认为这些系统的健全性缺陷极少，对 99.9% 的软件已足够。andai 还提出另一类问题：代理可能针对自己对需求的错误理解去证明“正确性”，即使证明检查通过，实现仍可能做反。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cr.yp.to/proofs/falseccp.html">False computer - checked proofs (djb)</a></li>
<li><a href="https://mathoverflow.net/questions/518109/after-the-lean-verification-of-the-riemann-hypothesis-proof-what-residual-trust">computer science - After the Lean verification of the... - MathOverflow</a></li>

</ul>
</details>

**标签**: `#formal verification`, `#proof assistants`, `#soundness bugs`, `#Lean`, `#Metamath`

---

<a id="item-tech-news-6"></a>
### [多州总检察长起诉 SpaceX，指 Grok 生成儿童性虐待与未经同意的私密图像](https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform) ⭐️ 7.0/10

美国多名州总检察长对 SpaceX 提起诉讼，指控其子公司 xAI 的聊天机器人 Grok 生成儿童性虐待材料以及未经同意的私密图像（常被称为“报复色情”）。该诉讼的新闻稿发布在弗吉尼亚州总检察长办公室网站上，署名的总检察长为 Jones 与 Rayfield；诉状把 SpaceX 而非仅 xAI 列为被告。现有公开信息只有起诉这一事实本身，未包含具体诉讼请求、参与诉讼的州数量，也未包含 xAI 或 SpaceX 的回应。

hackernews · DeepLogin · 11月27日 19:42 · [社区讨论](https://news.ycombinator.com/item?id=50670855)

**「背景」** 这起诉讼有更早的产品与诉讼背景：Engadget 报道称，诉状指 SpaceX 方面推出 Grok 的“spicy mode”，以吸引数千万新用户，并称该模式可被用于生成儿童性虐待材料。Guardian 报道则称，xAI 已面临多起类似诉讼，其中不少涉及今年初 Grok 防护较松、用户可要求其去除照片中人物衣物的时期；这些均为诉讼中的指控。

**「影响与关注点」** 被告的选择是本轮诉讼的关键：起诉对象是作为 xAI 母公司的 SpaceX，而不只是模型提供方，因此案件将检验母公司是否需要为子公司的模型输出承担法律责任。对提供图像生成功能的产品而言，这意味着内容审核机制与输出限制会成为诉讼中需要举证的核心事实。

**「社区讨论」** 有评论者质疑，这类内容在主流平台上早已被禁止，究竟是 Grok 本身审核过于宽松，还是使用者需要“诱导”它才会生成；另一名评论者则反问，是否也应追究实际制作这些图像的人。还有评论者声称，美国最高法院已裁定，为个人消费而用 AI 制作儿童性虐待材料属于受保护言论，但对涉及真实儿童的内容设有例外；这一说法在讨论中未获独立证实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.engadget.com/2325111/two-states-sue-spacex-over-sexually-explicit-grok-deepfakes/">Two States Sue SpaceX Over Sexually Explicit Grok Deepfakes</a></li>
<li><a href="https://www.theguardian.com/technology/2026/sep/03/elon-musk-ai-grok-child-porn-lawsuit">Child sexual abuse survivor alleges Elon Musk’s AI... | The Guardian</a></li>

</ul>
</details>

**标签**: `#AI safety`, `#generative AI`, `#content moderation`, `#regulation`, `#Grok/xAI`

---

<a id="item-tech-news-7"></a>
### [SemiAnalysis 深度解析 AWS Trainium3 推理与微架构](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 7.0/10

SemiAnalysis 发布了对 AWS Trainium3 推理性能与微架构的技术分析，称 Trainium3 与 TPU 已上线其开源推理基准平台 InferenceX，在生成 token 的总拥有成本（TCO）上与 Nvidia GB300“互有胜负甚至胜出”。文章认为这一优势不只来自亚马逊的低成本供应链，也来自微架构选择：Trainium 以 tile 作为一等原语从零为机器学习负载设计，而 Nvidia 数据中心 GPU 自 2017 年起逐代叠加 AI 专用硬件（Volta 的 Tensor Core、Hopper 的 TMA、Blackwell 的 Tensor Memory）。作者称其 UBenchX 微基准显示，借助 Trainium Descriptor Generation Engines（DGE，对应 Nvidia TMA 与 AMD MI455X TDM），Trainium 能在较小消息尺寸下达到峰值 HBM 带宽利用率（MBU），这在 Nvidia GPU 上无法实现。测试还覆盖 SRAM scratchpad（SBUF 到 PSUM）的周期级延迟与带宽、机架级带宽与延迟、attention 指数运算，以及不同 head\_dim 对 roofline 占比的影响；在 AgentX 端到端智能体负载上，Trainium3 配合 PDS 与 vLLM 的每美元性能在整条 TCO 与 p90 交互性曲线上优于除 Vera Rubin 外的所有加速器。需注意，所给摘录未包含具体基准数值，上述结论来自 SemiAnalysis 自行建模与测量、并获 AWS Annapurna Labs 团队协助验证的分析，而非独立第三方复现。

rss · Semianalysis · 11月27日 15:54

**「背景」** 英伟达的数据中心 GPU 源自图形渲染架构，之后逐代加入 Tensor Core（Volta）、TMA（Hopper）和 Tensor Memory（Blackwell）等 AI 专用单元；Trainium 则是 AWS 从零面向 ML 工作负载设计的加速器，把 tile 作为一等原语。SemiAnalysis 的 InferenceX 用吞吐-延迟帕累托前沿比较各加速器在单位总拥有成本下的推理性能，此次将 Trainium3 纳入同口径测试，才使其与 GB300 的成本对比有据可依。

**「对推理选型的影响」** 对以每 token 成本为决策依据的推理部署方来说，Trainium3 现在已进入 InferenceX 的 TCO 与 p90 交互性前沿曲线，SemiAnalysis 称其 PDS + vLLM 栈在该曲线全段优于除 Vera Rubin 外的所有加速器，这意味着采购比较中可把 GB300 方案与基于 Trainium3 的方案并列评估。但需注意这些数字来自 SemiAnalysis 自建微基准与 InferenceX 提交，且 AWS Annapurna 团队参与了架构讲解和实验验证，实际节省仍需在自有工作负载上复现，同时要确认 vLLM/PDS 路径对所需算子的支持程度；其 DGE 在小消息尺寸下达到峰值 HBM 带宽利用率的结论同样属于该机构的微基准结果，而非独立第三方测量。

**标签**: `#AWS Trainium`, `#AI hardware`, `#inference`, `#microarchitecture`, `#Nvidia`

---

<a id="item-tech-news-8"></a>
### [黑客借 AI 工具 Artex 攻击美情报机构](https://www.forbes.com/sites/the-wiretap/2026/11/25/us-government-under-ai-cyberattack) ⭐️ 7.0/10

一则转述《纽约时报》和《福布斯》报道的 Telegram 消息称，黑客使用名为 Artex 的 AI 工具攻击了美国中央情报局、国家地理空间情报局和国家情报总监办公室，受影响的是非机密侦察数据，攻击看起来不算严重。Artex 可整合多个开源 AI 模型来测试网络和计算机防御；一名中国开发者今年早些时候发布了它，后来将其从自己的 GitHub 账号删除。报道称，Artex 还被用于包括针对欧盟在内的多起攻击，FBI 今年早些时候曾警告网络罪犯和间谍正在广泛使用该工具。上述细节来自二手摘要，未提供攻击时间、规模或具体技术机制。

telegram · zaihuapd · 11月27日 10:42

**「背景」** Artex 是一个 AI 驱动的渗透测试框架，可调用多种模型（包括 Claude、GPT 以及 DeepSeek、GLM 等）自动探测网络和计算机防御。FBI 此前警告称，该工具被用于全球多起攻击，包括 ConnectWise 供应链事件，并可在不到三小时内攻破网络；其开发者随后将 Artex 转为闭源。

**「影响」** 对依赖开源情报分析系统的机构来说，这次事件表明非机密数据同样可能成为突破口：CIA 的开源情报分析系统据报遭入侵，CIA、国家情报总监办公室和国家地理空间情报局的非机密信息受到影响。相关团队应审查此类平台的访问权限与日志，并关注 Artex 这类可整合多个开源 AI 模型的侦察工具。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bleepingcomputer.com/news/security/fbi-warns-artex-ai-hacking-tool-is-powering-global-cyberattacks/">FBI warns ARTEX AI hacking tool is powering global cyberattacks</a></li>
<li><a href="https://techcrunch.com/2026/11/16/fbi-says-artex-ai-open-source-hacking-tool-used-to-breach-networks-in-under-three-hours/">FBI says Artex AI open source hacking tool used to... | TechCrunch</a></li>
<li><a href="https://therecord.media/artex-ai-tool-fbi-flash-alert">FBI flash alert says Artex tool automating cyberattacks at ‘machine...</a></li>
<li><a href="https://www.cnn.com/2026/11/24/politics/cia-odni-hack-unclassified-information">CIA hit by hack impacting unclassified information - CNN</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/hackers-reportedly-breached-cia-intelligence-analysis-system/">Hackers reportedly breached CIA intelligence analysis system</a></li>
<li><a href="https://www.nytimes.com/2026/11/24/us/politics/spy-agencies-computer-network-breaches.html">U.S. Spy Agencies Suffer Breach of Some Unclassified ...</a></li>

</ul>
</details>

**标签**: `#AI security`, `#cyberattack`, `#US intelligence`, `#open-source AI`, `#Artex`

---

<a id="item-tech-news-9"></a>
### [《我的世界》基岩版资源包漏洞影响 26.52–26.63，26.65 修复](https://www.zaikei.co.jp/article/20261119/878386.html) ⭐️ 7.0/10

《我的世界》基岩版存在资源包漏洞：带有 content.zipe 文件的资源包可改动游戏界面框架 Ore UI 的文件并运行隐藏脚本。附加组件开发者 8Crafter 于 11 月 15 日在 Reddit 公开该问题，称已确认影响 26.52 至 26.63 版本，更早版本也可能受影响，覆盖 PC、手机和主机，Java 版不受影响。加入服务器或 Realm 时若开启资源包自动下载，玩家无需手动安装就可能收到问题文件；已列出的利用方式包括删除全部存档、获取玩家 IP，以及在 Windows 上特定条件下无提示打开任意 URI、启动资源包内的批处理文件下载恶意软件。Mojang 已在 26.65 版修复；AxmBro 发布了 Windows 只读检测工具，可查找 content.zipe，但不能判定资源包是否恶意。

telegram · zaihuapd · 11月27日 18:04

**「背景」** Ore UI 是《我的世界》基岩版中驱动几乎所有菜单的 TypeScript/React 界面框架，因此资源包一旦能写入该框架，影响就不再局限于替换材质或界面外观。此次漏洞由附加组件开发者 8Crafter 公开后，Mojang 才以 26.65 热修复处理，相关报道称补丁发布较为低调。

**「影响与应对」** 对玩家而言，加入启用了资源包自动下载的服务器或 Realm 前应升级到 26.65；若无法升级，可关闭自动下载以降低接收问题资源包的风险。AxmBro 的 Windows 只读工具只能发现 content.zipe 的存在，不能判断资源包是否恶意，因此不能替代版本修复。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.techtimes.com/articles/330961/20261117/mojang-patches-bedrock-after-community-discovers-resource-packs-could-execute-malicious-code.htm">Mojang Patches Bedrock After Community Discovers Resource ...</a></li>
<li><a href="https://kaimux.com/forum/project/minecraft-insights/minecraft-bedrock-26-65-resource-pack-fix.1063">Minecraft Bedrock 26.65: the resource pack security fix | KAIMUX</a></li>
<li><a href="https://minecraft.pl/en/news/minecraft-bedrock-mojang-patches-resource-pack-security-hole">Minecraft Bedrock: Mojang patches resource pack security</a></li>

</ul>
</details>

**标签**: `#Minecraft Bedrock`, `#security vulnerability`, `#resource packs`, `#game security`, `#Mojang patch`

---

<a id="item-tech-news-10"></a>
### [微软拟用 Windows 内置驱动替代部分第三方驱动](https://www.techspot.com/news/114721-microsoft-wants-replace-most-third-party-device-drivers.html) ⭐️ 7.0/10

微软在 Ignite 2026 大会上确认，正为整类硬件开发新的 Windows 内置驱动，目标是尽量减少第三方代码进入系统内核，部分第三方驱动未来可能被内置功能取代。打印机是首批重点，近期推出的 Windows Ready Print 模式用于取代旧式第三方打印驱动。Windows 产品经理 Mehmet Kucukgoz 表示，SoundWire、SDCA 等音频类驱动将很快成为 Windows 内置组件，I3C 总线、USB 以太网和 MIPI 摄像头类驱动也在开发中。微软近期还在 Windows 硬件工程大会上推出驱动质量倡议（DQI），以提升驱动可靠性、质量和安全标准，并鼓励第三方开发者及 OEM 定制驱动尽量采用内置驱动思路。

telegram · zaihuapd · 11月28日 02:09

**「背景」** Windows 的驱动通常由硬件厂商提供并运行在内核态，因此驱动质量会直接影响系统兼容性、稳定性和安全性。微软的内置驱动（in-box driver）策略是让系统自带通用驱动，减少对第三方驱动包的依赖；此次在打印机、音频、总线和摄像头等类别上的扩展，正是这一思路的延续。

**「对硬件厂商的影响」** 打印机厂商和用户会最先受到影响：Windows Ready Print 将取代旧式第三方打印驱动，相关厂商应评估设备与内置驱动的兼容性。音频、I3C、USB 以太网和 MIPI 摄像头类驱动仍在开发中，微软未公布时间表，因此这些设备短期内仍可能依赖现有第三方驱动；同时，OEM 定制驱动需遵循 DQI，驱动开发者应检查自有驱动与内置类驱动重叠的部分。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://windowsforum.com/news/microsoft-expands-windows-11-class-drivers-to-reduce-crashes-and-kernel-risks.453854/">Microsoft Expands Windows 11 Class Drivers to Reduce Crashes ...</a></li>
<li><a href="https://finance.biggo.com/news/780e9526-5af6-4c4b-8b8d-f810046e41fa">Microsoft Looks to Replace Most Third-Party Drivers With ...</a></li>

</ul>
</details>

**标签**: `#Windows drivers`, `#Microsoft`, `#kernel security`, `#hardware ecosystem`, `#driver quality`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [国常会部署稳市：加力发挥“国家队”作用，优化中央汇金类“平准基金”功能](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 8.0/10

11 月 27 日国务院常务会议由总理李强主持，会议提出持续完善资本市场稳市机制，加力发挥“国家队”稳市作用，进一步优化中央汇金公司的类“平准基金”功能并提供充足流动性保障。会议同时要求推动上市公司加大分红回购力度、完善保险与企业年金和社保基金等中长期资金入市支持政策，并依法强化全链条监管、查处财务造假和违规减持；上述内容为政策方向，未公布具体规模、时间表或已定稿措施。

telegram · zaihuapd · 11月27日 05:35

**「背景」** 国常会即国务院常务会议；会议所称“国家队”主要指中央汇金公司等承担稳市功能的资金力量，“类‘平准基金’”则指其通过提供流动性等方式平抑市场波动的安排。

**「影响」** 若后续增量政策落地，A 股投资者和上市公司可能分别受到中央汇金增持 ETF 带来的边际买盘、以及分红回购力度加大的影响，但会议未公布资金规模或时间表。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cls.cn/detail/2528462">A股，这些重要托举变量正在集聚</a></li>

</ul>
</details>

**标签**: `#中国资本市场`, `#国常会`, `#中央汇金`, `#平准基金`, `#中长期资金入市`

---

<a id="item-finance-news-2"></a>
### [央行发布大额存单新规：个人认购起点降至 10 万元](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

中国人民银行 11 月 27 日公布《大额存单管理办法》，将个人投资人认购起点定为不低于 10 万元、机构投资人不低于 500 万元，均较 2015 年暂行办法的 20 万元和 1000 万元下调一半，自 2027 年 3 月 21 日起施行。同日公布的《人民币存贷款利率管理规定》要求金融机构自主确定存贷款利率、不得通过高息揽储等不正当手段吸收存款，同样自 2027 年 3 月 21 日起施行。

telegram · zaihuapd · 11月27日 11:36

**「背景」** 此前施行的 2015 年《大额存单管理暂行办法》规定，个人认购起点为 20 万元、机构为 1000 万元；新办法将这两项门槛都下调一半，并从 2027 年 3 月 21 日起取代旧规。

**「影响」** 门槛下调后，存款在 10 万至 20 万元之间的个人投资者可参与大额存单；同时，银行须自主确定存贷款利率，且不得通过高息揽储等不正当手段吸收存款，因此其以高利率争夺存款的空间受到约束。

**标签**: `#大额存单`, `#央行监管`, `#存款利率`, `#银行业`, `#个人金融`

---