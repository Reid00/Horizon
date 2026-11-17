---
layout: default
title: "Horizon Summary: 2026-11-17 (ZH)"
date: 2026-11-17
lang: zh
---

> 从 57 条内容中筛选出 16 条重要资讯。

---

**科技新闻**
1. [vLLM v0.34.0 发布：默认启用扩展 KV 缓存并移除 Model Runner V1](#item-tech-news-1) ⭐️ 8.0/10
2. [Jiff 1.0 发布：Rust 日期时间库](#item-tech-news-2) ⭐️ 8.0/10
3. [美国将 AI 芯片出口管制延伸至远程访问](#item-tech-news-3) ⭐️ 8.0/10
4. [Optimizely 被指经 CDN 向 Zoom、GitLab 等站点投放恶意代码](#item-tech-news-4) ⭐️ 7.0/10
5. [卡内基梅隆大学在 YouTube 免费发布完整计算机科学课程讲座](#item-tech-news-5) ⭐️ 7.0/10
6. [Linebender wiki 解释 squircle 与平滑曲线](#item-tech-news-6) ⭐️ 7.0/10
7. [Windows 11 被指收集开发者工具与 AI 编码代理遥测](#item-tech-news-7) ⭐️ 7.0/10
8. [Marimba：单次冻结 ASR 编码器支持多类语音查询](#item-tech-news-8) ⭐️ 7.0/10
9. [duetto：采样时引导预训练音乐 Transformer 实时爵士伴奏](#item-tech-news-9) ⭐️ 7.0/10
10. [美国与九国签署《旧金山宣言》协调 AI 供应链安全](#item-tech-news-10) ⭐️ 7.0/10
11. [亚马逊称 AI 代理借 Artex 窃取 API 密钥供血](#item-tech-news-11) ⭐️ 7.0/10
12. [阿里、腾讯、月之暗面据报限制新模型攻击性网络能力](#item-tech-news-12) ⭐️ 7.0/10
13. [苹果中国区 App Store 新增 AIGC 合规备案入口](#item-tech-news-13) ⭐️ 7.0/10

**财经新闻**
1. [中东出口恢复，美国原油跌至每桶 85 美元](#item-finance-news-1) ⭐️ 7.0/10
2. [卢特尼克因英伟达关系受审视，Cantor 报告持股减半](#item-finance-news-2) ⭐️ 7.0/10
3. [英特尔及 CEO 陈立武遭股东集体诉讼](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [vLLM v0.34.0 发布：默认启用扩展 KV 缓存并移除 Model Runner V1](https://github.com/vllm-project/vllm/releases/tag/v0.34.0) ⭐️ 8.0/10

vLLM 发布 v0.34.0，包含 1,061 次提交、412 名贡献者，新增 10 个模型。该版本默认启用可扩展 KV 缓存，按预热后实际空闲显存确定缓存大小，并移除 Model Runner V1，仅保留 V2。升级需注意默认 block size 从 16 改为 64、ROCm 7.2 镜像不再发布、要求 huggingface\_hub &gt;= 2.0.0 等破坏性变更。项目自报在 Blackwell 和 MI355X 上最高 1.95 倍解码加速，但未提供独立验证。

github · khluu · 11月16日 23:22

**「背景」** vLLM 的 PagedAttention 风格 KV cache 以固定大小的块为单位分配，块大小长期默认为 16，这会直接影响显存碎片、可缓存 token 数量以及既有调优参数。v0.34.0 将默认块大小改为 64（ROCm 的 paged attention 仍为 16），因此从旧版本升级且依赖原默认值的部署需要显式指定 \`--block-size 16\` 才能保持原有行为。

**「升级影响」** 部署方升级前应检查启动参数和依赖：若需保留旧缓存策略，可传 --gpu-memory-utilization 0.9 或 --no-enable-extensible-kv-cache；若需旧 block size，可传 --block-size 16；使用 V1 logits 处理器或依赖 fp\_quant、Marlin W4A8 的配置需先迁移。

**标签**: `#vLLM`, `#LLM inference`, `#open source`, `#performance`, `#breaking changes`

---

<a id="item-tech-news-2"></a>
### [Jiff 1.0 发布：Rust 日期时间库](https://burntsushi.net/jiff/) ⭐️ 8.0/10

Jiff 1.0 已发布，这是一个面向 Rust 开发者的日期时间库，作者为 burntsushi。现有材料没有给出具体的 API、性能或兼容性细节，社区关注点集中在 API 设计、与 chrono 的关系以及生态采用前景。

hackernews · burntsushi · 11月16日 16:53 · [社区讨论](https://news.ycombinator.com/item?id=50519744)

**「背景」** Jiff 是 BurntSushi 开发的 Rust 日期时间库，强调提供难以误用且性能合理的高层日期时间原语。其文档还专门与 Rust 生态中其他主流日期时间库作比较，帮助开发者判断适用场景。

**「影响」** 对 Rust 项目而言，日期时间库选型多了一个 1.0 版本可选；但材料未提供与 chrono 的兼容性或迁移路径，现有项目在替换前需要自行验证。

**「社区讨论」** 曾维护 chrono 约五年的 quodlibetor 表示，chrono 的 API 稳定性既是用户采用的原因，也让改进屡遇阻力，并称自己因看不到改进路径而停止维护；他对 burntsushi 编写 Jiff 表示感谢。也有评论者赞赏 Jiff 明确说明自己并非适用于所有场景，另有评论者询问其对 TAI、UT1 等时间尺度的支持。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/BurntSushi/jiff">GitHub - BurntSushi/jiff: A datetime library for Rust that ...</a></li>
<li><a href="https://docs.rs/jiff/latest/jiff/_documentation/comparison/index.html">jiff::_documentation::comparison - Rust - Docs.rs</a></li>

</ul>
</details>

**标签**: `#Rust`, `#datetime`, `#Jiff`, `#time zones`, `#open source`

---

<a id="item-tech-news-3"></a>
### [美国将 AI 芯片出口管制延伸至远程访问](https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/) ⭐️ 8.0/10

美国商务部 11 月 16 日发布临时最终规则，将先进 AI 芯片与服务器的出口管制延伸到远程访问，以堵住通过第三国数据中心规避限制的漏洞。据 The Verge 报道，新规还要求向印度尼西亚、马来西亚、新加坡、泰国和巴西再出口 AI 芯片时申请许可。

telegram · zaihuapd · 11月16日 14:44

**「背景」** 美国此前对先进 AI 芯片与服务器的出口管制主要针对实物出口和再出口，由工业与安全局（BIS）执行。由于管制未覆盖境外数据中心向受限实体提供的远程算力，相关方可以通过第三国机房调用芯片而不转移硬件，形成所谓“远程访问”漏洞；11 月 16 日的临时最终规则正是把这一环节纳入管制。

**「合规影响」** 对在印尼、马来西亚、新加坡、泰国和巴西运营云服务或数据中心的企业来说，向中国客户提供先进 AI 芯片与服务器的远程访问前需申请许可，合规审查将嵌入算力租赁和云服务合同流程；彭博社报道称，该规则正是要限制这些国家向中国企业提供远程访问。Reason 报道该规则对 TikTok 母公司字节跳动给予豁免，说明限制范围并非覆盖所有远程访问场景。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-16/us-moves-to-limit-remote-access-to-advanced-ai-chips">US Moves to Curb China’s Remote Access to Nvidia’s AI Chips</a></li>
<li><a href="https://reason.com/2026/11/16/trumps-new-chip-export-rule-targets-china-but-exempts-tiktoks-parent-company/">Trump’s new chip export rule exempts TikTok’s parent company</a></li>

</ul>
</details>

**标签**: `#AI chip export controls`, `#US BIS`, `#remote cloud access`, `#semiconductor policy`, `#AI infrastructure`

---

<a id="item-tech-news-4"></a>
### [Optimizely 被指经 CDN 向 Zoom、GitLab 等站点投放恶意代码](https://blog.report-uri.com/worlds-largest-brands-infected-with-malware-via-optimizely/) ⭐️ 7.0/10

据 report-uri.com 的安全博客，Optimizely 被指遭入侵，其 CDN 向包括 Zoom 和 GitLab 在内的客户站点提供了恶意代码，受影响的是加载这些第三方脚本的访客及使用该服务的网站运营方。报道将事件置于第三方 JavaScript 与供应链安全的背景下，但目前公开信息未给出受影响站点的完整名单、恶意代码的具体行为，也未说明攻击者如何取得写入权限。

hackernews · kristjansson · 11月16日 23:00 · [社区讨论](https://news.ycombinator.com/item?id=50524767)

**「背景」** 许多大型网站通过在页面中嵌入 Optimizely 的代码片段，从 Optimizely 的 CDN 动态加载实验与个性化脚本，因此一旦该第三方服务被入侵，恶意代码就会自动出现在所有接入方的页面上——这正是此次事件中 Zoom、GitLab 等站点受影响的机制。据 Gizmodo 的报道，恶意 JavaScript 经 Optimizely 分发至约 178 个组织，涉及加密货币窃取、信用卡侧录和 iOS 漏洞利用等载荷。

**「影响」** 对使用 Optimizely 的网站，直接后果是访客可能在正常域名下加载到恶意 JavaScript；运营方应审计该脚本的加载范围，并评估暂停或替换该第三方依赖。

**「社区讨论」** 有评论者批评 Google Tag Manager 这类让营销部门无需工程介入即可加标签的模式，认为它导致页面脚本膨胀和风险累积；也有人主张大站点不应把关键页面交给外部供应商，并质疑 Optimizely 的发布管控与问责机制。另有评论指出，攻击者如何取得跨客户写入权限仍待 Optimizely 解释，且此次并非 CDN 缓存投毒。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://gizmodo.com/sprawling-malware-attack-reportedly-affects-zoom-cnn-fox-news-peacock-and-170-others-2000840831">Sprawling Malware Attack Reportedly Affects Zoom and Other Major...</a></li>

</ul>
</details>

**标签**: `#supply-chain-security`, `#web-security`, `#third-party-scripts`, `#malware`, `#optimizely`

---

<a id="item-tech-news-5"></a>
### [卡内基梅隆大学在 YouTube 免费发布完整计算机科学课程讲座](https://www.cs.cmu.edu/learn/) ⭐️ 7.0/10

卡内基梅隆大学推出 CS Learn，在 YouTube 免费发布当前 CMU 计算机科学课程的整学期讲座。该项目本周每天首播一门课程，并计划在明年 1 月上线更多课程。项目负责人表示，部分学生构建的工具承担了大量制作自动化工作。

hackernews · pcompeau · 11月16日 20:43 · [社区讨论](https://news.ycombinator.com/item?id=50522980)

**「背景」** CS Learn 由 CMU 的 Kenneth C. Griffin 计算机科学学院推出，其 YouTube 频道按完整学期组织课程播放列表，每个列表对应一门真实课程的全学期讲座。按现有介绍，视频之外的自定进度课程材料、即时反馈、徽章和 AI 辅导是下一阶段计划，由学生与 ScottyLabs 共同开发。

**「影响」** 对自学者来说，这提供了按完整学期顺序学习当前 CMU 课程视频的免费入口；但现有信息只确认了讲座视频，项目、作业和反馈机制尚未说明，选课时应把缺少这些环节视为限制。

**「社区讨论」** 评论者欢迎具体课程上线，有人期待 15-259 概率与计算和 Tianqi Chen 的 ML Systems，也有人请求增加统计、分布式系统、操作系统等课程。另有评论提醒，若只有讲座而缺少项目和反馈，学习效果会打折扣，并关注课程材料何时跟进以及是否会覆盖研究生课程。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/channel/UCqvooOJo8792T83va7LMMSA">CS Learn at Carnegie Mellon - YouTube</a></li>
<li><a href="https://zeli.app/story/50522980">Carnegie Mellon opens its CS classrooms · Hacker News | Zeli</a></li>

</ul>
</details>

**标签**: `#computer science education`, `#open courseware`, `#CMU`, `#YouTube`

---

<a id="item-tech-news-6"></a>
### [Linebender wiki 解释 squircle 与平滑曲线](https://linebender.org/wiki/curves/squircle/) ⭐️ 7.0/10

Linebender 的 wiki 文章《Squircles》解释 squircle（方圆形）的几何概念及其在平滑曲线设计中的作用，讨论范围涉及样条、超椭圆和渲染。该文在 Hacker News 上引发讨论，内容属于技术参考，而非产品发布、版本更新或性能公告。现有材料没有给出可直接采用的库、版本号或基准数据，读者应将其视为理解曲线连续性与形状设计的背景读物。

hackernews · raphlinus · 11月16日 07:55 · [社区讨论](https://news.ycombinator.com/item?id=50515151)

**「背景」** 圆角方形（squircle）指介于正方形与圆形之间的形状，并没有唯一的数学定义；常见的一类定义来自超椭圆（也称 Lamé 曲线），另一类则源自光学研究。超椭圆通过方程让形状在矩形与椭圆之间连续变化，Linebender 的 wiki 文章则专门梳理这类曲线及其在平滑曲线设计中的用途。

**「影响」** 对图形与 UI 开发者来说，这篇文章可作为理解 squircle、超椭圆与样条之间取舍的参考；但它不提供现成实现或性能结论，是否采用仍需结合具体渲染管线和曲线连续性要求验证。

**「社区讨论」** 评论者 mosura 认为，避免导数不连续的曲线在与物理世界交互时尤其重要，squircle 只是其中一例；thot\_experiment 则分享了一个仍在探索阶段的样条/超椭圆创作工具演示，并提醒其 UI 和边界情况尚不完善。另有评论者提到 Zune 第二代播放器的 squircle 方向键手感，以及认为“sphube”更胜一筹并给出论文链接。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Squircle">Squircle - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Superellipse">Superellipse - Wikipedia</a></li>
<li><a href="https://linebender.org/wiki/curves/squircle/">Squircles - Linebender</a></li>

</ul>
</details>

**标签**: `#squircles`, `#curve geometry`, `#computer graphics`, `#UI design`, `#superellipses`

---

<a id="item-tech-news-7"></a>
### [Windows 11 被指收集开发者工具与 AI 编码代理遥测](https://xusheng.dev/posts/windows-coding-agent-telemetry/) ⭐️ 7.0/10

一篇报告称，Windows 11 正在收集开发者使用哪些开发工具和 AI 编码代理的遥测数据，相关讨论集中在隐私与平台功能优先级上。由于原始报道正文未提供，具体收集字段、默认开关状态和覆盖的 Windows 版本都无法从现有材料核实。

hackernews · cwaffles · 11月16日 22:58 · [社区讨论](https://news.ycombinator.com/item?id=50524736)

**「背景」** Windows 11 的遥测由“设置 → 隐私和安全性 → 诊断和反馈”控制，其中可选诊断数据默认开启，并会随应用使用情况一并上报；讨论中的读者正是据此指出，开发者工具的使用数据也走同一开关。隐私社区对关闭这类遥测的讨论已持续多年，Privacy Guides 论坛在 2024 年 5 月就有专门寻找 Windows 11 遥测禁用工具的帖子。

**「影响」** 对使用 Windows 11 的开发者来说，若在意工具使用情况被上报，应核对系统的诊断与反馈设置；但现有材料只给出评论者转述的关闭路径，尚不能确认默认状态或数据范围。

**「社区讨论」** 评论区有人称，开发工具的使用情况会被跟踪，并可能在启用相应诊断数据时上报，且该选项默认开启；其给出的关闭路径是“设置 → 隐私和安全性 → 诊断和反馈”。也有评论认为，Windows 的 AI 代理沙箱推进较慢（提到 10 月 7 日推出的 MXC 尚未被 Claude Code 支持），若遥测用于确定这类功能的优先级，非侵入式收集可以接受；另有评论指出显卡驱动和浏览器等也会收集类似信息。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://discuss.privacyguides.net/t/best-tool-to-disable-telemetry-on-win11/18516">Best tool to disable telemetry on Win 11 - Questions - Privacy Guides...</a></li>

</ul>
</details>

**标签**: `#Windows 11`, `#telemetry`, `#privacy`, `#developer tools`, `#AI coding agents`

---

<a id="item-tech-news-8"></a>
### [Marimba：单次冻结 ASR 编码器支持多类语音查询](https://www.reddit.com/r/MachineLearning/comments/1xxsqro/marimba_a_system_one_model_for_speech_r/) ⭐️ 7.0/10

Reddit 帖子附上的 arXiv 预印本介绍了 Marimba：用户可对 8 秒音频窗口提出是/否、多选或评分式文本问题，模型返回校准后的概率，而每个窗口只运行一次冻结的 Qwen3-ASR-0.6B 编码器。术语查询为零样本，由解码器的贪心假设和 4 条束搜索假设评分后做 Platt 校准；语种识别使用 ASR 模型自身的语言分数；话轮结束用冻结第 18 层的小型读出器，说话人变化和人数用第 12 层读出器。作者自报在 1,000 条公开问题的 9 项测试中，有 6 项匹配或超过 Qwen3-Omni（30B-A3B），但在 Speech Commands 上仍落后；语种识别在 300 条 FLEURS 片段上达到 100%，说话人变化 AUROC 为 0.966–0.980，高于 ECAPA，说话人数超过 pyannote 3.1。局限也很具体：话轮结束在 Smart Turn 自身测试集上 AUROC 为 0.930，低于 Smart Turn v3.2 的 0.982，在 ICSI 上为 0.716 对 0.712、基本持平，且该读出器用 Smart Turn 数据训练，属于分布内结果；在 CochlScene 场景分类上所有头都只有随机水平。

reddit · r/MachineLearning · /u/solanotodesch · 11月16日 15:47

**「背景」** 语音理解系统通常要为关键词检测、语种识别、话轮结束和说话人变化等任务分别训练模型或分类头。Marimba 试图用一次冻结的 Qwen3-ASR-0.6B 编码器前向，配合轻量读出与校准，让同一音频窗口回答多种类型化查询。该 Reddit 帖是上周预告的后续，此次补充了 arXiv 论文、代码、Apache-2.0 权重和在线演示。

**「影响」** 对语音和机器学习开发者而言，Marimba 提供了 pip install marimba-audio 的安装方式、Apache-2.0 权重和演示，可把多类查询压到一次编码器前向中评估。但话轮结束和未见任务上的表现说明它不能直接替代专用关键词识别、Smart Turn 或场景分类模型，部署前需在目标域重新验证。

**标签**: `#speech recognition`, `#machine learning`, `#model efficiency`, `#calibration`, `#audio understanding`

---

<a id="item-tech-news-9"></a>
### [duetto：采样时引导预训练音乐 Transformer 实时爵士伴奏](https://www.reddit.com/r/MachineLearning/comments/1xxkyh3/steering_a_pretrained_music_transformer_at/) ⭐️ 7.0/10

Reddit 用户 GGAllin43 发布了 duetto：一个面向 MIDI 键盘的实时爵士伴奏项目。它不微调模型，而是直接使用预训练的 Anticipatory Music Transformer，在每次采样前用规则层对 logits 做掩码和偏置，以控制声部等待、音域、拍点以及和弦音、引导音等。作者提供的《Autumn Leaves》160 bpm 演示中，约 61% 的独奏音符来自 Weimar Jazz Database 的引用乐句或主题，其余由模型生成；代码可免费用于非商业用途。作者报告在 3080 Ti 上中号模型约 12 ms/音符、大号模型约 18 ms/音符，大号模型在 Jetson Orin Nano 上约 90 ms/音符，仍足以现场演奏；但他也承认系统会偏离演奏者、响应难以预测，模型创意与规则偏置之间的平衡很脆弱。

reddit · r/MachineLearning · /u/GGAllin43 · 11月16日 09:19

**「背景」** Anticipatory Music Transformer 是 Thickstun 等人于 2023 年提出的符号音乐生成模型，除了按提示续写，还支持填充式控制任务（例如生成伴奏），其预训练权重通过 Hugging Face 发布。duetto 直接加载这一预训练模型，把演奏者与模型的音符放进同一事件序列，再在采样阶段用规则约束输出，因此不需要微调。

**「影响」** 对希望避免微调成本的符号音乐开发者，duetto 提供了一个可试用的工程路径：把乐理约束放在采样层，并用约 1 秒预采样与重采样来掩盖模型规划延迟；但作者报告的控制不稳定意味着它目前更适合作为研究原型，而非可直接依赖的现场伴奏系统。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2306.08620">[2306.08620] Anticipatory Music Transformer - arXiv.org</a></li>
<li><a href="https://github.com/jthickstun/anticipation">GitHub - jthickstun/anticipation: Anticipatory Autoregressive ... Anticipatory Music Transformer Anticipatory Music Transformer: A Controllable Infilling ... Anticipatory Music Transformer - John Thickstun (PDF) Anticipatory Music Transformer - ResearchGate Anticipatory Music Transformer - NASA/ADS</a></li>

</ul>
</details>

**标签**: `#music generation`, `#inference-time control`, `#transformers`, `#real-time systems`, `#pretrained models`

---

<a id="item-tech-news-10"></a>
### [美国与九国签署《旧金山宣言》协调 AI 供应链安全](https://www.state.gov/releases/office-of-the-spokesman/2026/11/the-san-francisco-declaration-on-the-secure-foundations-of-enduring-prosperity/) ⭐️ 7.0/10

11 月 15 日，美国与澳大利亚、印度、以色列、日本、韩国、卡塔尔、新加坡、阿联酋和英国签署《旧金山宣言》，确认经济安全是国家安全的基础，并协调保护支撑超级智能（SI）供应链的敏感技术与关键基础设施。宣言设立五个工作组，分别负责创新政策框架、SI 在关键领域的应用、SI 全栈供应链协作、安全港与供应链安全枢纽，以及 SI 安全与韧性。该文件目前属于宣言级安排，未包含约束性承诺、资金或具体技术细则。

telegram · zaihuapd · 11月16日 10:40

**「背景」** 《旧金山宣言》把“超级智能（SI）供应链”作为政策对象，覆盖支撑 SI 的敏感技术和关键基础设施，并设五个工作组协调创新政策、关键领域应用、全栈供应链、安全港与供应链安全枢纽、安全与韧性。公开信息目前只到宣言和工作组架构层面，未披露具体技术清单、资金安排或约束性承诺。

**「实际影响」** 由于宣言没有约束性承诺、资金或技术细则，跨国 AI、芯片和云基础设施企业短期内不会因此承担新的合规义务；后续影响将取决于五个工作组是否形成可执行的政策或标准。

**标签**: `#AI policy`, `#AI supply chain`, `#international cooperation`, `#national security`, `#superintelligence`

---

<a id="item-tech-news-11"></a>
### [亚马逊称 AI 代理借 Artex 窃取 API 密钥供血](https://cybernews.com/security/amazon-autonomous-cybercrime-artex-framework/) ⭐️ 7.0/10

亚马逊称，攻击者利用开源框架 Artex 驱动 AI 代理，从公网暴露的 LiteLLM、Dify 等 AI 应用窃取 API 密钥，验证后汇入共享池，用于支付更多大模型调用。该活动据称始于 10 月 3 日，并于 11 月 5 日被亚马逊的诱饵网络 MadPot 截获阻断。亚马逊以中等信心将行动归因于中国相关威胁组织，并称并非所有被列目标都已失陷，已通知可能受影响的 AWS 客户。

telegram · zaihuapd · 11月16日 13:00

**「背景」** 公开资料显示，ARTEX 是一个开源 AI 渗透测试框架，会把多个 AI 代理串成结构化的攻击流水线：一个代理生成候选利用，另一个代理充当严格评分器来验证输出。亚马逊此前介绍，MadPot 是由全球分布的诱饵传感器组成的威胁情报网络，既收集攻击活动信息，也借助 AWS 网络控制和其他互联网参与方进行干扰。

**「影响与应对」** 对使用公网暴露的 LiteLLM 或 Dify 的运营者而言，泄露的 API 密钥可能被用于支付攻击者的模型调用费用；亚马逊称已通知可能受影响的 AWS 客户，相关用户应核查密钥并轮换。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.probackend.com/ai-nation-state-cyber-operations/autonomous-agentic-ai-framework-artex-deployed-in-massive">AI Cybersecurity Threats 2026: The Autonomous ARTEX AI Framework</a></li>
<li><a href="https://www.aboutamazon.com/news/aws/amazon-madpot-stops-cybersecurity-crime">Meet MadPot, a threat intelligence tool Amazon uses to ... How AWS threat intelligence deters threat actors Amazon spins up AI honeypot, grabs ARTEX attack chain. Amazon Threat Intelligence: MadPot Decoys Posing as LLM ... Amazon Threat Intelligence observes threat actors running ... Amazon MadPot Caught ARTEX AI Agents: What Leaked - explainx.ai</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#cybersecurity`, `#API key theft`, `#cloud security`, `#Amazon`

---

<a id="item-tech-news-12"></a>
### [阿里、腾讯、月之暗面据报限制新模型攻击性网络能力](https://www.bloomberg.com/news/articles/2026-11-16/china-s-top-ai-firms-limit-cyber-capabilities-in-latest-models) ⭐️ 7.0/10

据 Bloomberg 报道，阿里巴巴、腾讯和月之暗面等中国头部 AI 公司在新一代模型中削弱了进攻性网络能力，同时提升防御表现。阿里最新旗舰 Qwen 未开放权重，用户无法下载并自定义完整版本；腾讯则在今年本月发布 Hy4 前削减了网络功能。报道称，这一变化与商务部上月公布的出口管制草案有关，该草案拟禁止可攻击关键基础设施和政府网络的 AI 工具出口。上述收紧措施目前来自媒体报道，相关技术细节和独立验证仍有限。

telegram · zaihuapd · 11月17日 02:20

**「背景」** 2026 年 10 月，中国商务部和科技部联合发布出口管制技术目录修订草案，拟限制 AI 软件和数据向境外转移，并使境外部署中国 AI 模型面临审查；路透社 10 月 28 日报道称，草案仍大体允许通过海外云访问，但会收紧中国对 AI 基础设施的对外控制。该草案的适用范围与本次企业在新模型发布前收缩网络攻击能力、并让阿里 Qwen 旗舰版不再开放权重直接相关。

**「对开发者的影响」** 由于阿里最新旗舰 Qwen4-Max 未开放权重，此前依赖下载权重自行部署、微调和审查模型的开发者无法再获得完整版本，只能通过阿里提供的接口访问该旗舰模型。腾讯本月发布 Hy4 前也已削减网络功能，对于在自有环境中运行这些新模型并设置安全边界的团队而言，需要重新评估迁移路径和访问方式。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reuters.com/business/retail-consumer/chinas-new-export-curbs-draw-line-around-its-ai-crown-jewels-2026-10-28/">China&#x27;s new export curbs draw a line around its AI crown ...</a></li>
<li><a href="https://apnews.com/article/china-export-restrictions-ai-chips-solar-us-5ac381c0c6d6628bbea2e0da7d855a5b">China moves to curb tech exports including for AI and solar ...</a></li>
<li><a href="https://thenextweb.com/news/alibaba-launches-qwen4-max-flagship-ai-model-without-open-weights">Alibaba launches Qwen4-Max flagship AI model without open weights</a></li>

</ul>
</details>

**标签**: `#AI policy`, `#cybersecurity`, `#China AI`, `#open-weight models`, `#export controls`

---

<a id="item-tech-news-13"></a>
### [苹果中国区 App Store 新增 AIGC 合规备案入口](https://www.ithome.com/1/028/158.htm) ⭐️ 7.0/10

苹果 App Store Connect 后台面向中国大陆分发新增两项合规必填项：AIGC 服务声明与备案信息、安全评估证明。现有应用须在 2027 年 1 月 31 日前补齐，新应用则需立即提交。范围涵盖聊天机器人、图像或视频生成、语音或人脸编辑等 AIGC 应用；使用第三方技术的还须上传授权协议和算法备案号，苹果 2026 年审核指南已纳入生成式 AI 条款。

telegram · zaihuapd · 11月17日 04:29

**「背景」** 中国大陆对生成式 AI 服务设有备案和安全评估要求，应用分发平台需要开发者提交相应材料。苹果在 2026 年审核指南中已纳入生成式 AI 条款，此次新增入口是把这些条款具体化为 App Store Connect 的必填字段。

**「开发者需先判定是否属于“舆论属性”服务」** 对在中国大陆分发 AIGC 应用的开发者来说，第一步是判定自身功能是否属于“具有舆论属性或社会动员能力”的服务：按中国生成式 AI 暂行办法，安全评估与算法备案仅对该类服务强制，代码生成等专用工具类应用通常不在此列，但苹果后台仍要求提交 AIGC 声明与备案信息。使用第三方模型或技术的应用还须向苹果上传授权协议和算法备案号，因此相关团队需在 2027 年 1 月 31 日前完成自查并向供应方索取材料，否则现有应用将面临合规缺口。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aegisfirma.com/en/compliance/china-aigc">China Interim Measures for Generative AI Services ( AIGC ) — AI...</a></li>
<li><a href="https://www.lexology.com/library/detail.aspx?g=521c1406-4c5c-44d0-9c89-e794fc0d9b69">China officially launches AIGC regulatory provisions - Lexology</a></li>

</ul>
</details>

**标签**: `#Apple App Store`, `#AIGC compliance`, `#China regulation`, `#app developers`, `#generative AI`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [中东出口恢复，美国原油跌至每桶 85 美元](https://www.cnbc.com/2026/11/16/us-crude-oil-declines-to-87-a-barrel-on-recovering-middle-east-exports.html) ⭐️ 7.0/10

周一，布伦特原油下跌 3.55%至每桶 92.44 美元，美国西得克萨斯中质原油（WTI）期货结算价下跌 3.58%至每桶 85.39 美元，原因是霍尔木兹海峡的运输正在恢复。国际能源署（IEA）上周五表示，随着中东出口恢复速度快于全球需求增长，目前预计 2026 年第四季度全球供应将超出需求 170 万桶/日以上，而此前该机构预测为供应短缺。

rss · CNBC Finance · 11月16日 22:19

**「背景」** 霍尔木兹海峡是全球关键的石油运输通道；2026 年伊朗冲突一度使沙特等产油国因无法经该海峡出口而减产，这成为此前供应紧张的重要背景。

**「影响」** 若跌势持续，原油作为运输和工业生产的投入品，价格下降可减轻家庭和企业的短期成本与通胀压力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://investingnews.com/daily/resource-investing/energy-investing/oil-and-gas-investing/top-oil-producing-countries/">10 Top Oil -producing Countries | INN</a></li>
<li><a href="https://www.iea.org/about/oil-security-and-emergency-response/strait-of-hormuz">Strait of Hormuz : Oil and LNG Trade Facts - IEA - About - IEA</a></li>
<li><a href="https://globalmarketsreview.org/markets/brent-crude-falls-us-midterms-iran-war-bond-yields-november-2026">Oil&#x27;s Post-Election Slide Is Reshaping the Inflation Trade</a></li>

</ul>
</details>

**标签**: `#oil markets`, `#crude oil`, `#IEA`, `#supply and demand`, `#commodity prices`

---

<a id="item-finance-news-2"></a>
### [卢特尼克因英伟达关系受审视，Cantor 报告持股减半](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 7.0/10

CNBC 报道，美国商务部长霍华德·卢特尼克因其子布兰登和凯尔经营的 Cantor Fitzgerald 与英伟达的密切关系而受到审视；该公司向监管机构报告的英伟达持股数量在 2025 年 9 月底至 2026 年 3 月底间下降 49%，从约 350 万股降至 178 万股，对应市值从 6.52 亿美元降至 3.10 亿美元。报道称，这一减持与白宫及情报官员施压卢特尼克打击涉嫌向中国转运英伟达芯片的新加坡公司 Megaspeed 在时间上重合，但 CNBC 同时指出，没有证据显示两者存在关联，相关利益冲突指控均未获证实。

rss · CNBC Finance · 11月16日 12:14

**「背景」** 卢特尼克在 2025 年出任美国商务部长前长期执掌坎托·菲茨杰拉德，并已回避该公司事务；这家华尔街机构目前由他的儿子布兰登和凯尔经营。美国商务部负责出口管制，包括维护限制外国实体的“实体清单”。

**「影响」** 对英伟达投资者而言，黄仁勋已于 11 月 12 日辞去首席执行官、总裁及董事职务，首席财务官科莱特·克雷斯（Colette Kress）出任临时首席执行官，公司由此进入领导层过渡期，同时仍需面对美国对华芯片出口管制的审查。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/11/15/us/politics/trump-lutnick-ai-chips-nvidia-cantor-fitzgerald.html">Lutnick Pushed to Weaken Chip Rules That Overlap With His Family...</a></li>
<li><a href="https://aiweekly.co/alerts/commerce-delays-entity-list-additions-megaspeed-stays-off">Commerce delays Entity List additions, Megaspeed stays off</a></li>
<li><a href="https://www.gate.com/blog/jensen-huang-resigns-is-nvda-stock-still-a-good-investment">Jensen Huang Resigns : Is NVDA Stock Still a Good... | Gate Blog</a></li>
<li><a href="https://www.bbc.com/news/live/c6zjry11v8w1t">Huang agrees to appear before Congress, US lawmakers... - BBC News</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#US export controls`, `#Commerce Department`, `#conflict of interest`, `#China chip smuggling`

---

<a id="item-finance-news-3"></a>
### [英特尔及 CEO 陈立武遭股东集体诉讼](https://www.investing.com/news/stock-market-news/intel-sued-by-shareholders-following-29-stock-plunge-5028171) ⭐️ 7.0/10

英特尔及 CEO 陈立武、CFO 津斯纳被股东集体起诉，被指隐瞒 PC 需求疲软和库存积压的影响；公司 10 月 29 日发布的第四季度营收和利润预测不及预期，次日股价暴跌 28.6%，市值蒸发约 1400 亿美元。诉讼由一家密歇根州养老基金牵头，上周五在圣何塞联邦法院提起，代表 2026 年 7 月 23 日至 10 月 29 日期间买入股票的投资者。

telegram · zaihuapd · 11月16日 11:10

**「背景」** 这起拟议的股东集体诉讼由密歇根州南菲尔德市消防与警察退休基金牵头，代表在 2026 年 7 月 23 日至 10 月 29 日期间买入英特尔股票的投资者，寻求金额未定的赔偿；股东称，英特尔在 10 月 29 日给出不及预期的第四季度营收和利润预测前，隐瞒了个人电脑需求疲软和库存积压的影响。

**「受影响投资者」** 在 2026 年 7 月 23 日至 10 月 29 日买入英特尔股票的投资者是这起拟议集体诉讼的潜在成员，可能通过诉讼寻求赔偿，但诉状要求的赔偿金额尚未披露。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reuters.com/business/intel-sued-by-shareholders-following-29-stock-plunge-2026-11-15/">Intel sued by shareholders following 29% stock plunge | Reuters</a></li>
<li><a href="https://finance.yahoo.com/markets/stocks/articles/intel-faces-lawsuit-29-stock-113912819.html?fr=sycsrp_catchall">Intel Faces Lawsuit After 29% Stock Crash. Investors Allege ...</a></li>
<li><a href="https://www.claimsjournal.com/news/national/2026/11/16/341342.htm">Intel Sued By Shareholders Following 29% Stock Plunge</a></li>

</ul>
</details>

**标签**: `#Intel`, `#shareholder lawsuit`, `#earnings warning`, `#stock plunge`, `#semiconductors`

---