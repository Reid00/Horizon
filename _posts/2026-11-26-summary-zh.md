---
layout: default
title: "Horizon Summary: 2026-11-26 (ZH)"
date: 2026-11-26
lang: zh
---

> 从 35 条内容中筛选出 10 条重要资讯。

---

**科技新闻**
1. [1Password 确认安全事件，部分客户账户信息被窃](#item-tech-news-1) ⭐️ 8.0/10
2. [Anthropic 的 GRH Lean 验证出现约 7.6 万行精简版](#item-tech-news-2) ⭐️ 8.0/10
3. [Minecraft Java 版曝高危 RCE，1.20.5 起受影响](#item-tech-news-3) ⭐️ 8.0/10
4. [Scott Aaronson 博文指向“矩阵乘法指数为 9/4”的论文](#item-tech-news-4) ⭐️ 7.0/10
5. [Google Research 发布整数分解与离散对数论文合集](#item-tech-news-5) ⭐️ 7.0/10
6. [SemiAnalysis 发布 GDPx 基准，评估近期前沿模型](#item-tech-news-6) ⭐️ 7.0/10
7. [腾讯开源 Hy4 flash GGUF 量化权重，最小版可在 64GB Mac mini 运行](#item-tech-news-7) ⭐️ 7.0/10
8. [三星与 SK 海力士据悉将采用长江存储 Xtacking 技术](#item-tech-news-8) ⭐️ 7.0/10

**财经新闻**
1. [美商务部被曝施压英特尔交出 10%股份](#item-finance-news-1) ⭐️ 9.0/10
2. [美国拟对 14 个贸易伙伴加征第 301 条新关税](#item-finance-news-2) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [1Password 确认安全事件，部分客户账户信息被窃](https://1password.com/blog/update-on-nov-2026-security-incident) ⭐️ 8.0/10

1Password 确认发生安全事件：攻击者入侵一名员工的企业 GitHub 账户，访问源代码并向后台服务推送恶意代码，导致部分客户账户信息被下载。被窃信息包括姓名、邮箱地址、账户标识以及账户创建和最近登录时间；客户保险库及其内容未受影响。公司未披露受影响用户数量，已停用涉事账户、轮换或撤销可能暴露的内部凭证，并加强邀请和恢复邮件的验证码；1Password 表示用户无需更改账户，但应警惕钓鱼。

hackernews · lxhrstn · 11月25日 17:18 · [社区讨论](https://news.ycombinator.com/item?id=50644817)

**「背景」** 对 SaaS 密码管理器而言，源代码仓库和后台部署权限是高价值目标：员工账户一旦被攻破，攻击者可能借代码推送进入生产服务。1Password 此次披露的核心入口正是员工企业 GitHub 账户和后台代码推送链路，而非客户保险库内容被解密。

**「影响」** 受影响客户面临更高的定向钓鱼风险：泄露的姓名、邮箱、账户标识和登录时间可被用于伪造共享保险库或账户通知；1Password 表示用户无需更改账户，但应警惕钓鱼。

**「社区讨论」** tptacek 认为，员工终端被攻破后攻击者向 GitHub 推送代码、代码再被部署，是 SaaS 公司的标准入侵路径，且员工规模越大风险越接近必然；ctidd 质疑 1Password 是否缺少对 main 分支的推送保护，或相关规则被绕过。qixxiq 则报告收到一封包含部分个人细节、来自非官方域名的钓鱼邮件。

**标签**: `#security incident`, `#password managers`, `#SaaS security`, `#supply chain security`, `#phishing`

---

<a id="item-tech-news-2"></a>
### [Anthropic 的 GRH Lean 验证出现约 7.6 万行精简版](https://github.com/lsernau/grh-lean) ⭐️ 8.0/10

GitHub 上出现了一个更短、更易读的 GRH Lean 验证版本，社区讨论称其把证明从约 1700 万行压缩到约 7.6 万行。该版本还按“已知数学”和“新数学”分区，并配有较完整的人类可读文档，便于审阅和消化。相关说法来自项目分析与 Hacker News 评论，仓库并非 Anthropic 官方发布，也未见同行评审；因此行数缩减和可读性提升应视为社区报告，而非已独立验证的结论。

hackernews · nb-t · 11月25日 21:48 · [社区讨论](https://news.ycombinator.com/item?id=50648050)

**「背景」** Lean 是交互式定理证明器，形式化验证需要把数学论证写成可被机器逐行检查的代码，因此代码规模会直接影响编译、审阅和社区理解成本。此前公开的这份 GRH 验证没有配套论文，而是以约 175,187 个文件、约 1,740 万行 Lean 代码的归档形式出现；据对该归档的独立编译统计，它可在单台 Mac 上以 0 错误完成编译，耗时约 36 小时 44 分钟。

**「影响」** 对需要审计或复用该形式化证明的 Lean 用户而言，更短的行数和分区文档降低了浏览、比对与教学成本；但由于仓库非官方且未经同行评审，它不能替代对原证明或 GRH 数学结论的独立核验。

**「社区讨论」** 评论者称赞精简版把“已知数学”和“新数学”分开，并配有可读文档，认为这有助于消化；也有人追问这是否回应了陶哲轩一个月前关于“巨大证明缺乏洞见”的担忧，并希望有数学家以论文或会议报告讲清核心论证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=aDl7-MWFLVc">17 Million Lines Claim to Prove Riemann. We Ran Them. - YouTube</a></li>

</ul>
</details>

**标签**: `#Lean`, `#formal verification`, `#proof engineering`, `#AI-assisted mathematics`, `#GRH`

---

<a id="item-tech-news-3"></a>
### [Minecraft Java 版曝高危 RCE，1.20.5 起受影响](https://github.com/bikini/minecraft2shell) ⭐️ 8.0/10

11 月 22 日公开的 minecraft2shell 显示，服务器资源包中的特制 TrueType 字体可触发 FreeType 2.14.3 及更早版本的原生越界写，并在 Java 版 26.3 Windows 客户端执行任意代码。受影响范围为 Java 版 1.20.5 至 1.21.10 以及 26.1 至 26.4 快照，1.20.4 及更早版本和基岩版不受影响。Mojang 目前仍使用 lwjgl-freetype 3.4.3，尚无官方补丁。社区在 11 月 24 日发布 m2sfix 1.0.0，可通过 Java agent 或 mod 关闭 hinting；投稿人建议修复前不要添加资源包，或将多人游戏服务器资源包权限设为“禁用”。

telegram · zaihuapd · 11月25日 12:46

**「背景」** 服务器可要求 Minecraft Java 版客户端加载资源包，而资源包能携带自定义 TrueType 字体；客户端通过 LWJGL 的 lwjgl-freetype 绑定调用原生 FreeType 字体引擎来渲染这些字体。由于渲染发生在 JVM 之外的本地内存中，FreeType 2.14.3 及更早版本的越界写一旦被特制字体触发，就可能直接导致原生代码执行。

**「影响与处置」** 对多人服务器运营者来说，风险来自服务器下发的资源包，而不只是玩家自行安装的内容；在官方修复前，应关闭资源包下发或让客户端安装 m2sfix 以降低触发面。

**标签**: `#security`, `#RCE vulnerability`, `#Minecraft`, `#FreeType`, `#mitigation`

---

<a id="item-tech-news-4"></a>
### [Scott Aaronson 博文指向“矩阵乘法指数为 9/4”的论文](https://scottaaronson.blog/?p=10379) ⭐️ 7.0/10

Scott Aaronson 发布了一篇以连续惊叹词为标题的博文，正文并未展开技术论证，而是给出“另见”链接，指向一份题为《矩阵乘法指数是九分之四》\(The matrix multiplication exponent is nine fourths\) 的 PDF，以及该 PDF 在 Hacker News 上的讨论帖。就所提供的摘录而言，其中没有出现作者、证明方法、验证状态或同行评审信息，因此这只是一个被提出的结果，而非已被确认的进展。博文标题的情绪强度与摘录中可核查的技术内容之间存在明显落差，读者目前无法据此判断该指数界是否成立。

hackernews · Kotlopou · 11月25日 19:11 · [社区讨论](https://news.ycombinator.com/item?id=50646108)

**「背景：矩阵乘法指数 ω」** 矩阵乘法指数通常记作 ω，用来描述计算两个 n×n 矩阵相乘所需算术运算量随 n 增大的增长速度；ω 越小，对应的算法在渐近意义上越快。Scott Aaronson 所指向的 OpenAI math 仓库预印本（标注日期为 2026 年 11 月 24 日）声称该指数为 9/4，即 2.25，这一说法仍需独立验证。

**「社区讨论」** 评论者 jsLavaGoat 认为，AI 在公理化数学这类分析性、先验性工作上表现良好，但这不能推出它同样能“解决”其他领域的问题，两者之间没有必然的逻辑联系。另一位评论者 utopiah 则提出反向假设：如果没有 LLM 或生成式 AI，仅靠 Lean（2013 年）、MathLib（2017 年）以及大量算力，类似进展是否早已在酝酿之中，当前的时间点或许只是因为大公司补贴算力而显得巧合。这些都属于个人观点与推测，不构成对论文结论的验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf">math/preprints/The- matrix - multiplication - exponent -is...</a></li>
<li><a href="https://interestingengineering.com/culture/openai-exact-2-25-matrix-multiplication-exponent">OpenAI establishes exact 2.25 exponent for matrix multiplication</a></li>

</ul>
</details>

**标签**: `#AI and mathematics`, `#matrix multiplication`, `#complexity theory`, `#Hacker News discussion`, `#Scott Aaronson`

---

<a id="item-tech-news-5"></a>
### [Google Research 发布整数分解与离散对数论文合集](https://github.com/google-research/google-research/tree/master/cogentic_research_papers) ⭐️ 7.0/10

Google Research 已在 google-research 仓库的 cogentic\_research\_papers 目录下发布一组论文，主题包括整数分解、离散对数及相关方向。现有材料只有仓库链接，没有论文摘要、具体结果或独立验证，因此尚不能判断这些工作对公钥密码学的实际影响。对密码学研究者而言，这是一批需要直接阅读原文才能评估的新资料。

hackernews · rgwohlbold · 11月25日 13:33 · [社区讨论](https://news.ycombinator.com/item?id=50642086)

**「背景」** 整数分解与离散对数是计算数论中的两类经典难题，其计算难度被用作许多公钥密码方案的安全假设。既有研究包括刷新分解或离散对数记录的计算、对筛选步骤的分析，以及基于同余组合的基本算法。

**「社区讨论」** 有评论者把该合集与所谓“更大突破”的传闻以及 AI 推动数学发现的趋势联系起来，但这些说法多为猜测，未提供可核验的论文结果或技术细节。

<details><summary>参考链接</summary>
<ul>
<li>New Records for Integer Factorization and Discrete Logarithm</li>
<li>[PDF] The filtering step of discrete logarithm and integer factorization algorithms</li>
<li>[PDF] Integer factorization and discrete logarithm problems - CRIStAL</li>

</ul>
</details>

**标签**: `#cryptography`, `#integer factorization`, `#discrete logarithms`, `#Google Research`, `#research papers`

---

<a id="item-tech-news-6"></a>
### [SemiAnalysis 发布 GDPx 基准，评估近期前沿模型](https://newsletter.semianalysis.com/p/evaluating-recent-model-releases) ⭐️ 7.0/10

SemiAnalysis 发布了 GDPx 基准，用于衡量前沿模型在最具经济价值领域的进展；该基准与 14 家专业数据伙伴合作构建了 206 项任务，覆盖芯片设计、网络安全、生物、金融、法律、量化交易、递归自我改进、硬件设计、材料科学、对齐和软件工程，并刻意排除政府和房地产等行业。SemiAnalysis 称，发布日得分最高的 Opus 5.5 仅达到 12%，远低于许多新基准首日超过 50% 的水平，目的是保留区分未来模型的空间。文章还用 GDPx 评估了 Anthropic、OpenAI、Google Gemini 4 系列以及阿里巴巴、Moonshot 的近期发布，但所给摘录未包含具体排名和分数。

rss · Semianalysis · 11月26日 00:05

**「背景」** 在 GDPx 之前，衡量智能体能力的基准大多只覆盖单一领域（如编程或法律）；少数试图做到全面的基准，如 OpenAI 的 GDPVal 和 Agent&\#x27;s Last Exam，则按行业占 GDP 的比重或 O\*NET 职业分类来挑选领域。SemiAnalysis 认为这种选法忽略了 AI 影响在经济中分布极不均衡，因此 11 月 1 日发布的 GDPx 改按“前沿模型影响最大的领域”取样，并刻意保持高难度：发布当天得分最高的 Opus 5.5 仅得 12%，而 Terminal Bench 4.0 等基准已接近饱和。

**「影响」** 对使用基准比较模型的人来说，GDPx 的结果需要结合评分口径解读：SemiAnalysis 指出，Fable 5.2 和 GPT-6.2 Astra 的总分因安全分类器而被人为压低；若排除网络安全、生物和对齐三个领域，并对默认二值评分的法律、金融改用部分评分，排行榜会发生变化。因此，直接横向比较总分可能低估受安全策略影响的模型，读者应确认结果是否包含拒答以及采用何种评分方式。

**标签**: `#AI benchmarks`, `#frontier models`, `#model evaluation`, `#agentic AI`, `#GDPx`

---

<a id="item-tech-news-7"></a>
### [腾讯开源 Hy4 flash GGUF 量化权重，最小版可在 64GB Mac mini 运行](https://mp.weixin.qq.com/s/o0xxShVQX6g2UllrrEv1WQ) ⭐️ 7.0/10

腾讯混元通过 AngelSlim 开源了 224B 参数模型 Hy4 flash 的 GGUF 量化权重：原始权重约 410.27GiB，最小的 IQ2-AH 版本为 125.73GiB，约为原版的 30%。该最小版本借助 Strata offload 框架可在 64GB Mac mini 上运行。公布数据显示，48GB 显存设备在 10K 上下文下每秒生成 89 个 token，M5 Max 128GB 上 Q3\_K 版本在 32K 上下文下为每秒 47 个 token；在 DeepSWE v1.1 等评测中，Q3\_K 与原模型得分差距不超过 0.4 分。

telegram · zaihuapd · 11月25日 09:29

**「背景」** GGUF 是面向本地推理的模型权重封装格式，量化通过降低权重精度来压缩模型体积和内存占用；AngelSlim 则是腾讯混元用于模型压缩与加速的工具箱。Offload 通常指把部分模型权重移出高速内存或显存、在推理时按需调入，从而降低硬件门槛；此次 Hy4 flash 的最小量化版正是借助 Strata offload 框架，才具备在 64 GB Mac mini 上运行的可能。

**「影响」** 对 64GB Mac mini 用户，最小 IQ2-AH 版 125.73GiB 权重需借助 Strata offload 才能运行；该模型支持 1M token 上下文、每 token 12B 激活参数，因此长上下文本地推理会受 offload 与内存带宽限制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/tencent/Hy4-flash">tencent / Hy 4 - flash · Hugging Face</a></li>

</ul>
</details>

**标签**: `#Tencent Hunyuan`, `#model quantization`, `#GGUF`, `#local inference`, `#Apple Silicon`

---

<a id="item-tech-news-8"></a>
### [三星与 SK 海力士据悉将采用长江存储 Xtacking 技术](https://tech.ifeng.com/c/8yLRPKxQy4L) ⭐️ 7.0/10

据报道，三星电子和 SK 海力士已通过交叉许可协议，同意在 3D NAND 闪存中采用长江存储 Xtacking 堆叠技术的部分技术。该消息尚未得到三方确认，三星、SK 海力士和长江存储均拒绝置评。Xtacking 将存储单元与控制电路（CMOS）分别制作在两片晶圆上再键合，使两部分可独立生产和优化；Omdia 高级分析师称，厂商因此可自行生产存储阵列，并把逻辑电路交给晶圆代工厂以使用更先进制程。

telegram · zaihuapd · 11月25日 14:33

**「技术背景」** Xtacking 的基本做法是把 3D NAND 的存储单元阵列与控制电路（CMOS）分别放在两片晶圆上制造，再通过晶圆键合合为一体，因此两部分可以独立生产和优化。按报道中 Omdia 分析师的说法，这种分工还允许厂商自行生产存储阵列、把逻辑电路交给晶圆代工厂，从而采用更先进的制程。

**「影响」** 若授权落地，三星和 SK 海力士可在 3D NAND 中把存储阵列与 CMOS 逻辑分片制造，并将逻辑部分交给代工厂使用更先进制程，这会改变其制造分工与代工依赖；但三方均拒评，授权范围、产品和时间表未披露，目前只能视为未确认的采用计划。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.techpowerup.com/355199/samsung-and-sk-hynix-to-license-ymtcs-xtacking-technology">Samsung and SK hynix to License YMTC &#x27;s Xtacking ... | TechPowerUp</a></li>

</ul>
</details>

**标签**: `#3D NAND`, `#semiconductor manufacturing`, `#Xtacking`, `#Samsung`, `#SK Hynix`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美商务部被曝施压英特尔交出 10%股份](https://www.wired.com/story/inside-trumps-demands-to-another-chips-ceo/) ⭐️ 9.0/10

据 WIRED 引述法庭文件报道，美国商务部律师在 2025 年 8 月与英特尔首席财务官的电话中警告，不要误以为这是一场谈判，董事会可以拒绝，但会面临不可预测的后果。几天后，英特尔董事会交出了约 10%股份，现值约 110 亿美元，美方未支付对价。

telegram · zaihuapd · 11月25日 13:25

**「背景」** 这些指控出现在英特尔股东诉讼中解封的法庭文件里；文件称，商务部律师 David Shapiro 在 2025 年 8 月告诉英特尔 CFO，拒绝约 10% 股权要求会带来“无法预料”的后果，而相关报道将这一要求与英特尔此前获得的约 89 亿美元补贴联系起来。英特尔董事会会议纪要曾称条款“缺乏吸引力”，但最终接受。

**「影响」** 对英特尔而言，美国政府由此成为其最大股东，将在公司治理和重大决策上拥有直接影响力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/wired-commerce-lawyer-warned-intel-cfo-rejecting-us-10-stake-would-carry">Court records: Commerce threatened Intel CFO over 10% US stake</a></li>
<li><a href="https://www.gate.com/news/detail/us-commerce-department-threatened-intel-over-10-equity-stake-for-89b-25860002">U.S. Commerce Department Threatened Intel Over 10% Equity ...</a></li>
<li><a href="https://finance.biggo.com/news/1eea079d-982e-483f-be72-28381b50b545">Unsealed Filings Allege White House Pressured Intel Board ...</a></li>
<li><a href="https://www.softwareseni.com/us-government-equity-stakes-in-intel-industrial-policy-or-nationalisation/">US Government Equity Stakes in Intel: How a $8.9B Grant ...</a></li>

</ul>
</details>

**标签**: `#Intel`, `#US government equity stake`, `#semiconductor policy`, `#corporate governance`, `#industrial policy`

---

<a id="item-finance-news-2"></a>
### [美国拟对 14 个贸易伙伴加征第 301 条新关税](https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html) ⭐️ 8.0/10

据报道，美国政府拟依据 1974 年《贸易法》第 301 条，对中国、欧盟、日本、印度等 14 个贸易伙伴加征国别设定的新关税，理由是制造业结构性产能过剩。报道称，中国将在 2018 年已加征的 25%基础上再加征 20%，若未遵守 2025 年 10 月在韩国釜山达成的贸易休战协议，对华新关税可能升至 40%。

telegram · zaihuapd · 11月25日 13:59

**「背景」** 美国贸易代表办公室 11 月 25 日依据 1974 年《贸易法》第 301 条——该条款允许美国对认定不公平的外国贸易做法加征关税——认定 14 个经济体的制造业结构性产能过剩做法不合理并提议征税。此举把相关调查推进到拟议行动阶段，关税尚未最终生效。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://ustr.gov/about/policy-offices/press-office/press-releases/2026/november/ustr-makes-determinations-and-proposes-actions-14-section-301-investigations-relating-structural">USTR Makes Determinations and Proposes Actions in 14 Section ...</a></li>
<li><a href="https://www.hklaw.com/en/insights/publications/2026/11/ustr-proposes-tariffs-following-14-section-301">USTR Proposes Tariffs Following 14 Section 301 Manufacturing ...</a></li>

</ul>
</details>

**标签**: `#US trade policy`, `#Section 301 tariffs`, `#US-China trade`, `#global trade`, `#manufacturing overcapacity`

---