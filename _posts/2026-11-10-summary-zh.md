---
layout: default
title: "Horizon Summary: 2026-11-10 (ZH)"
date: 2026-11-10
lang: zh
---

> 从 46 条内容中筛选出 10 条重要资讯。

---

**科技新闻**
1. [Anthropic 据称发布 Claude Fable 5.2 与 Mythos 5.2](#item-tech-news-1) ⭐️ 7.0/10
2. [E-means 宣称以十分之一迭代轮数媲美 k-means](#item-tech-news-2) ⭐️ 7.0/10
3. [watched.earth：一周卫星过境与影像查询](#item-tech-news-3) ⭐️ 7.0/10
4. [Google Gemini 消费者版被指将个人数据转人工审核](#item-tech-news-4) ⭐️ 7.0/10
5. [谷歌发布 TPU 8tx 与 8i Max](#item-tech-news-5) ⭐️ 7.0/10
6. [LingBot-Touch：JEPA 式触觉预训练优于重建基线](#item-tech-news-6) ⭐️ 7.0/10
7. [县级新增停电两小时预报：PR-AUC 达警报基线 2.4 倍](#item-tech-news-7) ⭐️ 7.0/10
8. [OPPO、vivo、小米、荣耀上线 ADV 侧载开发者验证互认](#item-tech-news-8) ⭐️ 7.0/10
9. [欧盟数字公平法案草案拟限制成瘾性设计与游戏虚拟货币](#item-tech-news-9) ⭐️ 7.0/10

**财经新闻**
1. [英伟达董事会调查黄仁勋，股价跌逾 5%](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Anthropic 据称发布 Claude Fable 5.2 与 Mythos 5.2](https://www.anthropic.com/claude-fable-and-mythos-5-2) ⭐️ 7.0/10

Hacker News 上出现关于 Anthropic 据称发布 Claude Fable 5.2 与 Mythos 5.2 的讨论，但所给条目没有公告正文，模型规格、可用性和定价均无法从材料确认。评论者主要讨论 Fable 5.2 的实际编码表现：一位早期测试者称它用两天在约 60 万行 Fortran 材料科学代码库上把部分计算加速 36 倍，并计划开源结果；另一位评论者称 1,000 个 Fable 5.2 代理在 30 小时内完成了费马大定理的形式化，但该说法同样来自评论且原文被截断。还有用户表示，普通编码任务中 Fable 5.2 与 Opus 5.5 的差距不明显，需要把提示目标推得更激进才能看出区别。

hackernews · lairv · 11月9日 18:01 · [社区讨论](https://news.ycombinator.com/item?id=50429068)

**「背景」** Anthropic 的系统卡显示，Fable 5.2 与 Mythos 5.2 是同一新模型的两个配置：Fable 5.2 面向一般使用，并附加了防止模型执行生物学、网络安全等高风险双用途任务的安全措施；Mythos 5.2 是另一配置。CNBC 报道称，这是 Anthropic 自其 CEO 呼吁放缓以来首次发布前沿模型。

**「影响」** 对计算科学团队而言，最具体的信号是遗留 Fortran 代码优化可能成为大模型编码助手的实际用例；但 36 倍加速目前只是单一早期用户的报告，且所给材料没有官方复现或基准细节，采用前仍需自行验证。

**「社区讨论」** 评论中最实质的质疑集中在基准方法：为何用 Fable xHigh 对比 Carbon Med、为何 Carbon 的努力—智能曲线与现有基准相悖、为何在唯一的网络安全基准比较中漏掉主攻网络安全的 Carbon，以及 robodojo 为何改用 Argon 对比。另有评论者推测 5.2 而非 5.5 的命名与 OpenAI 和 Anthropic 的发布节奏博弈有关，但这只是未经证实的猜测。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://assets.claude.com/27d60918d218125e7504bc7354c4b4626ec56b11.pdf">Claude Fable 5.2 &amp; Claude Mythos 5.2 System Card</a></li>
<li><a href="https://www.cnbc.com/2026/11/09/anthropic-claude-fable-5-2-mythos-5-2.html">Anthropic releases Claude Fable 5.2 and Claude Mythos 5.2 ...</a></li>

</ul>
</details>

**标签**: `#Anthropic`, `#AI model release`, `#benchmarking`, `#coding assistants`, `#Hacker News discussion`

---

<a id="item-tech-news-2"></a>
### [E-means 宣称以十分之一迭代轮数媲美 k-means](https://e-means.github.io/) ⭐️ 7.0/10

E-means 项目页面提出一种 k-means 替代聚类方法，声称能在约为 k-means 十分之一的迭代轮数（epochs）内取得相当或更好的聚类结果。当前证据主要来自项目自述和从业者的初步试验，尚缺独立基准验证。社区中有人将其适配到 IVF 索引并在 GPU 上报告 146 倍加速，也有团队称在分片拆分等全量重建场景中快 2.5 倍，但日常增量插入的整体耗时变化不大；另有实践者称该方法在球面等面积网格的 Lloyd 松弛场景中反而更差。

hackernews · porridgeraisin · 11月9日 18:45 · [社区讨论](https://news.ycombinator.com/item?id=50429734)

**「背景：Lloyd 算法与 e-means 的差异」** 传统 k-means 依赖 Lloyd 算法反复执行“把点分配给最近质心、再重算质心”这两个阶段，每轮都要遍历全量数据，因此达到收敛所需的迭代轮数（epoch）直接决定计算成本。据 arXiv 论文摘要，e-means 改用小批量更新，并结合指数移动平均来移动质心：在多个嵌入数据集上，它用 1.4 至 2.6 个 epoch 就达到 Lloyd k-means 训练 25 个 epoch 时的损失水平（tool-1-1）；第三方介绍也把它概括为用基于指数移动平均的小批量更新取代 Lloyd 迭代（tool-1-3）。

**「影响」** 对使用 IVF 索引或需要批量重建索引的团队，适配 E-means 可能明显缩短聚类阶段，但已有报告显示整体插入耗时未必下降，且在球形网格等特定几何场景可能退化，采用前应按自身数据分布和工作负载复测。

**「社区讨论」** 评论者 real\_faxenoff 报告在 IVF 索引上适配后获得 GPU 146 倍加速，kingcauchy 则称分片拆分等全量重建快 2.5 倍、但增量插入整体变化不大；jlhawn 的球面网格试验结果明确更差。shiandow 还从期望最大化或模拟退火的角度讨论其更新规则，并指出质心保持在凸包内很重要。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/pdf/2611.09501">e-means: outperforming k-means (in one-tenth the epochs)</a></li>
<li><a href="https://daily.dev/posts/e-means-10x-faster-k-means-at-equal-loss-wjgmcpump">E-means: 10x faster k-means at equal loss - daily.dev</a></li>

</ul>
</details>

**标签**: `#clustering`, `#k-means`, `#algorithms`, `#performance`, `#vector-search`

---

<a id="item-tech-news-3"></a>
### [watched.earth：一周卫星过境与影像查询](https://www.watched.earth/) ⭐️ 7.0/10

watched.earth 是一个开源浏览器工具：输入任意地点后，它会用 SGP4 和 CelesTrak 目录检索过去 7 天内经过该地的卫星，作者称搜索约半秒完成，再调取这些过境对应的 Sentinel-2、Landsat 和 NASA 实际影像。作者称，过境搜索已用暴力枚举在极点、反子午线和小幅宽等场景中核对，未漏掉过境；约 1.7 万个在轨目标由 GPU 每帧求解开普勒方程绘制。工具还处理了 Sentinel-2 时间戳与实际过境时刻常相差 5–10 分钟的问题，并且仅在存在真实影像时标记“watched”，同时表示不存储用户位置。源码已在 GitHub 公开。

hackernews · a585gupt · 11月9日 17:51 · [社区讨论](https://news.ycombinator.com/item?id=50428907)

**「背景」** SGP4 是一种轨道传播模型，CelesTrak 则提供公开的卫星轨道目录；工具在浏览器里用这两者按时间推算卫星位置，从而判断过去一周内哪些卫星经过指定地点。Sentinel-2、Landsat 和 NASA 的影像是公开遥感数据，但卫星过境时刻与影像时间戳可能相差数分钟，匹配时需要处理这一偏差。

**「实际影响」** 对需要确认某地近期是否被公开卫星拍摄的用户，它把卫星过境搜索与影像检索放在同一个浏览器流程中；由于源码公开，且作者称不存储位置，使用者可以自行审查或部署。

**「社区讨论」** 多位评论者称赞其视觉呈现与多源数据整合，一位自称从事地理空间工作的用户表示能看到卫星实际拍摄的影像；另一位用户说它适合规划徒步行程，覆盖比 Copernicus 更多且更易访问。

**标签**: `#satellite-tracking`, `#SGP4`, `#geospatial`, `#orbital-mechanics`, `#open-source`

---

<a id="item-tech-news-4"></a>
### [Google Gemini 消费者版被指将个人数据转人工审核](https://github.com/thisisme6598/gemini_files/) ⭐️ 7.0/10

Hacker News 讨论中流传的说法称，消费者版 Google Gemini 在用户授权 Connected Apps 后，会把个人 Drive 文件和 Gmail 邮件交给人工标注员处理。评论者指出，这针对的是消费者版 Gemini，而非 Workspace Gemini；后者仍声称不受人工审查。该说法源自一个 GitHub 帖子，尚无 Google 官方说明或独立核验，应视为未经证实的指控。

hackernews · gf74918 · 11月9日 18:24 · [社区讨论](https://news.ycombinator.com/item?id=50429426)

**「背景」** Google 的 Gemini Apps 隐私中心说明，用户授权 Connected Apps 后，在符合条件并选择开启个性化时，Google 会使用这些应用的数据来个性化 Gemini。AI Weekly 的一则报道称，Google 在 2026 年 10 月修改政策，推翻了 2023 年“个人 Drive 和 Gmail 内容不会被人工审阅”的承诺，并形成最长三年、且用户删除后仍可能保留的数据留存流程。这为当前关于消费者版 Gemini 连接个人应用后数据可能进入人工审阅的争议提供了政策背景，但相关说法仍需以 Google 官方说明为准。

**「消费者版与企业版的处理差异」** 对已授权 Gmail、Drive 等连接应用的消费者版 Gemini 用户来说，实际后果是个人邮件和文件可能进入人工审阅流程；Google 面向消费者版的说明本身即建议不要输入不愿被人工审阅者看到的内容。相比之下，Workspace 企业版 Gemini 受企业协议约束，数据不用于训练模型并保留在 Workspace 保护范围内，因此处理敏感材料时应改用 Workspace 账号，或断开消费者账号中已授权的连接应用。

**「社区讨论」** 评论者 bri3d 区分了消费者版与 Workspace 版的数据处理，并称 Workspace Gemini 仍承诺不受人工审查；rustyhancock 则抱怨 Gemini 的回答有时与邮件内容高度吻合，却未披露读取了邮件。另有评论者认为，任何带人工审核的模型都可能让用户数据被阅读或泄露，因此对隐私现状感到不满。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://support.google.com/gemini/answer/13594961?hl=en">Gemini Apps Privacy Hub - Google Help</a></li>
<li><a href="https://support.google.com/gemini/answer/13594961?hl=en-BD">Gemini Apps Privacy Hub - Gemini Apps Help - Google Help</a></li>
<li><a href="https://aiweekly.co/alerts/google-gemini-routes-personal-drive-gmail-to-human-reviewers">Google Gemini Routes Personal Drive, Gmail to Human Reviewers</a></li>
<li><a href="https://knowledge.workspace.google.com/admin/generative-ai/generative-ai-in-google-workspace-privacy-hub">Generative AI in Google Workspace Privacy Hub</a></li>
<li><a href="https://www.strac.io/blog/gemini-data-privacy">Gemini Data Privacy: What Google Collects &amp; Reviews (2026)</a></li>

</ul>
</details>

**标签**: `#Google Gemini`, `#AI privacy`, `#human annotation`, `#consumer AI`, `#data governance`

---

<a id="item-tech-news-5"></a>
### [谷歌发布 TPU 8tx 与 8i Max](https://blog.google/innovation-and-ai/infrastructure-and-cloud/global-network/tpu-8i-max-and-8tx/) ⭐️ 7.0/10

谷歌宣布推出两款新张量处理单元：TPU 8tx 面向政府机构及受严格监管行业，用于处理安全机密数据，并将与 AMD 芯片协同工作；TPU 8i Max 面向超长上下文窗口 AI 应用，把两颗 TPU 芯片集成在同一封装内，以提供更强算力和更大内存。谷歌表示正打破过去每两年推出一款新处理器的节奏，今年连续扩充 TPU 产品线，苹果、Meta、甲骨文和 Anthropic 等已成为客户。目前披露的信息未包含两款芯片的性能、功耗、价格或具体上市时间。

hackernews · \_benx\_ · 11月9日 21:56 · [社区讨论](https://news.ycombinator.com/item?id=50432831)

**「背景」** TPU 是谷歌自研的 AI 加速芯片，谷歌正将其定位为英伟达 GPU 之外的云端算力选择，苹果、Meta、甲骨文和 Anthropic 等已成为其客户。谷歌过去大致每两年推出一款新 TPU，今年则打破这一节奏，改为针对不同场景连续扩充产品线。

**「影响」** 对需要处理机密数据的政府机构与受监管行业客户而言，TPU 8tx 是新增的专用选项，但它要与 AMD 芯片协同工作，部署方案因此需要同时兼容两套硬件栈。对超长上下文推理场景，8i Max 把两颗 TPU 集成在同一封装内，以单封装内存容量换取更大的可用上下文窗口；不过公告未披露功耗、每 token 成本或价格，采购方目前无法据此与英伟达 GPU 做单位成本对比。

**「社区讨论」** 有评论者追问每 token 的功耗和成本，并要求与英伟达同价位产品对比，认为公告缺少这些关键指标；另一名用户则希望 Google Colab 能提供更新的 TPU，称目前可用的最强型号仍是 v6e-1，难以支撑严肃工作。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cloud.google.com/blog/topics/ai-infrastructure/tpu-8tx-and-tpu-8i-max">Introducing TPU 8tx and TPU 8i Max | Google Cloud Blog</a></li>
<li><a href="https://www.datacenterknowledge.com/data-center-chips/google-adds-tpu-8tx-8i-max-for-enterprise-ai">Google Adds TPU 8tx, 8i Max for Enterprise AI</a></li>

</ul>
</details>

**标签**: `#TPU`, `#Google Cloud`, `#AI infrastructure`, `#hardware`, `#agentic AI`

---

<a id="item-tech-news-6"></a>
### [LingBot-Touch：JEPA 式触觉预训练优于重建基线](https://www.reddit.com/r/MachineLearning/comments/1xs05uo/latent_prediction_beats_reconstruction_for/) ⭐️ 7.0/10

Reddit 帖子介绍 Robbyant 的 LingBot-Touch：一个 JEPA 式自监督触觉编码器，预测被遮挡接触的潜在表示而非重建原始传感器信号，并已公开推理代码和检查点。帖子称，在相同数据上对比同尺寸 MAE、VAE 重建模型，触觉到视频的 top-5 召回率在 1K 小时为 32.1%（MAE 5.6%、VAE 4.4%），到 4K 小时 JEPA 为 49.3%，MAE 低于 9%，VAE 反而降至 3.1%；其掩码比例从 40% 预热到 80%，并通过规范指尖坐标和 5D RoPE 让三种传感器共享一个 Transformer。在 26 个真实机器人任务、4 种策略下，冻结编码器特征在 104 个策略与任务组合中有 89 个得分最高；在预训练中未见过的磁触觉手上，LingBot-VLA 从 57.21 提升到 75.04。上述数字来自帖子摘要，尚未经独立验证。

reddit · r/MachineLearning · /u/Zealousideal-War7154 · 11月9日 18:52

**「背景」** LingBot-Touch 属于蚂蚁集团旗下具身智能公司 Robbyant 的 LingBot 模型家族，该家族此前已开源世界模型 LingBot-World，以及把图像边界当作原生预训练信号、参数量 1B 的自监督视觉模型 LingBot-Vision。JEPA（联合嵌入预测架构）的核心做法是在潜空间中预测被掩码部分的表示，而不是像 MAE/VAE 那样重建原始像素或传感器信号；LingBot-Touch 把这一思路用于触觉信号，因此论文选择的对照基线正是同尺寸的 MAE 与 VAE 重建模型。

**「对灵巧操作触觉研发的影响」** 对做灵巧操作的研究团队来说，可直接把公开的推理代码和检查点作为冻结触觉编码器接入现有流程；LingBot-VLA 已公开代码与预训练权重，便于在同一套基础上验证触觉特征。来源称在预训练中未见的磁性手上，LingBot-VLA 的指标从 57.21 提升到 75.04，但这是作者自报结果，尚非独立复现。复现时需按论文设置让掩码比例从 40% 逐步升到 80%，因为一开始就用高掩码会遮住稀疏信号中的接触点并引发梯度爆炸。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://technology.robbyant.com/">Technology - Robbyant</a></li>
<li><a href="https://github.com/Robbyant/lingbot-world">GitHub - Robbyant / lingbot -world: Advancing Open-source World...</a></li>
<li><a href="https://www.youtube.com/watch?v=c8dJI75WcfY">LingBot -Vision: Ant Group&#x27;s 1B Boundary-Centric Vision... - YouTube</a></li>
<li><a href="https://aiwiki.ai/wiki/lingbot_vla_2_0">LingBot - VLA 2.0 | AI Wiki</a></li>

</ul>
</details>

**标签**: `#tactile sensing`, `#self-supervised learning`, `#JEPA`, `#dexterous manipulation`, `#robotics`

---

<a id="item-tech-news-7"></a>
### [县级新增停电两小时预报：PR-AUC 达警报基线 2.4 倍](https://www.reddit.com/r/MachineLearning/comments/1xs4hq8/forecasting_new_power_outages_per_county_hourly_2/) ⭐️ 7.0/10

一位 Reddit 用户发布了一个覆盖密苏里州和伊利诺伊州 216 个县的小时级模型，用于预测“未来 2 小时起 6 小时内某县新增停电客户达到 5% 及以上”的概率；模型以 XGBoost 结合 HRRR 风暴相关预报、县级特征、当前停电和邻县数据，训练期为 2020–2024 年。作者报告在 2025 年留出测试中，该模型的 PR-AUC 为 0.094，而基于 NWS 警报和 SPC 第一日展望的基线为 0.039，约为后者的 2.4 倍（自助法 95% 区间 2.0–3.3 倍）。在相同警报量下，模型捕获 30% 的新增停电事件，基线为 17%，精确率分别为 15% 和 11%；县小时基准发生率仅 0.5%。该结果来自未经同行评审的 Reddit 帖子和作者自述，且仅覆盖两州、单一年份；模型自 11 月 1 日起在线运行并保存每次预报，供盲测使用。

reddit · r/MachineLearning · /u/CarRepresentative843 · 11月9日 21:34

**「背景」** 这项任务把“新停电”定义为未来 6 小时窗口内某县新增至少 5% 用户断电，且预测时点提前 2 小时；由于县-小时样本中正例仅约 0.5%，PR-AUC 比 ROC-AUC 更能反映稀有事件下的预警质量。基线用 NWS 预警和 SPC Day 1 展望拟合发生率表，代表业务中可获得的官方风险信号，因此模型比较的是相对这类信号的增量。

**「影响」** 对希望用机器学习补充或替代固定警报阈值表的停电预报团队，这项结果提供了一个可操作的比较口径：在相同警报量下比较召回率和精确率，而不只看 PR-AUC；但两州 216 县、单一年份和未经评审的限制意味着不能直接外推到其他服务区。

**标签**: `#power outage forecasting`, `#XGBoost`, `#weather data`, `#PR-AUC`, `#applied machine learning`

---

<a id="item-tech-news-8"></a>
### [OPPO、vivo、小米、荣耀上线 ADV 侧载开发者验证互认](https://mp.weixin.qq.com/s/ZiKBASSLzvsZ6WR2AUmFeg) ⭐️ 7.0/10

OPPO、vivo、小米、荣耀已在中国大陆上线面向 Android 侧载应用的 ADV（开发者身份验证）机制，并支持四家平台的验证结果互认。已在四家开放平台注册上架的 APP 会自动提交验证，无需单独申请。未完成验证的应用在侧载安装时会显示“未验证”提示，用户需手动确认后才能继续安装。

telegram · zaihuapd · 11月9日 11:44

**「背景」** 谷歌此前推动 Android 开发者验证（ADV）计划，并联合小米、OPPO、vivo、荣耀、三星、传音等厂商，计划于 2026 年 9 月 30 日在巴西、印尼、新加坡、泰国率先实施，要求侧载应用关联可验证的开发者身份（tool-2-2）。此次四家中国厂商在中国大陆上线互认的 ADV 机制，属于同一验证思路在本地侧载场景的落地；但谷歌方案的国际推进时间表与四家厂商的本地规则并不等同。

**「影响」** 对依赖侧载分发的未验证应用而言，安装不会被直接阻止，但会增加“未验证”提示和手动确认步骤，分发方需预期用户安装流程发生变化；已在四家平台注册上架的应用则自动进入验证流程，无需单独申请。现有信息未说明未在四家平台注册上架的应用如何单独申请验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://post.smzdm.com/p/anvomm2v/">安 卓 彻底告别自由 侧 载 ？ 谷歌联合六大厂商，装陌生APK等24...</a></li>

</ul>
</details>

**标签**: `#Android sideloading`, `#developer verification`, `#app security`, `#China mobile ecosystem`, `#Android`

---

<a id="item-tech-news-9"></a>
### [欧盟数字公平法案草案拟限制成瘾性设计与游戏虚拟货币](https://www.mlex.com/mlex/articles/2546584/digital-businesses-face-addictive-design-controls-under-draft-eu-consumer-law) ⭐️ 7.0/10

一份泄露的欧盟《数字公平法案》草案拟限制成瘾性设计和订阅陷阱，要求数字企业允许用户关闭自动播放、连续使用奖励等诱导强迫或过度使用的功能，并为在线订阅提供取消按钮、续费提醒和人工客服，在免费试用转为付费订阅前取得用户明确同意。草案还拟禁止面向未成年人的游戏付费抽奖、“付费获胜”和画像广告，并要求游戏虚拟货币标明真实币值。欧盟委员会计划于 11 月 11 日提交该法案，违规企业最高可被罚全球营业额的 6%；该提案仍需欧洲议会和欧盟各国政府同意才能生效。

telegram · zaihuapd · 11月9日 16:42

**「背景」** 《数字公平法案》目前仍是泄露的草案，而非已生效法律；它由欧盟委员会提出，并需欧洲议会与欧盟各国政府同意后才能生效。草案把成瘾性设计、订阅陷阱和游戏内虚拟货币定价披露纳入消费者保护规则，并与消费者保护合作框架改革配套推进，违规企业最高面临全球营业额 6% 的罚款。

**「对开发者的影响」** 对在欧盟提供游戏或订阅服务的开发者而言，草案一旦按泄露文本生效，产品需增加订阅取消入口、续费提醒和人工客服，并在免费试用转付费前取得明确同意；面向未成年人的付费抽奖、付费获胜机制和画像广告将被禁止，虚拟货币须标注真实币值。由于该文本仍是泄露草案、且须经欧洲议会和成员国批准，企业应先评估这些设计改动和最高达全球营业额 6%的罚款风险，而不宜把它当作已生效规则。

**标签**: `#EU regulation`, `#consumer protection`, `#dark patterns`, `#gaming monetization`, `#digital policy`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [英伟达董事会调查黄仁勋，股价跌逾 5%](https://www.cnbc.com/2026/11/09/jensen-huang-nvidia-exit-prediction-markets.html) ⭐️ 7.0/10

据 CNBC 报道，英伟达董事会正调查 CEO 黄仁勋，缘由是有关他成为“外国情报行动”目标的报道，公司股价周一下跌超过 5%。预测市场 Kalshi 的交易员认为他在 2027 年前离职的概率为 17%，Polymarket 则给出到 2027 年 3 月底前辞职或被罢免的四分之一概率。

rss · CNBC Finance · 11月9日 18:46

**「背景」** 英伟达董事会此前宣布，在媒体报道黄仁勋成为“外国情报行动”目标后，启动由独立董事委员会和外部独立律师监督的独立调查，并称美国国家和经济安全是其首要考量。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://investor.nvidia.com/news/press-release-details/2026/Statement-from-NVIDIA-Board-of-Directors/default.aspx">NVIDIA Corporation - Statement from NVIDIA Board of Directors</a></li>
<li><a href="https://www.theguardian.com/us-news/2026/nov/08/nvidia-jensen-huang-investigation">Nvidia opens investigation after report CEO Jensen Huang was ...</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#corporate governance`, `#CEO succession`, `#prediction markets`, `#market reaction`

---