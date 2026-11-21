---
layout: default
title: "Horizon Summary: 2026-11-21 (ZH)"
date: 2026-11-21
lang: zh
---

> 从 40 条内容中筛选出 13 条重要资讯。

---

**科技新闻**
1. [Thinking Machines 发布 Inkling 2 Mini 开放权重模型](#item-tech-news-1) ⭐️ 8.0/10
2. [陶哲轩讨论无外力纳维-斯托克斯奇点与广义黎曼猜想](#item-tech-news-2) ⭐️ 8.0/10
3. [Levent Alpöge 称与 Claude 证明广义黎曼猜想](#item-tech-news-3) ⭐️ 8.0/10
4. [GitHub 项目声称纳维–斯托克斯方程有限时间爆破，尚未验证](#item-tech-news-4) ⭐️ 8.0/10
5. [KVM 漏洞 CVE-2026-99312：虚拟机可读取 AMD 宿主机内存](#item-tech-news-5) ⭐️ 8.0/10
6. [arXiv 论文称语言模型可改写自身权重，评论质疑泛化性](#item-tech-news-6) ⭐️ 7.0/10
7. [Signal 呼吁移动平台限制 AI 代理抓取数据](#item-tech-news-7) ⭐️ 7.0/10
8. [美国收紧芯片出口，印度拟扩 AI 算力](#item-tech-news-8) ⭐️ 7.0/10
9. [台积电据报停接中国 16nm 及以下订单](#item-tech-news-9) ⭐️ 7.0/10

**科技博客**
1. [为什么缓存 LLM 输出收效甚微](#item-tech-blog-1) ⭐️ 6.0/10

**财经新闻**
1. [Warsh wants Fed officials to talk less. Instead, they’re talking more](#item-finance-news-1) ⭐️ 7.0/10
2. [美国企业从回购转向发行股票，或成牛市逆风](#item-finance-news-2) ⭐️ 7.0/10
3. [北京拟明确租房正常损耗不得扣减押金](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Thinking Machines 发布 Inkling 2 Mini 开放权重模型](https://thinkingmachines.ai/news/inkling-2-mini/) ⭐️ 8.0/10

Thinking Machines 发布开放权重的 Inkling 2 Mini，采用循环 Transformer 架构，主打本地推理。社区用户报告称，在 Ryzen 395 上通过 llama.cpp 的 Vulkan 后端解码约 27 tokens/s，在 32GB M1 Pro 上以 q4 量化运行约 10 tokens/s；这些是个人测试结果，尚未独立验证。讨论还提到该模型训练端到端使用 nvfp4，并且要获得更好性能需应用若干尚未合并的 llama.cpp PR 及一个小补丁。

hackernews · jasondavies · 11月20日 20:12 · [社区讨论](https://news.ycombinator.com/item?id=50581260)

**「背景」** Inkling 2 Mini 是 Thinking Machines 发布的开源权重模型，官方称其小到可在笔记本上运行，并通过循环中间层让模型在每个 token 上做更多推理，从而用更少 token 得到答案。Hugging Face 页面显示该模型为 26B 参数、支持图像-文本到文本；Artificial Analysis 进一步记录其为 26B 总参数、5.4B 激活参数的混合专家模型。

**「本地部署需自行打补丁」** 对想在本地运行该模型的用户来说，目前 llama.cpp 尚未合并相关支持：社区测试者指出需要先合入 32694、32657、32429、32704 等未合并的 PR，再额外应用一个小补丁才能获得约 30% 的解码速度提升。已有人给出可在 Ollama/llama.cpp 上使用的 GGUF 版本，实测在 Ryzen 395 配 Vulkan 后端约 27 tokens/s，M1 Pro 32GB 上以 q4 量化运行约 10 tokens/s，说明可用但需自行编译和调优。

**「社区讨论」** 社区反应总体积极，但证据不一：有用户称快速编码测试表现不错，也有用户在 M1 Pro 上报告简单 CSV 任务成功、硬币识别测试失败。另有评论认为开放权重的循环架构可能促使更多开放模型跟进，并对其安全与可解释性影响提出疑问。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>
<li><a href="https://huggingface.co/thinkingmachines/Inkling-2-Mini">thinkingmachines/Inkling-2-Mini - Hugging Face</a></li>
<li><a href="https://artificialanalysis.ai/articles/inkling-2-mini">Thinking Machines has released Inkling 2 Mini, an open ...</a></li>

</ul>
</details>

**标签**: `#open-weight models`, `#looped transformers`, `#local inference`, `#llama.cpp`, `#model release`

---

<a id="item-tech-news-2"></a>
### [陶哲轩讨论无外力纳维-斯托克斯奇点与广义黎曼猜想](https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/) ⭐️ 8.0/10

陶哲轩（Terry Tao）于 11 月 20 日发布文章《Unforced Navier-Stokes Singularity and the Generalized Riemann Hypothesis》，讨论无外力纳维-斯托克斯奇点与广义黎曼猜想。由于提供的材料只有标题、元数据和 Hacker News 评论，没有文章正文，文章具体证明了什么、结果是否已正式发表或经过同行评审，均无法从现有信息确认。评论中有人称两个独立内核接受了相关 Lean 结果，并据此认为出现内核漏洞利用的可能性较低；这属于社区说法，不是独立验证。

hackernews · archon1410 · 11月20日 17:21 · [社区讨论](https://news.ycombinator.com/item?id=50578358)

**「背景」** 陶哲轩在 2026 年 10 月 4 日的另一篇博客中讨论过不可压缩流体的经典解与奇点形成，把目标描述为：从光滑初值出发，解先在一段正时间内保持正则，随后在某个有限正时刻出现奇点（tool-1-3）。当前这篇 11 月 20 日的文章把同类的“无外力”奇点问题与广义黎曼猜想联系起来；据一篇二手摘要，Levent Alpöge、Tristan Buckmaster 和 Matei Coiculescu 在大量 AI 辅助下得到了相关新结果，但该摘要称原文被截断，具体方法与验证仍待确认（tool-1-2）。

**「社区讨论」** 评论中最具体的讨论集中在形式验证的可信边界：有人指出两个独立内核接受结果，因而内核漏洞被利用的可能性较低；也有人反问，面对约 1500 万行 Lean 代码，如何确认通过构建的命题就是目标定理，而不是一个无关的简单陈述。另有评论表达了对 AI 数学能力快速进展的职业焦虑，但这属于个人感受，并非对结果的验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://todayforai.com/en/items/art-87f06889-96c">Tao Reports AI-Assisted Proofs on Euler and Navier-Stokes ...</a></li>
<li><a href="https://terrytao.wordpress.com/2026/10/04/on-classical-solutions-and-singularity-formation-in-incompressible-fluids/">On classical solutions and singularity formation in ...</a></li>

</ul>
</details>

**标签**: `#mathematics`, `#Lean theorem proving`, `#AI in mathematics`, `#formal verification`, `#research`

---

<a id="item-tech-news-3"></a>
### [Levent Alpöge 称与 Claude 证明广义黎曼猜想](https://alpo.ge/remark.pdf) ⭐️ 8.0/10

Levent Alpöge 于 11 月 20 日发布文章，声称与 Claude 合作找到了黎曼猜想的证明，并称该方法可推广到广义黎曼猜想（GRH），还预期能进一步处理扩展黎曼猜想（ERH）；他表示相关论证已在无额外假设下完成形式化。Hacker News 评论称该 Lean 形式化约 1.3GB、1500 万行，另有人链接到一份据称完全由人类完成的证明。上述材料尚未给出可独立核验的 Lean 内核检查或同行评审结果，因此目前只能视为一项待验证的声称。

hackernews · iamronaldo · 11月20日 14:16 · [社区讨论](https://news.ycombinator.com/item?id=50574968)

**「背景」** 广义黎曼猜想（GRH）是黎曼猜想的推广，断言包括狄利克雷 L 函数在内的一类更广泛 L 函数的非平凡零点位于临界线上；若成立，黎曼猜想是其特例。Lean 是交互式定理证明器，形式化证明原则上可由机器检查，但前提是证明脚本正确且可复现；当前材料只呈现了作者与社区的说法，尚未给出独立验证结论。

**「核验成本与验证状态」** 对想自行核验该声明的人来说，实际门槛是工程规模：按评论给出的步骤，需要分 14 段下载并拼接约 1.3GB 的 Lean 归档，再解压构建约 1500 万行的形式化代码。评论中引用的独立检查页面显示结果截至 2026-11-20 22:05 UTC、其余检查仍在进行，因此在该形式化被独立复现之前，这项 GRH 声明仍属未确认的宣称，而非已确立的定理。

**「社区讨论」** 评论区的核心分歧是验证状态：有评论称已有多重形式化验证，并提到 Andrew Sutherland（MIT）用 Claude Code 进行的检查，但也有人指出还存在一份据称完全由人类完成的证明；这些说法都来自评论，不能当作独立确认。另有评论引用 Terence Tao 此前对 AI 攻克黎曼猜想的怀疑，与此次声称形成对照。

**标签**: `#formal verification`, `#Lean theorem prover`, `#Riemann Hypothesis`, `#AI-assisted mathematics`, `#mathematical proof`

---

<a id="item-tech-news-4"></a>
### [GitHub 项目声称纳维–斯托克斯方程有限时间爆破，尚未验证](https://github.com/tristanbuckmaster/navier-stokes/) ⭐️ 8.0/10

一个托管在 GitHub 上、署名 tristanbuckmaster 的项目声称给出了纳维–斯托克斯方程的有限时间爆破结果，该页面于 11 月 20 日在 Hacker News 上被提交并引发大量关注。目前没有可获取的论文正文、证明细节或同行评议信息，因此这仍是一项未经独立核验的声明，而非已确立的数学结论。对数学与流体力学研究者而言，若该证明成立，将直接触及三维纳维–斯托克斯方程解的正则性问题；在核验完成前，其适用范围与正确性都属未知。

hackernews · trotro · 11月20日 15:34 · [社区讨论](https://news.ycombinator.com/item?id=50576232)

**「背景」** 三维不可压纳维–斯托克斯方程的光滑解是否对任意光滑初值长期存在，是千禧年大奖难题之一；有限时间爆破就是给出否定答案。此前有报道称，Buckmaster 指称 OpenAI 在得知他与 Anthropic 研究员 Levent Alpöge 的相关工作后，开始追攻“受迫”纳维–斯托克斯方程的有限时间爆破证明。当前 GitHub 条目在讨论中被称作“无外力”版本，问题设定与受迫情形不同。

**「对研究者的实际影响」** 对数学与流体力学研究者而言，直接后果是：这项结果目前只是托管在 GitHub 上的未验证声明，既无同行评审，也无独立复现，因此任何引用或在此基础上继续推进的工作都必须自行核验其论证。讨论中有人希望看到能实时展示爆破的数值模拟或物理演示，但这类演示目前并不存在，所以也无法借助可视化直观判断方程在何处偏离现实。

**「社区讨论」** 评论者 \[tancop\] 称这一结果是“无外力”（unforced）版本，与 OpenAI 此前通过精心设计的外部力构造的反例不同，因而在某种意义上更“真实”；这一区分来自评论者的说法，尚未得到源材料确认。另有评论者 \[xianshou\] 与 \[jrflo\] 将当天同时出现的广义黎曼猜想结果、该爆破结果以及围绕 Anthropic 的传闻并列，感叹当天数学进展的密度，并猜测作者可能被抢先；\[ninkendo\] 则询问能否用实时数值模拟把爆破过程可视化，以便直观理解方程在何处偏离现实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://analyticsindiamag.com/ai-news/mathematician-alleges-openai-pursued-navierstokes-breakthrough-after-learning-of-his-work">Mathematician Alleges OpenAI Pursued Navier – Stokes Breakthrough...</a></li>
<li><a href="https://news.ssbcrack.com/openai-claims-an-artificial-intelligence-solution-to-the-navier-stokes-millennium-prize-problem/">OpenAI Claims an Artificial-Intelligence Solution to the Navier – Stokes ...</a></li>

</ul>
</details>

**标签**: `#Navier-Stokes equations`, `#mathematics`, `#fluid dynamics`, `#research`, `#open source`

---

<a id="item-tech-news-5"></a>
### [KVM 漏洞 CVE-2026-99312：虚拟机可读取 AMD 宿主机内存](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 8.0/10

Linux KVM 的 CVE-2026-99312 漏洞允许虚拟机在启用嵌套虚拟化的 AMD 主机上读取宿主机内存；研究人员在 DigitalOcean 环境中从虚拟机内读取到约 127 GB 宿主内存。上游修复已于 11 月 18 日随稳定内核 7.3.5 等版本发布，但 Debian、Ubuntu 等发行版内核尚未修复。受影响的 AMD 虚拟化主机在补丁到位前可关闭嵌套虚拟化作为缓解措施。

telegram · zaihuapd · 11月20日 14:23

**「背景：KVM 嵌套虚拟化缺陷来源」** KVM 是内置于 Linux 内核的虚拟化层；此次问题出在 AMD 嵌套虚拟化路径中的一个陈旧指针（stale pointer）。据 DigitalOcean 与 Terra Security 的分析，该缺陷在内核中已存在近四年，并且是由早先的一次安全修复引入的。

**「影响」** 运行启用嵌套虚拟化的 AMD KVM 主机的运维者应确认所用内核是否已包含上游修复；若使用 Debian、Ubuntu 等尚未修复的内核，关闭嵌套虚拟化是来源给出的补丁前缓解措施，但会影响依赖该功能的负载。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.digitalocean.com/blog/cve-2026-99312-kvm-patch">Virtualization , Responsible Disclosure, and CVE - 2026 - 99312</a></li>
<li><a href="https://www.terra.security/blog/kvm-guest-to-host-escape">KVM Guest-to- Host Escape | Terra Security Research</a></li>

</ul>
</details>

**标签**: `#KVM`, `#Linux kernel`, `#virtualization security`, `#CVE-2026-99312`, `#AMD`

---

<a id="item-tech-news-6"></a>
### [arXiv 论文称语言模型可改写自身权重，评论质疑泛化性](https://arxiv.org/abs/2611.21885) ⭐️ 7.0/10

一篇 arXiv 论文（2611.21885）声称，语言模型可以仅凭自身推理改写权重，无需梯度或训练，并在连续八次会话中只保留在练习题上有效的修改，使准确率持续上升。Hacker News 评论者则指出，目前观察到的自我改进只是缩短推理轨迹以避开 token 上限，并认为这与近期“权重空间编程”和 Google“sleep”框架等工作相似，尚不足以证明通用自我改进。另有评论者警告，若模型能自主定位并抑制安全相关激活，这类能力会带来对齐风险。

hackernews · lwhsiao · 11月20日 16:29 · [社区讨论](https://news.ycombinator.com/item?id=50577265)

**「背景」** “模型直接读写权重”在此前已有先例：据 2026 年 11 月 2 日 MIT CSAIL 四位研究者的博客介绍，GPT-6 Astra 通过直接编辑 Qwen3.5-0.8B 的权重，把该小模型在 MATH-500 上的成绩从 7.9% 提升到 48.1%，而改动的权重仅约 0.016%。这类被称为“权重空间编程”的工作把权重当作可读写的文本，不依赖梯度或训练循环，并被视为通向递归自我改进的一条路径。谷歌的“sleep”框架则让模型在离线阶段解锁预分配的 MoE 记忆块，用自生成的练习题更新自身数值权重。与这些让模型编辑另一个模型或按预设流程更新的做法相比，本次 arXiv 论文的主张是模型依据自身推理改写自己的权重。

**「影响」** 对部署方而言，需要把模型对自身权重的修改纳入安全评估，因为评论者指出模型可自动搜索并抑制安全相关激活；但现有证据只显示缩短推理轨迹这一项改动，尚不能证明模型能普遍自我改进。

**「社区讨论」** 评论区的核心分歧在于这是否算真正的“无训练”自我改进：Toutouxc 认为“只提交有效修改”听起来仍像训练，aesthesia 则指出唯一改进只是缩短推理轨迹以避开 token 上限，并称与既有权重空间编程结果类似。LarsDu88 进一步从安全角度警告，自主模型可能定位并抑制安全相关激活。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://rikiyat.github.io/blog/weight-space-programming/">Sparks of Weight - Space Programming : LLMs can natively read...</a></li>
<li><a href="https://explainx.ai/blog/weight-space-programming-gpt-6-astra-edits-qwen3-5-0-8b-weights-math-7-9-to-48-1-mit-csail-2026">GPT-6 Astra Edits Qwen Weights : MATH-500 7.9% to... | explainx.ai</a></li>
<li><a href="https://research.google/blog/the-sleep-framework-a-new-way-for-llms-to-retain-knowledge-in-continual-learning/">The sleep framework : A new way for LLMs to retain knowledge in...</a></li>

</ul>
</details>

**标签**: `#LLM self-modification`, `#weight editing`, `#AI safety`, `#research paper`, `#Hacker News discussion`

---

<a id="item-tech-news-7"></a>
### [Signal 呼吁移动平台限制 AI 代理抓取数据](https://signal.org/blog/protecting-your-privacy/) ⭐️ 7.0/10

Signal 发布博文，主张移动操作系统平台应限制 AI 代理抓取用户数据，并把这一问题与聊天应用的隐私风险联系起来。现有材料未提供具体平台名称、版本、实施时间表或已上线的限制措施，因此尚不能确认这是已落地的系统能力还是政策主张。

hackernews · dotcoma · 11月20日 09:42 · [社区讨论](https://news.ycombinator.com/item?id=50572348)

**「背景」** Signal 的博文将这一调整描述为针对移动操作系统内置 AI 代理的应对措施，因为这些代理可能捕获并存储 Signal 数据。The Verge 报道称，Signal 正在限制 Android 和 iOS 上的截图功能，以阻止 Gemini 和 Siri 等 AI 代理读取用户消息及其他数据。

**「影响」** 对移动应用开发者而言，若平台按这一方向收紧权限，AI 代理读取其他应用数据的能力将需要重新评估；但现有材料没有说明 Signal 已推动哪家平台修改规则或何时生效。

**「社区讨论」** 评论中，有人援引 Meredith Whittaker 的访谈称，风险不只来自用户自己安装的 AI 应用，联系人的应用也可能读取聊天内容；也有人主张 Signal 应直接提示系统含间谍软件并推荐 GrapheneOS 等替代方案，而不是只依赖防截屏。另有评论要求 Signal 公开其取证调查结果，以便资源较少的开发者复用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://signal.org/blog/protecting-your-privacy/">Signal &gt;&gt; Blog &gt;&gt; Signal is Serious About Protecting Your Privacy</a></li>
<li><a href="https://www.theverge.com/ai-artificial-intelligence/1038390/signal-blocking-ai-agent-screenshots-mobile-app">Signal is blocking Gemini and Siri AI from reading your... | The Verge</a></li>

</ul>
</details>

**标签**: `#privacy`, `#mobile-security`, `#AI-agents`, `#Signal`, `#operating-systems`

---

<a id="item-tech-news-8"></a>
### [美国收紧芯片出口，印度拟扩 AI 算力](https://www.bloomberg.com/news/articles/2026-11-20/nvidia-scandal-fallout-india-ai-yotta-ambani-adani-am-intelligence-e2e-networks) ⭐️ 7.0/10

美国收紧对马来西亚、泰国和新加坡的先进芯片出口，印度 AI 业界希望承接外溢的算力需求。Yotta 称未来一年将新增约 10 万块 GPU，相当于印度现有算力再增约 10%；这是公司的扩容计划，并非已交付的算力。印度目前有 153 个数据中心，数量居全球第 14；信实承诺投入至多 1100 亿美元、阿达尼承诺投入 1000 亿美元建设 AI 基础设施，但印度长期受算力基础设施短缺和资本受限拖累。

telegram · zaihuapd · 11月20日 07:31

**「背景」** 印度目前有 153 个数据中心，居全球第 14，但 AI 基础设施长期受算力短缺和资本受限拖累。信实承诺投入至多 1100 亿美元、阿达尼 1000 亿美元建设 AI 基础设施，说明本地资本已在为扩大算力供给布局。

**「对印度本地算力用户的实际影响」** 对印度本地开发者和需要 GPU 的企业来说，Yotta 计划一年内新增的约 10 万块 GPU 仅相当于全国现有算力的约 10%，短期内难以改变供给偏紧的局面；Yotta 此前曾表示印度市场的 GPU 需求已超过供给。信实至多 1100 亿美元、阿达尼 1000 亿美元的投入属于多年期承诺，在电力、数据中心和资本实际到位前并不构成可用容量，因此印度能否承接外溢需求，取决于这些项目能否按期落地。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/02/27/india-yotta-nvidia-ai-gpu-demand-data-centers-investment.html">India’s Yotta to build $2 billion AI hub with Nvidia GPUs ...</a></li>

</ul>
</details>

**标签**: `#AI infrastructure`, `#semiconductor export controls`, `#India`, `#data centers`, `#GPU compute`

---

<a id="item-tech-news-9"></a>
### [台积电据报停接中国 16nm 及以下订单](https://appleinsider.com/articles/26/11/20/apple-supplier-tsmc-cuts-off-china-chip-orders-amid-tighter-export-controls) ⭐️ 7.0/10

据一则 Telegram 聚合消息，台积电已通知客户暂停接受中国公司 16nm 及以下先进制程订单；按收紧后的美国半导体出口新规，除非事先取得美国出口许可或豁免，否则台积电不得供货。受限中国企业因此只能使用 28nm、40nm 等较旧制程，也无法使用 AI 数据中心所需的高带宽内存。此前台积电可自行评估客户设计是否符合豁免条件，现在客户须提前申请；美国获批名单中有苹果、AMD 和英伟达，尚无中国公司。台积电表示将遵守新规，但该消息尚未获得独立核实。

telegram · zaihuapd · 11月21日 02:01

**「背景」** 美国半导体出口管制按制程节点、最终用途和客户资格设置许可门槛；16nm 及以下属于受重点限制的先进制程，而 28nm、40nm 等成熟制程仍可供货。此前的安排允许台积电自行评估客户设计是否符合豁免条件，新规改为由客户预先申请美国许可或豁免；美国获批名单中包括苹果、AMD、英伟达，尚无中国公司。

**「影响」** 中国芯片设计企业若继续使用台积电 16nm 及以下制程，必须提前申请美国出口许可或豁免；否则只能转向 28nm、40nm 等成熟制程。由于美国获批名单中尚无中国公司，相关企业的先进芯片流片和量产节奏将直接受影响，面向 AI 数据中心的产品还会因高带宽内存获取受限而面临设计调整或延迟。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.trendforce.com/news/2026/11/20/news-tsmc-samsung-reportedly-pause-china-consumer-chip-shipments-under-new-u-s-rules-16nm-orders-affected/">[News] TSMC , Samsung Reportedly Pause China Consumer Chip...</a></li>

</ul>
</details>

**标签**: `#TSMC`, `#semiconductor export controls`, `#advanced process nodes`, `#China chip industry`, `#AI hardware`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [为什么缓存 LLM 输出收效甚微](https://seangoedecke.com/why-output-caching-doesnt-work/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月21日 00:00

**「背景」** LLM 推理成本优化通常依赖缓存输入（如 KV cache），避免每轮重新计算整段对话历史。作者由此追问：既然模型输出也会重复，是否也应缓存或避免重复输出？毕竟输出 token 的生成成本明显高于输入 token。

**「方案」** 作者认为不值得，因为可优化的是用户可见的输出，而它只占输出 token 的一小部分。根据其个人 agent 历史，约 6%的输出 token 可见，50%是推理 token，44%是工具调用。即使乐观地省掉可见输出三分之二的 token，按 Amdahl 定律，总输出也只节省约 4%。实现上可以微调或提示模型用“src/script.py:12-15”这类引用代替复述，并由 harness 展开，但这仍只触及可见部分。要真正节省输出 token，必须减少不可见的推理和工具调用，这主要取决于模型智能：更贵的模型可能单 token 价格高 5 倍，但用少 6 倍的 token 得到正确答案，总成本反而更低。作者也承认，6%来自个人经验，且对前沿模型是否在思维链中重复内容只有中等确信。

**「启示」** 输出缓存不是降低 LLM 成本的有效杠杆，因为大部分输出 token 不可见；优化应聚焦推理与工具调用，而更强的模型智能可能同时减少 token 用量和总成本。

**标签**: `#LLM inference`, `#output caching`, `#token economics`, `#AI agents`, `#Amdahl&\#x27;s law`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [Warsh wants Fed officials to talk less. Instead, they’re talking more](https://www.cnbc.com/2026/11/20/warsh-fed-forward-guidance-rate-hikes.html) ⭐️ 7.0/10

Fed officials are speaking more frequently and sometimes conflictingly about rate hikes as Chair Kevin Warsh avoids forward guidance, deepening an FOMC divide ahead of the December meeting.

rss · CNBC Finance · 11月20日 21:10

**标签**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#FOMC communication`, `#Kevin Warsh`

---

<a id="item-finance-news-2"></a>
### [美国企业从回购转向发行股票，或成牛市逆风](https://www.cnbc.com/2026/11/20/equity-issuance-bull-market-problem.html) ⭐️ 7.0/10

据 Acadian Asset Management 分析，美国公司已从 2024 年的净回购转为净发行股票，截至上周晚些时候，净新股发行相当于总市值的 3.1%。该机构投资组合经理 Owen Lamont 称，这结束了回购时代，可能给已持续四年的牛市带来供给压力。

rss · CNBC Finance · 11月20日 14:15

**「背景」** 此前多年，公司回购股票会减少流通股数量并抬高每股收益，而当前转为发行股票意味着市场需要吸收更多供给。

**标签**: `#equity issuance`, `#share buybacks`, `#bull market`, `#AI infrastructure`, `#IPO market`

---

<a id="item-finance-news-3"></a>
### [北京拟明确租房正常损耗不得扣减押金](https://mp.weixin.qq.com/s/PmGxh5knIyxiBRhpRoJnoQ) ⭐️ 7.0/10

北京市住建委与市场监管局自 11 月 20 日起就《北京市住房租赁合同（示范文本）（修订征求意见稿）》公开征求意见，拟明确承租人正常使用造成的房屋正常损耗不承担赔偿责任，出租人不得以此为由扣减押金。征求意见稿还要求转租经营的租赁企业将租押金付至监管账户，并新增保密和个人信息保护条款。

telegram · zaihuapd · 11月20日 13:46

**「背景」** 此次发布的是对现有《北京市住房租赁合同（示范文本）》的修订稿，11 月 20 日起公开征求意见；示范文本是主管部门提供的合同范本，供房东与租客签约时参照使用，需经征求意见并定稿后才正式发布。

**「影响」** 若该征求意见稿最终落地，北京租户因房屋正常使用损耗被扣减押金的风险将降低；从事转租经营的租赁企业则需将租押金存入监管账户，资金使用会受到更大约束。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://t.me/zaihuapd/45263">在花 科技圈 – Telegram</a></li>

</ul>
</details>

**标签**: `#北京住房租赁`, `#押金监管`, `#租户权益`, `#政策征求意见`, `#住房租赁合同`

---