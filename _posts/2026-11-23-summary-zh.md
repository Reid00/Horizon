---
layout: default
title: "Horizon Summary: 2026-11-23 (ZH)"
date: 2026-11-23
lang: zh
---

> 从 28 条内容中筛选出 7 条重要资讯。

---

**科技新闻**
1. [OpenAI 发文讨论困惑度与模型智能的关系](#item-tech-news-1) ⭐️ 8.0/10
2. [硅谷发生了什么：重设技术业的优化目标](#item-tech-news-2) ⭐️ 7.0/10
3. [Windows Server 2028 默认移除 WoW64，32 位应用需手动装回](#item-tech-news-3) ⭐️ 7.0/10

**科技博客**
1. [不确定时，不妨“乱试一通”](#item-tech-blog-1) ⭐️ 6.0/10

**财经新闻**
1. [美股科技股大幅下跌，亚洲多市场推出稳定市场措施](#item-finance-news-1) ⭐️ 9.0/10
2. [中国要求美国撤销 FCC 电话号段接入限制](#item-finance-news-2) ⭐️ 7.0/10
3. [超级厄尔尼诺海温指标破纪录，世界粮食计划署警告援助承压](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [OpenAI 发文讨论困惑度与模型智能的关系](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 8.0/10

OpenAI 发布文章《Perplexity and Intelligence》，讨论困惑度（perplexity）与模型智能之间的关系。由于原文内容未提供，文章的具体结论、是否提出新的评估方法以及涉及哪些模型，均无法从现有材料确认。Hacker News 的讨论则围绕交叉熵趋势、强化学习后的评估，以及 GPT-4.5 与 GPT-5 的困惑度对比展开。

hackernews · acossta · 11月22日 17:06 · [社区讨论](https://news.ycombinator.com/item?id=50601525)

**「背景」** 困惑度（perplexity）是语言模型对一段 token 序列预测不确定性的度量：模型对每个下一 token 的预测越确定，困惑度越低；最理想为 1，随机猜测时约等于词表大小。OpenAI 的《Perplexity and Intelligence》围绕这一指标与模型能力之间的关系展开，Hacker News 上的讨论则集中在交叉熵趋势、强化学习后的评估以及基准是否过于简化。

**「社区讨论」** 评论区有人对强化学习普及后交叉熵趋势仍如此清晰感到意外，并认为简单基准比日益复杂的评测更有价值；也有人从“预测即压缩”的角度认为困惑度与智能的对应并不意外。另有评论称微软的 MAI 模型被加入同一图表，并承诺在共同留出集上报告预训练进展，但这一说法来自评论者转述，未在原文中核实。

<details><summary>参考链接</summary>
<ul>
<li>Perplexity and Intelligence | OpenAI</li>
<li>Perplexity and Intelligence - Hacker News</li>

</ul>
</details>

**标签**: `#LLM evaluation`, `#perplexity`, `#cross-entropy`, `#OpenAI`, `#model intelligence`

---

<a id="item-tech-news-2"></a>
### [硅谷发生了什么：重设技术业的优化目标](https://www.oreilly.com/radar/what-happened-to-silicon-valley/) ⭐️ 7.0/10

O&\#x27;Reilly Radar 刊出的《What Happened to Silicon Valley?》是一篇观点文章，而非产品发布或技术突破；它回看硅谷的市场与激励结构如何塑造行业轨迹，并主张重新思考技术业应当优化什么。文章把“机制设计”称为反向博弈论：不只问当前游戏规则，而先问“我们应当玩哪一场游戏”，并给出“人类福祉”这一目标。其论点是应把优化目标从默认的股东价值转向人类福祉，但这是一套规范性论证，没有提供已实施的治理方案或效果数据。

hackernews · greenyouse · 11月22日 19:20 · [社区讨论](https://news.ycombinator.com/item?id=50602947)

**「背景：机制设计与“逆向博弈论”」** 这篇文章源自 Tim O&\#x27;Reilly 于 2026 年 10 月 16 日在约翰斯·霍普金斯大学所做的一场演讲，其核心论点是硅谷的机制在奖励“价值榨取”而非“价值创造”，而 AI 需要一套为人类福祉而设的新市场规则。其论证依托“机制设计”这一概念——O&\#x27;Reilly 将其称为“逆向博弈论”，即不把市场当作只能被动接受的自然现象，而是把游戏规则本身当作可以有意识设计、并追究设计者责任的对象。在此基础上，他追问的是“我们本该玩什么游戏”，而非仅仅描述当下的规则如何运作。

**「社区讨论」** 评论者大多认同文章对激励机制的批评，Animats 进一步主张必须把市场视为被人为设计并运行的“机器”，追究机制设计者责任；michalsustr 则认为全文最重要的观点是“机制设计即反向博弈论”，即先问应当玩哪场游戏。CoolestBeans 把近因归于零利率时代催生的扩张和当下以 AI 为由的支出，smath 则追问弗里德曼式股东利润责任应放在多长的时间框架内、以及为何一定是错的。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.lavx.hu/article/tim-o-reilly-traces-silicon-valley-s-shift-from-value-creation-to-extraction">Tim O&#x27;Reilly Traces Silicon Valley&#x27;s Shift From Value ...</a></li>

</ul>
</details>

**标签**: `#Silicon Valley`, `#tech industry`, `#mechanism design`, `#capitalism`, `#AI`

---

<a id="item-tech-news-3"></a>
### [Windows Server 2028 默认移除 WoW64，32 位应用需手动装回](https://www.windowslatest.com/2026/11/23/32-bit-apps-days-are-numbered-as-microsoft-strips-support-bit-by-bit-starting-with-windows-server-2028-but-windows-11-is-safe-for-now/) ⭐️ 7.0/10

微软在 Ignite 2026 上表示，Windows Server 2028 将默认不再包含 WoW64 兼容子系统，因此系统开箱无法运行 32 位应用。该版本计划于 2027 年秋季与 Windows 11 27H2 一同发布。需要时可通过“按需功能”（FoD）把 WoW64 装回，Server Core 上通常使用 PowerShell 或 DISM 添加；微软称此举旨在减少攻击面、阻止 32 位恶意软件。Windows 11 目前仍保留 WoW64，微软未公布移除计划。

telegram · zaihuapd · 11月23日 03:03

**「背景」** WoW64（Windows 32-bit on Windows 64-bit）是 64 位 Windows 上运行 32 位应用的兼容层。此前 64 位 Windows 一直默认包含该子系统，32 位程序无需额外配置即可运行；据 Windows Central 报道，Windows Server 2028 将是首个开箱不支持 32 位应用、把 WoW64 改为可选组件的 Windows Server 版本。

**「影响」** 仍依赖 32 位应用的服务器环境在部署 Windows Server 2028 时，需要先通过 FoD 安装 WoW64，否则这些程序在默认配置下无法启动；Server Core 用户还需准备 PowerShell 或 DISM 的安装流程。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.windowscentral.com/microsoft/windows-11/microsoft-is-removing-32-bit-app-support-from-the-next-version-of-windows-server-wow64-subsystem-to-become-optional-component-to-reduce-malware-attack-surface">Windows Server 2028 to remove 32-bit app support for improved ...</a></li>
<li><a href="https://undercodenews.com/microsoft-plans-to-remove-32-bit-app-support-by-default-in-windows-server-2028-citing-growing-security-risks/">Microsoft Plans to Remove 32-Bit App Support by Default in ...</a></li>

</ul>
</details>

**标签**: `#Windows Server 2028`, `#WoW64`, `#32-bit compatibility`, `#Microsoft`, `#enterprise IT`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [不确定时，不妨“乱试一通”](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月23日 00:00

**「背景」** 面对缺乏明确指引、不知道什么做法有效的局面，作者认为谨慎等待通常不如主动“乱试一通”；但作者也承认，这种做法有损害个人声誉的风险。

**「方案」** 作者所说的“乱试”不是盲目折腾，而是同时尝试多个方向，以便尽快接触现实、获得反馈。因为人在信息不足时大多判断会出错，多试几个方案既能提高命中率，也能避免对单一计划过度投入；随后要密切观察来自同事、专家和实际指标的反馈，并果断放弃没有积极效果的方向。作者举了三个场景：产品尚未找到市场契合时，可在核心设想周边多做尝试，他在 GitHub Models（现已退役）上做的“用 GitHub Actions token 运行 AI 推理”原本只是众多尝试之一，却意外有黏性，后来成为“Continuous AI”的种子；面对复杂系统时，与其通读全部代码，不如先做几组试探性改动，看效果再决定是否深挖；在组织问题上，则可自动化部分手工工作、主动接手任务或提出长期方案。组织场景尤其需要敏感于反馈，否则帮助对象的不满可能转向自己。作者也提醒，从内部看这很像反复失败，但这种感觉不应阻止行动。

**「启示」** 作者的核心论点是，在高度不确定的环境中，广泛实验、紧贴反馈并快速淘汰，比等待完整理解更快建立判断力；前提是能承受“像在乱试”的心理不适并控制声誉风险。

**标签**: `#engineering judgment`, `#uncertainty`, `#experimentation`, `#feedback loops`, `#organizational engineering`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美股科技股大幅下跌，亚洲多市场推出稳定市场措施](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 9.0/10

周五美国 AI 科技股遭遇大规模抛售，纳斯达克指数单日下跌 5.28%，费城半导体指数下跌近 11%。随后中国内地、韩国及中国台湾地区相继推出稳定市场措施，包括下调融资保证金最低比例至 80%、放宽上市公司每日回购订单数量限制，以及全面禁止平盘以下卖空。

telegram · zaihuapd · 11月22日 13:24

**「背景」** 此前一个交易日，美国 AI 科技股遭遇集中抛售，纳斯达克指数收跌 5.28%，费城半导体指数跌近 11%，恐慌情绪随即传导至亚洲市场。韩国和台湾地区监管机构随后推出放宽回购、限制卖空等稳定措施，这类工具通常用于压低杠杆和卖压。

**「影响」** 对市场参与者而言，中国内地融资保证金最低比例降至 80%、中国台湾地区融券保证金从 130%升至 150%并禁止低于前收盘价卖空，直接改变杠杆交易者和卖空者的资金门槛；韩国放宽回购订单限制则扩大上市公司三个月内的回购空间。

<details><summary>参考链接</summary>
<ul>
<li>South Korea readies its market stabilization fund and Taiwan bans short sales of falling stocks after Asia&#x27;s AI rout | MLQ.ai</li>
<li>Taiwan Widens Short Sale Curbs After Shares Plunge on AI Concern - Bloomberg</li>

</ul>
</details>

**标签**: `#US tech selloff`, `#Asian markets`, `#margin trading rules`, `#short-selling restrictions`, `#market stabilization`

---

<a id="item-finance-news-2"></a>
### [中国要求美国撤销 FCC 电话号段接入限制](https://www.bloomberg.com/news/articles/2026-11-22/china-objects-to-us-curbs-on-telecoms-access-to-phone-numbers) ⭐️ 7.0/10

中国商务部 11 月 22 日要求美国撤销联邦通信委员会（FCC）11 月 19 日投票通过的措施：该措施对申请直接接入美国电话号码的互联网语音服务商新增国家安全认证，从而阻止中国移动、中国电信、中国联通直接获取美国号码。商务部称此举违反非歧视与公平竞争原则，并警告相关举措正推动两国在电信领域脱钩。

telegram · zaihuapd · 11月22日 06:44

**「背景」** 美国联邦通信委员会（FCC）是美国电信监管机构；它在 11 月 19 日投票新增国家安全认证，禁止被列入其“覆盖清单”（视为国家安全风险的设备和服务名单）的实体直接接入美国电话网络。

**「影响」** FCC 新规将中国移动、中国电信、中国联通及其他受限互联网语音服务商排除在美国号码的直接接入之外，依赖这些线路的跨境通话将不得不经由第三方运营商转接。

<details><summary>参考链接</summary>
<ul>
<li>FCC Votes to Ban Chinese Telecoms From Direct Access to US Phone Numbers</li>
<li><a href="https://www.jpost.com/international/article-915665">China slams US FCC ban on direct phone number access for...</a></li>

</ul>
</details>

**标签**: `#美中电信政策`, `#FCC监管`, `#中国运营商`, `#国家安全`, `#电信脱钩`

---

<a id="item-finance-news-3"></a>
### [超级厄尔尼诺海温指标破纪录，世界粮食计划署警告援助承压](https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/) ⭐️ 7.0/10

据伯克利地球气候学家 Zeke Hausfather，截至 10 月，用于衡量厄尔尼诺强度的中热带太平洋升温已达 3.5℃，打破此前约 2.75℃的纪录，并预计在初冬升至约 4℃的峰值。世界粮食计划署 8 月警告，本轮厄尔尼诺可能在 2027 年底前把额外 4900 万人推入急性粮食不安全，使总数达到 2.74 亿；该署还称，全球援助资金 2025 年较 2022 年峰值下降 30%，索马里遭遇类似旱情时其覆盖人数从 1000 万降至不足 100 万。

telegram · zaihuapd · 11月22日 14:09

**「背景」** 厄尔尼诺是赤道太平洋海水异常升温、扰乱全球降雨和气温模式的气候现象；联合国世界粮食计划署 8 月据此警告，到 2027 年底可能新增 4900 万人陷入急性粮食不安全（食物严重不足、危及生命或生计），使总数达到 2.74 亿。

**「影响」** 若上述预测成立，依赖粮食援助的急性粮食不安全家庭将同时面对需求增加和援助资金减少。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/">How This Year’s Super El Niño Will Worsen Global Hunger | WIRED</a></li>

</ul>
</details>

**标签**: `#El Niño`, `#food insecurity`, `#humanitarian funding`, `#climate risk`, `#WFP`

---