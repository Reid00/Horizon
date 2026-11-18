---
layout: default
title: "Horizon Summary: 2026-11-18 (EN)"
date: 2026-11-18
lang: en
---

> From 43 items, 14 important content pieces were selected

---

**Technology News**
1. [Java4Shell: Reported OpenJDK Base64 RCE Affects Java 17, 21, 25, 27](#item-tech-news-1) ⭐️ 8.0/10
2. [OpenAI introduces GPT-6.2 Astra and Sol with lower Astra pricing](#item-tech-news-2) ⭐️ 8.0/10
3. [Solid 2.0 adds server RPC, live/broadcast, and better diagnostics](#item-tech-news-3) ⭐️ 8.0/10
4. [External sandbox pattern ships three servers for coding agents](#item-tech-news-4) ⭐️ 8.0/10
5. [Datasette Lite rewrite runs full Datasette in the browser](#item-tech-news-5) ⭐️ 8.0/10
6. [Microsoft ONNX Runtime GitHub repository reported unavailable](#item-tech-news-6) ⭐️ 7.0/10
7. [Quad9&\#x27;s France withdrawal spotlights DNS filtering fight](#item-tech-news-7) ⭐️ 7.0/10
8. [Nvidia halts Singapore sales disclosure as entity revenue hits $104B](#item-tech-news-8) ⭐️ 7.0/10
9. [Phrack Issue 73 Published With Docker Escape, SSH1 History](#item-tech-news-9) ⭐️ 7.0/10
10. [China&\#x27;s Q/V-band wireless test reaches 27 Gbps bidirectional](#item-tech-news-10) ⭐️ 7.0/10
11. [Telegram reportedly mandates Stars for bot and mini-app digital goods](#item-tech-news-11) ⭐️ 7.0/10

**Financial News**
1. [U.S. Tightens Remote-Access Chip Curbs as Tech Firms Weigh China Exposure](#item-finance-news-1) ⭐️ 7.0/10
2. [UK tribunal dismisses £1.97bn Sony PlayStation Store class action](#item-finance-news-2) ⭐️ 7.0/10
3. [China&\#x27;s auto association evaluates 17 automakers on 60-day supplier payment terms](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Java4Shell: Reported OpenJDK Base64 RCE Affects Java 17, 21, 25, 27](https://calif.io/java4shell/) ⭐️ 8.0/10

A reported unauthenticated remote code execution flaw in OpenJDK&\#x27;s Base64 processing, dubbed Java4Shell and tracked in the source as CVE-2026-114938, carries a CVSS 4.0 score of 9.2 and is said to affect Java 17.0.6 and later on the 17 line, plus Java 21, 25, and 27. The source says exploitation requires x86-64 processors with AVX-512 VBMI—roughly Intel Ice Lake-era Xeon and AMD Zen 4 or newer—while ARM64 and standard Java 8/11 are reported unaffected, except Oracle Java 8 Performance Pack. The source does not identify a fixed release.

hackernews · werrett · Nov 17, 21:11 · [Discussion](https://news.ycombinator.com/item?id=50538240)

**「Background」** Java4Shell is an out-of-bounds write in OpenJDK&\#x27;s optimized Base64 decoder, so practical exposure depends on whether an application feeds attacker-controlled Base64 data into that decoder. Calif&\#x27;s technical write-up says the flaw enabled pre-auth code execution in Jira, Confluence, Jenkins and Keycloak, while Datadog&\#x27;s analysis notes that denial of service is the more readily achievable impact and that reliable RCE requires additional exploitation tailored to the application and JVM.

**「Exposure and remediation」** The practical exposure is limited to x86-64 hosts with AVX-512 VBMI running affected JDK lines, so operators should inventory those systems and move to vendor-fixed builds; Oracle has shipped fixes for Java 17, 21, 25, and 27, and Amazon has released a fixed Corretto 17. Standard Java 8 and 11 deployments are generally not affected, but Oracle Java 8 Enterprise Performance Pack is an exception.

**「Community discussion」** Commenters focused on exploitability: one quoted the write-up&\#x27;s remote heap-grooming section, which says the attack is sensitive to RTT and jitter, while another said the conditions are specific but many hosts will still be affected and pointed to Semgrep detection scripts covering five conditions. A separate commenter relayed an unconfirmed suggestion that the bug lies in the AVX-512 Base64 decoder and that running with -XX:UseAVX=2 may avoid it.

<details><summary>References</summary>
<ul>
<li><a href="https://securitylabs.datadoghq.com/articles/java4shell-remote-code-execution-in-openjdk-cve-2026-114938/">Java4Shell: Remote Code Execution in OpenJDK (CVE-2026-114938)</a></li>
<li><a href="https://securityonline.info/java4shell-cve-2026-114938/">Java4Shell (CVE-2026-114938): Java SE RCE Explained</a></li>
<li><a href="https://www.cyberkendra.com/2026/11/cve-2026-114938-pre-auth-rce-flaw-in-java-17-puts-servers-at-risk.html">Java 4 Shell (CVE-2026-114938): Java Base 64 Flaw... - Cyber Kendra</a></li>
<li><a href="https://blog.qualys.com/vulnerabilities-threat-research/2026/11/17/how-to-find-mitigate-and-patch-the-critical-java4shell-flaw-cve-2026-114938-now">How to Find, Mitigate, and Patch the Critical Java 4 Shell Flaw... | Qualys</a></li>

</ul>
</details>

**Tags**: `#Java`, `#OpenJDK`, `#RCE`, `#security vulnerability`, `#Base64`

---

<a id="item-tech-news-2"></a>
### [OpenAI introduces GPT-6.2 Astra and Sol with lower Astra pricing](https://openai.com/index/introducing-gpt-6-2-astra-sol/) ⭐️ 8.0/10

OpenAI introduced GPT-6.2 Astra, a frontier model for hard projects, and GPT-6.2 Sol, an efficient model for everyday work, both available in the API as gpt-6.2-astra and gpt-6.2-sol; LLM 0.38 adds support. Astra costs $8 per million input tokens and $40 per million output tokens, 80% of GPT-6 Astra&\#x27;s $10/$50, with cached input at $0.40 per million versus $1. Sol remains at $2/$10, half GPT-5.6 Sol&\#x27;s $4/$20. Early reaction is mixed: Astra is not scoring as high as Claude Fable 5.2 on various benchmarks, and reviewers have flagged confusing communication during long tasks, even as commenters report lower costs and faster runs.

hackernews · jasondavies · Nov 17, 17:46 · [Discussion](https://news.ycombinator.com/item?id=50535230)

**「Earlier GPT-6 tiers」** OpenAI&\#x27;s GPT-6.x lineup separates Astra, a higher-priced frontier tier, from Sol, a cheaper everyday tier. GPT-6.2 Astra succeeds GPT-6 Astra, and GPT-6.2 Sol succeeds GPT-6.1 Sol, updating the two-tier structure and pricing established by those earlier releases.

**「Impact」** For API users, Astra&\#x27;s cached-input cut from $1 to $0.40 per million tokens makes long agentic sessions cheaper than with GPT-6 Astra, while Sol offers no price reduction over GPT-6.1 Sol. The models are reachable through the gpt-6.2-astra and gpt-6.2-sol IDs, with LLM 0.38 as one supported client.

**「Community discussion」** Commenters reported concrete cost and speed gains alongside quality concerns: one data-analytics exam fell from about $20 to $4 for Astra and $2.60 to $1.20 for Sol with similar accuracy, though in some cases it finished early and missed the answer, while another cited PacBench results in which Astra scored 92 for $2.04 versus Kimi K3.1 Pro&\#x27;s 93 for $0.68. Others criticized the office-document examples as poor and questioned how the models compare with competitors such as Opus 5.5.

**Tags**: `#OpenAI`, `#GPT-6.2`, `#LLM release`, `#model benchmarks`, `#cost efficiency`

---

<a id="item-tech-news-3"></a>
### [Solid 2.0 adds server RPC, live/broadcast, and better diagnostics](https://www.solidjs.com/blog/solid-2-0-the-long-hold/) ⭐️ 8.0/10

Solid 2.0, a new major release of the Solid JavaScript framework, introduces server-oriented features including server RPC and &quot;live&quot; and &quot;broadcast&quot; capabilities, plus improved debug diagnostics, according to the release post and Hacker News commenters. The post groups the diagnostics work under a &quot;Built to Be Written by Agents&quot; heading, though commenters argue the improvements are general debugging aids rather than agent-specific. The supplied material does not include release dates, migration notes, or independent performance measurements.

hackernews · pier25 · Nov 17, 18:56 · [Discussion](https://news.ycombinator.com/item?id=50536387)

**「Background」** Solid 2.0 follows an August 2026 release candidate, when ecosystem libraries including Solid Primitives, Kobalte, and Solid Testing Library were already being prepared for 2.0 \(tool-2-2\). The stable release arrives five years after Solid 1.0, according to coverage of the launch \(tool-2-3\).

**「Impact」** For developers considering Solid, the release keeps server data flow—RPC plus live and broadcast updates—inside the framework, which one commenter contrasts with wiring in LiveView or htmx/Datastar separately. The supplied material provides no compatibility or migration details, so teams on earlier Solid releases cannot assess upgrade cost from it.

**「Community discussion」** Commenters focused on the server features: pwmglenn called Solid&\#x27;s server RPC, live, and broadcast &quot;seamless&quot; and more natural than LiveView or htmx/Datastar, while wk\_end argued the &quot;Built to Be Written by Agents&quot; section is really about better debug diagnostics that help human developers too. dmix separately noted they are still waiting for Vue 3.6 Vapor, framing Solid&\#x27;s release against Vue&\#x27;s pending performance work.

<details><summary>References</summary>
<ul>
<li><a href="https://www.solidjs.com/blog/solid-2-0-rc-the-big-reveal">Solid 2.0 RC: The Big | SolidJS</a></li>
<li><a href="https://codingislove.com/solid-2-0/">Solid 2.0 released: async reactivity, server functions, no ...</a></li>

</ul>
</details>

**Tags**: `#SolidJS`, `#JavaScript frameworks`, `#frontend development`, `#server RPC`, `#software releases`

---

<a id="item-tech-news-4"></a>
### [External sandbox pattern ships three servers for coding agents](https://simonwillison.net/2026/Nov/17/external-sandboxes-for-coding-agents/) ⭐️ 8.0/10

Simon Willison and Prime Radiant introduced an “external sandbox” pattern in which a coding agent runs outside a dedicated sandbox and sends its code there for execution, aimed at limiting damage from mistakes or prompt injection when testing local models. They released three server implementations with the same localhost API: external-sandbox-v86 \(Node.js, Alpine Linux under v86 in WebAssembly\), external-sandbox-container \(Python, Alpine Linux in an Apple Containers instance\), and external-sandbox-quicksand \(Python, using Microsoft’s Quicksand library with QEMU and Alpine Linux bundled\). Pi, Claude Code, and Codex can be configured to call that API for code execution, and the sandboxes include an optional HTTP/HTTPS allow-list proxy plus credential replacement so authenticated calls can be made without giving the agent the secret.

rss · Simon Willison · Nov 17, 22:52

**「Why external sandboxes」** Coding agents such as Claude Code and Codex can execute generated code on the host machine, so a mistake or prompt-injection attack can cause damaging local actions. The external sandbox pattern separates the agent process from the execution environment: the agent stays outside, while the code it runs is confined to a dedicated sandbox. The three released servers implement that boundary using v86/WebAssembly, Apple Containers, or Microsoft&\#x27;s Quicksand, and expose a common localhost API.

**「Impact」** For developers, the shared localhost API means the same sandbox can sit behind different agents, while the allow-list proxy and credential replacement let them constrain outbound hosts and keep API secrets out of the agent’s environment; adopting it requires configuring the agent to route code execution to the sandbox rather than running it locally.

**Tags**: `#AI coding agents`, `#sandboxing`, `#security`, `#prompt injection`, `#developer tools`

---

<a id="item-tech-news-5"></a>
### [Datasette Lite rewrite runs full Datasette in the browser](https://simonwillison.net/2026/Nov/17/datasette-lite/) ⭐️ 8.0/10

Simon Willison released a complete service-worker-based rewrite of Datasette Lite that runs the full Datasette Python application in the browser using WebAssembly and Pyodide. Crafted URLs to lite.datasette.io can load SQLite databases, JSON files, CSV files, or SQL scripts; select a released Datasette version from PyPI or a GitHub commit, tag, or branch; choose from over 100 SQLite versions; and install Datasette plugins from PyPI or wheel URLs. Database URLs must have open CORS headers, and the README documents the full set of supported URL arguments. Willison says the rewrite is now almost indistinguishable from the server-side application.

rss · Simon Willison · Nov 17, 16:48

**「Background」** Datasette Lite is not a new project: Simon Willison launched its first version in 2022 as a Pyodide-based experiment that ran Datasette in a web worker, simulated requests, and injected the resulting HTML into the top-level page with innerHTML. That design meant features depending on JavaScript failed, because script tags inserted through innerHTML do not execute. The new release replaces that approach with service workers, which the source says makes the browser version almost indistinguishable from the server-side application.

**「Impact」** Developers can share URL-addressable Datasette demos pinned to a specific Datasette reference and SQLite version without running a web server, which Willison demonstrates by linking to both the broken and fixed behavior of a pagination bug in Datasette issue demos.

**Tags**: `#Datasette`, `#Pyodide`, `#WebAssembly`, `#service workers`, `#SQLite`

---

<a id="item-tech-news-6"></a>
### [Microsoft ONNX Runtime GitHub repository reported unavailable](https://github.com/microsoft/onnxruntime) ⭐️ 7.0/10

The microsoft/onnxruntime GitHub repository is reported to be unavailable, with a Hacker News poster saying their evaluation pipelines began failing that morning and that they saw no advance warning. The item provides no official Microsoft explanation or confirmed cause, so the disappearance remains an unverified availability event rather than a documented security or supply-chain incident. ONNX Runtime is Microsoft&\#x27;s widely used cross-platform inference engine for running machine-learning models, and loss of repository access affects users who depend on its source, releases, and issue tracker.

hackernews · nvader · Nov 17, 23:18 · [Discussion](https://news.ycombinator.com/item?id=50539610)

**「Background」** ONNX Runtime is Microsoft&\#x27;s cross-platform inference and training accelerator for machine-learning models. Its GitHub repository hosts the project&\#x27;s source code and release notes, making it a reference point for developers who build ONNX Runtime into AI pipelines.

**「Pipeline breakage and mitigation」** Teams that pull ONNX Runtime directly from the GitHub repository rather than a pinned package saw evaluation pipelines start failing the morning the repo went dark, according to one commenter in the thread, who also noted that Microsoft&\#x27;s azure-functions-host repository vanished temporarily about six months earlier. The nearest public substitute identified in the discussion is Intel&\#x27;s fork, which carries OpenVINO modifications and so is not a drop-in equivalent; until Microsoft explains the removal, pinning to a mirrored package or a known-good fork is the available workaround.

**「Community Discussion」** Commenters offered competing explanations rather than confirmed facts: one speculated that the disappearance might be related to a compromised package, another claimed ONNX Runtime exfiltrates application telemetry unless built from source with telemetry disabled, and another raised backdoored-model attack vectors. A commenter pointed users to Intel&\#x27;s onnxruntime fork, noting that it includes Intel&\#x27;s OpenVINO modifications.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/microsoft/onnxruntime">GitHub - microsoft/onnxruntime: ONNX Runtime: cross-platform ...</a></li>
<li><a href="https://github.com/microsoft/onnxruntime/releases">Releases · microsoft/onnxruntime · GitHub</a></li>
<li><a href="https://news.ycombinator.com/item?id=50539610">Microsoft &#x27;s ONNX Runtime has disappeared from GitHub</a></li>

</ul>
</details>

**Tags**: `#ONNX Runtime`, `#Microsoft`, `#GitHub`, `#open-source supply chain`, `#AI infrastructure`

---

<a id="item-tech-news-7"></a>
### [Quad9&\#x27;s France withdrawal spotlights DNS filtering fight](https://blog.cloudflare.com/quad9-withdrawal-from-france/) ⭐️ 7.0/10

Quad9 has withdrawn from France, and Cloudflare is framing the exit as a warning sign for DNS filtering and internet regulation. The change affects French users who relied on Quad9&\#x27;s public DNS resolver and removes an independent resolver option from that market. The supplied material does not detail the underlying ruling, the withdrawal timeline, or any specific remedy Cloudflare proposes.

hackernews · subset · Nov 17, 22:13 · [Discussion](https://news.ycombinator.com/item?id=50538994)

**「Context: DNS filtering」** Quad9 is a free public recursive DNS resolver that blocks domains associated with malware and phishing, filtering queries before users connect to those domains. That places it within the DNS-filtering mechanism at issue in its withdrawal from France and in Cloudflare&\#x27;s warning about the precedent.

**「Impact」** For French users and organizations that had standardized on Quad9, the immediate consequence is the need to choose another DNS resolver; for other resolver operators, the case is a concrete example of how DNS blocking obligations can lead to market exit.

**「Community discussion」** Quad9&\#x27;s CTO, commenting as johnhtodd, said at IETF 127 that support for Quad9&\#x27;s position was unanimous so far and that attendees felt a general dread about DNS cases. Other commenters criticized European internet overregulation, and one pressed Cloudflare to commit to withdrawing from affected countries if its appeal fails.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Quad9">Quad 9 - Wikipedia</a></li>
<li><a href="https://quad9.net/">Quad 9 | A public and free DNS service for a better security and privacy</a></li>

</ul>
</details>

**Tags**: `#DNS`, `#internet regulation`, `#privacy`, `#France`, `#Cloudflare`

---

<a id="item-tech-news-8"></a>
### [Nvidia halts Singapore sales disclosure as entity revenue hits $104B](https://www.ft.com/content/dbde7a30-548c-4f9d-a4be-7898a0c24dcf) ⭐️ 7.0/10

Nvidia has stopped separately disclosing Singapore sales after the external revenue of its Singapore entity reached $104 billion, according to a Financial Times report. The change comes amid scrutiny over whether AI chips were routed to China, affecting investors and export-control observers who previously used the country breakdown to track Nvidia&\#x27;s Asia business. The $104 billion figure is the Singapore entity&\#x27;s external revenue, not a confirmed measure of chips consumed in Singapore; the supplied material does not establish final chip destinations.

hackernews · louiereederson · Nov 17, 17:12 · [Discussion](https://news.ycombinator.com/item?id=50534631)

**「Background」** Nvidia had previously disclosed $23.68 billion in revenue billed to Singapore even though less than 2% of its revenue came from products physically shipped there, highlighting that booking location is not the same as where chips are delivered. In May 2025, investigators requested Nvidia&\#x27;s records on direct or indirect sales to Megaspeed, and Nvidia placed the Singapore-based firm on its &quot;no sell&quot; list the following month.

**「Impact」** Investors and compliance teams lose a country-level revenue line that could be compared with export-control risk, and they will need to rely on other disclosures or shipment data to judge Singapore-linked exposure. The remaining figure should not be read as evidence that $104 billion of Nvidia chips were deployed in Singapore.

**「Community discussion」** Commenters disputed treating the $104 billion as chips sold into Singapore: one said it is the Singapore subsidiary&\#x27;s external revenue and can include orders routed through that entity by OEMs, ODMs and resellers, so it says little about final destination. Another called the change an accounting-attribution issue rather than evidence about where chips end up.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/17/nvidia-nvda-earnings-report-q3-2027.html">Nvidia (NVDA) Q3 2027 earnings report: Live updates</a></li>
<li><a href="https://www.youtube.com/watch?v=I8Yhx5U_hiQ">NVIDIA ’s $24B Singapore Mystery — What It Means for... - YouTube</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#export controls`, `#AI hardware`, `#Singapore`, `#semiconductor supply chain`

---

<a id="item-tech-news-9"></a>
### [Phrack Issue 73 Published With Docker Escape, SSH1 History](https://phrack.org/issues/73/introduction_md) ⭐️ 7.0/10

Phrack issue 73 has been published at phrack.org. The release is drawing attention for a Docker escape write-up and a history of the 2000 SSH1 exploit, as referenced in the submission and discussion. The supplied material does not include the issue text, so the full contents and whether the Docker research was disclosed with a CVE remain unverified.

hackernews · notmine1337 · Nov 17, 18:31 · [Discussion](https://news.ycombinator.com/item?id=50535992)

**「Background」** Phrack issue 73 is the third issue curated by the zine&\#x27;s new staff and is larger than last year&\#x27;s, with 23 main papers and eight Line Noise articles, according to a summary of the release. The issue also includes a Phrack World History article on the SSH1 CRC32 vulnerability, the flaw featured in The Matrix Reloaded.

**「Container operators get a concrete audit prompt」** For teams running container workloads, the Docker escape writeup in issue 73 is a prompt to verify that no containers run privileged and that host kernels carry current fixes, since escapes typically succeed through privileged containers or kernel flaws rather than through the container runtime itself. The supplied material does not state whether the technique was disclosed to the vendor or assigned a CVE before publication, so it should not be read as confirmation of a patched or unpatched bug.

**「Community Discussion」** Commenters welcomed the issue&\#x27;s archival material, including a 300-baud modem synth, ANSI art, and Issue 36, and one praised the zine&\#x27;s unpolished style for encouraging freer expression. A separate commenter asked whether the Docker escape had gone through responsible disclosure and CVE assignment, but no answer appears in the supplied comments.

<details><summary>References</summary>
<ul>
<li><a href="https://zeli.app/story/50535992">Phrack 73 Arrives With 23 Papers · 28 HN comments | Zeli</a></li>
<li><a href="https://phrack.org/issues/73/introduction_md">Introduction - phrack.org</a></li>
<li><a href="https://www.startupdefense.io/cyberattacks/docker-escape">Docker Escape : A Technical Guide to Container Security Risks</a></li>

</ul>
</details>

**Tags**: `#computer security`, `#exploits`, `#Phrack`, `#vulnerability disclosure`, `#technical writing`

---

<a id="item-tech-news-10"></a>
### [China&\#x27;s Q/V-band wireless test reaches 27 Gbps bidirectional](https://www.news.cn/tech/20261117/d6323540dccf4e2a976c48a762795956/c.html) ⭐️ 7.0/10

Researchers at the Chinese Academy of Sciences&\#x27; Aerospace Information Research Institute and partner institutions reported a Q/V-band bidirectional wireless communication experiment at the Lijiang China Remote Sensing Satellite Ground Station, reaching 27 Gbps using dual carriers and polarization multiplexing. The test systematically covered 64QAM through 512QAM; at 512QAM, a single channel reached 6.75 Gbps bidirectional, and the combined rate rose to 27 Gbps, described as a domestic record for the band. The team presented the result as an experimental verification relevant to 6G and satellite links, with a stated goal of exceeding 50 Gbps, not as a deployed commercial service.

telegram · zaihuapd · Nov 17, 08:45

**「Background」** Q/V band refers to high-frequency millimeter-wave spectrum, where wider available bandwidth can support higher data rates but atmospheric loss and link-budget constraints are more severe than at lower frequencies. Higher-order QAM such as 512QAM packs more bits into each symbol but requires a cleaner signal-to-noise ratio, so the reported test combines modulation, dual carriers, and polarization multiplexing to reach the aggregate rate.

**「What it means for 6G and satellite links」** For satellite ground-segment and 6G backhaul work, the Lijiang trial establishes a measured domestic baseline across 64QAM to 512QAM in Q/V band, with 6.75 Gbps per channel at 512QAM and 27 Gbps once dual carriers and polarization multiplexing are added — figures the researchers describe as domestically leading and internationally advanced. The team states it will next target rates above 50 Gbps, so the result remains an experimental verification rather than a deployed capability, and no timeline or service commitment was given.

**Tags**: `#6G`, `#Q/V band`, `#satellite communications`, `#wireless communications`, `#512QAM`

---

<a id="item-tech-news-11"></a>
### [Telegram reportedly mandates Stars for bot and mini-app digital goods](https://telegram.me/zaihuapd/45189) ⭐️ 7.0/10

A single Telegram-channel report says Telegram notified developers that digital goods in bots and mini-apps must be sold only through Telegram Stars, citing Apple and Google in-app purchase rules. The reported scope includes bot subscriptions, paid tools, third-party AI-model access, and credits or tokens; cryptocurrency-related transactions may use only GRAM. The notice says proactive checks start this week, with violators subject to bans at any time and no separate warning. The channel said an earlier version of the report lacked corroboration, so the policy details and enforcement remain unconfirmed.

telegram · zaihuapd · Nov 17, 14:46

**「What Telegram Stars are」** Telegram Stars are the platform&\#x27;s in-app currency for digital goods: users buy them through Apple&\#x27;s and Google&\#x27;s in-app purchase systems or via PremiumBot, then spend them in bots on items such as e-books, online courses and game items, according to Telegram&\#x27;s own description of the feature. The reported notice would make Stars the sole permitted payment route for digital goods in bots and mini-apps, a warning Meduza also reported, citing a screenshot published by a Telegram news channel.

**「Developer impact」** Under the reported policy, developers selling bot subscriptions, paid tools, AI-model access, or credits through other payment methods would need to use Stars—or GRAM for crypto—instead of those methods and could be banned without a separate warning.

<details><summary>References</summary>
<ul>
<li><a href="https://meduza.io/en/news/2026/11/18/telegram-to-bar-in-app-card-payments-for-digital-services-exempting-vpn-bots-in-authoritarian-countries">Telegram to bar in - app card payments for digital services... — Meduza</a></li>
<li><a href="https://telegram.org/blog/telegram-stars">Telegram Stars : Pay for Digital Goods and More</a></li>

</ul>
</details>

**Tags**: `#Telegram`, `#platform policy`, `#payments`, `#bots`, `#app store rules`

---

## Financial News

<a id="item-finance-news-1"></a>
### [U.S. Tightens Remote-Access Chip Curbs as Tech Firms Weigh China Exposure](https://www.cnbc.com/2026/11/17/us-tech-firms-china-ties-political-pressure.html) ⭐️ 7.0/10

The Trump administration tightened restrictions on Chinese companies’ remote access to advanced U.S. chips on Monday, CNBC reported, aiming to stop them from bypassing export controls through overseas data centers. Apple, which still makes most of its iPhones in China, gets around 15% of sales from Greater China—mainland China, Hong Kong and Taiwan—a baseline for the market exposure U.S. tech firms are weighing.

rss · CNBC Finance · Nov 17, 08:52

**「Background」** The scrutiny intensified after Nvidia CEO Jensen Huang resigned last week following reports of extramarital affairs, including with a woman U.S. intelligence suspected of being a Chinese spy, and the Trump administration tightened rules on Chinese firms’ remote access to advanced U.S. chips through overseas data centers.

<details><summary>References</summary>
<ul>
<li><a href="https://apnews.com/article/nvidia-jensen-huang-resigns-ceo-affairs-314714d463cf578cbb0dbd49de903107">What we know after Jensen Huang resigns as Nvidia CEO</a></li>
<li><a href="https://www.theguardian.com/technology/2026/nov/12/nvidia-ceo-jensen-huang-resigns">Jensen Huang resigns as Nvidia CEO after alleged affairs</a></li>
<li><a href="https://www.politico.com/news/2026/11/16/commerce-closes-chinas-backdoor-to-nvidia-chips-after-white-house-steps-in-01167199">Commerce closes China’s backdoor to Nvidia chips after White ...</a></li>
<li><a href="https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/">US to curb China&#x27;s access to AI chips as Trump heads to Asia</a></li>
<li><a href="https://techcrunch.com/2026/11/16/us-tightens-ai-chip-export-controls-to-deter-chinese-companies-from-accessing-compute-remotely/">US tightens AI chip export controls to deter Chinese ...</a></li>

</ul>
</details>

**Tags**: `#US-China relations`, `#semiconductor export controls`, `#Nvidia`, `#Apple`, `#rare earths`

---

<a id="item-finance-news-2"></a>
### [UK tribunal dismisses £1.97bn Sony PlayStation Store class action](https://www.reuters.com/world/sony-defeats-2-billion-uk-claim-over-playstation-store-pricing-2026-11-17/) ⭐️ 7.0/10

The UK Competition Appeal Tribunal dismissed a roughly £1.97 billion class action that accused Sony of abusing its dominance to overcharge for PlayStation Store digital content, a case brought on behalf of about 12.2 million UK consumers. The tribunal found that competition between consoles already constrained Sony’s pricing.

telegram · zaihuapd · Nov 17, 16:02

**「Background」** The case was an opt-out collective action, a UK procedure that lets one representative bring a claim on behalf of a defined group of consumers without each member signing up individually.

<details><summary>References</summary>
<ul>
<li><a href="https://www.brickcourt.co.uk/news/detail/competition-appeal-tribunal-dismisses-2-billion-playstation-class-action-against-sony">Competition Appeal Tribunal dismisses £2 billion PlayStation ...</a></li>

</ul>
</details>

**Tags**: `#Sony`, `#PlayStation Store`, `#UK competition law`, `#class action`, `#digital platforms`

---

<a id="item-finance-news-3"></a>
### [China&\#x27;s auto association evaluates 17 automakers on 60-day supplier payment terms](http://www.caam.org.cn/chn/5/cate_68/con_5237404.html) ⭐️ 7.0/10

The China Association of Automobile Manufacturers said on November 16 that, commissioned by the Ministry of Industry and Information Technology \(MIIT\) as a third-party evaluator, it is reviewing supplier payment practices at 17 major automakers, including whether 60-day payment terms have been implemented. The review covers payment systems, whether payment terms for small and medium-sized suppliers stay within 60 days, and a requirement that cash and bank acceptance bills make up at least 80% of payments to larger suppliers; the list includes FAW, SAIC, BYD, Li Auto, NIO, Xpeng, Xiaomi Auto and Leapmotor.

telegram · zaihuapd · Nov 18, 01:15

**「Background」** The 60-day standard began as a voluntary pledge: in June 2025, 17 major Chinese automakers publicly committed to paying suppliers within 60 days of acceptance, and the CAAM review is the check on whether those commitments were actually carried out, with such evaluations planned to run annually.

**「Impact」** Small and medium-sized auto-parts suppliers to the 17 named automakers are the directly affected businesses, because the review will test whether they are paid within 60 days and whether larger suppliers receive at least 80% in cash or bank acceptance bills.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bjnews.com.cn/detail/1757908524168188.html">多 家 车 企 响应 中 汽 协 “ 60 天 账 期 ”倡议 — 新京报</a></li>
<li><a href="https://news.qq.com/rain/a/20260907A0CGJS00">厘清关键要素、引入第三方调研 评 估 汽 车 行业 账 期 进入“强监管”_腾讯新闻</a></li>

</ul>
</details>

**Tags**: `#China auto industry`, `#supply chain finance`, `#payment terms`, `#regulatory oversight`, `#SME suppliers`

---