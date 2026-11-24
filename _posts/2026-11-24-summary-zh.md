---
layout: default
title: "Horizon Summary: 2026-11-24 (ZH)"
date: 2026-11-24
lang: zh
---

> 从 38 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [Ladybird 发布首个 alpha 版](#item-tech-news-1) ⭐️ 8.0/10
2. [Z.ai 发布 GLM-5.4：采用循环 Transformer 架构](#item-tech-news-2) ⭐️ 8.0/10
3. [Anthropic 称内部 Claude 发现 VP≠VNP 并公开 Lean 4 证明](#item-tech-news-3) ⭐️ 8.0/10
4. [Nvidia 董事会重新任命黄仁勋为 CEO](#item-tech-news-4) ⭐️ 7.0/10
5. [NariQ 发布 Qwen3.8-27B 的 3 位及以下 GGUF 量化](#item-tech-news-5) ⭐️ 7.0/10
6. [Stalwart 宣称成为 Microsoft Exchange 的直接替代品](#item-tech-news-6) ⭐️ 7.0/10
7. [Codex2api 疑遭供应链投毒，受影响版本应回退至 3.1.9](#item-tech-news-7) ⭐️ 7.0/10

**科技博客**
1. [vLLM 插件实现 ERNIE 5.5 Flash Preview 首日支持](#item-tech-blog-1) ⭐️ 7.0/10

**财经新闻**
1. [Anthropic 上市后 AI 股遭抛售，DeepSeek 与月之暗面上市计划承压](#item-finance-news-1) ⭐️ 8.0/10
2. [威廉姆斯：美联储仍需行动让通胀回到 2%](#item-finance-news-2) ⭐️ 7.0/10
3. [上海地铁 12 月 1 日起调整票价，为 21 年来首次](#item-finance-news-3) ⭐️ 7.0/10
4. [黄循财：新加坡不会成为规避美国芯片管制的通道](#item-finance-news-4) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Ladybird 发布首个 alpha 版](https://ladybird.org/posts/alpha/) ⭐️ 8.0/10

Ladybird 项目发布了首个 alpha 版，macOS 和 Linux 用户现在可以直接下载安装，不必自行编译。该浏览器使用自研的 HTML 解析、CSS、布局、JavaScript 和 WebAssembly 组件，同时仍依赖 HarfBuzz、Skia、ffmpeg 和 SQLite 等外部库。官方说明这仍是早期版本：部分网站会无法使用，浏览器有时会崩溃，用户可从浏览器内报告损坏网站，并在崩溃后选择是否发送报告。项目 10 月通讯称，Ladybird 在约 225 万项 web-platform-tests 子测试中通过 2,184,722 项，高于 Safari 的 2,172,990 项，但低于 Firefox 的 2,189,315 项和 Chrome 的 2,244,397 项。

hackernews · janvdberg · 11月23日 16:13 · [社区讨论](https://news.ycombinator.com/item?id=50614249)

**「背景」** Ladybird 源自 SerenityOS 项目，目标是自行实现 HTML 解析、CSS 引擎、布局和 JavaScript 等核心组件，仅复用 HarfBuzz、Skia、FFmpeg 和 SQLite 等少数外部库。2026 年 2 月，项目宣布引入 Rust，并借助 AI 编程代理将 LibJS 的部分代码从 C++ 移植为约 2.5 万行 Rust；到 10 月，团队又报告在约 225 万项 web-platform-tests 子测试上大幅提升了通过数。

**「实际影响」** 对准备试用的用户，当前 alpha 虽可安装，但仍是会崩溃、存在站点兼容缺口的早期版本；已有依赖 Service Worker 的站点因此失败，试用 Datasette Lite 时触发了 \`undefined is not a function \(evaluated from &\#x27;navigator.serviceWorker.startMessages&\#x27;\)\`，对应接口在源码中仍标有 FIXME。

**「社区讨论」** 试用者报告了较广的兼容性和不错的性能：有人称自己测试的网站全部正确渲染，只是滚动略显卡顿；也有人称 NoVNC 在 Ladybird 中比 Firefox 更流畅。讨论中还有人对项目改用 SQLite、Skia 等成熟外部库、取代部分自研组件表示怀念，并有人呼吁未来认真处理浏览器指纹识别和权限粒度问题。

**标签**: `#browsers`, `#open-source`, `#web-engines`, `#ladybird`, `#software-releases`

---

<a id="item-tech-news-2"></a>
### [Z.ai 发布 GLM-5.4：采用循环 Transformer 架构](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

Z.ai 发布 GLM-5.4，称这是其首个采用循环 Transformer 架构的模型，面向通用编码场景；该架构让一组共享权重的层在一次前向传播中多次迭代，从而在不增加参数量的情况下加深网络。该模型目前未开放权重，也不能通过常规 API 套餐访问；用户需订阅 Coding Plan，其 API key 可在 https://api.z.ai/api/v1 的 OpenAI 兼容 Responses API 上调用。Simon Willison 为此发布了 llm-glm 插件，并指出现有 llm-zai 插件尚未支持新模型。他的初步试用显示，GLM-5.4 在低、高、最高三档 effort 下生成的鹈鹕图与 GLM-5.3 质量相近，最高档结果仍不算好；这属于个人测试，并非独立基准。

hackernews · foohis · 11月23日 10:06 · [社区讨论](https://news.ycombinator.com/item?id=50609685)

**「背景」** 标准 Transformer 的每一层在一次前向传播中只计算一次；Loop Transformer（循环 Transformer）则让一组共享权重的层重复运行多轮，在每轮中细化上一轮的隐藏状态，从而在不增加参数量的情况下提高有效深度。同一周内，Thinking Machines Lab 的 Inkling 2 Mini 也采用了让中间层对每个 token 运行三次的循环设计，并称这有助于在智能体编程等依赖推理质量的任务上减少 token 消耗。

**「接入方式受限」** 对开发者而言，最直接的影响是接入路径变窄：GLM-5.4 目前无法通过常规 API 套餐或 OpenRouter 调用，需要订阅 Z.ai 的 Coding Plan，其 API key 可在 https://api.z.ai/api/v1 的 OpenAI 兼容 Responses 接口上使用；同时官方未提供开放权重，因此无法本地部署。现有工具链也需跟进——原文作者提到 llm-zai 插件尚不支持新模型，才临时另写了 llm-glm 插件，并计划在对方支持后停用自己的版本。

**「社区讨论」** 有评论者赞赏 Zhipu 公开架构细节，认为循环 Transformer 是 SOTA 模型的明显演进方向；也有人抱怨部分中国模型的“马拉松式思考”会让简单任务耗时显著增加。另有评论者解释，循环结构可减少推理时在 HBM 与芯片间搬运整层权重的开销，从而针对内存带宽瓶颈。

**标签**: `#large language models`, `#transformer architecture`, `#coding models`, `#model release`, `#AI research`

---

<a id="item-tech-news-3"></a>
### [Anthropic 称内部 Claude 发现 VP≠VNP 并公开 Lean 4 证明](https://github.com/anthropics/formal-math/blob/main/vp-vnp/README.md) ⭐️ 8.0/10

Anthropic 于 11 月 24 日公开论文《VP ≠ VNP over every field》及配套 Lean 4 形式化证明，仓库称结果由其内部研究用 Claude 模型发现，论文和代码均由 AI 撰写。论文给出哈密顿圈多项式的超多项式算术电路下界，并据此推出 VP 是 VNP 的真子类；若成立，这将解决 Valiant 1979 年提出的代数复杂度猜想，但结论只涉及算术电路，不涉及 P 与 NP。仓库称证明通过三条标准公理审计和独立内核 nanoda 复核，除预留文件外没有 sorry；不过尚无人类数学家通读，Lean 也无法确认形式化陈述与所声称的命题一致，附录 Q 列出了出入，结果仍待独立审阅。

telegram · zaihuapd · 11月24日 06:02

**「背景：Valiant 猜想与 Lean 4 校验的边界」** VP 与 VNP 是 Lesley Valiant 在 1979 年提出的代数复杂度类，VP≠VNP 被视为算术电路模型下 P≠NP 的类比命题：它只涉及多项式算术电路规模的下界，即使成立也不能直接推出 P≠NP（tool-2-2）。Lean 4 这类证明助手的检查对象只是仓库中写下的形式化陈述，内核通过仅表示该陈述被证，若要确认形式化陈述与论文声称的定理一致，仍需人类数学家逐条比对。

**「影响」** 对代数复杂度和形式化验证研究者而言，当前可操作的影响是：在独立审阅确认 Lean 陈述与论文命题一致之前，不应把该仓库当作 VP≠VNP 已获证的结论引用；复核重点包括附录 Q 列出的出入，以及预留文件在形式化中的角色。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=UuOiRi9T-9c">Claude&#x27;s VP VNP Proof: 47 Years Open, Still Unchecked... - YouTube</a></li>

</ul>
</details>

**标签**: `#complexity theory`, `#Lean 4`, `#formal verification`, `#AI for mathematics`, `#Anthropic`

---

<a id="item-tech-news-4"></a>
### [Nvidia 董事会重新任命黄仁勋为 CEO](https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo.html) ⭐️ 7.0/10

据 CNBC 报道，Nvidia 董事会重新任命黄仁勋为总裁、首席执行官兼董事会成员，恢复其在这家 AI 芯片公司的最高管理职务。董事会声明称，在作出决定过程中听取了美国政府高层意见，并据此认为黄的回归不构成国家安全风险。现有材料未披露黄此前离任的原因、任命生效时间或董事会投票细节，相关说法主要来自公司公告链接和社区转述。

hackernews · jaz · 11月23日 14:00 · [社区讨论](https://news.ycombinator.com/item?id=50611576)

**「背景」** 标题中的“Reinstates”暗示黄仁勋此前曾被解除职务，但这条链接帖没有给出董事会声明全文、解除与复职的具体日期或理由。评论者提到董事会不到两周便反转、司法部不提起诉讼以及美国政府高层意见，但这些都属于社区说法，未在源内容中得到确认。

**「影响」** 复职“立即生效”，使 Nvidia 在黄仁勋辞职不到两周后恢复原有 CEO 领导层。更具体的治理影响是，董事会公开以美国政府高层意见为依据认定复职不构成国家安全风险，这意味着投资者和业务伙伴在评估 Nvidia 的人事与合规风险时，政府态度已成为一个公开变量，而不再只是公司内部治理问题。

**「社区讨论」** 评论者最关注董事会声明中“收到美国政府高层意见”的表述，有人认为这是整份声明的关键，质疑国家安全考量是否影响了公司治理；也有评论者称目前没有公开证据表明 Nvidia 或黄仁勋存在违法行为，并讨论董事会责任的法律门槛。还有评论者对董事会在不到两周内从罢免转为重新任命感到意外，认为名义治理结构未必等于实际治理结构。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Board-Reinstates-Jensen-Huang-as-President-CEO-and-Board-Director/default.aspx">NVIDIA Corporation - NVIDIA Board Reinstates Jensen Huang as...</a></li>
<li><a href="https://www.latimes.com/business/story/2026-11-23/nvidia-board-jensen-huang-ceo">Nvidia board reinstates Jensen Huang . &#x27;It&#x27;s wrong, and it&#x27;s shock...</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#semiconductor industry`, `#corporate governance`, `#US tech policy`, `#AI hardware`

---

<a id="item-tech-news-5"></a>
### [NariQ 发布 Qwen3.8-27B 的 3 位及以下 GGUF 量化](https://huggingface.co/nari-labs/Qwen3.8-27B-NariQ-GGUF) ⭐️ 7.0/10

NariQ 发布了 Qwen3.8-27B 的 3 位、2.5 位和 2 位 GGUF 量化，声称在智能体、数学、多语言和图像任务上接近 BF16 质量；这些结果由团队自行报告，且目前必须使用其 llama.cpp 分支运行。其公布的对比中，3 位和 2.5 位在 DeepSWE、Terminal-Bench 2.1、AIME 25+26 等基准上与 BF16 接近甚至略高，而 2 位在 DeepSWE 降至 28.6（BF16 为 39.8）、AIME 降至 86.0（BF16 为 97.7）。在 RTX PRO 6000 上解码速度与其他量化相当，但社区报告 M3 Pro 上 3.0bpw 仅约 3.8 tok/s。

hackernews · toebee · 11月23日 13:42 · [社区讨论](https://news.ycombinator.com/item?id=50611402)

**「背景」** Qwen3.8-27B 是采用 Apache 2.0 许可的 27B 开放权重模型，带有视觉编码器和 262k 上下文，Hugging Face 上已出现多个基于它的量化版本。GGUF 量化通过降低权重位宽来压缩模型文件，使本地硬件能够加载；低比特版本能否保持原模型能力，通常要看长程任务和不同上下文长度下的实测结果。

**「影响」** 想使用这些量化文件的用户需要切换到 NariQ 的 llama.cpp 分支，标准 llama.cpp 工作流不能直接加载；在 Apple Silicon 上性能也明显低于 CUDA，M3 Pro 上 3.0bpw 约 3.8 tok/s，因此 16 GB Mac 能否实用仍待验证。

**「社区讨论」** rao-v 肯定该项目在多种长程任务和“held out”设置上做了基本验证，但 Retro\_Dev 追问压缩究竟丢失了哪些信息，WithinReason 则认为从图表看大部分提升来自评测框架差异而非模型本身。jedbrooke 报告 M3 Pro 上 3.0bpw 约 3.8 tok/s、2.0bpw 约 4.9 tok/s，远慢于 CUDA，并询问能否压进 16 GB Mac。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.yottalabs.ai/post/how-to-run-qwen-3-8-27b-locally-ollama-gguf-single-gpu-2026">How to Run Qwen 3 . 8 27 B Locally: Ollama, GGUF , and... | Yotta Labs</a></li>
<li><a href="https://huggingface.co/models?other=base_model:quantized:Qwen/Qwen3.8-27B">Quantized Models for Qwen/ Qwen 3 . 8 - 27 B – Hugging Face</a></li>

</ul>
</details>

**标签**: `#quantization`, `#LLM inference`, `#Qwen`, `#GGUF`, `#local LLMs`

---

<a id="item-tech-news-6"></a>
### [Stalwart 宣称成为 Microsoft Exchange 的直接替代品](https://stalw.art/blog/microsoft-exchange-replacement/) ⭐️ 7.0/10

开源邮件服务器 Stalwart 宣布具备 Microsoft Exchange/MAPI 兼容能力，并自我定位为 Exchange 的“直接替代品”，主要面向需要保留 Outlook 和现有邮件流程的系统管理员。现有材料没有给出具体版本、功能覆盖范围或独立测试结果，因此“直接替代”仍是项目方的说法，尚未经过验证、不能视为完整兼容。

hackernews · shaunpud · 11月23日 22:32 · [社区讨论](https://news.ycombinator.com/item?id=50620349)

**「背景」** Stalwart 是一个开源邮件与协作服务器，支持 JMAP、IMAP4、POP3、SMTP、CalDAV、CardDAV 和 WebDAV 等标准协议。其 1.2.0 版本加入了 MAPI over HTTP、Exchange Web Services、ActiveSync 和 Autodiscover，使 Outlook、Apple Mail 和移动设备可以像连接 Exchange 一样连接它。

**「合规与客户端兼容性」** 对于受德国 GoBD 等法规约束、需要以不可篡改方式归档邮件并保存至多十年的企业和自由职业者，评论者指出 Stalwart 的常规套餐与开源版本并不包含该归档能力，因此这类用户若采用它，仍需额外部署独立的归档系统（例如提供防篡改归档与保留策略的 Piler）才能满足审计要求。在客户端方面，微软新版 Outlook 对 IMAP 的处理方式正在变化，所以“drop-in replacement”能否成立要按具体 Outlook 版本和部署方式逐项验证，不能只凭协议兼容声明推断。

**「社区讨论」** 评论者质疑“直接替代”的说法：traceroute66 认为 Outlook 集成和 Office 365 捆绑使这一说法被夸大；hobo123 则援引 Outlook 将只支持云端 Exchange 的说法，追问客户届时如何连接 Stalwart。rmoriz 指出，德国 GoBD 要求邮件不可篡改地保存最长 10 年，而 Stalwart 的常规套餐或开源版本缺少这项功能；andreashaerter 还认为，支持 MAPI 会加深 Microsoft 的协议锁定，不利于开放邮件生态。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://stalw.art/blog/microsoft-exchange-replacement/">Stalwart is now a drop-in replacement for Microsoft Exchange | Stalwart</a></li>
<li><a href="https://github.com/stalwartlabs/stalwart">GitHub - stalwartlabs/ stalwart : All-in-one Mail &amp; Collaboration server .</a></li>
<li><a href="https://www.mailpiler.org/">Piler - Open Source Email Archiving</a></li>

</ul>
</details>

**标签**: `#email`, `#open-source`, `#microsoft-exchange`, `#interoperability`, `#mail-server`

---

<a id="item-tech-news-7"></a>
### [Codex2api 疑遭供应链投毒，受影响版本应回退至 3.1.9](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 7.0/10

据项目事件复盘，Codex2api 作者账号被黑，攻击者绕过 main 分支推送 tag，使 Release 构建出带后门的版本；v3.1.11 移除了鉴权，可能导致无需密码的远程命令执行。相关 workflow 还被指外传仓库的 16 个 GitHub Actions secrets，波及同账号下至少 21 个仓库。已安装或更新到 3.1.10–3.1.12 的用户被建议立即停用并回退到 3.1.9，同时轮换 GitHub token、SSH key、数据库和 DeepSeek 等相关密钥。上述影响来自项目方复盘，尚待独立验证。

telegram · zaihuapd · 11月23日 11:21

**「背景」** Codex2api 是托管在 GitHub 上的开源项目，其发布流程通过打 tag 触发 Release 构建；GitHub Actions secrets 则是仓库工作流使用的凭据，例如 token、SSH key 以及数据库或 API 密钥。一旦发布流程被滥用，影响范围就可能超出单个构建产物，因为工作流能够访问同一账号下的多个仓库及其中保存的密钥。

**「处置建议」** 已安装或更新 3.1.10–3.1.12 的用户应立即停用相关服务并回退到 3.1.9，同时轮换 GitHub token、SSH key、数据库和 DeepSeek 等所有相关密钥。由于 v3.1.11 移除了鉴权，攻击者可无密码远程执行命令，且同账号下至少 21 个仓库的 Actions secrets 可能已外泄，延迟处置会扩大风险。

**标签**: `#supply-chain-security`, `#security-incident`, `#github-actions`, `#remote-code-execution`, `#open-source`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [vLLM 插件实现 ERNIE 5.5 Flash Preview 首日支持](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 7.0/10

rss · vLLM Blog · 11月24日 00:00

**「背景」** 百度 ERNIE 5.5 Flash Preview 是总参数 280B、每 token 激活 14B 的稀疏 MoE 模型，支持 100 万 token 上下文和长程 Agent 任务。为在发布首日即可用 vLLM 部署，同时避免维护 fork、定制镜像或等待 nightly 构建，双方选择了独立插件方案。

**「方案」** 该 vLLM-ERNIE 插件安装在与 vllm==0.32.0 相同的环境中，通过 vllm.general\_plugins 入口自动注册模型架构、配置、分词器、聊天渲染器及解析器，且仅在配置匹配时导入模型代码，因此不影响同环境中的其他模型；注意力内核、KV cache 管理、投机解码、并行和服务端仍复用 vLLM。作者称，针对 VHA 跨头混合、Multi-Router Latent MoE、MultiMax 输出头等新结构，团队按计算与访存特征设计融合内核并在加载时预折叠权重，使单内核比朴素实现快 1.55×–6.53×，关键结果与未融合实现一致。FlashIndexer 用动态头路由和阈值预过滤降低稀疏索引成本，在 1M 上下文下报告 1.4× 加速；默认检查点采用 MXFP4 路由专家、FP8 其余权重、FP8 KV cache 和 FP4 DSA 索引器。DSpark 三层 MoE 草稿模型每步最多提议 7 个 token，作者称在真实编码和 Agent 负载上平均接受长度超过 4.0。

**「启示」** 作者的核心结论是：把模型代码与内核优化放进独立插件，可在不牺牲 vLLM 通用能力的前提下实现新模型首日部署；而围绕具体结构做融合，并与量化和投机解码协同，是长上下文 MoE 推理加速的关键。

**标签**: `#vLLM`, `#ERNIE`, `#MoE inference`, `#kernel fusion`, `#speculative decoding`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [Anthropic 上市后 AI 股遭抛售，DeepSeek 与月之暗面上市计划承压](https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo) ⭐️ 8.0/10

据彭博社报道，Anthropic 完成 1195 亿美元 IPO 后全球科技股加速下跌，令 DeepSeek、月之暗面、阶跃星辰等中国 AI 公司筹备中的上市计划蒙上阴影。报道称，中国科技股自 6 月底以来累计蒸发 1.7 万亿美元市值，智谱较 6 月高点跌超 85%，MiniMax 本月跌破发行价。

telegram · zaihuapd · 11月23日 09:31

**「背景」** 中国大模型公司此前已开始试水公开市场：智谱和 MiniMax 于 2026 年 1 月先后在香港上市，其股价表现成为 DeepSeek、月之暗面等后来者首次公开募股（IPO）定价的参照。Anthropic 的上市首日大涨未能扭转 AI 板块的抛售，给新股发行进一步降温。

**「影响」** 如果这轮抛售继续，DeepSeek、月之暗面等正在筹备上市的中国 AI 公司，其 IPO 估值和融资规模可能受到限制；而智谱、MiniMax 等已上市公司的股价已经下跌，持有这些股票的投资者会直接承受损失。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=xfm3Vj8W1zU">Anthropic Makes Trading Debut - YouTube</a></li>
<li><a href="https://blog.prompt20.com/posts/chinese-ai-labs-complete-guide/">Chinese AI Labs: The Complete Guide to DeepSeek , Qwen, Kimi...</a></li>
<li><a href="https://www.outlookbusiness.com/deeptech/deepseek-moonshot-gigaai-why-chinas-ai-startups-are-rushing-for-ipo">DeepSeek , Moonshot , GigaAI: Why China &#x27;s AI Startups Are Rushing...</a></li>
<li><a href="https://fortune.com/2026/07/23/moonshot-deepseek-great-chinese-ai-ipo-rush/">Moonshot , DeepSeek , and the Great Chinese AI IPO Rush | Fortune</a></li>

</ul>
</details>

**标签**: `#AI selloff`, `#China AI IPOs`, `#Anthropic IPO`, `#tech stocks`, `#market disruption`

---

<a id="item-finance-news-2"></a>
### [威廉姆斯：美联储仍需行动让通胀回到 2%](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 7.0/10

纽约联储主席威廉姆斯 11 月 23 日表示，美联储仍需随着时间推移采取行动，把通胀拉回 2%目标；他预计通胀将在 2027 年更接近 2%，并在次年达到目标。市场目前完全计入 12 月 8 日至 9 日会议加息 25 个基点的预期，即把联邦基金利率目标区间从 3.75%-4%上调。

rss · CNBC Finance · 11月23日 21:02

**「背景」** 美联储当前利率目标区间为 3.75%-4%，通胀仍高于 2%目标，官员们对加息速度存在分歧。

**标签**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#interest rates`, `#John Williams`

---

<a id="item-finance-news-3"></a>
### [上海地铁 12 月 1 日起调整票价，为 21 年来首次](https://weibo.com/1699432410/5368461393397183) ⭐️ 7.0/10

据新华社报道，上海宣布自 12 月 1 日起调整地铁票价，为 21 年来首次，新方案起乘价 3 元、覆盖 0 至 4 公里，之后按里程分段加价。

telegram · zaihuapd · 11月23日 10:45

**「背景」** 上海地铁票价已约 21 年未调整；此次调整将按距离分段加价，并同步推出计次票和满额优惠，目的是减少调价对高频出行人群的影响。

**「影响」** 此次调价直接影响上海地铁的日常通勤者，官方同步推出 11 月 26 日开售的计次票，以及同一支付渠道当月累计满 90 元后的 9 折优惠，以减轻对高频出行人群的影响。

**标签**: `#Shanghai metro`, `#public transit fares`, `#fare reform`, `#commuting costs`, `#China transport policy`

---

<a id="item-finance-news-4"></a>
### [黄循财：新加坡不会成为规避美国芯片管制的通道](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

新加坡总理黄循财表示，新加坡不会成为企业规避美国芯片出口管制的通道，当局正在调查 Megaspeed 采购英伟达芯片的交易。此前一天，美国商务部将 Megaspeed 及另外 6 家东南亚企业列入贸易黑名单；《联邦公报》称这些企业存在向未获授权用户转移先进计算产品的“重大风险”。

telegram · zaihuapd · 11月24日 05:03

**「背景」** 路透社报道，阿里巴巴新加坡子公司 Apex Enterprise Solutions 也在名单中，阿里巴巴称从未转移受管制的先进计算芯片。

**标签**: `#Singapore`, `#US chip export controls`, `#semiconductors`, `#Megaspeed`, `#Alibaba`

---