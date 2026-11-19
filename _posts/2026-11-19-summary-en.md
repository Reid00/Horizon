---
layout: default
title: "Horizon Summary: 2026-11-19 (EN)"
date: 2026-11-19
lang: en
---

> From 44 items, 14 important content pieces were selected

---

**Technology News**
1. [Google releases Gemini 4 Neon with 1M-token context](#item-tech-news-1) ⭐️ 9.0/10
2. [Wiz reports unauthenticated RCE in Nginx HTTP/2](#item-tech-news-2) ⭐️ 8.0/10
3. [Xint discloses five nginx flaws chaining to host root](#item-tech-news-3) ⭐️ 8.0/10
4. [Google DeepMind says Genie 4 is available](#item-tech-news-4) ⭐️ 7.0/10
5. [Energy-Based Reasoners Claim 385x More Efficient Inference](#item-tech-news-5) ⭐️ 7.0/10
6. [Microsoft announces seven AI models at scalable price-performance](#item-tech-news-6) ⭐️ 7.0/10
7. [A Retrospective on Intel’s Early CPUs, From 4004 to 486](#item-tech-news-7) ⭐️ 7.0/10
8. [Analysis: DNS blocking is the wrong piracy tool after Quad9 France exit](#item-tech-news-8) ⭐️ 7.0/10
9. [Show HN: Interactive Voyager 1 tour reaches a single memory chip](#item-tech-news-9) ⭐️ 7.0/10
10. [Stenberg: AI Rust rewrites lag curl&\#x27;s 200+ bugfixes](#item-tech-news-10) ⭐️ 7.0/10

**Financial News**
1. [Fed minutes signal more rate hikes and AI inflation risk](#item-finance-news-1) ⭐️ 8.0/10
2. [Fed’s Waller calls for possible half-point December rate hike](#item-finance-news-2) ⭐️ 8.0/10
3. [Tencent Q3 2026: capex jumps, free cash flow negative](#item-finance-news-3) ⭐️ 7.0/10
4. [China and South Korea announce substantive conclusion of FTA services and investment talks](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Google releases Gemini 4 Neon with 1M-token context](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) ⭐️ 9.0/10

Google has released Gemini 4 Neon, a model aimed at complex software engineering, knowledge work, and research workflows, according to a single-source report, and made it available to developers, enterprises, and Google AI Pro/Ultra subscribers. It supports a 1M-token context and is priced at $3 per million input tokens, $0.15 per million cached input tokens, and $15 per million output tokens. Google&\#x27;s reported benchmark claims put Neon first on Artificial Analysis&\#x27;s coding-agent index at 58.6, third overall on its intelligence index at the xhigh setting with 61, and at 65.2% on Terminal-Bench 4.1, with a 32% lower per-task cost than Carbon at the default high setting; these figures have not been independently verified here.

telegram · zaihuapd · Nov 19, 02:00

**「Background」** A YouTube overview describes Gemini 4 Neon as the fourth Gemini 4 model released in seven weeks, positioned between Carbon and Hydrogen in Google&\#x27;s lineup. That places Neon within an already expanding Gemini 4 family rather than as a standalone first release.

**「Cost and model-choice implications」** For teams running coding agents through the API, Google says a task at Neon&\#x27;s default &quot;high&quot; setting costs 32% less than on Gemini 4 Carbon, priced at $3 per million input tokens \($0.15 cached\) and $15 per million output tokens. The trade-off is not a clean upgrade: one commenter notes that on the Artificial Analysis index Carbon still outscores Neon on evaluations such as CritPt, which test research-scale reasoning, so users doing long-horizon research work may want to keep Carbon in their routing rather than switch wholesale.

**「Community discussion」** Commenters on Hacker News focused on model-name confusion across Google, Anthropic, and OpenAI, and one user argued that Gemini models still feel less capable than Opus 5.5 in general use despite benchmark results. Another commenter noted that Carbon remains positioned as the long-horizon model even though Neon scores higher overall, and a third reported Neon running at 127 tokens per second on OpenRouter versus 46 for Carbon.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=a0xbwYt6-qQ">Gemini 4 Neon IS HERE! Everything You Need to Know! - YouTube</a></li>
<li>AI Coding Agent Benchmarks &amp; Leaderboard - Artificial Analysis</li>
<li>Introducing Gemini 4 Neon - Google Blog</li>

</ul>
</details>

**Tags**: `#Google Gemini`, `#AI models`, `#coding agents`, `#benchmarks`, `#API pricing`

---

<a id="item-tech-news-2"></a>
### [Wiz reports unauthenticated RCE in Nginx HTTP/2](https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities) ⭐️ 8.0/10

Wiz reports unauthenticated remote code execution vulnerabilities in Nginx&\#x27;s HTTP/2 implementation, tracked as CVE-2026-123633 and CVE-2026-123007. The source does not specify affected Nginx versions, patched releases, or exploit prerequisites. Community commenters note that HTTP/2 is not enabled by default in Nginx and that one reported exploit path requires very high HTTP/2 traffic and specific CPU instructions.

hackernews · speedping · Nov 18, 15:19 · [Discussion](https://news.ycombinator.com/item?id=50547374)

**「Prerequisite context」** HTTP/2 in Nginx is not enabled by default; it must be turned on explicitly for a server, so whether a deployment is exposed to the flaws in CVE-2026-123633 and CVE-2026-123007 depends on that configuration choice. The report identifies the two issues by those CVE records.

**「Exposure and remediation」** CVE-2026-123007 affects a broader range of HTTP/2 deployments, while CVE-2026-123633 is narrower and requires specific reverse-proxy and resource-management conditions. A summary of the flaws says servers running versions below 1.31.9 \(mainline\) or 1.30.7 \(stable\) with HTTP/2 enabled are affected, so operators should upgrade to those fixed releases or disable HTTP/2 as a workaround; servers that do not enable HTTP/2 are outside this attack path.

**「Community discussion」** Commenters criticized the disclosure timing, saying the fix appeared in the open-source repository about a week before the advisory and that a public warning could have been issued because disabling HTTP/2 is a simple workaround. Others argued the issue is limited in practice because HTTP/2 is not enabled by default and the exploit reportedly requires 128 Gb of traffic and specific CPU instructions.

<details><summary>References</summary>
<ul>
<li>NGINX HTTP/2 RCE: Two Critical Flaws Turn Protocol Handling into Remote Code Execution - Safe Security</li>
<li>Nginx2Shell: All You Need to Know About CVE-2026-123007 and CVE-2026-123633</li>

</ul>
</details>

**Tags**: `#nginx`, `#security`, `#http2`, `#remote code execution`, `#vulnerability`

---

<a id="item-tech-news-3"></a>
### [Xint discloses five nginx flaws chaining to host root](https://nginx2root.com/) ⭐️ 8.0/10

Xint has disclosed NGINX2Root, a chain of five nginx vulnerabilities plus a Linux kernel flaw that it says can take an nginx visitor to host root. The central issue, CVE-2026-123007, is described as an HTTP/2 flow-control memory-corruption bug that allows unauthenticated command execution in an nginx worker. nginx 1.30.7 and 1.31.9 fix 10 CVEs, with the disclosure dated November 18; Rapid7 has published a proof-of-concept, and Xint reports no in-the-wild exploitation. These are the disclosure&\#x27;s claims and have not been independently verified in the supplied material.

telegram · zaihuapd · Nov 18, 16:21

**「Background」** The chain centers on CVE-2026-123007, which Rapid7 describes as an HTTP/2 integer underflow that can be exploited for unauthenticated remote code execution against a vulnerable nginx 1.31.8 linux/amd64 Docker image; Rapid7 also published PoC scripts. For administrators who cannot upgrade, Red Hat notes that HTTP/2 can be disabled by removing the \`http2\` parameter from \`listen\` directives and setting \`http2 off;\` on nginx 1.25 and later.

**「Impact」** Administrators who cannot move to nginx 1.30.7 or 1.31.9 should disable HTTP/2 on externally reachable endpoints, as the disclosure recommends, because the unauthenticated worker-level execution is the entry point for the chain to host root.

<details><summary>References</summary>
<ul>
<li><a href="https://www.rapid7.com/blog/post/ve-cve-2026-123007-critical-nginx-http-2-integer-underflow-leads-to-rce-fixed/">Rapid7 discloses a critical vulnerability affecting NGINX ...</a></li>
<li><a href="https://github.com/sfewer-r7/CVE-2026-123007">GitHub - sfewer-r7/CVE-2026-123007: Proof-of-concept (PoC ...</a></li>
<li><a href="https://access.redhat.com/security/cve/cve-2026-123007">CVE-2026-123007 - Red Hat Customer Portal</a></li>

</ul>
</details>

**Tags**: `#nginx`, `#HTTP/2`, `#vulnerability disclosure`, `#remote code execution`, `#Linux kernel`

---

<a id="item-tech-news-4"></a>
### [Google DeepMind says Genie 4 is available](https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/) ⭐️ 7.0/10

Google DeepMind announced that Genie 4, the next version of its Project Genie generative world-model work, is now available. The supplied announcement provides no technical details, benchmarks, or specific capability claims, so the release&\#x27;s actual features and limits cannot be verified from the available material. Hacker News discussion focused less on demonstrated capabilities than on who can access the product and whether such models could eventually serve as game engines.

hackernews · leumon · Nov 18, 18:49 · [Discussion](https://news.ycombinator.com/item?id=50550415)

**「Background」** Genie is Google DeepMind&\#x27;s generative world-model line: systems intended to produce interactive environments rather than only static images or video. The item announces Genie 4 as available, but the supplied material contains no technical details, benchmarks, or source content, so its concrete capabilities and access terms cannot be verified here.

**「Access and production readiness」** Developers considering Genie 4 as a game-engine component should treat it as an experimental research preview, not a production dependency: TechCrunch reports the release adds audio, more realistic worlds, and real-time steering, with Gemini planning steps and checking frames while Genie generates visuals. Access also remains gated, and a commenter reports that their Workspace account cannot obtain the required Google AI Ultra subscription and that UK availability is unclear, so teams should verify account and regional eligibility before planning work around it.

**「Community discussion」** Commenters reported confusion over access: one said the page limits Genie 4 to &quot;Eligible Google AI Ultra subscribers,&quot; while their Workspace account could not subscribe and their personal account showed Ultra including Genie 3, leaving UK availability unclear. Others speculated about future use as a game engine—one wondered whether Google would permit recreations such as GTA—while another argued the thread focused too much on pricing and capability and too little on potential negative consequences.

<details><summary>References</summary>
<ul>
<li><a href="https://techcrunch.com/2026/10/27/googles-genie-4-world-model-adds-audio-more-realistic-worlds-and-real-time-steering/">Google ’s Genie 4 world model adds audio, more... | TechCrunch</a></li>

</ul>
</details>

**Tags**: `#world models`, `#generative AI`, `#Google DeepMind`, `#game engines`, `#product launch`

---

<a id="item-tech-news-5"></a>
### [Energy-Based Reasoners Claim 385x More Efficient Inference](https://energy-based-reasoners.github.io/) ⭐️ 7.0/10

A project page for Energy-Based Reasoners claims 385x more efficient inference, but the supplied material contains no source details and no independent verification of that figure. The page presents energy-based models as an alternative approach for reasoning tasks. Hacker News commenters focused on whether the method can scale beyond narrow logic puzzles and on how the term &quot;energy&quot; is defined. The 385x number should be treated as a project claim, not a measured result.

hackernews · frenchmajesty · Nov 18, 09:29 · [Discussion](https://news.ycombinator.com/item?id=50543989)

**「Background」** Energy-based models assign a scalar energy to candidate predictions and reason by searching for low-energy solutions, an alternative to the token-by-token generation used by LLMs. The approach has recently moved into commercial products: Logical Intelligence released Kona 1.0 in January 2026, described as the first commercial energy-based reasoning model, with Yann LeCun as founding chair of its technical research board.

**「Community Discussion」** Commenters were skeptical: one described energy-based models as impressive validators but &quot;insanely hard to train&quot; and very niche-specific, while another said the approach works well for a specific logic-puzzle problem set and questioned scalability. A separate comment asked what codomain the learned scalar &quot;energy&quot; function has, suggesting the page does not clearly define the term.

<details><summary>References</summary>
<ul>
<li><a href="https://paperlens.io/idea/kona-1/">Kona 1: Energy-Based Reasoning | PaperLens</a></li>
<li><a href="https://www.businesswire.com/news/home/20260120751310/en/Logical-Intelligence-Introduces-First-Energy-Based-Reasoning-AI-Model-Signals-Early-Steps-Toward-AGI-Adds-Yann-LeCun-and-Patrick-Hillmann-to-Leadership">Logical Intelligence Introduces First Energy-Based Reasoning ...</a></li>

</ul>
</details>

**Tags**: `#energy-based models`, `#inference efficiency`, `#AI reasoning`, `#machine learning`

---

<a id="item-tech-news-6"></a>
### [Microsoft announces seven AI models at scalable price-performance](https://microsoft.ai/news/microsoft-ignite-2026/) ⭐️ 7.0/10

Microsoft announced seven new AI models, according to a Microsoft Ignite 2026 news page, with the release framed around scalable price-performance. The supplied item provides no model names beyond MAI Code 2, which appears only in comments, and no benchmarks, pricing, availability, or licensing terms, so the scope and comparative claims cannot be verified. The announcement drew Hacker News discussion focused on competitiveness and openness rather than published technical details.

hackernews · gmays · Nov 18, 16:08 · [Discussion](https://news.ycombinator.com/item?id=50548021)

**「Background」** Microsoft used its Ignite 2026 conference to pitch task-specific models rather than one general-purpose system, with coverage for coding, vulnerability discovery, and image generation. Microsoft&\#x27;s announcement names MAI Cyber 2 Flash and claims it beats GPT-6 Astra&\#x27;s quality at less than 2% of the cost per task on the CyberGymE 2 E benchmark, while Yahoo Finance characterizes the broader message as cheaper AI for enterprises. Those cost and quality comparisons are Microsoft&\#x27;s claims, not independently verified results in the supplied material.

**「Cost pressure on coding-model buyers」** Microsoft is pitching the new models squarely at teams choosing a coding assistant, claiming MAI Code 2 delivers 98% of GPT-6.1 Sol&\#x27;s performance at 40% of the cost and 96% of Claude Opus 5.5&\#x27;s at just 5% of the cost. Those are Microsoft&\#x27;s own figures rather than independent benchmarks, so organizations weighing a switch should validate them on their own workloads before treating the advertised cost gap as a like-for-like saving.

**「Community discussion」** A commenter who tested MAI Code 2 called it “quite good” for their usual work and said they would not argue much with a comparison to Opus or Sol, while another argued Microsoft should offer some models as open source or open-weight to secure market share, warning it could be “Windows Phone OS all over again.” Other comments addressed AI pricing and labor concerns rather than the new models’ technical details.

<details><summary>References</summary>
<ul>
<li><a href="https://microsoft.ai/news/microsoft-ignite-2026/">Seven new world class models at scalable ... | Microsoft AI</a></li>
<li><a href="https://forklog.com/en/microsoft-unveils-ai-models-for-coding-and-cybersecurity/">Microsoft unveils AI models for coding and cybersecurity | ForkLog</a></li>
<li><a href="https://finance.yahoo.com/markets/article/microsoft-ignite-focuses-on-ai-models-for-specific-tasks-lowering-costs-for-enterprise-203433266.html">Microsoft &#x27;s AI pitch at Ignite : Cheaper models as business &#x27;token...</a></li>
<li>MAI Code 2 and Code 2 Flash: Everyday coding at scalable prices | Microsoft AI</li>
<li>Microsoft AI on X: &quot;MAI Code 2 gives you 98% of GPT-6.1 Sol&#x27;s performance at 40% of the cost, and 96% of Claude Opus 5.5&#x27;s at just 5% of the cost. https://t.co/jDy0sd6KhI&quot; / X</li>

</ul>
</details>

**Tags**: `#Microsoft`, `#AI models`, `#LLM pricing`, `#model release`, `#AI industry`

---

<a id="item-tech-news-7"></a>
### [A Retrospective on Intel’s Early CPUs, From 4004 to 486](https://pikuma.com/blog/history-of-x86-4004-to-486) ⭐️ 7.0/10

A pikuma.com article dated 18 November 2026 presents a detailed historical overview of Intel’s early CPU line from the 4004 through the 486, aimed at readers interested in microprocessor architecture and computing history. It is a retrospective explainer rather than an announcement of a new chip, version, or capability. The supplied Hacker News comments add technical corrections and context about early design choices, including the origin of little-endian byte order and the 8008’s instruction set.

hackernews · ibobev · Nov 18, 14:47 · [Discussion](https://news.ycombinator.com/item?id=50546967)

**「Background」** The x86 line is named after the 8086, the 16-bit microprocessor Intel introduced in 1978 with about 29,000 transistors and clock speeds of 5–10 MHz. Intel designed it to deliver roughly an order of magnitude more throughput than the 8080, and its instruction set became the base that later x86 chips extended. The 8080 itself had arrived in April 1974 as the 8008&\#x27;s successor but was not binary compatible with it, a break that contrasts with the continuity the 8086 family became known for.

**「Community discussion」** Hacker News commenters disputed or refined several technical points: one argued that little-endian ordering originally sped data access on the 2200 rather than serving arithmetic, another said Intel engineers did modify the 8008 instruction set, and a third stressed that the 4004 and 8008 are otherwise unrelated beyond shared personnel. These are commenter claims and opinions, not independently verified in the supplied material.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Intel_8080">Intel 8080 - Wikipedia</a></li>
<li><a href="https://stevemorse.org/8086history/8086history.pdf">Intel Microprocessors: 8008 to 8086</a></li>
<li><a href="https://www.auslogics.com/en/articles/intel-processor-generations-in-a-timeline-history-and-evolution/">Intel Processor Generations in a Timeline: History ... — Auslogics Blog</a></li>

</ul>
</details>

**Tags**: `#x86`, `#CPU history`, `#computer architecture`, `#Intel`, `#retrocomputing`

---

<a id="item-tech-news-8"></a>
### [Analysis: DNS blocking is the wrong piracy tool after Quad9 France exit](https://techstackups.com/articles/quad9-leaves-france-dns-blocking/) ⭐️ 7.0/10

An analysis tied to Quad9&\#x27;s departure from France argues that DNS resolvers are an inappropriate enforcement point for copyright piracy blocking. It frames DNS-level blocking as a censorship measure that pushes enforcement onto neutral infrastructure providers rather than targeting pirates directly. The supplied item does not include the article body, so the precise French legal basis, court order, and Quad9 operational timeline are not established here.

hackernews · ritzaco · Nov 18, 13:18 · [Discussion](https://news.ycombinator.com/item?id=50545958)

**「Background」** Quad9 is a global public recursive DNS resolver that blocks access to domains associated with malware and phishing. In this dispute, a French court sided with beIN Sports and ordered DNS blocking; rather than comply, Quad9 said it would stop serving users in France on November 24, 2026.

**「Impact」** The case puts a concrete choice to DNS operators: comply with piracy-blocking orders or exit a market, while users in the affected jurisdiction lose that resolver option. For other public resolvers, Quad9&\#x27;s departure illustrates how neutral DNS service can become a compliance chokepoint.

**「Community discussion」** Commenters disagree over both blame and remedy: one calls non-prosecution anti-piracy measures a backdoor to speech suppression, another argues better legal access would reduce piracy, and a third asks whether the French court or the legislature is responsible. A separate complaint says enforcement is inconsistent because commercial AI copying of copyrighted works goes unprosecuted while individual piracy is targeted.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Quad9">Quad 9 - Wikipedia</a></li>
<li><a href="https://techstackups.com/articles/quad9-leaves-france-dns-blocking/">Quad 9 Is Leaving France : Why DNS Resolvers Are... | Tech Stackups</a></li>
<li><a href="https://www.techpassion.net/internet/quad9-leaves-france-dns-blocking/2169/">Quad 9 leaves France : DNS blocking order explained - TechPassion</a></li>

</ul>
</details>

**Tags**: `#DNS resolvers`, `#internet censorship`, `#privacy`, `#copyright enforcement`, `#internet governance`

---

<a id="item-tech-news-9"></a>
### [Show HN: Interactive Voyager 1 tour reaches a single memory chip](https://rshekhar.com/voyager/) ⭐️ 7.0/10

Raj Shekhar published an interactive Show HN site that lets visitors explore Voyager 1&\#x27;s hardware and mission systems, from its nuclear battery&\#x27;s 24 plutonium spheres to the data computer&\#x27;s individual memory chips. The site also shows the Golden Record cover, how Voyager 1 was repaired by radio, and which Earth dish is listening live; the post states that Voyager 1 reached one light-day from Earth that day. It is an educational visualization rather than a new mission update, and the author also links a four-minute film.

hackernews · raj-shekhar · Nov 18, 16:18 · [Discussion](https://news.ycombinator.com/item?id=50548161)

**「Background」** Voyager 1 launched in 1977 and became the first human-made spacecraft to enter interstellar space in 2012. On November 18, 2026, it crossed one light-day from Earth at 5:16:07 a.m. EST, the milestone the Show HN explorer was released to mark.

**「Impact」** For educators and space-hardware enthusiasts, the site offers a directly navigable model of Voyager 1&\#x27;s subsystems, including author-supplied deep links to the nuclear battery, the data computer&\#x27;s memory, and a single bit of the command computer&\#x27;s memory. The author notes that some sections are hard to find without those links, making the direct URLs the practical entry point.

**「Community Discussion」** Commenters praised the visualization and shared related Golden Record projects, while one asked what analog failure mode could make a CMOS memory IC consistently misread stored values and another asked whether the site was “vibecoded” and checked against authoritative sources. The author acknowledged that some sections are hard to find and posted direct links.

<details><summary>References</summary>
<ul>
<li><a href="https://svs.gsfc.nasa.gov/15120">How Far Away Is Voyager 1? One Light-Day, Explained</a></li>
<li><a href="https://spaceflightnow.com/2026/11/18/nasas-voyager-1-is-one-light-day-from-earth/">NASA’s Voyager 1 is one light-day from Earth — Spaceflight Now</a></li>

</ul>
</details>

**Tags**: `#Voyager 1`, `#interactive visualization`, `#computer hardware`, `#space technology`, `#explorable explanation`

---

<a id="item-tech-news-10"></a>
### [Stenberg: AI Rust rewrites lag curl&\#x27;s 200+ bugfixes](https://simonwillison.net/2026/Nov/18/daniel-stenberg/) ⭐️ 7.0/10

Daniel Stenberg said AI coding agents converted 185,000 lines of curl&\#x27;s C code into 340,000 lines of Rust over a little more than three weeks. During the same period, he said, the actual curl project merged more than 300 commits, including over 200 bugfixes and several vulnerability fixes that the Rust rewrites do not have. He asked whether the clones can keep up as curl continues to change.

rss · Simon Willison · Nov 18, 15:58

**「Background」** AI coding agents have been used to convert large C codebases into Rust, and curl became one target of that practice. Stenberg&\#x27;s post treats the resulting Rust versions as separate clones, which is why he compares them with the official project&\#x27;s continuing commits, bug fixes, and security fixes.

**「Impact」** For developers evaluating an AI-generated Rust port, code volume is not the key measure: the port would need a process for tracking upstream curl&\#x27;s ongoing bug and security fixes, since Stenberg says the rewrites started without the 200-plus fixes landed during the conversion period.

<details><summary>References</summary>
<ul>
<li><a href="https://daniel.haxx.se/blog/2026/11/17/actual-curl-rewrites-in-rust/">Actual curl rewrites in rust | daniel .haxx.se</a></li>

</ul>
</details>

**Tags**: `#curl`, `#Rust`, `#AI coding agents`, `#open source maintenance`, `#software security`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed minutes signal more rate hikes and AI inflation risk](https://www.cnbc.com/2026/11/18/fed-minutes-october-2026.html) ⭐️ 8.0/10

Minutes of the Federal Reserve&\#x27;s October meeting released Wednesday showed almost all participants judged further increases in the federal funds rate would likely be appropriate to return inflation to the 2% target, even as the committee voted 10-2 to hold the benchmark range at 3.75%-4%. The minutes also said AI-related demand was a &quot;material source of inflation risk&quot; and flagged rapid growth in complex, opaque AI-related debt as a financial-stability concern.

rss · CNBC Finance · Nov 18, 19:41

**「Background」** The federal funds rate is the benchmark for overnight borrowing that the Fed uses to steer inflation toward its 2% target; since the October meeting, October CPI rose 0.4% for all items and 0.3% for core prices excluding food and energy, each 0.1 percentage point above expectations.

**「Impact」** Futures traders are fully pricing a quarter-point increase at the Dec. 8-9 meeting, with low odds of a half-point move, and see a solid likelihood of two more increases in 2027, according to CME Group&\#x27;s FedWatch.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#interest rates`, `#AI financial risk`

---

<a id="item-finance-news-2"></a>
### [Fed’s Waller calls for possible half-point December rate hike](https://www.cnbc.com/2026/11/18/federal-reserve-governor-christopher-waller.html) ⭐️ 8.0/10

Federal Reserve Governor Christopher Waller said the central bank may need a half-percentage-point rate hike at its Dec. 8-9 meeting to “shock people” and fight inflation, a larger move than the quarter-point increase futures markets fully price in.

rss · CNBC Finance · Nov 18, 15:13

**「Background」** The Fed cut rates three times in 2025, then raised them in September 2026 and held steady in October, with inflation still above its 2% target.

**「Impact」** If adopted, a half-point hike would raise borrowing costs faster for households and businesses with variable-rate loans tied to the benchmark rate than the quarter-point move markets expect.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#Christopher Waller`

---

<a id="item-finance-news-3"></a>
### [Tencent Q3 2026: capex jumps, free cash flow negative](https://api3.cls.cn/share/article/2537922?os=android&amp;amp;sv=8.8.5&amp;amp;app=cailianpress&amp;amp;selected=) ⭐️ 7.0/10

Tencent reported 2026 third-quarter revenue of 207.3 billion yuan, up 8% year on year and below market expectations, with net profit attributable to shareholders up 0.8% to 63.6 billion yuan. Capital expenditure was 81.43 billion yuan, far above the 55.4 billion yuan market estimate, quarterly free cash flow was negative 69.1 billion yuan, and Tencent said its WorkBuddy app had the highest daily token usage among Chinese large-language-model products at more than 100 trillion tokens a day.

telegram · zaihuapd · Nov 18, 09:20

**「Background」** Tencent had reported positive free cash flow of 56.7 billion yuan in the first quarter of 2026, a contrast with the negative cash flow in the latest quarter as AI infrastructure spending rose; its WorkBuddy AI assistant, launched in March, had more than 10 million daily active users by early November, according to company figures.

<details><summary>References</summary>
<ul>
<li>[PDF] TENCENT ANNOUNCES 2026 FIRST QUARTER RESULTS - Significant Progress in Hy Capabilities and Productivity AI Agents Utilising AI to Grow Existing Core Businesses</li>
<li><a href="https://www.kucoin.com/news/flash/tencent-workbuddy-hits-10m-daily-active-users-100-trillion-daily-token-usage">Tencent WorkBuddy reaches 10 million daily active ... - KuCoin</a></li>
<li><a href="https://www.gamersky.com/news/202611/2249061.shtml">腾讯WorkBuddy成中国使用量最高AI产品 日均Token消耗量超百万亿 _ 游...</a></li>

</ul>
</details>

**Tags**: `#Tencent earnings`, `#AI capex`, `#free cash flow`, `#China tech`, `#AI token usage`

---

<a id="item-finance-news-4"></a>
### [China and South Korea announce substantive conclusion of FTA services and investment talks](https://x.com/Jaemyung_Lee/status/2122988472994791476) ⭐️ 7.0/10

China and South Korea said on November 18 that follow-up negotiations on services and investment under their free trade agreement had reached a substantive conclusion. China committed to most-favored-nation treatment for South Korean film and gaming firms and to wider opening in tourism, legal, construction and finance; the parties also agreed to expand audiovisual co-production from films to TV dramas, animation, variety shows and documentaries, though some technical issues remain for working-level talks.

telegram · zaihuapd · Nov 18, 10:02

**「Background」** The original Korea-China FTA covering goods took effect in 2015, while the services-and-investment follow-up talks began in March 2018 and ran for more than eight years; the final text has not been released, so the declaration of a &quot;substantial conclusion&quot; represents broad agreement rather than a signed or ratified treaty.

**「Who is affected」** South Korean film, gaming, tourism, legal, construction and finance firms stand to gain wider access to China&\#x27;s market, and producers in both countries could co-produce TV dramas, animation, variety shows and documentaries as well as films — though the commitments are not yet a signed or ratified agreement.

<details><summary>References</summary>
<ul>
<li><a href="https://www.chosun.com/english/national-en/2026/11/19/NTPG5ZDJMBAKLH427BSO5LHJKU/">Korea-China FTA Service, Investment Negotiations ...</a></li>

</ul>
</details>

**Tags**: `#China-South Korea FTA`, `#services and investment`, `#trade policy`, `#audiovisual co-production`, `#market access`

---