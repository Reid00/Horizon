---
layout: default
title: "Horizon Summary: 2026-11-08 (ZH)"
date: 2026-11-08
lang: zh
---

> 从 39 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [Mac 被指内置未公开“家庭成员”分类器](#item-tech-news-1) ⭐️ 8.0/10
2. [内蒙古 Galaxy 数据中心：800MW 规划、首期一年交付](#item-tech-news-2) ⭐️ 8.0/10
3. [苹果披露 HALO 人形机器人系统，采用两个千问模型](#item-tech-news-3) ⭐️ 8.0/10
4. [GitHub Rubicon 架构：内部测试每秒 7200 次推送](#item-tech-news-4) ⭐️ 8.0/10
5. [微软研究院 AI Frontiers 团队据报结束](#item-tech-news-5) ⭐️ 7.0/10
6. [Claude Code 本地设置文件在 1,122 个公开 GitHub 文件中暴露凭据](#item-tech-news-6) ⭐️ 7.0/10
7. [Coldframe：伪装超市冷柜控制器的单文件蜜罐](#item-tech-news-7) ⭐️ 7.0/10
8. [MaxxBench：DeepSWE 分数经任务改写后未必稳健](#item-tech-news-8) ⭐️ 7.0/10
9. [Asahi Linux 7.3 报告：Fedora Asahi Remix 首次同日发布](#item-tech-news-9) ⭐️ 7.0/10
10. [Claude Code 被指联网请求泄露登录邮箱](#item-tech-news-10) ⭐️ 7.0/10

**财经新闻**
1. [伯克希尔第三季度回购翻倍至 96 亿美元，利润下滑](#item-finance-news-1) ⭐️ 7.0/10
2. [软银与 ABB 考虑分拆中国机器人业务以挽救 54 亿美元收购](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Mac 被指内置未公开“家庭成员”分类器](https://8rank.ai/game/apple-intelligence-personal-knowledge-graph) ⭐️ 8.0/10

一篇在 Hacker News 上传播、由 8rank.ai 发布的分析称，macOS 中存在未公开的守护进程，用来构建关于用户及其周围人物的个人知识图谱并判断关系类别；有评论引用文章称，这类守护进程自 2022 年起随每台 Mac 提供。文章把这种端侧关系推断视为隐私和伦理问题，而不是普通本地缓存。现有材料未给出可核验的守护进程名称、具体版本范围或默认开关状态，因此覆盖范围、数据保留和用户控制仍不明确。

hackernews · infwhispers · 11月7日 09:46 · [社区讨论](https://news.ycombinator.com/item?id=50403097)

**「背景」** “个人知识图谱”指设备端把联系人、通信、位置等线索关联成可查询的实体关系库，供本地模型检索使用。现有报道显示，自 macOS 13（2022）起，Mac 上就有两个后台守护进程负责构建这类图谱，数据存放在 ~/Library/IntelligencePlatform 下的 51 个明文 SQLite 数据库中，并受 TCC 完全磁盘访问权限保护；相关研究还点名了 knowledgeconstructiond 与 intelligenceplatformd 两个守护进程。

**「影响」** 对 Mac 用户而言，实际影响是本地助手可借助关系图谱区分同名联系人或理解“老板”等称谓（aetherspawn 如此解释其用途），但联系人关系也因此成为系统推断出的敏感数据；缺少公开说明会使用户难以判断边界并作出知情选择。

**「社区讨论」** 评论者的分歧集中在实用性与隐私：aetherspawn 认为这类图谱是 Siri 等本地助手的上下文，用来判断“Text James”指哪个 James 或“老板”是谁；thomascountz 则更担心日常对话被系统记住的社会后果，并指出即便参与者觉得有用，也不等于伦理上没问题。另有评论称照片应用早已识别人脸和宠物，因此对苹果构建此类关系数据并不意外。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://daily.dev/posts/every-mac-comes-with-an-undocumented-family-member-classifier-s3lfxwdun">Every Mac comes with an (undocumented) family member classifier</a></li>
<li><a href="https://techplanet.today/post/apples-hidden-personal-knowledge-graph-understanding-macoss-undocumented-family-classifier">Apple&#x27;s Hidden Personal Knowledge Graph: Understanding macOS ...</a></li>

</ul>
</details>

**标签**: `#Apple`, `#macOS`, `#privacy`, `#personal knowledge graph`, `#on-device ML`

---

<a id="item-tech-news-2"></a>
### [内蒙古 Galaxy 数据中心：800MW 规划、首期一年交付](https://newsletter.semianalysis.com/p/we-visited-chinas-stargate-in-inner) ⭐️ 8.0/10

SemiAnalysis 在 11 月 7 日发布的实地探访报告中称，其于 9 月走访了内蒙古乌兰察布的 Galaxy 数据中心园区；该园区由 Envision Group 拥有，规划 IT 容量最高 800MW，首期 120MW 已在一年内交付，成本约为美国同类项目的五分之一。园区四期均为两家互联网巨头定制建设，但报告未披露客户名称。Envision 不仅运营数据中心，还自建风电场和专用供电线路，并在园区内设计集成低压功率模块、800V 系统、储能电池和预制变电站；马路对面就是其叶片工厂。探访时园区其余部分仍在施工，当地报道称察哈尔高新区 22 个数据中心项目共有近 3 万名建筑工人。

rss · Semianalysis · 11月7日 19:01

**「背景」** “星际之门”（Stargate）阿比林园区是 OpenAI 在得克萨斯州建设的吉瓦级数据中心，已被视为美国 AI 基础设施扩张的标志性项目。乌兰察布所在的内蒙古凭借能源和建设条件，成为中国增长最快的数据中心聚集区之一；Galaxy 园区位于乌兰察布，由远景集团拥有，规划 IT 容量最高达 800MW。

**「影响」** 对计划建设 GW 级 AI 园区的运营商而言，这一案例的具体约束是电力自供、专用线路和本地施工队伍必须与机房建设同步推进；SemiAnalysis 给出的“五分之一成本”和“一年交付”是其探访结论，并非公开招标或独立审计数据，不能直接当作可复制报价。

**标签**: `#AI infrastructure`, `#datacenters`, `#China tech`, `#compute economics`, `#energy`

---

<a id="item-tech-news-3"></a>
### [苹果披露 HALO 人形机器人系统，采用两个千问模型](https://weibo.com/1642634100/RqjjGllvw) ⭐️ 8.0/10

苹果研究团队在 11 月 4 日提交至 arXiv 的预印本中披露人形机器人自主控制系统 HALO，并在宇树 G1 上验证了把仿真环境中学到的动作迁移到陌生真实房间执行。该系统分三层：上层由 Qwen3.6-35B-A3B 负责任务编排，中层由 Qwen3.5-2B 生成动作，底层是经强化学习训练的动作跟踪器。团队已公开数据生成、模型训练与部署代码；相关结果来自预印本和社媒转述，尚待同行评审或独立复现。

telegram · zaihuapd · 11月7日 13:35

**「背景：仿真到真实迁移与分层控制」** 仿真到真实（sim-to-real）迁移是人形机器人研究的常见路径：先在物理仿真中训练控制策略，再部署到实体机器人，但仿真与现实的动力学和感知差异常导致性能明显下降。分层控制把长程任务编排、动作生成和底层关节跟踪拆开，使各层可分别训练和替换。HALO 以 arXiv 预印本形式公开，尚未经过同行评审。

**「对复现者的实际影响」** 对想复现的开发者来说，苹果已公开数据生成、模型训练与部署代码，且 HALO 的策略完全在机器人本体上运行，因此复现路径绑定宇树 G1 这一特定硬件平台及其机载算力。其能力来自纯仿真的合成数据，并能在未扫描过的真实房间中零样本执行任务，但这也意味着使用者在把系统部署到自家场景前，仍需自行验证鲁棒性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/html/2611.06908">Perceptive Humanoid Motion from Simulation - arXiv.org</a></li>
<li><a href="https://github.com/apple-aiml-research/ml-halo">GitHub - apple-aiml-research/ml-halo: HALO: Perceptive ...</a></li>
<li><a href="https://ai.42how.com/en/article/ee6a8f15-db79-4091-9a86-3bc31de6c02f">Apple Integrates Humanoid Perception Into Simulation for Zero ...</a></li>

</ul>
</details>

**标签**: `#Apple`, `#humanoid robotics`, `#Qwen`, `#sim-to-real`, `#open-source research`

---

<a id="item-tech-news-4"></a>
### [GitHub Rubicon 架构：内部测试每秒 7200 次推送](https://github.blog/engineering/architecture-optimization/inside-githubs-new-git-storage-architecture/) ⭐️ 8.0/10

GitHub 推出代号 Rubicon 的新 Git 存储架构，主要面向大量 AI 智能体并发操作同一个仓库的场景。该架构把 Git 对象存入 Azure Blob Storage，由 Ref-CAS 管理引用状态，并用虚拟副本处理读写、由后台节点压缩数据包。GitHub 称，在内部测试中，该架构支持 5000 个智能体同时协作，每秒处理 7200 次推送，读取延迟保持在较低水平；这些均为厂商内部测试数据，尚未经过独立验证。该架构目前处于有限私有预览阶段，GitHub 表示将逐步扩大推广范围。

telegram · zaihuapd · 11月7日 14:12

**「背景」** GitHub 此前已在推进把仓库副本迁移到 Azure 对象存储；10 月 21 日的工程文章称，已迁移 99.99999% 仓库的副本，并计划用按引用仲裁（per-reference quorums）处理剩余部分，让读取能力随对象存储独立扩展。Rubicon 延续这一方向，把 Git 对象存入 Azure Blob Storage，并用 Ref-CAS 管理引用状态。

**「影响」** 对需要在单个仓库上运行大量并发 AI 智能体的团队来说，如果 Rubicon 能按内部测试的水平实际运行，那么它可以缓解推送排队和读写争用；不过该架构仅以有限私有预览形式提供，外部开发者目前无法把它当作可用的容量或兼容性承诺来规划生产负载，现有 Git 存储路径仍是默认选择。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.blog/engineering/architecture-optimization/the-bridge-to-agent-scale-git-infrastructure/">The bridge to agent-scale Git infrastructure - The GitHub Blog</a></li>

</ul>
</details>

**标签**: `#GitHub`, `#Git storage architecture`, `#AI agents`, `#Azure Blob Storage`, `#distributed systems`

---

<a id="item-tech-news-5"></a>
### [微软研究院 AI Frontiers 团队据报结束](https://hunch.net/?p=13764006) ⭐️ 7.0/10

据 Hacker News 讨论中链接的报道，微软研究院的 AI Frontiers 研究组被宣告结束，研究员 John Langford 将离开。帖子本身以链接为主，未提供微软官方确认、团队规模或人员安置细节。目前应把这则消息视为待独立证实的组织与人事变动信号。

hackernews · srean · 11月7日 18:02 · [社区讨论](https://news.ycombinator.com/item?id=50406563)

**「背景」** AI Frontiers 是 Microsoft Research 旗下专注于 AI 基础突破的研究团队，并非一个产品；据报该团队约有 50 人，由 John Langford 共同创建。该团队于 2026 年 9 月初被划入 Microsoft AI，随后在 MAI 以扩展（scaling）为优先方向的重组中被关闭，Langford 也由此离开。

**「影响」** 对依赖微软研究院公开论文、代码或合作项目的 AI 研究者来说，若报道属实，一个探索性研究出口可能关闭；在官方说明出现前，相关项目是否迁移、人员如何安排仍不确定。

**「社区讨论」** 评论者多把此事解读为大公司集中资源押注 transformer 规模化、压缩探索性研究的信号，并有人以 Meta 的人事变动为例。也有评论认为研究与规模化应并行，另有人批评微软研究院“做好研究就有好结果”的旧契约被破坏。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://explainx.ai/blog/john-langford-microsoft-ai-frontiers-ended-mai-scaling-only-2026">Microsoft AI Frontiers Ends: Langford on MAI Clash - explainx.ai</a></li>
<li><a href="https://daily.dev/posts/microsoft-researcher-john-langford-exits-ai-frontiers-group-declared-finished-t8nprypt6">Microsoft Researcher John Langford Exits. AI Frontiers Group ...</a></li>

</ul>
</details>

**标签**: `#AI research`, `#Microsoft Research`, `#AI strategy`, `#industry news`, `#Hacker News`

---

<a id="item-tech-news-6"></a>
### [Claude Code 本地设置文件在 1,122 个公开 GitHub 文件中暴露凭据](https://apiiro.com/blog/coding-agents-leaking-secrets-github-dont-ask-again) ⭐️ 7.0/10

安全博客 Apiiro 的扫描报告称，公开 GitHub 仓库中有 1,122 个文件在 Claude Code 的本地设置里包含密码或密钥。问题并非仅由点击“Don&\#x27;t Ask Again”触发：用户需要把 .claude/settings.local.json 提交到仓库，且其中保存的已批准命令直接嵌入了明文凭据。Claude Code 团队的 Boris 表示，该工具过去没有做密钥清理，正在研究预防措施，并强调该文件应仅保留在本地、由 Claude 创建时会自动加入 gitignore，因此此次暴露的文件是用户手动创建并提交的。

hackernews · shmulc · 11月7日 20:45 · [社区讨论](https://news.ycombinator.com/item?id=50407882)

**「背景」** Claude Code 的“Don&\#x27;t Ask Again”会把用户批准的命令写入项目内的 .claude/settings.local.json，作为后续免确认的本地权限配置。Claude Code 团队在讨论中说明，该文件本应只留在本地，由 Claude 创建时会自动加入 .gitignore；此次暴露的前提是用户手动创建或提交了该文件，且其中保存的已批准命令本身含有密码或密钥。

**「影响」** 对使用 Claude Code 的团队来说，具体后果是：公开仓库中的 .claude/settings.local.json 可能包含已批准命令里内嵌的真实密码或密钥；一项统计称，1,122 个公开文件含有真实密钥，若把历史记录、共享设置和会话记录也计算在内，则涉及 2,539 个密钥、1,994 个仓库。应检查这些仓库中的该设置文件，并轮换已经暴露的凭据。

**「社区讨论」** 评论者 Aurornis 认为标题混淆了因果：仅点击“Don&\#x27;t Ask Again”不会泄露密码，只有把含明文密钥的已批准命令写入并提交本地设置才会暴露。tsergiu 和 binarymax 则分别报告了用隔离虚拟机加 API 代理、以及用 1Password CLI 指纹授权来限制代理访问凭据的做法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cellcog.ai/blog/claude-code-settings-secrets-github/">Claude Code&#x27;s settings.local.json Is Leaking Secrets | CellCog</a></li>
<li><a href="https://www.agentbeam.com/blog/claude-code-dont-ask-again-settings-local-json-secrets-public-github">Claude Code settings.local.json Leaks Secrets on GitHub | Beam</a></li>

</ul>
</details>

**标签**: `#AI coding agents`, `#security`, `#secrets management`, `#GitHub`, `#Claude Code`

---

<a id="item-tech-news-7"></a>
### [Coldframe：伪装超市冷柜控制器的单文件蜜罐](https://github.com/hedgerow-dev/coldframe) ⭐️ 7.0/10

作者发布了 Coldframe：一个仅用 Python 标准库实现的单文件蜜罐，伪装成 Danfoss AK-SM 800A 和 Dixell XWEB 超市制冷控制器界面，并识别针对这些设备的漏洞利用尝试，包括 CVE-2025-41450（Danfoss“当日代码”登录绕过）、另外三个 Danfoss CVE 及 XWEB 漏洞。它依据 Shodan 上的真实设备记录匹配 HTTP 头顺序、页面标题、TLS 版本和证书字段等细节，默认登录会进入带除霜按钮的假门店仪表盘，以便观察攻击者的下一步操作。作者称两个实例已上线一天，目前只看到通用扫描器和 Shodan 爬虫 refrigerator.census.shodan.io；项目建立在 eppser/danfoss-ak-sm-decoy 及 Synacktiv、Claroty、Ironhackers 的公开研究之上。

hackernews · hedgerow-dev · 11月7日 17:27 · [社区讨论](https://news.ycombinator.com/item?id=50406292)

**「背景」** Danfoss AK-SM 8xxA 系列在 4.2 版本之前存在 CVE-2025-41450 身份验证绕过漏洞，可导致特权访问，这也是 Coldframe 重点识别的一类真实攻击面。该项目还延续了 eppser/danfoss-ak-sm-decoy 的诱捕思路，并参考 Synacktiv、Claroty 和 Ironhackers 的公开研究来构造更可信的设备伪装。

**「实际影响」** 对 ICS 安全研究者，这个工具提供了无需第三方依赖、可记录登录后交互和漏洞利用标签的诱饵；但伪装参数来自 Shodan 记录，且一天的在线观测只覆盖扫描器，尚不足以证明它能长期骗过真实攻击者。

**「社区讨论」** 评论中，supriyo-biswas 对用 Shodan 数据校准诱饵表示怀疑，认为网上许多可见设备本身就是蜜罐或已被入侵，建议先取得一台易受攻击的真实设备进行探测；xrd 则追问近期大规模制冷设备事件是否已有确凿的黑客攻击结论，显示相关前提仍存在争议。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://vulners.com/cve/CVE-2025-41450">CVE - 2025 - 41450 - vulnerability database | Vulners.com</a></li>
<li><a href="https://www.danfoss.com/en/service-and-support/coordinated-vulnerability-disclosure/danfoss-security-advisories/">Danfoss security advisories | Danfoss</a></li>

</ul>
</details>

**标签**: `#honeypots`, `#ICS security`, `#industrial control systems`, `#Danfoss`, `#Shodan`

---

<a id="item-tech-news-8"></a>
### [MaxxBench：DeepSWE 分数经任务改写后未必稳健](https://maxxbench.unlap.ai/research/why-maxxbench/) ⭐️ 7.0/10

MaxxBench 对 DeepSWE 基准的任务说明进行扰动，以检验已报告分数是否稳健，结论是这些分数未必能泛化到改写后的任务。分析称，部分模型在扰动下明显退化，尤其是名称带“flash”的较小变体。该文属于对评测方法的批评，而非新模型或新基准发布。

hackernews · antiuniverse · 11月7日 17:19 · [社区讨论](https://news.ycombinator.com/item?id=50406222)

**「背景」** DeepSWE 是面向长周期软件工程任务的编码代理基准：其提示长度约为 SWE-bench Pro 的一半，但解题所需代码量约为后者的 5.5 倍，覆盖 91 个仓库和 5 种语言，并用人工编写的验证器检查软件行为而非实现细节。Artificial Analysis 的编码代理排行榜也收录了 DeepSWE v1.1，说明这类分数常被用来横向比较模型；MaxxBench 此次检验的正是这些分数在任务描述被改动后是否仍然可靠。

**「影响」** 对依赖 DeepSWE 选型的团队来说，只看原始榜单分数可能高估模型在任务描述稍有变化时的表现；更稳妥的做法是先用改写后的任务说明复测候选模型，并单独检查较小或“flash”变体的稳定性。

**「社区讨论」** 评论者认为，改变一个参数并观察分数变化，是检验基准泛化性的低成本方法，并指出图中较小模型退化最明显；也有人提到 DeepSWE 本身存在缺陷，以及“不要使用 max 模式”的实用结论。另有评论者把问题归因于训练环境未充分变化，而非模型直接针对基准训练。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://deepswe.datacurve.ai/">DeepSWE measures frontier coding agents on original, long-horizon...</a></li>
<li><a href="https://deepswe.lol/">DeepSWE — Long-Horizon Software Engineering Benchmark</a></li>
<li><a href="https://artificialanalysis.ai/agents/coding-agents">AI Coding Agent Benchmarks &amp; Leaderboard | Artificial Analysis</a></li>

</ul>
</details>

**标签**: `#llm-benchmarks`, `#benchmark-validity`, `#model-evaluation`, `#ai-evaluation`, `#deepswe`

---

<a id="item-tech-news-9"></a>
### [Asahi Linux 7.3 报告：Fedora Asahi Remix 首次同日发布](https://asahilinux.org/2026/11/progress-report-7-3/) ⭐️ 7.0/10

Asahi Linux 7.3 进度报告的核心更新是 Fedora Asahi Remix 首次与上游 Fedora 同日发布；社区评论引述称，对应版本为 11 月 3 日发布的 Fedora Linux 45。报告还涵盖 Apple Silicon 上 Linux 的持续硬件支持工作，但现有材料未列出具体设备、功能或剩余缺口。

hackernews · ackyshake · 11月7日 05:20 · [社区讨论](https://news.ycombinator.com/item?id=50401867)

**「背景」** Asahi Linux 是让 Linux 能在 Apple Silicon Mac 上运行的开源项目，Fedora Asahi Remix 则是该项目提供的 Fedora 发行版。其进展报告按阶段汇总内核与硬件支持工作；本次 7.3 报告的一个直接背景是 Fedora Asahi Remix 首次做到与上游 Fedora Linux 45 同日发布。

**「实际影响」** 对 Apple Silicon 用户而言，Fedora Asahi Remix 首次与上游 Fedora Linux 45 同日发布，意味着选择该发行版的用户不必再像过去那样等待数月才能获得新版 Fedora 的软件包与更新。不过硬件支持仍不完整：有评论者指出 USB-C 外接显示器支持仍缺失，这会让需要外接屏幕的 MacBook Air 用户暂时无法把它当作主力系统。

**「社区讨论」** 有评论者表示，USB-C 外接显示器支持仍是其采用 Asahi Linux 的主要障碍，并对项目优先支持较新 CPU 表示不解；这是个人使用诉求，不代表项目路线。另有评论者就报告提到的宽松许可证被利用一事，追问是否指 Omarchy，并认为该项目当初采用 MIT 而非 GPL 令人意外。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://asahilinux.org/2026/11/progress-report-7-3/">Progress Report : Linux 7 . 3 - Asahi Linux</a></li>

</ul>
</details>

**标签**: `#Asahi Linux`, `#Apple Silicon`, `#Linux`, `#Open Source`, `#Fedora`

---

<a id="item-tech-news-10"></a>
### [Claude Code 被指联网请求泄露登录邮箱](https://github.com/anthropics/claude-code/issues/107757) ⭐️ 7.0/10

一名开发者投诉称，Claude Code 会在联网搜索请求中填入并发送用户的登录邮箱，导致其每天收到大量诈骗邮件。Anthropic 工程师回应称，登录邮箱最初被放入模型上下文，是为了解决 Claude 乱填作者名的问题；该问题今年 7 月已有人报告，邮箱曾被发送给 Wikipedia、美国证券交易委员会等网站。2.1.317 版已加入拦截，但可用 Python 脚本绕过，公司计划在下一版本从上下文中移除登录邮箱。

telegram · zaihuapd · 11月7日 08:09

**「背景」** 根据该 issue 的描述，邮箱是在 Claude Code 执行联网搜索时随 User-Agent 请求头一起发出的，并非出现在网页内容里。Anthropic 工程师在讨论中解释，把登录邮箱放进模型上下文，最初是为了纠正 Claude 生成内容时乱填作者名的问题；相关报告最早在今年 7 月出现。Hacker News 上也有评论对影响范围提出质疑，认为邮箱并非默认或频繁发送，且 Wikipedia 与美国证券交易委员会并不会出售邮箱地址。

**「影响与应对」** 2.1.317 版的拦截可被 Python 脚本绕过，因此使用联网搜索的开发者不能把该版本视为已修复；在下一版从模型上下文中移除登录邮箱之前，邮箱仍可能被发送到 Wikipedia、美国证券交易委员会等第三方站点，相关用户可能因此收到诈骗邮件，需要警惕钓鱼邮件，或暂时避免让 Claude Code 发起联网请求。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/anthropics/claude-code/issues/107757">Bug Report: Privacy violation in User-Agent header · Issue # 107757 ...</a></li>
<li><a href="https://news.ycombinator.com/item?id=50385272">Claude Code sends your email address to websites | Hacker News</a></li>

</ul>
</details>

**标签**: `#Claude Code`, `#privacy`, `#security vulnerability`, `#AI coding tools`, `#Anthropic`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [伯克希尔第三季度回购翻倍至 96 亿美元，利润下滑](https://www.cnbc.com/2026/11/07/berkshire-hathaway-q3-2026-earnings-buybacks.html) ⭐️ 7.0/10

伯克希尔·哈撒韦在 2026 年第三季度将股票回购规模提高至 96 亿美元，超过第二季度 45 亿美元的两倍，尽管同期营业利润同比下降 5.8%至 127.05 亿美元，整体利润下降 28%至 221.12 亿美元。

rss · CNBC Finance · 11月7日 15:23

**「背景」** 格雷格·阿贝尔于 2026 年 1 月接任伯克希尔·哈撒韦 CEO，而此前在巴菲特执掌时期，公司很少使用回购。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://management.org/berkshire-hathaway-s-new-ceo-backs-his-own-judgment-with-a-4-5-billion-buyback">Berkshire Hathaway &#x27;s New CEO Backs His Own... - Management.org</a></li>

</ul>
</details>

**标签**: `#Berkshire Hathaway`, `#share buybacks`, `#earnings`, `#insurance`, `#cash reserves`

---

<a id="item-finance-news-2"></a>
### [软银与 ABB 考虑分拆中国机器人业务以挽救 54 亿美元收购](https://www.bloomberg.com/news/articles/2026-11-07/softbank-abb-weigh-china-carve-out-to-salvage-robotics-deal) ⭐️ 7.0/10

据报道，软银与 ABB 正考虑分拆 ABB 机器人业务的中国部分，以挽救被中国外商投资安全审查工作机制办公室本周四叫停的 54 亿美元收购；知情人士称，该中国业务估值可能为 20 亿至 30 亿美元。

telegram · zaihuapd · 11月7日 11:24

**「背景」** 拟议方案是为中国业务设立股权安排不同的独立实体，由软银主导；知情人士称此举可能失败，ABB 也在评估另寻买家等选项。

**标签**: `#M&amp;A`, `#China regulatory review`, `#robotics`, `#SoftBank`, `#ABB`

---