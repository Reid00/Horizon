---
layout: default
title: "Horizon Summary: 2026-11-08 (EN)"
date: 2026-11-08
lang: en
---

> From 39 items, 12 important content pieces were selected

---

**Technology News**
1. [Undocumented macOS daemons build a personal relationship graph](#item-tech-news-1) ⭐️ 8.0/10
2. [SemiAnalysis tours China’s 800MW Galaxy AI campus in Inner Mongolia](#item-tech-news-2) ⭐️ 8.0/10
3. [Apple discloses HALO humanoid control system using two Qwen models](#item-tech-news-3) ⭐️ 8.0/10
4. [GitHub&\#x27;s Rubicon Git storage targets 7,200 pushes per second](#item-tech-news-4) ⭐️ 8.0/10
5. [Reports: Microsoft Research&\#x27;s AI Frontiers Group Is Ending](#item-tech-news-5) ⭐️ 7.0/10
6. [Scan finds secrets in committed Claude Code local settings](#item-tech-news-6) ⭐️ 7.0/10
7. [Coldframe honeypot mimics Danfoss and Dixell fridge controllers](#item-tech-news-7) ⭐️ 7.0/10
8. [MaxxBench probes DeepSWE benchmark robustness to task-spec changes](#item-tech-news-8) ⭐️ 7.0/10
9. [Asahi Linux 7.3 progress report covers Fedora release and hardware work](#item-tech-news-9) ⭐️ 7.0/10
10. [Claude Code accused of leaking login emails in web requests](#item-tech-news-10) ⭐️ 7.0/10

**Financial News**
1. [Berkshire more than doubles Q3 buybacks as earnings decline](#item-finance-news-1) ⭐️ 7.0/10
2. [SoftBank and ABB Weigh China Carve-Out to Salvage Robotics Deal](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Undocumented macOS daemons build a personal relationship graph](https://8rank.ai/game/apple-intelligence-personal-knowledge-graph) ⭐️ 8.0/10

A new analysis examines undocumented macOS daemons that build a personal knowledge graph about the user and the people around them, including a family-member or relationship classifier. The report frames the system as a privacy and ethics issue because it infers who users know, how those people relate, and how users communicate with them. The supplied material does not document which macOS versions, settings, or user-facing disclosures are involved; a commenter quotes the article as saying every Mac since 2022 ships a pair of such daemons.

hackernews · infwhispers · Nov 7, 09:46 · [Discussion](https://news.ycombinator.com/item?id=50403097)

**「Background」** According to the research, the system dates to macOS 13 \(2022\): every Mac since then has run two background daemons, knowledgeconstructiond and intelligenceplatformd, which together assemble what Apple calls a &quot;personal knowledge graph.&quot; The data sits in ~/Library/IntelligencePlatform as 51 plaintext SQLite databases guarded by TCC Full Disk Access, and the researchers examined the architecture inside the Apple Intelligence bundle on macOS 26. The daemons&\#x27; output is described as a queryable store that local models retrieve from to resolve references, such as which &quot;James&quot; a message is meant for.

**「Impact」** For Mac users, the reported design means sensitive relationship inferences can be produced on-device even when data never leaves the machine, so privacy assessments should cover local inference and not just cloud uploads. The article&\#x27;s focus on undocumented daemons also makes transparency and auditability the immediate concern.

**「Community Discussion」** Commenters split between seeing the graph as useful context for local assistants—one example is disambiguating &\#x27;Text James&\#x27; or &\#x27;Tell my boss&\#x27;—and raising consent and social concerns about relationship data being inferred without an explicit opt-in. Another commenter says the capability is unsurprising because Photos already recognizes names and faces of loved ones and pets.

<details><summary>References</summary>
<ul>
<li><a href="https://daily.dev/posts/every-mac-comes-with-an-undocumented-family-member-classifier-s3lfxwdun">Every Mac comes with an (undocumented) family member classifier</a></li>
<li><a href="https://techbytes.app/posts/every-mac-comes-with-an-undocumented-family-member-classifier/">Every Mac comes with an (undocumented) family member classifier</a></li>
<li><a href="https://techplanet.today/post/apples-hidden-personal-knowledge-graph-understanding-macoss-undocumented-family-classifier">Apple&#x27;s Hidden Personal Knowledge Graph: Understanding macOS ...</a></li>

</ul>
</details>

**Tags**: `#Apple`, `#macOS`, `#privacy`, `#personal knowledge graph`, `#on-device ML`

---

<a id="item-tech-news-2"></a>
### [SemiAnalysis tours China’s 800MW Galaxy AI campus in Inner Mongolia](https://newsletter.semianalysis.com/p/we-visited-chinas-stargate-in-inner) ⭐️ 8.0/10

SemiAnalysis reported after a September visit that the Galaxy campus in Ulanqab, Inner Mongolia, is planned for up to 800 MW of IT capacity, with its first 120 MW phase delivered within a year at a fifth of US costs. The campus is owned by Envision Group, which integrates a dedicated wind farm and power line, a blade factory across the road, low-voltage power modules, an 800V system, battery storage, and a prefabricated substation. All four phases are built-to-suit for two unnamed internet giants, and the surrounding Chahar High-tech Zone had 22 datacenter projects under construction at the time of the visit.

rss · Semianalysis · Nov 7, 19:01

**「Context」** Stargate Abilene, a gigawatt-scale campus in Texas built for OpenAI, has become the reference point for the U.S. AI datacenter buildout. China has campuses on a similar scale, but few outside the country have seen them; SemiAnalysis visited one in Inner Mongolia’s Ulanqab region, China’s fastest-growing AI datacenter area.

**「Impact」** The 120 MW first phase is delivered and built to suit two unnamed internet giants, so the campus’s cost and speed advantage is tied to a specific owner and power arrangement rather than a general-purpose cloud offering.

**Tags**: `#AI infrastructure`, `#datacenters`, `#China tech`, `#compute economics`, `#energy`

---

<a id="item-tech-news-3"></a>
### [Apple discloses HALO humanoid control system using two Qwen models](https://weibo.com/1642634100/RqjjGllvw) ⭐️ 8.0/10

Apple&\#x27;s research team disclosed HALO, a three-layer autonomous control system for humanoid robots, in a paper submitted to arXiv on 4 November. The top layer uses Qwen3.6-35B-A3B to orchestrate tasks, the middle layer uses Qwen3.5-2B to generate motions, and the bottom layer is a reinforcement-learning-trained action tracker. The team validated the system on a Unitree G1, transferring motions learned in simulation to an unfamiliar real room, and released code for data generation, model training, and deployment. The disclosure is a preprint rather than a peer-reviewed result or a product announcement.

telegram · zaihuapd · Nov 7, 13:35

**「Background」** HALO is a research preprint, not a shipped product or peer-reviewed release. Its central technical step is sim-to-real transfer: a control policy is trained in simulation and then run on a physical Unitree G1 in a real, unfamiliar room, where differences between simulated and real conditions can affect execution.

**「Impact」** Apple&\#x27;s released data-generation, training, and deployment code lets robotics developers reproduce a simulation-only pipeline that runs fully onboard a Unitree G1 and performs zero-shot tasks in unscanned rooms; the evidence remains a preprint limited to that robot, so porting the approach to other humanoid platforms is unproven.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/html/2611.06908">Perceptive Humanoid Motion from Simulation - arXiv.org</a></li>
<li><a href="https://github.com/apple-aiml-research/ml-halo">GitHub - apple-aiml-research/ml-halo: HALO: Perceptive ...</a></li>
<li><a href="https://ai.42how.com/en/article/ee6a8f15-db79-4091-9a86-3bc31de6c02f">Apple Integrates Humanoid Perception Into Simulation for Zero ...</a></li>

</ul>
</details>

**Tags**: `#Apple`, `#humanoid robotics`, `#Qwen`, `#sim-to-real`, `#open-source research`

---

<a id="item-tech-news-4"></a>
### [GitHub&\#x27;s Rubicon Git storage targets 7,200 pushes per second](https://github.blog/engineering/architecture-optimization/inside-githubs-new-git-storage-architecture/) ⭐️ 8.0/10

GitHub has introduced Rubicon, a new Git storage architecture aimed at many AI agents operating concurrently on a single repository. In internal tests, GitHub says the system supported 5,000 agents collaborating at once and handled 7,200 pushes per second while keeping read latency low. The design stores Git objects in Azure Blob Storage, manages reference state with Ref-CAS, and uses virtual replicas for reads and writes plus background nodes to compact data packs. Rubicon is currently in a limited private preview, with GitHub saying it will expand availability gradually.

telegram · zaihuapd · Nov 7, 14:12

**「Background」** GitHub’s October 21 engineering post said it had moved a copy of 99.99999% of its repositories to Azure and was using per-reference quorums for the remainder, with object storage letting reads scale independently; it framed that work as a bridge to agent-scale Git infrastructure \(tool-2-3\).

**「Impact」** Because Rubicon is only in limited private preview, developers and organizations cannot yet rely on the 7,200-pushes-per-second figure for production GitHub workflows; broader availability is planned only gradually.

<details><summary>References</summary>
<ul>
<li><a href="https://github.blog/engineering/architecture-optimization/the-bridge-to-agent-scale-git-infrastructure/">The bridge to agent-scale Git infrastructure - The GitHub Blog</a></li>

</ul>
</details>

**Tags**: `#GitHub`, `#Git storage architecture`, `#AI agents`, `#Azure Blob Storage`, `#distributed systems`

---

<a id="item-tech-news-5"></a>
### [Reports: Microsoft Research&\#x27;s AI Frontiers Group Is Ending](https://hunch.net/?p=13764006) ⭐️ 7.0/10

Reports linked from Hacker News say Microsoft Research&\#x27;s AI Frontiers group is ending and that researcher John Langford is leaving. The submission provides no independent confirmation, technical detail, or timeline, so the closure&\#x27;s scope and whether the group&\#x27;s projects will continue elsewhere remain unclear.

hackernews · srean · Nov 7, 18:02 · [Discussion](https://news.ycombinator.com/item?id=50406563)

**「Background」** AI Frontiers was a roughly 50-person Microsoft Research group focused on fundamental AI advances; reports cited in the discussion say it was moved out of Microsoft Research and into Microsoft AI in early September. John Langford, a partner researcher manager at Microsoft Research New York who co-created the group, then left Microsoft and declared the group finished amid a dispute over Microsoft AI&\#x27;s scaling-first research strategy.

**「Community discussion」** Commenters disagreed about the implications: one argued that large companies now discourage exploratory AI research and push transformer scaling, while another said research and scale both need funding and warned that concentrating investment on one approach is risky. A further commenter said the implicit MSR norm of &quot;do good work and good things happen&quot; has been broken under current leadership and called that culture-destroying.

<details><summary>References</summary>
<ul>
<li><a href="https://explainx.ai/blog/john-langford-microsoft-ai-frontiers-ended-mai-scaling-only-2026">Microsoft AI Frontiers Ends: Langford on MAI Clash - explainx.ai</a></li>
<li><a href="https://www.indiatoday.in/technology/news/story/microsoft-ai-research-clash-john-langford-quits-declares-ai-frontiers-over-3034334-2026-11-07">Microsoft AI research clash: John Langford quits, declares AI ...</a></li>
<li><a href="https://daily.dev/posts/microsoft-researcher-john-langford-exits-ai-frontiers-group-declared-finished-t8nprypt6">Microsoft Researcher John Langford Exits. AI Frontiers Group ...</a></li>

</ul>
</details>

**Tags**: `#AI research`, `#Microsoft Research`, `#AI strategy`, `#industry news`, `#Hacker News`

---

<a id="item-tech-news-6"></a>
### [Scan finds secrets in committed Claude Code local settings](https://apiiro.com/blog/coding-agents-leaking-secrets-github-dont-ask-again) ⭐️ 7.0/10

A security blog post reports that a scan found 1,122 public GitHub files containing Claude Code local settings whose approved commands embedded passwords or keys. The exposure required users to manually create and commit .claude/settings.local.json, not merely choose “Don’t Ask Again,” according to commenters and the Claude Code team. Boris from the Claude Code team said the file is meant to stay local and is automatically gitignored when Claude creates it, and that the team historically has not done secret scrubbing but is looking into preventing this.

hackernews · shmulc · Nov 7, 20:45 · [Discussion](https://news.ycombinator.com/item?id=50407882)

**「Background」** Claude Code keeps locally approved commands in \`.claude/settings.local.json\`, a settings file that the Claude Code team says is meant to remain local and is automatically gitignored when Claude creates it. The &quot;Don&\#x27;t Ask Again&quot; option records an approved command in that local allowlist, so a password or key embedded directly in such a command can persist in the file. The reported exposures involve users manually committing that file to public repositories.

**「Exposure risk」** Developers who manually committed \`.claude/settings.local.json\` can expose credentials embedded in approved commands: the scan found 1,122 public files containing secrets, or 2,539 secrets across 1,994 repositories when history, shared settings, and transcripts are counted. Teams should search both current trees and Git history for the file, keep it ignored, and rotate any credentials found rather than only deleting the file.

**「Community discussion」** Commenters disputed the framing: Aurornis said pressing “Don’t Ask Again” alone does not expose secrets, because exposure requires committing local settings with approved commands containing credentials. Boris from the Claude Code team said the file is meant to remain local and auto-gitignored when Claude creates it, while acknowledging the team is looking into secret scrubbing; other users described mitigations such as ephemeral VMs with restricted proxies or password-manager CLI access.

<details><summary>References</summary>
<ul>
<li><a href="https://cellcog.ai/blog/claude-code-settings-secrets-github/">Claude Code&#x27;s settings.local.json Is Leaking Secrets | CellCog</a></li>
<li><a href="https://www.agentbeam.com/blog/claude-code-dont-ask-again-settings-local-json-secrets-public-github">Claude Code settings.local.json Leaks Secrets on GitHub | Beam</a></li>

</ul>
</details>

**Tags**: `#AI coding agents`, `#security`, `#secrets management`, `#GitHub`, `#Claude Code`

---

<a id="item-tech-news-7"></a>
### [Coldframe honeypot mimics Danfoss and Dixell fridge controllers](https://github.com/hedgerow-dev/coldframe) ⭐️ 7.0/10

Coldframe is an open-source, single-file Python honeypot built only with the standard library that impersonates Danfoss AK-SM 800A and Dixell XWEB supermarket refrigeration controllers. Its author says both personas are recognized on Shodan as real devices rather than honeypots, and the tool recognizes CVE-2025-41450, the Danfoss “code of the day” login bypass, while tagging attempts against three other Danfoss CVEs and XWEB vulnerabilities. Default logins open a fake store dashboard with defrost buttons; in the first day, two live instances saw only generic scanners and Shodan’s crawler refrigerator.census.shodan.io, so the claimed realism has not yet been independently validated.

hackernews · hedgerow-dev · Nov 7, 17:27 · [Discussion](https://news.ycombinator.com/item?id=50406292)

**「Background」** Coldframe’s “code of the day” exploit check corresponds to CVE-2025-41450, an improper-authentication vulnerability that allows authentication bypass with privileged access on Danfoss AK-SM 8xxA series controllers before version 4.2. Danfoss’s advisory directs users to install the latest software through the AK-SM 800A series.

**「Impact」** For security researchers, the fake dashboard lets them observe what an attacker does after logging in, such as attempts to press defrost controls, rather than only the initial probe. Nothing behind the interface is real, according to the author.

**「Community discussion」** One commenter warned against relying on Shodan data to validate honeypot realism, saying many internet-facing devices are themselves honeypots or already compromised, while another asked whether large-scale refrigeration hacks were definitively established. The author argued that supermarkets have no security teams, so safe defaults and patching must come from vendors or installers.

<details><summary>References</summary>
<ul>
<li><a href="https://vulners.com/cve/CVE-2025-41450">CVE - 2025 - 41450 - vulnerability database | Vulners.com</a></li>
<li><a href="https://www.danfoss.com/en/service-and-support/coordinated-vulnerability-disclosure/danfoss-security-advisories/">Danfoss security advisories | Danfoss</a></li>

</ul>
</details>

**Tags**: `#honeypots`, `#ICS security`, `#industrial control systems`, `#Danfoss`, `#Shodan`

---

<a id="item-tech-news-8"></a>
### [MaxxBench probes DeepSWE benchmark robustness to task-spec changes](https://maxxbench.unlap.ai/research/why-maxxbench/) ⭐️ 7.0/10

MaxxBench published a robustness study of DeepSWE coding-benchmark scores, perturbing task specifications to test whether reported results hold up. It finds that scores may not generalize and that some models, notably smaller &quot;flash&quot; variants, degrade most under the perturbations. The work is an evaluation-methodology critique rather than a new model or leaderboard release, so its claims concern benchmark validity.

hackernews · antiuniverse · Nov 7, 17:19 · [Discussion](https://news.ycombinator.com/item?id=50406222)

**「Background」** DeepSWE is a long-horizon software-engineering benchmark for coding agents, with tasks written from scratch across 91 repositories and five languages and hand-written verifiers that test behavior rather than implementation details; Artificial Analysis tracks it as DeepSWE v1.1. MaxxBench&\#x27;s critique tests that benchmark&\#x27;s robustness by varying task specifications and checking whether reported scores generalize.

**「Impact」** Teams using DeepSWE to compare coding models should treat a single score as a point estimate and validate performance on varied task specifications, especially when considering smaller or &quot;flash&quot; variants.

**「Community discussion」** Several commenters treated the study as a useful generalization check: one described varying a single parameter as a cheap first-order test, while another read the graph as showing smaller &quot;flash&quot; variants collapsing most and noted that some same-suffix models are actually distinct lineages. Others raised benchmark hygiene concerns, reporting bugs in DeepSWE and arguing that labs should vary RL training environments rather than let smaller models overfit to simplified task specs.

<details><summary>References</summary>
<ul>
<li><a href="https://deepswe.datacurve.ai/">DeepSWE measures frontier coding agents on original, long-horizon...</a></li>
<li><a href="https://deepswe.lol/">DeepSWE — Long-Horizon Software Engineering Benchmark</a></li>
<li><a href="https://artificialanalysis.ai/agents/coding-agents">AI Coding Agent Benchmarks &amp; Leaderboard | Artificial Analysis</a></li>

</ul>
</details>

**Tags**: `#llm-benchmarks`, `#benchmark-validity`, `#model-evaluation`, `#ai-evaluation`, `#deepswe`

---

<a id="item-tech-news-9"></a>
### [Asahi Linux 7.3 progress report covers Fedora release and hardware work](https://asahilinux.org/2026/11/progress-report-7-3/) ⭐️ 7.0/10

Asahi Linux&\#x27;s 7.3 progress report covers continued Apple Silicon Linux development and includes a Fedora Asahi Remix release that shipped the same day as Fedora Linux 45 on 3 November. The report describes this as the first same-day Fedora Asahi Remix release, and it also addresses ongoing hardware support work and attempts to exploit the project&\#x27;s permissive licensing.

hackernews · ackyshake · Nov 7, 05:20 · [Discussion](https://news.ycombinator.com/item?id=50401867)

**「Background」** Asahi Linux is an open-source project working to run Linux natively on Apple Silicon Macs, and Fedora Asahi Remix is its Fedora-based distribution. The 7.3 report&\#x27;s same-day release with Fedora Linux 45 is presented as a first, implying earlier Remix releases did not ship in lockstep with upstream Fedora.

**「What it means for users」** Fedora Asahi Remix 45 shipped on the same day as Fedora Linux 45&\#x27;s 3 November release, the first time Asahi&\#x27;s remix has tracked an upstream Fedora version immediately, so Apple Silicon users can adopt the new Fedora base without waiting for a lagging rebuild. However, one commenter reports that USB-C external-display support is still absent and remains the reason they have not installed Asahi on a MacBook Air, so users who depend on an external monitor should confirm support before switching.

**「Community discussion」** Commenters highlighted USB-C display support as a blocker for adoption, with one user saying they would not install Asahi on a MacBook Air without external display support. Another commenter asked whether the licensing concerns referred to Omarchy, while a separate commenter promoted Gravity Linux&\#x27;s claims of Vulkan 1.4 and M4/M5 support.

<details><summary>References</summary>
<ul>
<li><a href="https://asahilinux.org/2026/11/progress-report-7-3/">Progress Report : Linux 7 . 3 - Asahi Linux</a></li>

</ul>
</details>

**Tags**: `#Asahi Linux`, `#Apple Silicon`, `#Linux`, `#Open Source`, `#Fedora`

---

<a id="item-tech-news-10"></a>
### [Claude Code accused of leaking login emails in web requests](https://github.com/anthropics/claude-code/issues/107757) ⭐️ 7.0/10

A developer report claims Claude Code inserted users&\#x27; login email addresses into outbound web requests, causing at least one user to receive many scam emails every day. According to the report, an Anthropic engineer said the email had been placed in the model context to stop Claude from inventing author names; the issue was reported in July, with emails sent to sites including Wikipedia and the U.S. Securities and Exchange Commission. The engineer said version 2.1.317 adds a block that Python scripts can bypass, and Anthropic plans to remove the login email from the context in the next version. The report comes via a brief aggregator summary and has not been independently verified.

telegram · zaihuapd · Nov 7, 08:09

**「Background」** Claude Code is Anthropic&\#x27;s agentic coding tool that can read repositories, run commands, and perform web searches from the terminal or IDE. The reported exposure stems from an earlier workaround: Anthropic placed the account&\#x27;s login email in the model context to stop Claude from inventing author names, and the issue report says that email appeared in the User-Agent header of outbound search requests.

**「Incomplete mitigation」** Users on version 2.1.317 are only partly protected: the added interception can be bypassed when web requests are issued through a Python script, so the login email can still reach third-party sites in that path. Until Anthropic ships the next release that removes the email from model context, teams running scripted web fetches through Claude Code should assume the address may be exposed and limit such runs to accounts they are willing to have associated with outbound requests.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/anthropics/claude-code/issues/107757">Bug Report: Privacy violation in User-Agent header · Issue # 107757 ...</a></li>
<li><a href="https://claude.com/product/claude-code">Claude Code by Anthropic | AI Coding Agent, Terminal, IDE</a></li>

</ul>
</details>

**Tags**: `#Claude Code`, `#privacy`, `#security vulnerability`, `#AI coding tools`, `#Anthropic`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Berkshire more than doubles Q3 buybacks as earnings decline](https://www.cnbc.com/2026/11/07/berkshire-hathaway-q3-2026-earnings-buybacks.html) ⭐️ 7.0/10

Berkshire Hathaway said it repurchased $9.6 billion of its own stock in the third quarter, more than double the $4.5 billion bought in the second quarter, even as operating earnings fell 5.8% to $12.705 billion from $13.485 billion a year earlier. Overall earnings, which include its stock portfolio, dropped 28% to $22.112 billion from $30.796 billion.

rss · CNBC Finance · Nov 7, 15:23

**「Background」** Greg Abel became Berkshire Hathaway’s chief executive in January 2026, and his first buyback as CEO—after a 21-month pause—was $234 million in the first quarter. Operating earnings cover Berkshire’s wholly owned businesses, while overall earnings also include gains and losses on its stock portfolio.

<details><summary>References</summary>
<ul>
<li><a href="https://www.heygotrade.com/en/news/berkshire-hathaway-greg-abel-buyback-cash-pile-2026/">Berkshire Under Greg Abel : $234M Buyback , $397B Cash Pile</a></li>
<li><a href="https://management.org/berkshire-hathaway-s-new-ceo-backs-his-own-judgment-with-a-4-5-billion-buyback">Berkshire Hathaway &#x27;s New CEO Backs His Own... - Management.org</a></li>

</ul>
</details>

**Tags**: `#Berkshire Hathaway`, `#share buybacks`, `#earnings`, `#insurance`, `#cash reserves`

---

<a id="item-finance-news-2"></a>
### [SoftBank and ABB Weigh China Carve-Out to Salvage Robotics Deal](https://www.bloomberg.com/news/articles/2026-11-07/softbank-abb-weigh-china-carve-out-to-salvage-robotics-deal) ⭐️ 7.0/10

SoftBank and ABB are reportedly considering separating ABB&\#x27;s China robotics business to salvage their blocked $5.4 billion acquisition, with the China unit potentially valued at $2 billion to $3 billion, according to Bloomberg.

telegram · zaihuapd · Nov 7, 11:24

**「Background」** China&\#x27;s foreign investment security review office halted the deal on Thursday, the report said; the proposed remedy would place the China business in a separate entity with different ownership terms, with SoftBank leading the effort.

**Tags**: `#M&amp;A`, `#China regulatory review`, `#robotics`, `#SoftBank`, `#ABB`

---