---
layout: default
title: "Horizon Summary: 2026-11-07 (EN)"
date: 2026-11-07
lang: en
---

> From 43 items, 13 important content pieces were selected

---

**Technology News**
1. [Baidu open-sources Wenxin 5.5 Flash Base 280B MoE model](#item-tech-news-1) ⭐️ 8.0/10
2. [Libghostty 1.0 released as embeddable terminal library](#item-tech-news-2) ⭐️ 7.0/10
3. [PwnEscape Part 2 Details Firecracker VM Escape Exploitation](#item-tech-news-3) ⭐️ 7.0/10
4. [Jev-to-Opus escalation matches Opus on identity resolution at 4x lower cost](#item-tech-news-4) ⭐️ 7.0/10
5. [Boson AI announces 45B full-duplex Higgs Realtime Duplex model](#item-tech-news-5) ⭐️ 7.0/10
6. [Moonshot AI reportedly seeks 8,000+ Nvidia Blackwell GPUs via European clouds](#item-tech-news-6) ⭐️ 7.0/10
7. [YMTC plans fourth Wuhan fab with up to 70% domestic tools](#item-tech-news-7) ⭐️ 7.0/10
8. [Taobao MNN open-sources 0.3B on-device model for offline mobile inference](#item-tech-news-8) ⭐️ 7.0/10

**Technology Blog**
1. [One Designer per Team, and the Trouble with Design Systems](#item-tech-blog-1) ⭐️ 7.0/10

**Financial News**
1. [CoreWeave 2032 bond yield tops 16% as AI credit stress rises](#item-finance-news-1) ⭐️ 8.0/10
2. [Nasdaq closes in correction after sharp selloff](#item-finance-news-2) ⭐️ 8.0/10
3. [Premarket Movers: Moderna and Lam Research Rise, DraftKings Falls](#item-finance-news-3) ⭐️ 7.0/10
4. [🤖 Anthropic 拟下周启动 IPO 路演，计划 11 月 16 日当周挂牌](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Baidu open-sources Wenxin 5.5 Flash Base 280B MoE model](https://www.news.cn/info/20261105/f3bbdb6854f5441ca9fb34062f213875/c.html) ⭐️ 8.0/10

Baidu has open-sourced Wenxin 5.5 Flash Base, a mixture-of-experts base model with 280 billion total parameters and 14 billion active per token. The model was pretrained on 33.5 trillion tokens with a 128K-token context, and Baidu says fine-tuning and inference support contexts up to 1 million tokens. Baidu describes systematic optimizations to attention, expert routing, and training objectives aimed at resource efficiency. The announcement provides architecture and scale details but no benchmark results or independent evaluation.

telegram · zaihuapd · Nov 6, 05:41

**「Background」** A base model is pretrained on raw text and released before instruction tuning, so it serves as a starting point for further training rather than a finished chat model. In a mixture-of-experts architecture, only a subset of parameters is activated for each token, which explains how Baidu can report 280 billion total parameters but 14 billion active parameters.

**「Impact」** Teams that need a long-context base model can fine-tune the released checkpoint instead of pretraining one from scratch, with fine-tuning and inference supported up to 1M tokens while pretraining used a 128K window. Because Baidu released pretraining-end weights rather than an instruction-tuned model, production deployment still requires task-specific fine-tuning and evaluation.

<details><summary>References</summary>
<ul>
<li><a href="https://ernie.baidu.com/zh/release/ernie-5-5-flash-base/">ERNIE 5.5 Flash Base · ERNIE</a></li>
<li><a href="https://www.knowflowhub.com/content/news/2026-11-06/baidu-ernie-5-5-flash-base-open-source-2026-11-05">百度开源文心5.5 Flash Base：280B总参数、14B激活，支持百万Token上...</a></li>

</ul>
</details>

**Tags**: `#Baidu`, `#open-source models`, `#MoE`, `#long context`, `#LLM`

---

<a id="item-tech-news-2"></a>
### [Libghostty 1.0 released as embeddable terminal library](https://mitchellh.com/writing/libghostty-1-0) ⭐️ 7.0/10

Libghostty, the embeddable terminal-emulator library behind Ghostty, has reached 1.0, according to the release post. The item frames the release as useful to developers building terminal and editor integrations, but it does not provide release notes, API details, platform support, or compatibility information. The 1.0 designation is the only version detail supplied.

hackernews · mfiguiere · Nov 6, 23:30 · [Discussion](https://news.ycombinator.com/item?id=50399933)

**「Background」** Ghostty is a terminal emulator, and Libghostty is the embeddable library built from its terminal-emulation core, packaged so other applications can reuse that engine instead of writing their own. The 1.0 release is the point at which that library is presented as a stable base for outside projects; commenters describe using it in an Android project, a separate terminal project, and the Emacs front-end Ghostel.

**「Impact」** Developers can embed Libghostty as a terminal-emulation core instead of building one themselves; commenters cite an Android project, a personal terminal project, and Emacs tooling \(Ghostel\) as practical uses. The supplied material does not state a support policy or compatibility guarantees for 1.0.

**「Community Discussion」** Commenters welcomed the release and described using Libghostty in an Android project, a personal terminal project, and Emacs tooling \(Ghostel\). One commenter asked why the project chose C rather than Zig with a C-like interface.

**Tags**: `#terminal emulators`, `#Ghostty`, `#open-source libraries`, `#developer tools`

---

<a id="item-tech-news-3"></a>
### [PwnEscape Part 2 Details Firecracker VM Escape Exploitation](https://pwn.ai/blog/firecracker-escape) ⭐️ 7.0/10

PwnEscape Part 2 is a practical exploitation writeup for the previously disclosed Firecracker VM escape, aimed at systems and security engineers. The configuration used in the writeup had no Firecracker jailer, and the article notes that production containment—privilege dropping, namespaces, and seccomp—would require a separate assessment of the privileges and resources available after a VMM compromise. Commenters emphasize that this is not a new vulnerability disclosure but a guide to exploiting PwnEscape, which was disclosed weeks earlier.

hackernews · SerCe · Nov 6, 19:33 · [Discussion](https://news.ycombinator.com/item?id=50397219)

**「Background」** PwnEscape is tracked as CVE-2026-99999, a Linux kernel networking subsystem flaw that allows code running inside a guest VM to read host memory. The Part 2 setup ran Firecracker v1.16.1 directly as root under systemd-run without the jailer; Firecracker&\#x27;s production containment is meant to drop privileges and restrict the VMM through namespaces and seccomp, so the demonstrated escape path reflects that unjailed configuration rather than a fully hardened deployment.

**「Jailer configuration determines exposure」** Deployments that launch Firecracker without its jailer companion—the configuration used in this writeup—forgo the second line of defense, so a VMM compromise yields whatever privileges the Firecracker process itself holds. Operators should verify that the jailer is actually enabled with privilege dropping, namespace and cgroup isolation, and seccomp filtering, and should treat a jailed deployment as requiring a separate assessment of post-compromise privileges rather than assuming the escape is fully contained.

**「Community discussion」** Commenters focused on real-world impact: one asked how a properly jailed and configured Firecracker instance would fare, since the writeup&\#x27;s demo omitted the jailer, while another stressed that the post is an exploitation guide for an already-disclosed bug rather than a new flaw. A third commenter argued for a formally verified microkernel hypervisor approach, and another offered a Firecracker-based public demo service as a possible testbed.

<details><summary>References</summary>
<ul>
<li><a href="https://dev.to/frankchu/93-to-root-in-5-hops-i-audited-the-firecracker-escape-4fhn">9.3 to root in 5 hops: I audited the Firecracker escape</a></li>
<li><a href="https://securityarsenal.com/blog/cve-2026-99999-pwnescape-linux-kernel-vm-escape-detection-and-remediation-guide-for-cloud-and-virtualization-operators">CVE-2026-99999 (PwnEscape): Linux Kernel VM Escape ...</a></li>
<li><a href="https://rustutils.com/tools/firecracker/">Firecracker — Rust Utils</a></li>
<li><a href="https://firecracker-microvm.github.io/">Firecracker</a></li>

</ul>
</details>

**Tags**: `#virtualization`, `#security`, `#firecracker`, `#exploitation`, `#microvm`

---

<a id="item-tech-news-4"></a>
### [Jev-to-Opus escalation matches Opus on identity resolution at 4x lower cost](https://hightouch.com/blog/llm-judges-identity-resolution) ⭐️ 7.0/10

Hightouch published a blog post describing a smaller “Jev” model that can escalate to Opus for help and reportedly matches Opus’s accuracy on identity resolution at roughly 4x lower cost. The result is a vendor-reported, task-specific benchmark rather than a demonstration of general model or coding-agent improvement. The post does not establish that the same accuracy-cost tradeoff holds outside identity resolution.

hackernews · theanomaly · Nov 6, 19:48 · [Discussion](https://news.ycombinator.com/item?id=50397429)

**「Background」** LLM-as-judge setups use one model to adjudicate another system&\#x27;s output — in this case, deciding whether two records refer to the same person. Hightouch&\#x27;s own testing pitted Jev and GPT-6 Luna against each other as identity-resolution judges, and the escalation design it describes forwards only Jev&\#x27;s uncertain verdicts: when Jev estimated a 30–90% chance of a bad merge, Opus re-checked the case, which routed 22% of profiles to Opus on the first dataset.

**「Impact」** Teams evaluating LLM judges for identity resolution could use a smaller escalation model to reduce inference cost, but they would need to validate escalation behavior and accuracy on their own data before relying on the reported 4x savings.

**「Community Discussion」** Commenters focused on scope: nico noted that the result is specific to identity resolution and does not demonstrate general usage or coding-agent gains, while netshade reported similar success getting a smaller model to decide when to escalate but said the right economics are highly task-specific. Fordec argued that model-controlled context curation may matter more than handing an agent all available context.

<details><summary>References</summary>
<ul>
<li><a href="https://hightouch.com/blog/llm-judges-identity-resolution">LLM Judges for Identity Resolution at 4 x Lower Cost | Hightouch</a></li>
<li><a href="https://dzen.ru/b/au5Dh4_iHEo_9lgB">Jev с Opus : почти та же точность вчетверо дешевле Hightouch ...</a></li>

</ul>
</details>

**Tags**: `#LLM routing`, `#model cascades`, `#AI cost optimization`, `#identity resolution`, `#LLM judges`

---

<a id="item-tech-news-5"></a>
### [Boson AI announces 45B full-duplex Higgs Realtime Duplex model](https://www.reddit.com/r/MachineLearning/comments/1xpn5pv/higgs_realtime_duplex_a_45b_moe_fullduplex_model/) ⭐️ 7.0/10

Boson AI announced Higgs Realtime Duplex, a 45B mixture-of-experts model for developers building real-time voice and video agents, which runs audio, video, text, and face outputs as parallel 160 ms streams while performing background thinking, tool calls, and delegation. The company says the model can start speaking before staged tool results are complete and can hand harder problems to a larger backend model with shared context. Duplex is not open weights and its API is waitlisted; the earlier turn-based Higgs Realtime is available now. Boson reports benchmark comparisons against OpenAI, Google, and Thinking Machines systems, but the results are self-reported and have not been independently validated.

reddit · r/MachineLearning · /u/Cali\_Cobarde · Nov 6, 20:23

**「From turn-taking to continuous streams」** Most voice assistants are turn-based: they wait for the user to finish, then reason and respond, so interaction timing is handled outside the model. Boson AI&\#x27;s earlier Higgs Realtime is turn-based and remains available now, while the new Duplex API is waitlisted. Duplex instead keeps audio and video input and audio and face output running as parallel 160 ms streams, treating silence as input the model uses to decide when to backchannel, interrupt, or stay quiet.

**「What this means for builders」** Developers already integrating Boson&\#x27;s turn-based Higgs Realtime API, which the company documents as compatible with the OpenAI Realtime API, can keep that integration running, since Duplex is waitlisted and not open weights. Teams whose applications depend on smooth turn-taking should benchmark before migrating: Boson&\#x27;s own table puts Duplex at 75.5 on Full-Duplex-Bench v1.5 versus 77.8 for Thinking Machines&\#x27; Interaction Small and 80.1 for OpenAI&\#x27;s best configuration, the area the author identifies as furthest behind.

<details><summary>References</summary>
<ul>
<li><a href="https://www.boson.ai/higgs-realtime">Higgs Realtime – Boson AI</a></li>

</ul>
</details>

**Tags**: `#full-duplex models`, `#multimodal LLM`, `#mixture-of-experts`, `#real-time voice AI`, `#tool use`

---

<a id="item-tech-news-6"></a>
### [Moonshot AI reportedly seeks 8,000+ Nvidia Blackwell GPUs via European clouds](https://www.cnbc.com/2026/11/05/moonshot-ai-nvidia-chips-europe-china.html) ⭐️ 7.0/10

Moonshot AI is reportedly negotiating to rent more than 8,000 Nvidia Blackwell GPUs from European neocloud data centers, mainly for inference but also for some training, according to CNBC. Under one proposed arrangement, the company would have to pay 30% to 50% more upfront than non-Chinese buyers, the report says, citing unnamed sources. The plan comes as U.S. export controls bar Blackwell imports into China; the White House said in July that Moonshot had obtained Blackwell chips through a facility in Thailand. Using overseas cloud capacity remotely is viewed as a way around the import ban, though the report does not establish that the proposed rental has been completed or approved.

telegram · zaihuapd · Nov 6, 05:02

**「Why Moonshot is renting abroad」** U.S. export controls prohibit selling Nvidia&\#x27;s top-end accelerators such as Blackwell to customers in China, so Chinese AI developers have turned to renting compute overseas rather than buying chips directly. That route runs through &quot;neocloud&quot; providers — smaller GPU-focused cloud operators that have expanded quickly to meet AI demand, with industry estimates cited in 2026 putting the sector at roughly $35 billion and projecting about 46% annual growth. The source also notes that the White House said in July that Moonshot had previously obtained Blackwell chips through a facility in Thailand.

**「Impact」** If completed, the deal would give Moonshot access to Blackwell capacity it cannot import directly while making it dependent on European third-party providers for a large block of inference compute. The reported 30% to 50% prepayment premium would also raise the upfront cash required compared with non-Chinese customers, and the arrangement would remain exposed to U.S. export-control enforcement.

<details><summary>References</summary>
<ul>
<li><a href="https://www.linkedin.com/pulse/100-billion-moat-why-one-can-build-next-credible-neocloud-neville-wlnkc">~$100B. Chamath estimate: cost of 1 GW of compute ( 2026 ) 684%.</a></li>

</ul>
</details>

**Tags**: `#AI compute`, `#Nvidia Blackwell`, `#export controls`, `#Moonshot AI`, `#cloud infrastructure`

---

<a id="item-tech-news-7"></a>
### [YMTC plans fourth Wuhan fab with up to 70% domestic tools](https://www.reuters.com/world/china/chinas-top-flash-memory-chipmaker-targets-more-homegrown-tools-new-factory-2026-11-06/) ⭐️ 7.0/10

Yangtze Memory Technologies \(YMTC\) plans a fourth fab in Wuhan, with construction expected to begin in 2027, and aims to source 60–70% of its equipment domestically—above the more than 50% level at its third fab, Reuters reported. The plant is intended to produce advanced NAND with more than 300 layers for data-center and AI storage, though YMTC would still rely on overseas suppliers for advanced lithography and inspection tools. The report also says YMTC&\#x27;s China NAND market share has risen to 38.5%, overtaking Samsung, and that its total capacity could double once three new fabs are fully operational.

telegram · zaihuapd · Nov 6, 08:34

**「Context」** YMTC is China’s largest NAND flash manufacturer, and U.S. export controls have limited its access to advanced chipmaking equipment, pushing it toward domestic suppliers. Its third Wuhan fab already sources more than 50% of its equipment domestically, establishing the baseline that the planned fourth fab would raise to 60–70%.

**「Impact」** The 60–70% target would expand domestic orders, particularly in cleaning, polishing, and etching equipment, while leaving advanced lithography and inspection dependent on overseas suppliers—a limit on how far the new fab can be localized.

**Tags**: `#YMTC`, `#NAND flash`, `#semiconductor supply chain`, `#China chip industry`, `#export controls`

---

<a id="item-tech-news-8"></a>
### [Taobao MNN open-sources 0.3B on-device model for offline mobile inference](https://www.ithome.com/1/023/212.htm) ⭐️ 7.0/10

Taobao&\#x27;s MNN team has open-sourced MNN-Pocket-0.3B, an approximately 300-million-parameter model intended for fully offline mobile inference. The team reports about 350 tokens/s decoding on an iPhone 18 Pro, a 173 MB INT4 deployment file, a 28-layer architecture, and a vocabulary reduced from 151K to 64K tokens. It released separate versions for pretraining, post-training, and on-device deployment, with stated targets of under 300 MB peak memory and more than 200 tokens/s decoding. The speed and memory figures are vendor-reported and have not been independently verified.

telegram · zaihuapd · Nov 6, 15:13

**「Background」** MNN is the Taobao team&\#x27;s mobile inference engine, and the Pocket model is designed to run natively inside phone apps rather than through a cloud service. The team says it co-designed the model&\#x27;s architecture, vocabulary, training, and inference engine to balance task ability with speed and low resource use at 0.3B parameters.

**「Impact」** Developers can test the 173 MB INT4 build and the separate training and deployment variants in their own mobile apps, but should treat the iPhone 18 Pro throughput as a best-case vendor result until it is reproduced on their target hardware.

<details><summary>References</summary>
<ul>
<li><a href="https://tool.lu/article/88c/detail">淘 宝 MNN 团队 开 源 0 . 3 B 手机 模 型 ，iPhone 18 Pro上离线跑出350 token/s</a></li>

</ul>
</details>

**Tags**: `#on-device AI`, `#small language models`, `#MNN`, `#open source`, `#mobile inference`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [One Designer per Team, and the Trouble with Design Systems](https://seangoedecke.com/working-with-designers/) ⭐️ 7.0/10

rss · Sean Goedecke · Nov 7, 00:00

**「Background」** Sean Goedecke argues that designers offer value engineers cannot easily replicate, but that team composition and design systems introduce persistent friction.

**「Solution」** He contends that one designer per team works best: on a product with three designers, a full redesign forced a frontend rewrite, and the designers then reversed each other&\#x27;s changes page by page until management froze the design near the deadline. He theorizes that engineering disputes can rely on concrete measures such as latency and bugs, while design disputes rest on taste, and that design changes affect the whole product because users experience it as one design. Design systems help scale consistency, but he describes an incentive conflict between system owners who want elegant components and product teams that need awkward customer requirements, which pushes engineers to fork components or patch CSS. Compatibility adds another problem: a React design system may not match a pure HTML/CSS frontend or an older React version, forcing reimplementation or mental translation between the designer&\#x27;s view and the available components. He still considers design systems better than the alternatives, and notes that some teams, such as APIs, billing, and rendering, have little need for visual design, while poorly designed products can still succeed commercially.

**「Takeaway」** Goedecke&\#x27;s larger point is that design is valuable but difficult to scale: one designer plus a design system is a pragmatic arrangement, even though the system often makes immediate engineering work harder.

**Tags**: `#design systems`, `#cross-functional collaboration`, `#frontend engineering`, `#engineering culture`, `#product development`

---

## Financial News

<a id="item-finance-news-1"></a>
### [CoreWeave 2032 bond yield tops 16% as AI credit stress rises](https://www.cnbc.com/2026/11/06/coreweave-bond-yield-tops-16percent-as-ai-credit-stress-rises.html) ⭐️ 8.0/10

The yield on CoreWeave’s 2032 bond, which carries a 9.625% coupon, has climbed above 16%, CNBC reported, as credit markets demand more compensation for AI data-center debt.

rss · CNBC Finance · Nov 6, 17:09

**「Background」** CoreWeave is a US cloud-computing company that operates AI-focused data centers rented out for GPU-intensive workloads, part of a group of smaller providers known as &quot;neoclouds&quot; whose borrowing is tied to AI capacity buildouts. The credit default swaps cited in the article are insurance-like contracts that pay out if a borrower defaults, so a wider spread means investors are charging more to cover that risk.

**「Impact」** The rise raises borrowing costs for CoreWeave and other AI data-center developers, making debt-funded expansion more expensive.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/CoreWeave">CoreWeave - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#AI infrastructure`, `#credit markets`, `#CoreWeave`, `#data centers`, `#corporate debt`

---

<a id="item-finance-news-2"></a>
### [Nasdaq closes in correction after sharp selloff](https://www.cnbc.com/2026/11/05/nasdaq-drops-into-correction-territory-heres-what-typically-happens-next.html) ⭐️ 8.0/10

The Nasdaq Composite fell more than 5% on Thursday and closed more than 11% below its record, putting the tech-heavy index in correction territory. CNBC reported the selloff came as investors weighed election-driven data-center policy risks after Democrats swept the House and Senate.

rss · CNBC Finance · Nov 6, 20:42

**「Background」** Gina Hinojosa, Texas&\#x27;s newly elected Democratic governor, campaigned on pausing new data center development until the state legislature passes protections for communities, so investors are weighing whether such state-level limits would slow the AI-related construction the chip stocks depend on.

**「Who feels it」** Companies tied to the AI buildout, including data-center developers and chipmakers, face pressure as investors assess whether tighter state-level restrictions could slow construction \(tool-2-3\).

<details><summary>References</summary>
<ul>
<li><a href="https://www.texastribune.org/2026/11/04/data-center-texas-pause-gina-hinojosa-governor-policies/">Under Hinojosa, Texas data center approvals could stay paused</a></li>
<li><a href="https://www.usatoday.com/story/news/2026/11/06/hinojosa-texas-data-centers-pause-what-to-know/92641237007/">Texas Governor-elect Hinojosa calls for data center pause</a></li>
<li><a href="https://www.businessinsider.com/blue-wave-data-center-slowdown-impact-on-ai-trade-2026-11">Blue Wave Sparks Fear of Data Center Slowdown, Hit to AI ...</a></li>

</ul>
</details>

**Tags**: `#Nasdaq`, `#market correction`, `#semiconductors`, `#US midterm elections`, `#data centers`

---

<a id="item-finance-news-3"></a>
### [Premarket Movers: Moderna and Lam Research Rise, DraftKings Falls](https://www.cnbc.com/2026/11/06/stocks-making-the-biggest-moves-premarket-moderna-airbnb-cloudflare-affirm-more.html) ⭐️ 7.0/10

CNBC’s premarket movers roundup highlighted sharp company-specific reactions to earnings and guidance: Moderna rose nearly 10% after raising its 2026 revenue growth guidance to 15%–25%, from no more than 10%, and Lam Research gained nearly 11% after authorizing a $25 billion buyback. On the downside, DraftKings fell more than 20% after reporting a third-quarter loss of 94 cents a share, wider than the 39-cent loss analysts expected.

rss · CNBC Finance · Nov 6, 13:05

**「Background」** Several of the premarket moves followed a sharp selloff in AI-linked shares the previous day over worries that data-center expansion could be constrained; analysts estimate AI data centers could absorb about 70% of high-end memory chips \(DRAM\) in 2026, a sharp reversal from earlier cycles. Five9&\#x27;s $325 million purchase of Level AI was announced alongside its third-quarter results on Nov. 5.

<details><summary>References</summary>
<ul>
<li><a href="https://www.avnet.com/integrated/resources/article/2026-memory-shortage-ai-supercycle/">Riding the AI Supercycle: Navigating the 2026 Memory ...</a></li>
<li><a href="https://www.five9.com/news/news-releases/five9-acquire-level-ai-advancing-ai-powered-cx-platform">Five9 to Acquire Level AI, Advancing AI-Powered CX Platform</a></li>
<li><a href="https://www.sidley.com/en/newslanding/newsannouncements/2026/11/sidley-represents-five9-in-its-us-325-million-acquisition-of-level-ai">Sidley Represents Five9 in Its US$325 Million Acquisition of ...</a></li>

</ul>
</details>

**Tags**: `#premarket movers`, `#earnings`, `#guidance`, `#stock buybacks`, `#AI stocks`

---

<a id="item-finance-news-4"></a>
### [🤖 Anthropic 拟下周启动 IPO 路演，计划 11 月 16 日当周挂牌](https://www.theinformation.com/briefings/anthropic-proceed-ipo-roadshow-next-week) ⭐️ 7.0/10

知情人士称Anthropic计划下周启动IPO路演、11月16日当周挂牌，市场此前预期其估值约1.5万亿美元并募资超800亿美元，但AI股担忧可能压低估值。

telegram · zaihuapd · Nov 7, 01:27

**Tags**: `#Anthropic`, `#IPO`, `#AI`, `#科技股`, `#估值`

---