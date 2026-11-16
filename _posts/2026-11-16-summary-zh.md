---
layout: default
title: "Horizon Summary: 2026-11-16 (ZH)"
date: 2026-11-16
lang: zh
---

> 从 36 条内容中筛选出 7 条重要资讯。

---

**科技新闻**
1. [美团开源 1.6 万亿参数 LongCat-2.5，称未用英伟达 GPU 训练](#item-tech-news-1) ⭐️ 8.0/10
2. [Sebastian Raschka 解析现代 LLM 的位置嵌入](#item-tech-news-2) ⭐️ 7.0/10
3. [MacBook Pro OLED 屏的 PWM 频闪问题](#item-tech-news-3) ⭐️ 7.0/10
4. [Protomaps：自托管地图瓦片更便宜、更简单](#item-tech-news-4) ⭐️ 7.0/10
5. [Meta FAIR 与 NYU：视觉编码器预训练可省，视觉专用参数不可省](#item-tech-news-5) ⭐️ 7.0/10

**财经新闻**
1. [卢特尼克因英伟达“间谍”风波受质询，其子执掌的公司与英伟达有业务往来](#item-finance-news-1) ⭐️ 7.0/10
2. [美法官驳回美光、三星、SK 海力士 DRAM 价格操纵案撤诉动议](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [美团开源 1.6 万亿参数 LongCat-2.5，称未用英伟达 GPU 训练](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

美团 LongCat 团队在模型正式发布一周后公开了 LongCat-2.5 的权重，这是一个面向编程和多步骤自主任务的智能体模型，采用 MIT 许可证并允许商用。模型总参数为 1.6 万亿，每个 token 激活约 480 亿参数，支持文本、图像和视频输入。官方称其训练全程使用华为升腾加速卡、未使用英伟达 GPU，但这一说法目前来自厂商，尚未见独立验证。官方公布的 Terminal Bench v2.1 得分为 88.4，略低于 Claude Opus 5 的 89.1。

telegram · zaihuapd · 11月15日 11:08

**「背景」** LongCat 是美团旗下的大模型团队，其上一代 LongCat-2.0 已采用 1.6 万亿总参数的 MoE 架构、MIT 许可证，并原生支持 100 万 token 上下文，定位为编程模型（tool-2-2）。据第三方报道，该系列训练所用的华为升腾 910C 由中芯国际 7nm 工艺制造，单卡性能约为英伟达 H100 的 60%（tool-2-1）。LongCat-2.5 延续了 1.6 万亿总参数、每 token 激活约 480 亿的规格（Hugging Face 模型卡），但转向原生多模态输入与长程智能体任务（tool-2-3）。

**「影响」** MIT 许可证允许商用，开发者和企业可直接下载、修改这些权重并用于商业产品；但官方基准分数和“全程升腾、未用英伟达 GPU”的说法尚未独立验证，采用前应自行复现或核验。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thesynthesis.ai/journal/the-delivery">The Delivery: Meituan &#x27;s 1 . 6 - Trillion - Parameter AI Model Trained ...</a></li>
<li><a href="https://chatforest.com/builders-log/meituan-longcat-2-0-owl-alpha-openrouter-chinese-asic-coding-model-builder-guide/">LongCat - 2 .0: The Trillion - Parameter Coding Model... — ChatForest</a></li>
<li><a href="https://huggingface.co/meituan-longcat/LongCat-2.5">meituan - longcat / LongCat - 2 . 5 · Hugging Face</a></li>

</ul>
</details>

**标签**: `#open-source AI`, `#LLM agents`, `#Huawei Ascend`, `#model release`, `#AI hardware`

---

<a id="item-tech-news-2"></a>
### [Sebastian Raschka 解析现代 LLM 的位置嵌入](https://magazine.sebastianraschka.com/p/understanding-positional-embeddings) ⭐️ 7.0/10

Sebastian Raschka 的文章《Understanding Positional Embeddings in Modern LLMs》解释了现代 LLM 中位置嵌入的实现方式，面向 AI/ML 从业者。文章是教学性内容，不是新模型或新版本发布，因此没有可验证的性能提升或兼容性变化。

hackernews · vismit2000 · 11月15日 12:14 · [社区讨论](https://news.ycombinator.com/item?id=50506376)

**「背景」** 位置编码要解决的是 Transformer 注意力机制本身不包含词序信息的问题，因此模型需要额外注入 token 的绝对或相对位置。早期设计常使用可学习的绝对位置表，而现代 LLM 越来越多采用相对位置形式，例如在注意力中应用旋转位置编码（RoPE）。

**「社区讨论」** 评论者 programjames 认为，仅理解实现细节不足以真正理解位置嵌入，并主张位置嵌入本质上是群表示；他举例说，旋转位置嵌入是平移群的表示，并据此说明如何找到并参数化可学习的位置嵌入。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://magazine.sebastianraschka.com/p/understanding-positional-embeddings">Understanding Positional Embeddings in Modern LLMs</a></li>
<li><a href="https://techbytes.app/posts/understanding-positional-embeddings-in-modern-llms/">Understanding Positional Embeddings in Modern LLMs</a></li>

</ul>
</details>

**标签**: `#positional embeddings`, `#LLMs`, `#transformer architecture`, `#rotary embeddings`, `#machine learning education`

---

<a id="item-tech-news-3"></a>
### [MacBook Pro OLED 屏的 PWM 频闪问题](https://macanorak.com/the-macbook-pros-oled-pwm-problem-when-a-better-display-becomes-worse-to-use/) ⭐️ 7.0/10

一篇分析文章指出，MacBook Pro 的 OLED 屏幕虽在技术上更优，但其 PWM 调光带来的闪烁可能让频闪敏感用户感到更不舒适。文章涉及的 240Hz 测量说法在 Hacker News 讨论中受到质疑：有评论者根据示波器观察推测，串联 OLED 的两层可能各以 480Hz、相差 180 度工作，在常用亮度下形成约 960Hz 的有效频率。该频率与机制尚未得到独立确认，讨论还延伸到 CRI、运动模糊等其他显示敏感因素。

hackernews · MacAnorak · 11月15日 13:15 · [社区讨论](https://news.ycombinator.com/item?id=50506719)

**「背景」** PWM 调光通过快速开关像素来调节亮度；频率越低、闪烁深度越大，部分敏感用户越容易感到眼疲劳、头痛或眩晕。2026 年 11 月上旬，Notebookcheck 的实验室测试称，新款 14 英寸 MacBook Pro 的 PROLED XDR 屏幕在亮度 99% 及以下时以 240Hz PWM 调光，闪烁深度约 56%；AppleInsider 也强调该频率不同于屏幕刷新率。随后有用户报告眼疲劳和眩晕，这些测量与报告是当前讨论的直接背景。

**「实际影响」** 对频闪敏感的用户而言，屏幕参数更高并不等于更适合长时间使用；选购时应把 PWM 调光方式和实测闪烁频率纳入判断，而不能只看亮度或对比度。

**「社区讨论」** 评论者对文章引用的 240Hz PWM 频率提出异议，有人根据示波器波形推测串联 OLED 两层以 480Hz 反相工作、有效频率可达 960Hz；也有人分享脑震荡后对屏幕闪烁、白光 CRI 和运动模糊更敏感的个人经历。这些测量推测和体验分享尚未形成共识，也不能替代独立验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.appleheadlines.com/macbook-pro-oled-eye-strain-pwm-flicker/">MacBook Pro OLED Eye Strain &amp; PWM Flicker: 7 Moves - AH</a></li>
<li><a href="https://macbreeze.com/proled-macbook-pro-pwm-dimming-eye-strain/">PROLED MacBook Pro Users Report Eye Strain Driven by Low ...</a></li>
<li><a href="https://appleinsider.com/articles/26/11/10/if-youre-getting-dizzy-using-proled-macbook-pro-you-are-not-alone">Pulse width modulation on MacBook Pro with PROLED - AppleInsider</a></li>

</ul>
</details>

**标签**: `#OLED`, `#PWM flicker`, `#MacBook Pro`, `#display hardware`, `#accessibility`

---

<a id="item-tech-news-4"></a>
### [Protomaps：自托管地图瓦片更便宜、更简单](https://bruceroettgers.eu/blog/protomaps/) ⭐️ 7.0/10

一篇实践文章称，借助 Protomaps 和 PMTiles，自托管地图瓦片对个人开发者和小型项目而言已变得便宜且容易上手。现有材料未提供具体版本、价格或性能基准，重点在于降低自建地图基础设施的门槛。

hackernews · bcye · 11月15日 19:26 · [社区讨论](https://news.ycombinator.com/item?id=50509837)

**「背景」** Protomaps 的自托管方案基于 PMTiles：这是一种把地图瓦片金字塔打包成单个文件的归档格式，可存放在 S3 等通用对象存储上，并通过 HTTP range 请求按需读取，因此不需要自建瓦片后端或依赖第三方瓦片服务。

**「影响」** 对希望掌控地图基础设施、又不想承担 Mapbox 或 Google Maps 成本的开发者，Protomaps 让普通底图的自托管成为可负担的侧项目选项；但高缩放级别卫星影像的存储会随级别快速膨胀，不能按普通底图的成本模型估算。

**「社区讨论」** 评论者补充了 OpenFreeMap 这一提供免费公共实例的类似项目，并分享了把瓦片放在 Cloudflare R2 上以兼顾隐私和访问控制的做法。也有开发者称 Protomaps 让地图类侧项目变得可负担，同时提醒高分辨率卫星影像的存储会迅速变贵，且 PMTiles 查看工具对超过 128M 的瓦片和部分栅格格式仍有兼容问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/protomaps/PMTiles">GitHub - protomaps/PMTiles: Pyramids of map tiles in a single ...</a></li>
<li><a href="https://protomaps.com/">Protomaps - The open source map in a file</a></li>
<li><a href="https://docs.protomaps.com/pmtiles/">PMTiles Concepts | Protomaps Docs</a></li>

</ul>
</details>

**标签**: `#Protomaps`, `#map tiles`, `#self-hosting`, `#open source`, `#PMTiles`

---

<a id="item-tech-news-5"></a>
### [Meta FAIR 与 NYU：视觉编码器预训练可省，视觉专用参数不可省](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 7.0/10

Meta FAIR 与 NYU 作者在 Reddit 上介绍的研究称，他们从零训练了 200 多个多模态大模型，把视觉编码器预训练、视觉专用参数和编码器位置拆开做受控消融。实验统一数据，把编码器预训练计入同一生命周期算力预算，主要覆盖 Qwen3-1.7B/4B 配置、0.4B 视觉容量和 0.6B–6.4B 骨干规模，并在 16 个 VQA 和 12 个语言基准上评估。结论是：单独预训练视觉编码器最多只能与从零训练打平，且不提升 VQA；视觉专用参数不可省，去掉编码器的模型在各规模都落后，需要约 3 倍算力才能追平；编码器放在 LLM 之前也不是必需，in-fusion 把零初始化视觉专用权重放到前 8 层，在 1.7B–6.4B 与编码器持平，首 token 时间约低 13%。

reddit · r/MachineLearning · /u/trungh98 · 11月15日 17:38

**「背景」** 多模态大模型通常沿用预训练的视觉编码器，但近期也有方案选择让编码器与语言模型一起从零训练，或直接去掉编码器。由于已发布模型在数据、架构和算力上各不相同，直接比较它们无法分离“预训练视觉先验”“专用视觉容量”和“融合前放置”这三个设计选择各自的作用，这正是该研究要拆解的前提。

**「影响」** 对多模态团队，最直接的取舍是：不必把预算花在单独视觉编码器预训练上，但必须保留视觉专用参数；否则在 VQA 上需要约 3 倍算力补课。若采用 in-fusion，视觉专用参数应放在 LLM 前层：1.7B 实验里前 8 层达到 45.0 VQA，与独立编码器的 44.4 基本持平，而文本共享这些参数时为 42.3，放到最后 8 层仅 35.1。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/pdf/2611.17334v1">Unbundling Multimodal Vision Encoding - arXiv.org</a></li>
<li><a href="https://huggingface.co/papers/2611.17334">Paper page - Unbundling Multimodal Vision Encoding</a></li>

</ul>
</details>

**标签**: `#multimodal LLMs`, `#vision encoders`, `#model pretraining`, `#scaling experiments`, `#research paper`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [卢特尼克因英伟达“间谍”风波受质询，其子执掌的公司与英伟达有业务往来](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 7.0/10

据 CNBC 报道，美国商务部长霍华德·卢特尼克因其前公司 Cantor Fitzgerald（现由其子布兰登和凯尔执掌）与英伟达的关系面临质询：该公司申报持有的英伟达股票数量在 2025 年 9 月至 2026 年 3 月间下降 49%，从约 350 万股降至 178 万股，同期卢特尼克正受到白宫和情报官员施压，要求打击涉嫌向中国转运英伟达 AI 芯片的新加坡公司 Megaspeed。报道同时指出，没有证据显示卢特尼克向该公司分享了非公开信息，也没有证据表明持股变化与相关警告有关。

rss · CNBC Finance · 11月15日 19:58

**「背景」** 美国商务部负责执行出口管制，包括维护限制企业名单（实体清单）。卢特尼克于 2025 年 2 月离开 Cantor Fitzgerald 出任商务部长，该公司现由其子布兰登和凯尔领导；此案涉及新加坡公司 Megaspeed 被指将英伟达芯片转运至中国。

**「影响」** 这场争议已把出口管制的执行问题推入国会视野：Lutnick 定于在参议院就商务部如何处理人工智能芯片出口管制作证，使该部门的执法决定直接面临政治审查。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/15/bessent-nvidia-ceo-lutnick-megaspeed.html">Bessent calls for ‘dramatic shakeup’ at Nvidia , urges outside CEO</a></li>
<li><a href="https://nypost.com/2026/11/13/business/howard-lutnick-to-testify-before-senate-on-nvidia-megaspeed-fiasco/">Howard Lutnick to testify before Senate on Nvidia , Megaspeed fiasco</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#export controls`, `#conflict of interest`, `#Commerce Department`, `#China chip smuggling`

---

<a id="item-finance-news-2"></a>
### [美法官驳回美光、三星、SK 海力士 DRAM 价格操纵案撤诉动议](https://www.tomshardware.com/tech-industry/big-tech/judge-denies-motion-to-dismiss-dram-price-fixing-lawsuit-against-micron-samsung-and-sk-hynix-says-chipmakers-acted-like-hawks-flying-in-formation-finds-evidence-of-dram-collusion-plausible-after-500-percent-price-surge) ⭐️ 7.0/10

美国法官 Noël Wise 驳回美光、三星、SK 海力士要求撤销 DRAM 价格操纵集体诉讼的动议，认为原告提交的新证据足以让三家厂商同步限供、价格最高上涨 500% 的合谋指控成立，案件将继续审理。三家公司须在 12 月 7 日前作出回应，案件管理会议定于 2027 年 1 月。

telegram · zaihuapd · 11月15日 16:39

**「背景」** 这起拟议集体诉讼由 17 名个人和小企业提起，指控美光、三星和 SK 海力士在一年内四次同步限制 DRAM（电脑和手机等设备使用的内存芯片）供应、将价格推高至多 500%；法官此次驳回撤诉动议只表示案件可继续审理，并不等于认定三家公司违法。

**「谁受影响」** 驳回撤诉意味着这起集体诉讼将继续推进：作为原告的 DRAM 购买者可继续寻求赔偿，而美光、三星和 SK 海力士则面临持续的诉讼与取证成本。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.tomshardware.com/tech-industry/big-tech/judge-denies-motion-to-dismiss-dram-price-fixing-lawsuit-against-micron-samsung-and-sk-hynix-says-chipmakers-acted-like-hawks-flying-in-formation-finds-evidence-of-dram-collusion-plausible-after-500-percent-price-surge">Judge denies motion to dismiss DRAM price - fixing lawsuit against...</a></li>
<li><a href="https://litnews.ai/articles/garciaguirre-samsung-sk-hynix-micron-dram-conspiracy-suit-survives-dismissal">Judge Refuses to Dismiss DRAM Supply Conspiracy Suit Against...</a></li>

</ul>
</details>

**标签**: `#DRAM`, `#antitrust`, `#Micron`, `#Samsung`, `#SK Hynix`

---