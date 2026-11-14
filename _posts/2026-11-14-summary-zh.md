---
layout: default
title: "Horizon Summary: 2026-11-14 (ZH)"
date: 2026-11-14
lang: zh
---

> 从 40 条内容中筛选出 7 条重要资讯。

---

**科技新闻**
1. [TorchTitan 在 384 块 GH200 上训练 1T MoE 的实践](#item-tech-news-1) ⭐️ 8.0/10
2. [KORS 实时航空波段服务覆盖全频段，记录地面停飞通话](#item-tech-news-2) ⭐️ 7.0/10
3. [Python 早期贡献者 Tim Peters 去世，享年 74 岁](#item-tech-news-3) ⭐️ 7.0/10
4. [微软 Outlook、Teams 全球宕机超 12 小时](#item-tech-news-4) ⭐️ 7.0/10
5. [DeepSeek 开放全家桶应用 API 并开源聊天 Demo](#item-tech-news-5) ⭐️ 7.0/10
6. [OpenAI 推出 ChatGPT Wallet 智能体支付钱包](#item-tech-news-6) ⭐️ 7.0/10

**财经新闻**
1. [芝加哥联储行长：通胀仍顽固，美联储“肯定还有工作要做”](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [TorchTitan 在 384 块 GH200 上训练 1T MoE 的实践](https://www.reddit.com/r/MachineLearning/comments/1xvce5h/scaling_to_1t_moe_on_torchtitan_p/) ⭐️ 8.0/10

一篇 Reddit 帖子总结了在 JUPITER 的 384 块 GH200 上，用 TorchTitan/PyTorch 训练约 1T 参数 MoE 的工程经验，报告约 1,300 tokens/s/GPU，相比起点提升 14 倍。作者采用 384 路 FSDP 加 4 路 EP（EP 限制在节点内），并称通过全量激活检查点、将检查点卸载到 Grace、改用 Muon 优化器，把序列长度推到 64k token。帖子还报告 FlexShard 按完整专家分片、把 Newton-Schulz 放到 GPU 执行使优化器步从 42 秒降到约 2 秒、吞吐提升 35%，以及修复 CUDA 流内存池问题后重试从 384 个 rank 降到零、吞吐提升 21%。这些是社区帖子中的自述结果，且所给内容在结尾处被截断，尚未经过独立验证。

reddit · r/MachineLearning · /u/f14-bertolotti · 11月13日 16:28

**「背景」** TorchTitan 是 PyTorch 官方的大规模训练框架，支持 dense、MoE 和扩散模型的规模化训练（InfoQ 报道）。GH200 是 Grace Hopper 超级芯片，JUPITER 超算即由它搭建；其节点内 NVLink 带宽远高于跨节点 InfiniBand，因此跨节点通信通常成为扩展瓶颈。文中反复用到的两种切分方式是 FSDP（每张卡持有全部权重的一个切片，计算前即时聚合）与专家并行 EP（每张卡只拥有部分专家，token 被路由到对应卡上）。

**「影响」** 对使用 TorchTitan 的团队而言，可直接参考的改动包括 FlexShard 的专家级分片、优化器卸载时在 GPU 上运行 Newton-Schulz，以及把集合通信临时分配移到计算流；后者依赖 FSDP2 的 unshard\_async\_op 私有开关，作者称其正在转为公开 API，因此在公开前升级需评估兼容性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.infoq.com/news/2026/10/google-meta-torchtpu/">PyTorch Conference 2026: Google and Meta Open-Source... - InfoQ</a></li>

</ul>
</details>

**标签**: `#mixture-of-experts`, `#distributed training`, `#PyTorch`, `#GPU scaling`, `#large language models`

---

<a id="item-tech-news-2"></a>
### [KORS 实时航空波段服务覆盖全频段，记录地面停飞通话](https://orcasairband.com/) ⭐️ 7.0/10

来自 KORS（Orcas）的实时航空波段收听服务现已覆盖整个 airband，面向航空爱好者以及想旁听本地空域通话的飞行员。项目作者称，系统由 ETTUS B210 SDR 接入双 4090 主机，在 GPU 上用 CUDA 做多相信道化和解调，并自动检测发射。作者还发布了与当天 ground stop 可能相关的原始、未编辑转录：126.400 Victoria Ground 提到“通信问题”并称交通已被停止，134.800 Vancouver Centre 也有相关通话。另一条评论回指 14:03 的记录，称当时已确认有飞往温哥华的 ground stop，且没有航班起飞前往温哥华降落；这些转录来自弱信号和实时抓取，完整性与准确性未获独立核实。

hackernews · mmaunder · 11月13日 22:04 · [社区讨论](https://news.ycombinator.com/item?id=50490593)

**「背景」** 航空波段是用于塔台、进近和航路管制的 VHF 语音频段，传统收听通常一次只守一个频率。项目作者在讨论中说明，该系统用 ETTUS B210 接收整个航空波段，再由双 RTX 4090 上的 CUDA 多相信道化器拆分信道并解调，因此能同时监测大量频率。

**「影响」** 对想复现该项目的 SDR 开发者而言，关键硬件门槛是 ETTUS B210 加双 4090 主机；讨论中没有给出成本、端到端延迟或具体频率覆盖指标。对本地飞行员和航空爱好者，站点提供的是实时、未编辑的转录，弱信号会导致部分通话难以辨认，因此更适合作为旁听参考而非完整记录。

**「社区讨论」** 评论中，molsongolden 回指 14:03 的通话记录，称当时已确认有飞往温哥华的 ground stop；ltrg 则把它类比为用公共 KiwiSDR 接收器解码船舶 DSC 信号的业余项目，并提到多接收机时延定位可用于追踪 AIS 暗船。plipt 对转录中大量含混不清的通话表示意外。

**标签**: `#software-defined radio`, `#GPU acceleration`, `#CUDA`, `#real-time signal processing`, `#aviation communications`

---

<a id="item-tech-news-3"></a>
### [Python 早期贡献者 Tim Peters 去世，享年 74 岁](https://x.com/Itsfoss/status/2120957452937998716) ⭐️ 7.0/10

据 Python 创造者 Guido van Rossum 公布的消息，早期 Python 贡献者 Tim Peters 去世，享年 74 岁。Peters 被称为 Python 的第二位真实用户，撰写了 Timsort 排序算法和《Python 之禅》（PEP 20），并曾在 Python 软件基金会董事会任职 13 年。上述消息来自转述，未提供去世日期或更多细节。

telegram · zaihuapd · 11月13日 09:55

**「背景」** PEP 20 属于 Python 的 PEP（Python Enhancement Proposal）文档体系，记录的是社区常引用的《Python 之禅》设计格言；Timsort 则是 Peters 编写的排序算法。二者分别对应 Python 的语言设计理念和底层实现贡献，也是他常被提及的两项工作。

**标签**: `#Python`, `#open source community`, `#Tim Peters`, `#Timsort`, `#obituary`

---

<a id="item-tech-news-4"></a>
### [微软 Outlook、Teams 全球宕机超 12 小时](https://www.reuters.com/technology/microsoft-365-outlook-down-thousands-us-users-downdetector-shows-2026-11-12/) ⭐️ 7.0/10

微软 Outlook、Teams 和 Copilot 在 11 月 13 日仍处于宕机状态，故障持续超过 12 小时，扰乱了全球企业与政府的通信。微软将原因归为服务器问题，称未发现恶意活动，并已扩大修复范围、看到回稳迹象。澳大利亚、日本和美国部分政府机构受到影响，Euronext 邮件受阻，台湾有金融机构改用传真确认交易；这是微软 365 服务今年第二次中断。

telegram · zaihuapd · 11月13日 12:21

**「背景」** Outlook、Teams 和 Copilot 均以微软 365 云服务形式提供，因此服务器端故障会同时波及多个地区的用户，而不只影响单一企业或本地部署。此次故障是微软 365 服务今年第二次中断，表明同一云平台在年内再次出现大范围不可用。

**「实际影响」** 在台湾，有金融机构在中断期间改用传真确认交易；依赖 Outlook 和 Teams 的企业与政府机构需要准备替代通信渠道，以应对关键服务不可用的情况。

**标签**: `#Microsoft 365`, `#service outage`, `#cloud reliability`, `#enterprise communications`

---

<a id="item-tech-news-5"></a>
### [DeepSeek 开放全家桶应用 API 并开源聊天 Demo](https://mp.weixin.qq.com/s/78KBHc4-4N5b2vfL9SkutQ) ⭐️ 7.0/10

DeepSeek 宣布开放全家桶应用 API，开发者只需在原有 API 中开启对应参数，即可获得深度思考搜索、文件输入、阅读链接、语音等对话能力，服务端会自动完成工具调用与上下文拼接。V4.1-Flash 模型已在三个接口支持这些能力；Search、Fetch、OCR、ASR、TTS 也可单独调用。官方同时开源了可导入历史对话的前端 Demo，并提供了体验地址。

telegram · zaihuapd · 11月13日 14:27

**「背景」** 应用级 API 指把网页端对话中常用的搜索、文件输入、链接阅读和语音等能力封装成可调用服务，而不只是返回模型生成的文本。DeepSeek 这次是在原有 API 上通过参数开关开放这些能力，并由服务端负责工具调用与上下文拼接，开发者无需在客户端逐项编排。

**「对开发者的影响」** 对于需要自建对话产品的团队，直接开启内置参数即可获得搜索、文件、链接阅读和语音能力，工具调用与上下文拼接由服务端完成；若要替换其中某一环节，则可改为单独调用 Search、Fetch、OCR、ASR、TTS。不过，应用级内置能力目前仅由 V4.1-Flash 在三个接口中支持，接入前需确认所用接口是否覆盖所需功能。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://api-docs.deepseek.com/news/news261113/">The full DeepSeek App experience, now via API | DeepSeek API Docs</a></li>

</ul>
</details>

**标签**: `#DeepSeek`, `#AI APIs`, `#tool use`, `#open-source demo`, `#multimodal AI`

---

<a id="item-tech-news-6"></a>
### [OpenAI 推出 ChatGPT Wallet 智能体支付钱包](https://openai.com/index/introducing-chatgpt-wallet/) ⭐️ 7.0/10

OpenAI 发布 ChatGPT Wallet，并与美国运通、万事达和 Visa 合作，让智能体在不接触用户真实卡号的情况下完成支付。该钱包自 2026 年 11 月 13 日起在美国通过 dots 向 18 岁以上的 ChatGPT Pro 订阅用户开放，并要求使用美国发行的银行卡。每笔购买都由用户核对商品和金额，再用 Face ID 或指纹确认；支付网络会下发支付令牌，用来替代真实卡号。

telegram · zaihuapd · 11月13日 15:43

**「背景」** ChatGPT Wallet 接入的是美国运通、万事达和 Visa 的既有卡网络，并非由 OpenAI 单独发卡；官方称初期通过 dots 向美国 ChatGPT Pro 订阅者开放，CNBC 报道持卡人可保留原有信用卡奖励。它依赖卡组织已有的支付令牌机制，用替代卡号的令牌完成智能体交易，因此用户卡号不会交给智能体或商户。

**「影响」** 对使用该钱包的智能体支付流程而言，授权被限定为逐笔人工核对加生物识别确认，无法按完全无人值守的自动扣款来设计。当前覆盖范围也受身份、订阅和发卡地限制：仅美国 18 岁以上 ChatGPT Pro 用户及美国发行卡可用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/introducing-chatgpt-wallet/">Introducing ChatGPT Wallet | OpenAI</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/openai-chatgpt-wallet-dot-purchases.html">OpenAI &#x27;s ChatGPT Wallet allows &#x27; dots &#x27; AI agents to make purchases</a></li>

</ul>
</details>

**标签**: `#OpenAI`, `#agentic payments`, `#ChatGPT`, `#payment security`, `#AI agents`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [芝加哥联储行长：通胀仍顽固，美联储“肯定还有工作要做”](https://www.cnbc.com/2026/11/13/chicago-feds-goolsbee-says-central-bank-has-definitely-got-work-to-do-on-inflation.html) ⭐️ 7.0/10

芝加哥联储行长古尔斯比（Austan Goolsbee）表示，美联储在通胀问题上“肯定还有工作要做”，以继续恢复公信力；此前公布的 10 月生产者价格指数（PPI）环比上涨 0.3%、同比上涨 6.5%，为 2022 年 11 月以来最高。据 CME Group 的 FedWatch 工具，市场完全计入美联储在 12 月 8-9 日会议上加息 25 个基点，并认为加息 50 个基点的概率超过 10%。

rss · CNBC Finance · 11月13日 14:22

**「背景」** 古尔斯比称，美国通胀已近六年高于美联储 2%的目标，近期没有进展、甚至方向相反；他目前不是联邦公开市场委员会（FOMC）投票委员，2027 年才将成为投票委员。

**标签**: `#Federal Reserve`, `#inflation`, `#PPI`, `#monetary policy`, `#market expectations`

---