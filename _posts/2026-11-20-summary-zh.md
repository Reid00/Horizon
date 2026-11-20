---
layout: default
title: "Horizon Summary: 2026-11-20 (ZH)"
date: 2026-11-20
lang: zh
---

> 从 33 条内容中筛选出 11 条重要资讯。

---

**科技新闻**
1. [PostgreSQL 19 发布：新增 WAIT FOR LSN 保障备库读一致性](#item-tech-news-1) ⭐️ 9.0/10
2. [Anthropic 纳斯达克首秀引发估值与就业讨论](#item-tech-news-2) ⭐️ 8.0/10
3. [Anthropic 称 Claude 协助解决两个黑洞物理开放问题](#item-tech-news-3) ⭐️ 8.0/10
4. [OpenAI 称模型助芯片设计，AMD 旗舰 GPU PPA 提升最高 14%](#item-tech-news-4) ⭐️ 8.0/10
5. [Gemini 在 Mac 上可代用户操作，支持后台运行与暂停](#item-tech-news-5) ⭐️ 8.0/10
6. [PHP 混合大小写 HTTPS 静默关闭 TLS，补丁发布](#item-tech-news-6) ⭐️ 8.0/10
7. [欧盟委员会向逾 4 万名员工部署 Matrix](#item-tech-news-7) ⭐️ 7.0/10
8. [OpenJDK“java4shell”漏洞报告被 Oracle 接管](#item-tech-news-8) ⭐️ 7.0/10
9. [英国政府被迫承认向 Apple 发出秘密加密命令](#item-tech-news-9) ⭐️ 7.0/10
10. [PHP 计划 11 月 19 日发布 CRITICAL 级安全更新](#item-tech-news-10) ⭐️ 7.0/10
11. [Google Play 2027 年起要求应用适配折叠屏与大屏](#item-tech-news-11) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [PostgreSQL 19 发布：新增 WAIT FOR LSN 保障备库读一致性](https://simonwillison.net/2026/Nov/19/postgresql-19/) ⭐️ 9.0/10

PostgreSQL 19 已发布，比通常的 9 月发布窗口晚了两个月；来源文章称，延迟主要因为团队需要处理大量由 AI 报告的漏洞问题。新版本为把读请求发往备库的应用加入 \`WAIT FOR LSN\` 命令：备库会话可先等待 WAL 回放到指定 LSN，再执行查询，从而读到主库刚写入的数据，实现“读己之写”一致性。该命令支持可选的 \`TIMEOUT\`，若备库在指定时间内未追上会返回错误。

rss · Simon Willison · 11月19日 20:43

**「背景」** PostgreSQL 的流复制备库是异步重放预写日志（WAL）的，因此应用把读请求发到备库时，可能读到落后于主库的数据，也就是常说的复制延迟。PostgreSQL 19 原定按惯例在 9 月发布，但据搜索结果，大量由 AI 辅助审查提交的缺陷报告迫使团队推迟发布并回退部分特性，最终晚了约两个月。

**「影响」** 使用备库读的开发者需要在写入后取得主库的 LSN（例如通过 \`pg\_current\_wal\_insert\_lsn\(\)\`），将其随会话或请求传递，并在下一次备库查询前执行 \`WAIT FOR LSN\`；若设置 \`TIMEOUT\`，应用还需处理超时报错。

<details><summary>参考链接</summary>
<ul>
<li>Postgres 19 delayed after AI reviewers find more bugs than humans can fix</li>
<li>Postgres 19 delayed after AI reviewers find more bugs than humans can fix</li>

</ul>
</details>

**标签**: `#PostgreSQL`, `#databases`, `#open source`, `#replication`, `#release`

---

<a id="item-tech-news-2"></a>
### [Anthropic 纳斯达克首秀引发估值与就业讨论](https://www.reuters.com/business/finance/anthropics-historic-debut-put-ais-promise-peril-wall-st-test-2026-11-19/) ⭐️ 8.0/10

Anthropic 已在纳斯达克首次亮相，进入公开市场，围绕其估值的讨论随之展开。提供的材料没有给出发行价、募资规模、首日收盘价或市值等具体数据；社区评论中出现的 83 美元、111.5 美元、97.17 美元和 1.26 万亿美元等数字只是评论者说法，不能视为已确认的发行结果。因此，目前可确认的是上市事件本身，以及它引发的对 AI 公司估值和软件工程就业前景的讨论，尚不能确认首日交易表现。

hackernews · wslh · 11月19日 17:02 · [社区讨论](https://news.ycombinator.com/item?id=50562754)

**「背景」** Anthropic 是 Claude 模型的开发商。上市前，该公司将 IPO 定价为每股 83 美元，高于路演时 70–78 美元的初始区间，并发行 9.8 亿股；按 111.50 美元的开盘价计算，估值一度达到约 2 万亿美元，募资规模为 813 亿美元。

**「公开定价与首日买卖双方的分化」** 据社区评论引用的首日交易数据，Anthropic 收盘报 97.17 美元，较 83 美元发行价上涨 17.07%，但较 111.5 美元开盘价下跌 12.85%，这意味着按发行价获配的投资者与在开盘价买入的投资者当日结果相反。上市也让 Anthropic 成为少数拥有公开市场定价的 AI 实验室，其 S-1 中披露的 800 亿美元亏损随之进入公开估值框架（tool-3-1、tool-3-2）；评论者据此认为，此后同类 AI 公司在一级市场融资时的估值将直接与这一公开价格相比较。

**「社区讨论」** 评论者对首日表现看法不一：有人按 83 美元发行价、111.5 美元开盘价和 97.17 美元收盘价指出，该股较发行价上涨 17.07%，但较开盘价下跌 12.85%；也有人称市值已降至 1.26 万亿美元，并认为这对 OpenAI 的私募估值不利。多名软件工程师则担心 AI 正在压缩传统编程岗位的长期前景，这些都属于个人判断而非已核实数据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.euronews.com/2026/11/19/anthropic-shares-open-34-above-ipo-price-in-nasdaq-debut-after-record-listing">Anthropic shares open 34% above IPO price in Nasdaq debut</a></li>
<li><a href="https://indianexpress.com/article/business/world-market/anthropic-nasdaq-debut-valuation-ai-ipo-10970472/">Anthropic blows past $2 trillion in Nasdaq debut ... - The Indian Express</a></li>
<li><a href="https://intellectia.ai/blog/anthropic-ipo-analysis-2026">Anthropic IPO Analysis 2026: $2T Valuation and AI Market Impact</a></li>
<li><a href="https://www.vistaequitypartners.com/insights/anthropic-ipo-takeaways-impact-on-software/">Takeaways From the Anthropic S-1: What It Means for Software</a></li>

</ul>
</details>

**标签**: `#Anthropic`, `#AI industry`, `#IPO`, `#valuation`, `#software engineering labor`

---

<a id="item-tech-news-3"></a>
### [Anthropic 称 Claude 协助解决两个黑洞物理开放问题](https://www.anthropic.com/research/claude-black-hole-physics) ⭐️ 8.0/10

Anthropic 在一篇研究公告中称，Claude 帮助解决了黑洞物理中的两个开放问题；公告同时说明，这两项结果并不直接描述我们所在的宇宙，也没有实际应用，只服务于量子力学与广义相对论统一的理论研究。该说法来自厂商公告，现有材料未显示独立验证，其具体贡献和可复现性仍待论文与外部审查确认。

hackernews · cybermango · 11月19日 17:30 · [社区讨论](https://news.ycombinator.com/item?id=50563148)

**「背景」** 这项工作的背景是量子引力研究长期试图调和广义相对论与量子力学，黑洞形成过程中的转变以及时空在极端条件下是否仍有确定形状，都是用于检验理论自洽性的具体问题。Anthropic 的研究页面称，Claude 的一项结果显示，与黑洞形成相关的突变在时空不再具有确定形状的情形下仍然存在。

**「影响」** 对理论物理研究者而言，最具体的后续影响是：Claude 给出的“给定中心电荷下黑洞质量上限”若经同行评审成立，将成为检验量子引力理论的一个约束条件，超出该上限的理论会被排除。但这两项结果目前只是未经评审的预印本，Anthropic 也明确表示它们不直接描述我们所在的宇宙、没有实际应用，因此在评审完成前不宜作为可靠依据使用。

**「社区讨论」** 评论中有人质疑“Claude 解决”是拟人化表述，指出公告和论文未说明提示词，难以判断模型的实际贡献；也有人认为第二项结果——在给定中心电荷下证明黑洞质量上限——更有意义。另有评论引用公告强调，两项结果不直接描述我们的宇宙，也没有实际应用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/research/claude-black-hole-physics">Claude Fable 5.2 solves two open problems in the physics of black ...</a></li>
<li><a href="https://www.anthropic.com/research/claude-black-hole-physics">Claude solves two open problems in the physics of black holes</a></li>
<li><a href="https://dailyai.com/2026/11/anthropic-says-claude-solved-two-black-hole-physics-problems/">Anthropic Says Claude Solved Two Black Hole Physics Problems</a></li>

</ul>
</details>

**标签**: `#AI for science`, `#large language models`, `#black hole physics`, `#research verification`, `#Anthropic`

---

<a id="item-tech-news-4"></a>
### [OpenAI 称模型助芯片设计，AMD 旗舰 GPU PPA 提升最高 14%](https://openai.com/index/advancing-chip-design-with-our-models/) ⭐️ 8.0/10

OpenAI 称其模型参与了自研推理芯片 Jalapeño 的设计，使向量单元标准单元面积减少约 13%、矩阵单元减少约 10%，相关优化已在芯片点亮中验证。OpenAI 还表示，在与 AMD 的合作中，旗舰 GPU IP 的功耗、性能、面积（PPA）指标相对高度优化基线提升最高 14%，部分改动已进入送厂制造的设计。OpenAI 同时宣布与 Synopsys 合作训练 GPT-Synopsys 模型；上述数据均为 OpenAI 公布的厂商说法，而非独立测量结果。

telegram · zaihuapd · 11月19日 09:30

**「背景概念」** PPA 指功耗、性能、面积，是评估 GPU 等芯片设计优劣的核心指标；标准单元面积则反映数字逻辑部分占用的硅片面积。EDA 工具长期用于这类优化，而把大模型接入设计流程，正是此次 OpenAI 与 Synopsys 合作要探索的方向。

**「对芯片设计团队的实际影响」** AMD 部分由模型辅助的改动已进入送厂制造的设计，说明这类优化已触及真实流片流程，而不只是研究演示。对其它芯片设计团队而言，短期影响仍是评估而非采用：与 Synopsys 的 GPT-Synopsys 仅处于合作训练阶段，未公布可用版本、接入方式或兼容性，外部团队无法直接复现 OpenAI 所称的 13%/10% 面积缩减和最高 14% 的 PPA 提升。

**标签**: `#AI-assisted chip design`, `#OpenAI`, `#AMD GPU`, `#Synopsys`, `#semiconductor design`

---

<a id="item-tech-news-5"></a>
### [Gemini 在 Mac 上可代用户操作，支持后台运行与暂停](https://www.bloomberg.com/news/articles/2026-11-19/google-s-gemini-can-now-control-mac-devices-on-users-behalf) ⭐️ 8.0/10

Google Gemini 新增 Mac 电脑操作功能，可代用户点击、输入、浏览菜单和填写表单。该功能已向美国地区使用 Mac 版 Gemini 并订阅 Google AI Plus、Pro 或 Ultra 的用户开放。用户可让 Gemini 在独立后台窗口运行，同时继续使用主屏幕和光标，并可限制其可访问的应用、实时查看操作、随时暂停，以及在关键操作前进行审批。

telegram · zaihuapd · 11月20日 02:51

**「背景」** 桌面代理（computer-use agent）的典型工作方式，是让模型通过模拟点击、输入和菜单导航直接操作图形界面，而不是只输出文本。由于这类能力需要访问应用并执行实际操作，相关产品通常会配套应用限制、实时查看、暂停和关键步骤审批等人工监督机制。

**「影响」** 对符合条件的用户，这允许把点击、填表等重复性桌面操作交给 Gemini，同时通过限制可访问应用、实时监控和关键操作审批保留控制权；但该功能目前仅面向美国地区及上述付费订阅层级，其他地区的可用性尚未公布。

**标签**: `#Google Gemini`, `#AI agents`, `#macOS`, `#human-in-the-loop`, `#product launch`

---

<a id="item-tech-news-6"></a>
### [PHP 混合大小写 HTTPS 静默关闭 TLS，补丁发布](https://x.com/ljachowicz/status/2123477025268924514) ⭐️ 8.0/10

PHP 的 HTTP/FTP 流包装器被披露存在静默 TLS 降级问题：scheme 识别不区分大小写，但只有第五个字符为小写 s 时才启用 TLS，因此 HTTPS://、httpS://、FTPS:// 会按明文 HTTP/FTP 发送，令牌、Basic 认证、Cookie、POST 请求体和 FTP 登录信息可能暴露，被第三方重定向到此类地址也同样受影响。该问题编号为 CVE-2026-128064（GHSA-f6gg-rchx-xw8j），CVSS 4.0 评分 8.2，据披露已存在约 20 年。修复已进入 PHP 8.2.36、8.3.37、8.4.28、8.5.13 和 8.6.0；8.1 及更早版本已 EOL，不会获得修复。

telegram · zaihuapd · 11月20日 03:04

**「背景」** 据 CVE-2026-128064 的描述，PHP 的 \`file\_get\_contents\(\)\`、\`fopen\(\)\` 等函数通过 HTTP/FTP 流包装器访问 URL；这些包装器识别 scheme 时不区分大小写，但启用 TLS 的判定却依赖 scheme 中固定位置的小写 \`s\`。因此，大小写混写的 \`HTTPS://\` 或 \`FTPS://\` 会走未加密的 HTTP/FTP 路径，作为 HTTP 重定向目标传入时也不例外。

**「影响与处置」** 运行受影响 PHP 版本的服务应升级到上述补丁版本；无法升级的 8.1 及更早环境只能在应用侧把 URL 的 scheme 统一规范为小写，以避免混合大小写地址触发明文传输。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://app.opencve.io/cve/CVE-2026-128064">CVE-2026-128064 - Vulnerability Details - OpenCVE</a></li>
<li><a href="https://www.tenable.com/cve/CVE-2026-128064">CVE-2026-128064 | Tenable®</a></li>

</ul>
</details>

**标签**: `#PHP`, `#security vulnerability`, `#TLS`, `#CVE`, `#open source`

---

<a id="item-tech-news-7"></a>
### [欧盟委员会向逾 4 万名员工部署 Matrix](https://element.io/blog/how-the-european-commission-rolled-out-matrix-to-more-than-40-000-staff/) ⭐️ 7.0/10

欧盟委员会已将 Matrix 部署给超过 4 万名员工，Element 的案例文章介绍了这次开源、去中心化通信协议的政府规模落地。该文属于供应商案例研究，而非独立技术评估；现有材料未给出独立测量的性能或安全结果。部署规模是明确事实，但端到端加密的实际强度与运维取舍仍是讨论焦点。

hackernews · liotier · 11月19日 10:58 · [社区讨论](https://news.ycombinator.com/item?id=50558533)

**「背景」** Matrix 是一个开放、去中心化的通信协议，Element 提供基于该协议的客户端及相关部署方案。Element 的案例文章称，欧盟委员会从 2025 年 12 月的 Matrix 概念验证起步，到 2026 年 9 月完成向所有委员会笔记本电脑的部署；这套由欧委会自行运营的系统目前服务超过 4 万名员工。

**「影响」** 对委员会 4 万多名员工而言，通信迁移到 Matrix 后，IT 团队需要长期承担客户端版本、会话验证和密钥管理的支持工作；有评论引述部署细节称，实时在线状态因负载被关闭，说明在这一规模下功能会为性能让路。Matrix 的端到端加密仍在向 MLS 演进，而 MLS 规范设计支持最多 5 万人的群组，因此加密迁移的进度直接关系到该部署能否满足敏感通信的安全要求。

**「社区讨论」** 评论者对 Matrix 的端到端加密提出尖锐质疑，有人称其远未达到国家安全用途所需水平，并批评转向 MLS 的工作似乎停滞；也有日常用户认为客户端碎片化、会话验证、加密错误和可用性问题真实存在，但希望欧盟委员会的采用能带来更多开发资源。另有自建实例的用户分享了脱离 WhatsApp 和 Telegram、自行托管并分享实时位置的正向体验。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://element.io/blog/how-the-european-commission-rolled-out-matrix-to-more-than-40-000-staff/">How the European Commission rolled out Matrix to more than 40 ...</a></li>
<li><a href="https://dzen.ru/b/av7xwZrWnjnx2lAj">Еврокомиссия развернула Matrix на всех служебных... | Дзен</a></li>
<li><a href="https://en.wikipedia.org/wiki/Messaging_Layer_Security">Messaging Layer Security - Wikipedia</a></li>

</ul>
</details>

**标签**: `#Matrix`, `#open-source`, `#government-adoption`, `#E2EE`, `#decentralized-communication`

---

<a id="item-tech-news-8"></a>
### [OpenJDK“java4shell”漏洞报告被 Oracle 接管](https://github.com/openjdk/jdk/pull/32781) ⭐️ 7.0/10

一个被称作“java4shell”的 OpenJDK 漏洞报告以 PR 形式出现在 openjdk/jdk 仓库；据评论引述的 Adoptium 支持 issue，PR 作者 10 月 1 日称 Oracle 要求其未经批准不要继续推进，10 月 28 日又称该工作已被 Oracle 接管、原报告者无需再操作。相关讨论还提到，Oracle 在合并提交中的说明与 PR 中的措辞逐字相同。现有材料没有给出漏洞严重性、受影响版本或利用条件，因此无法确认其实际影响范围。讨论的另一个焦点是 LLM 辅助研究是否独立发现了该问题，还是模型从公开 issue/PR 中获得了线索。

hackernews · notmine1337 · 11月19日 11:47 · [社区讨论](https://news.ycombinator.com/item?id=50558906)

**「背景」** Java4Shell 对应 CVE-2026-114938，是 OpenJDK Base64 解码器中的堆溢出漏洞。CERT-EU 列出的受影响发行版包括 Eclipse Temurin、Amazon Corretto、Azul Zulu、Microsoft Build of OpenJDK、BellSoft Liberica、SAP SapMachine 和 Red Hat 的 OpenJDK 构建。

**「影响」** 对使用 OpenJDK 的开发者而言，当前无法仅凭该 PR 判断自己的版本是否受影响，需等待 Oracle 或所用下游发行版发布修复与适用范围说明。

**「社区讨论」** 评论者围绕“LLM 辅助研究是否独立发现漏洞”存在分歧：wood\_spirit 怀疑模型可能读过此前的公开报告，dlor 则称其离线模糊测试工具独立发现并已向 Oracle 报告，但也承认无法排除训练数据包含该信息。darkamaul 认为，即便模型看过仓库 issue/PR，判断漏洞严重性和构造利用链仍需人工监督。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.dynatrace.com/news/blog/java4shell-cve-2026-114938-which-java-runtimes-are-affected-and-how-to-fix-them/">Java4Shell (CVE-2026-114938): Affected Java Versions &amp; fixes</a></li>
<li><a href="https://pentest-tools.com/blog/java4shell-cve-2026-114938">Java4Shell (CVE-2026-114938): affected versions and fixes</a></li>
<li><a href="https://computingforgeeks.com/java4shell-cve-2026-114938/">Java4Shell CVE-2026-114938: Patch Vulnerable OpenJDK ...</a></li>

</ul>
</details>

**标签**: `#OpenJDK`, `#Java security`, `#vulnerability disclosure`, `#LLM-assisted security research`, `#RCE`

---

<a id="item-tech-news-9"></a>
### [英国政府被迫承认向 Apple 发出秘密加密命令](https://macanorak.com/uk-government-forced-to-admit-it-issued-apple-a-secret-encryption-order/) ⭐️ 7.0/10

据 MacAnorak 报道，英国政府被迫承认曾向 Apple 发出一项秘密加密命令。该命令的具体内容和要求仍未公开，报道将其置于监控、隐私与安全软件设计的争议中。由于命令保密，外界目前无法确认它是否要求 Apple 削弱或绕过加密，也无法评估受影响的产品范围。

hackernews · Terretta · 11月19日 16:21 · [社区讨论](https://news.ycombinator.com/item?id=50562113)

**「法律机制与诉讼背景」** 英国《2016 年调查权力法》第 253 条允许内政大臣向“相关运营商”发出技术能力通知（technical capability notice），要求其采取指定的技术措施。调查权力法庭（Investigatory Powers Tribunal）2026 年 11 月 19 日的判决涉及 Apple 对内政大臣所发此类通知提出的挑战，该法庭同时驳回了内政部要求对相关命令保密的申请。

**「影响」** 由于命令内容保密，Apple 用户目前无法判断哪些加密保证受到影响，开发者也无法据此评估合规边界；这使安全声明与政府要求之间的冲突难以被外部验证。

**「社区讨论」** 评论中，natch 认为 Apple 的安全承诺已从“任何人都无法访问”退到“Apple 无法访问”，并称设备上的密钥只是用于解开实际数据密钥的 KEK；fweimer 则引用调查权力法庭的判决，指出媒体是通过机密安全简报而非泄密得知该命令，命令内容仍未公开。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://investigatorypowerstribunal.org.uk/judgement/1-mr-vincent-kearney-2-british-broadcasting-corporation-v-1-chief-constable-of-the-police-service-of-northern-ireland-2-chief-constable-of-durham-constabulary-3-security-service-4-governme/">Apple Inc and Secretary of State for the Home Department and ...</a></li>
<li><a href="https://www.judiciary.uk/judgments/apple-inc-v-home-secretary-and-others/">Apple Inc -v- Home Secretary and others - Courts and ...</a></li>
<li><a href="https://www.ft.com/content/46a5cf3c-a827-477f-b72f-e7415565e729?syn-25a6b1a6=1">UK loses bid to keep Apple ‘backdoor’ order secret</a></li>

</ul>
</details>

**标签**: `#encryption`, `#privacy`, `#UK government`, `#Apple`, `#surveillance`

---

<a id="item-tech-news-10"></a>
### [PHP 计划 11 月 19 日发布 CRITICAL 级安全更新](https://www.php.net/archive/2026.php) ⭐️ 7.0/10

PHP 安全团队宣布，计划于 2026 年 11 月 19 日 UTC 14:00 至 14:30 发布安全更新，修复影响所有受支持 PHP 版本的安全漏洞，最高严重级别为 CRITICAL。该更新属于 PHP 每四周一次的常规发布周期；官方表示，被评为 CRITICAL 的问题需要在非默认配置或不常见环境下才会触发。具体技术细节和修复版本号将随更新一同公布，当前公告未列出具体受影响版本号。

telegram · zaihuapd · 11月19日 07:10

**「PHP 安全更新周期」** PHP 安全更新按每四周一次的常规周期发布，官方通常先公布发布时间与最高严重级别，具体 CVE 和修复版本号则随版本上线一并公开。此次公告将最高级别标为 CRITICAL，但说明相关问题需在非默认配置或不常见环境下才会触发。

**「运维影响」** 由于官方在发布前不公布 CVE 编号和具体修复版本号，运维团队无法提前判断自身是否受影响，只能在 11 月 19 日 14:00–14:30 UTC 的发布窗口结束后，立即核对各受支持分支的新版本号并安排升级。官方同时说明，被评为 CRITICAL 的问题需要非默认配置或不常见环境才会触发，因此使用默认配置的部署风险相对较低，但仍应把该时间点纳入变更与回滚计划。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.aikido.dev/blog/php-security-release-19-november-2026-cve-2026-115560">PHP schedules a critical security release for 19 November , including...</a></li>
<li><a href="https://thehackernews.com/2026/11/php-warns-of-critical-security-flaws.html">PHP Warns of Critical Security Flaws Affecting All Supported ...</a></li>

</ul>
</details>

**标签**: `#PHP`, `#security`, `#vulnerability`, `#open source`, `#release`

---

<a id="item-tech-news-11"></a>
### [Google Play 2027 年起要求应用适配折叠屏与大屏](https://developer.android.google.cn/blog/posts/google-play-adaptive-quality-standards?hl=zh-cn) ⭐️ 7.0/10

Google 宣布，自 2027 年 4 月起，Google Play 上的应用需达到规定的自适应兼容等级，避免在折叠屏等大屏设备上出现界面拉伸、黑边或比例锁定，并确保设备形态切换时应用状态能够保持。开发者还需提交折叠屏设备截图；未达标准的应用可能面临更新发布限制或商店曝光下降。公告还规定，从 2027 年 8 月起，新应用及更新需以 Android 17（API 37）为目标版本。

telegram · zaihuapd · 11月19日 08:42

**「背景」** Android 应用的窗口尺寸并非固定：分屏、自由窗口以及折叠屏展开或折叠都会改变可用空间，应用需要按窗口大小重新排布界面，并在配置变化时保留用户状态。此次 Google Play 规则把这类大屏自适应能力与 Android 17（API 37）目标版本要求并列，作为应用更新和商店展示的合规要求。

**「影响」** 开发者需在 2027 年 4 月前覆盖折叠屏和大屏的布局、状态切换及商店截图要求，否则更新发布和曝光可能受影响；到 2027 年 8 月，还需将新应用和更新的目标 API 提升至 37。

**标签**: `#Android`, `#Google Play`, `#foldables`, `#app compatibility`, `#platform policy`

---