---
layout: default
title: "Horizon Summary: 2026-11-28 (EN)"
date: 2026-11-28
lang: en
---

> From 31 items, 12 important content pieces were selected

---

**Technology News**
1. [OpenSec reports 9.8 Linux nfsd pre-auth heap overflow](#item-tech-news-1) ⭐️ 8.0/10
2. [Google&\#x27;s DeepCrossAttention claims comparable quality with up to 3x speedup](#item-tech-news-2) ⭐️ 7.0/10
3. [Reported WebRTC card-skimmer scripts hit shopping sites](#item-tech-news-3) ⭐️ 7.0/10
4. [Convex AI coding skill accused of uploading app ideas without disclosure](#item-tech-news-4) ⭐️ 7.0/10
5. [False Computer-Checked Proofs: Soundness Bugs and Independent Verifiers](#item-tech-news-5) ⭐️ 7.0/10
6. [State attorneys general sue SpaceX and xAI over Grok sexual images](#item-tech-news-6) ⭐️ 7.0/10
7. [SemiAnalysis benchmarks Trainium3 inference cost against Nvidia GB300](#item-tech-news-7) ⭐️ 7.0/10
8. [Report: AI Tool Artex Used in Attacks on US Intelligence Agencies](#item-tech-news-8) ⭐️ 7.0/10
9. [Minecraft Bedrock resource-pack flaw affects 26.52–26.63, fixed in 26.65](#item-tech-news-9) ⭐️ 7.0/10
10. [Microsoft expands in-box Windows drivers for printers, audio, and buses](#item-tech-news-10) ⭐️ 7.0/10

**Financial News**
1. [China&\#x27;s State Council Calls for Stronger &\#x27;National Team&\#x27; Market Stabilization](#item-finance-news-1) ⭐️ 8.0/10
2. [央行将大额存单个人起购门槛下调至10万元](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [OpenSec reports 9.8 Linux nfsd pre-auth heap overflow](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 8.0/10

OpenSec reports CVE-2026-99362, a CVSS 9.8 pre-authentication heap overflow in the Linux kernel&\#x27;s nfsd server that can let an unauthenticated attacker write out of bounds via a connection to tcp/2049 and gain a root shell. The flaw is said to have existed since Linux 3.16 in 2014 and to affect hosts with NFSv4.1 or 4.2 enabled, including file servers, NAS devices, and clustered storage nodes. Fixes are listed in Linux 6.12.117, 6.18.61, 7.3.2, and 7.4-rc1; upgrading requires a reboot, and systems that cannot be upgraded immediately can restrict tcp/2049 at the firewall. The CVE was published on November 20, 2026, according to the report.

telegram · zaihuapd · Nov 27, 12:57

**「Background」** Linux&\#x27;s in-kernel NFS server, nfsd, exports local filesystems over the network, and in NFSv4.1 and 4.2 it keeps a session reply cache so clients can retransmit requests and receive cached replies. The vulnerable path lets a client negotiate a minimal cached reply size and then send crafted compound requests containing SEQUENCE operations, causing the server to copy a full reply past the end of the allocated buffer before any authentication happens. OpenSec&\#x27;s report states the flaw has existed since Linux 3.16 in 2014, which is why the affected kernel range spans roughly a decade of releases.

**「Impact and mitigation」** Administrators running nfsd with NFSv4.1 or 4.2 enabled must upgrade to kernel 6.12.117, 6.18.61, 7.3.2, or 7.4-rc1 and reboot, since the flaw is reachable over tcp/2049 before authentication. Where an immediate kernel upgrade is not possible, the source recommends restricting tcp/2049 to trusted addresses or stopping and disabling the NFS server service if it is not needed.

<details><summary>References</summary>
<ul>
<li><a href="https://access.redhat.com/security/cve/cve-2026-99362">CVE-2026-99362 - Red Hat Customer Portal</a></li>
<li><a href="https://rokkhe.hashnode.dev/nfs2root-cve-2026-99362-linux-nfsd">NFS2ROOT (CVE-2026-99362): what it is, who is exposed, and ...</a></li>
<li><a href="https://1275.ru/vulnerability/nfs2root-v-yadre-linux-zakryli-zapis-za-granitsy-v-nfsd_53834">NFS 2ROOT: в ядре Linux закрыли запись за границы в nfsd</a></li>

</ul>
</details>

**Tags**: `#Linux kernel`, `#NFS`, `#vulnerability`, `#security`, `#CVE`

---

<a id="item-tech-news-2"></a>
### [Google&\#x27;s DeepCrossAttention claims comparable quality with up to 3x speedup](https://research.google/blog/supercharging-transformer-residual-connections/) ⭐️ 7.0/10

Google Research presents DeepCrossAttention, a transformer residual-connection technique that it claims achieves model quality comparable to standard approaches while running up to 3x faster. The claim comes from a Google Research blog post; the supplied material does not include independent measurements or specify which workloads the speedup applies to.

hackernews · ComputedCamp995 · Nov 27, 23:06 · [Discussion](https://news.ycombinator.com/item?id=50672565)

**「Background」** Traditional transformer residual connections combine a layer&\#x27;s output with its input, which Google Research says can dilute information as depth grows. DeepCrossAttention instead uses learnable, input-dependent weights and depth-wise cross-attention to dynamically combine outputs from previous layers, according to Google Research and the arXiv paper describing the method.

**「Adoption impact」** For practitioners, DeepCrossAttention&\#x27;s input-dependent, depth-wise cross-attention over Query, Key, and Value changes how residual streams are aggregated, making it a model-architecture change rather than a drop-in inference optimization. Teams should reproduce the claimed up-to-3x speedup on their own hardware and workloads before relying on it.

**「Community discussion」** One commenter argued that the post&\#x27;s comparison charts should be bar charts rather than line graphs because the methods have no temporal ordering. Another commenter invoked DenseNet, and a third asked whether the technique could compound with MTP/Dflash speedups.

<details><summary>References</summary>
<ul>
<li><a href="https://research.google/blog/supercharging-transformer-residual-connections/">Supercharging transformer residual connections - Google Research</a></li>
<li><a href="https://arxiv.org/abs/2502.06785">[2502.06785] DeepCrossAttention: Supercharging Transformer ...</a></li>
<li><a href="https://arxiv.org/abs/2502.06785">[2502.06785] DeepCrossAttention : Supercharging Transformer ...</a></li>
<li><a href="https://www.alphaxiv.org/overview/2502.06785v1">DeepCrossAttention : Supercharging Transformer Residual ...</a></li>

</ul>
</details>

**Tags**: `#transformers`, `#model efficiency`, `#Google Research`, `#deep learning`, `#residual connections`

---

<a id="item-tech-news-3"></a>
### [Reported WebRTC card-skimmer scripts hit shopping sites](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

A security report cited on Hacker News says credit-card-skimming scripts using WebRTC were found on popular shopping sites. The supplied item gives no affected site names, number of sites, technical details, or independent confirmation, so the scope and mechanism remain unverified. The claim is that the skimmers abuse WebRTC on e-commerce sites, where third-party scripts are commonly embedded.

hackernews · scanr · Nov 27, 15:40 · [Discussion](https://news.ycombinator.com/item?id=50668145)

**「How digital skimming works」** Digital card-skimming attacks work by injecting malicious JavaScript into an e-commerce checkout page so payment-form data is captured as it is entered. Such code typically arrives through third-party scripts embedded in the page — analytics, chat widgets, tag managers — which site operators may neither control nor closely monitor. WebRTC is a browser API for real-time peer-to-peer data exchange; the report&\#x27;s claim that skimmers are using it as a channel is not substantiated beyond the headline in the supplied material.

**「Impact」** For checkout-page operators, the reported WebRTC exfiltration path means CSP and conventional script-monitoring controls may not surface stolen card data leaving the browser; threat-research coverage describes the technique as bypassing those traditional controls. The practical response is to inventory third-party scripts on payment pages and monitor or restrict WebRTC connections there.

**「Community discussion」** Commenters argued that the WebRTC label matters less than the underlying exposure: afavour said the approach could work with ordinary HTTP requests and that embedding third-party scripts leaves sites vulnerable, while s\_u\_d\_o asked why ad providers do not sandbox ads to prevent client-side JavaScript execution. jszymborski said the report reinforces their decision to block ads.

<details><summary>References</summary>
<ul>
<li><a href="https://www.linkedin.com/posts/chadbarr_webrtc-skimmer-bypasses-csp-to-steal-payment-activity-7442920958270562304-SdXp">WebRTC Skimmer Bypasses CSP to Steal Payment Data from...</a></li>
<li><a href="https://aviatrix.ai/threat-research-center/webrtc-skimmer-bypasses-csp-to-steal-payment-data-from-e-commerce-sites/">WebRTC Skimmer Bypasses CSP to Steal Payment Data from...</a></li>

</ul>
</details>

**Tags**: `#web security`, `#credit card skimming`, `#WebRTC`, `#third-party scripts`, `#e-commerce security`

---

<a id="item-tech-news-4"></a>
### [Convex AI coding skill accused of uploading app ideas without disclosure](https://github.com/convex/convex-backend-skill/issues/64) ⭐️ 7.0/10

A GitHub issue on the convex-backend-skill repository alleges that a Convex AI coding skill sends users&\#x27; app ideas, in the form of prompts, to a remote server without telling them. Convex CEO Jamie responded in the Hacker News thread that the prompt upload powers Convex&\#x27;s &quot;quickstart&quot; feature; he also said Convex recently shut down Convex Chef, its end-to-end vibe-coding product. The supplied material does not include the issue&\#x27;s technical details or independent verification of the allegation.

hackernews · MickyTheMouse · Nov 27, 18:02 · [Discussion](https://news.ycombinator.com/item?id=50669765)

**「Background」** Convex ships &quot;skills&quot; — SKILL.md instruction files that AI coding agents load to build type-safe backends on its reactive platform, covering queries, mutations, actions, auth, and deployment. The disputed behavior sits in the quickstart skill: its SKILL.md posts the user&\#x27;s one-sentence project idea to a convex.site host in a step a code comment labels telemetry, and the add skill pipes a script from that same host directly into bash.

**「What users should check」** Developers using the Convex skill should assume that prompts describing their app may leave their machine: Convex CEO Jamie confirmed in the thread that the plugin&\#x27;s prompt upload powers the &quot;quickstart&quot; feature, so proprietary ideas entered there are transmitted to Convex&\#x27;s servers rather than processed locally. Because the issue alleges that transfer was not disclosed, teams with confidential designs should review the skill&\#x27;s network behavior or avoid entering sensitive details until the disclosure is clarified.

**「Community Discussion」** Commenters focused on trust and architecture: one argued that self-hosted open-weight models are the better long-term path, while another said prompt injection is more common than models making malicious tool calls on their own and did not assert malice in this case. These are opinions, not established findings about the Convex plugin.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/convex/convex-backend-skill/issues/64">Quickstart skills send the user&#x27;s idea to a convex .site host and run...</a></li>
<li><a href="https://www.convex.dev/">Convex | All gas, no breakages</a></li>
<li><a href="https://mcpfield.com/en/skills/convex-backend">convex - backend · Skills · MCP Field</a></li>

</ul>
</details>

**Tags**: `#AI coding tools`, `#privacy`, `#security`, `#developer tooling`, `#Convex`

---

<a id="item-tech-news-5"></a>
### [False Computer-Checked Proofs: Soundness Bugs and Independent Verifiers](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

The essay “False Computer-Checked Proofs” argues that soundness bugs in proof checkers can make a computer-checked proof false, so acceptance by a single checker is not an absolute guarantee for developers and mathematicians relying on formal verification. It discusses systems including Lean and Metamath, but the supplied material does not identify a specific new bug, affected version, or exploit. Commenters argue that the practical risk is lower than the essay&\#x27;s framing suggests, citing multiple independently created checkers and informal review.

hackernews · \_tk\_ · Nov 27, 15:26 · [Discussion](https://news.ycombinator.com/item?id=50667989)

**「Background」** Computer-checked proofs are only as reliable as the checker&\#x27;s trusted core: a soundness bug can let a false statement pass even when each proof step is mechanically checked. Daniel J. Bernstein, the essay&\#x27;s author, is a mathematician and cryptologist; his page collects reported cases in which proof-checking programs at least potentially admitted false statements.

**「Community Discussion」** twotwotwo argued that one incorrect verification is not enough to mislead mathematicians because multiple checkers and informal review must also fail, and dwheeler noted that Metamath&\#x27;s set.mm and iset.mm accept proofs only after 5 independently created verifiers in 5 different programming languages pass them. gr\_norm added that known soundness bugs are rare enough to be “comfortably more than good enough for 99.9% of software,” which is a judgment about practical risk rather than a measured guarantee.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Daniel_J._Bernstein">Daniel J . Bernstein - Wikipedia</a></li>
<li><a href="https://cr.yp.to/proofs/falseccp.html">False computer - checked proofs (djb)</a></li>

</ul>
</details>

**Tags**: `#formal verification`, `#proof assistants`, `#soundness bugs`, `#Lean`, `#Metamath`

---

<a id="item-tech-news-6"></a>
### [State attorneys general sue SpaceX and xAI over Grok sexual images](https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform) ⭐️ 7.0/10

Attorneys general Jay Jones and Rayfield filed suit against SpaceX, which the announcement identifies as the parent company of xAI and X, over allegations that the Grok model generated child sexual exploitation material and non-consensual intimate images and that the company promoted such use. The suit treats the conduct as a corporate liability problem spanning the model developer and its parent rather than only the users who submitted prompts. The supplied material does not include the complaint text, the specific legal claims, the remedies sought, or the number of states participating, and the allegations have not been tested in court.

hackernews · DeepLogin · Nov 27, 19:42 · [Discussion](https://news.ycombinator.com/item?id=50670855)

**「Background」** Earlier lawsuits have already accused xAI of creating and distributing child sexual abuse material through Grok, with reporting noting that many stemmed from a period at the start of this year when loose safeguards let users direct the chatbot to remove clothing from photos. Separate coverage of those suits said Grok&\#x27;s turn toward sexualized material was part of an effort to attract more users.

**「Why it matters」** The case tests whether a parent company can be held responsible for images produced by a subsidiary&\#x27;s model, which puts xAI&\#x27;s and X&\#x27;s image safeguards and abuse-reporting practices directly at issue. Organizations that deploy Grok&\#x27;s image features may face pressure to document their own moderation controls while the litigation proceeds, since the theory extends beyond the end user who typed the prompt.

**「From the comments」** Commenters disagreed over whether Grok was unusually permissive by default or had to be manipulated into producing such images, and one argued that liability should fall on the people making the requests rather than the company. Another commenter asserted that the Supreme Court has already ruled AI-generated child sexual abuse material made for personal consumption is protected speech; that claim was offered without citation in the thread and is not verified here.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theguardian.com/technology/2026/sep/03/elon-musk-ai-grok-child-porn-lawsuit">Child sexual abuse survivor alleges Elon Musk’s AI... | The Guardian</a></li>
<li><a href="https://nz.news.yahoo.com/teens-allege-musk-grok-chatbot-164433263.html">Teens allege Musk’s Grok chatbot made sexual images of... - Yahoo</a></li>

</ul>
</details>

**Tags**: `#AI safety`, `#generative AI`, `#content moderation`, `#regulation`, `#Grok/xAI`

---

<a id="item-tech-news-7"></a>
### [SemiAnalysis benchmarks Trainium3 inference cost against Nvidia GB300](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 7.0/10

SemiAnalysis added AWS Trainium3 to its InferenceX benchmark and published a microarchitecture analysis reporting that a Trainium3 PDS + vLLM configuration delivers better performance per TCO than every accelerator except Nvidia&\#x27;s Vera Rubin across its TCO-versus-p90-interactivity frontier. The firm says Trainium3 trades blows with, and sometimes beats, Nvidia GB300 on cost to generate tokens, and its UBenchX microbenchmarks show Trainium reaching peak HBM bandwidth utilization at small message sizes—something it says Nvidia GPUs cannot do—through Trainium Descriptor Generation Engines analogous to Nvidia TMA. The analysis attributes part of the result to Trainium&\#x27;s tile-first, ground-up ML design rather than Nvidia&\#x27;s graphics-derived GPU evolution, though the excerpt provides no absolute benchmark figures or full methodology.

rss · Semianalysis · Nov 27, 15:54

**「Background」** Nvidia&\#x27;s datacenter GPUs evolved from graphics hardware, with Volta adding Tensor Cores, Hopper adding TMA for tile data movement between HBM and SRAM, and Blackwell adding Tensor Memory for accumulation. Trainium, by contrast, was designed from the ground up for ML workloads, treating tiles as a first-class primitive rather than starting with a sea of threads and bolting on tensor compute and data-movement engines.

**「Adoption hinges on the software stack」** For teams sizing inference deployments, SemiAnalysis&\#x27;s measurement puts Trainium3 PDS with vLLM ahead of every accelerator except Vera Rubin on perf-per-TCO across its throughput-latency frontier, making AWS a credible third option alongside Nvidia and Google TPUs. Acting on that means committing to AWS&\#x27;s software path rather than CUDA: support runs through vLLM on the Neuron stack, and AWS&\#x27;s TorchNeuron, in public beta since October 20, 2026, covers eager and compiled PyTorch on Trainium2 and Trainium3 with operator-compatibility gaps and migration costs still to be weighed.

<details><summary>References</summary>
<ul>
<li><a href="https://aicybr.com/blog/aws-torchneuron-pytorch-trainium2-trainium3-beta-setup-limitations">AWS TorchNeuron: Native PyTorch on Trainium2 and... | AiCybr Blog</a></li>

</ul>
</details>

**Tags**: `#AWS Trainium`, `#AI hardware`, `#inference`, `#microarchitecture`, `#Nvidia`

---

<a id="item-tech-news-8"></a>
### [Report: AI Tool Artex Used in Attacks on US Intelligence Agencies](https://www.forbes.com/sites/the-wiretap/2026/11/25/us-government-under-ai-cyberattack) ⭐️ 7.0/10

A Telegram post relaying reporting attributed to The New York Times and Forbes says hackers used an AI tool called Artex in attacks on the CIA, the National Geospatial-Intelligence Agency and the Office of the Director of National Intelligence. The reported impact was limited to non-classified reconnaissance data, and the post described the attacks as not appearing serious. According to the post, a Chinese developer released Artex earlier this year; it was later used in multiple attacks, including one against the EU, and the developer removed it from GitHub. The post also says the FBI warned earlier this year that criminals and spies were widely using Artex.

telegram · zaihuapd · Nov 27, 10:42

**「Background」** Artex is an AI-powered penetration-testing framework that can integrate multiple AI models, including frontier and open-source systems, to probe network and computer defenses. The FBI has warned that Artex was used to automate attacks, including a ConnectWise supply-chain breach and network compromises completed in under three hours; its developer later made the tool closed-source.

**「Impact」** The reported breach reached an open-source intelligence analysis system at the CIA and unclassified information at the CIA and ODNI, so the immediate exposure is to non-classified reconnaissance data rather than classified networks.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bleepingcomputer.com/news/security/fbi-warns-artex-ai-hacking-tool-is-powering-global-cyberattacks/">FBI warns ARTEX AI hacking tool is powering global cyberattacks</a></li>
<li><a href="https://techcrunch.com/2026/11/16/fbi-says-artex-ai-open-source-hacking-tool-used-to-breach-networks-in-under-three-hours/">FBI says Artex AI open source hacking tool used to... | TechCrunch</a></li>
<li><a href="https://therecord.media/artex-ai-tool-fbi-flash-alert">FBI flash alert says Artex tool automating cyberattacks at ‘machine...</a></li>
<li><a href="https://www.cnn.com/2026/11/24/politics/cia-odni-hack-unclassified-information">CIA hit by hack impacting unclassified information - CNN</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/hackers-reportedly-breached-cia-intelligence-analysis-system/">Hackers reportedly breached CIA intelligence analysis system</a></li>
<li><a href="https://www.nytimes.com/2026/11/24/us/politics/spy-agencies-computer-network-breaches.html">U.S. Spy Agencies Suffer Breach of Some Unclassified ...</a></li>

</ul>
</details>

**Tags**: `#AI security`, `#cyberattack`, `#US intelligence`, `#open-source AI`, `#Artex`

---

<a id="item-tech-news-9"></a>
### [Minecraft Bedrock resource-pack flaw affects 26.52–26.63, fixed in 26.65](https://www.zaikei.co.jp/article/20261119/878386.html) ⭐️ 7.0/10

A resource-pack vulnerability in Minecraft Bedrock allowed packs containing a content.zipe file to modify Ore UI files and run hidden scripts, according to developer 8Crafter, who disclosed it on Reddit on November 15. The flaw affects versions 26.52 through 26.63 and may affect earlier releases; it covers PC, mobile, and console, while Java Edition is unaffected. Players joining a server or Realm with automatic resource-pack downloads enabled could receive a malicious pack without manually installing it. Mojang fixed the issue in version 26.65.

telegram · zaihuapd · Nov 27, 18:04

**「Background」** Resource packs are Bedrock&\#x27;s installable content bundles, and Ore UI is the TypeScript/React framework that drives most of the edition&\#x27;s menus, so a pack able to write into Ore UI can reach interface code rather than only textures or models. Reports describe the 26.65 release as a hotfix issued after add-on developer 8Crafter brought the flaw to public attention.

**「Impact」** On Windows, 8Crafter reported that a malicious pack could, under specific conditions, open an arbitrary URI without prompting and launch a batch file from the pack to download malware; listed effects also include deleting all saves and obtaining the player&\#x27;s IP address. AxmBro&\#x27;s Windows-only read-only detection tool can find content.zipe files but cannot determine whether a pack is malicious, so users should update to 26.65 rather than rely on detection alone.

<details><summary>References</summary>
<ul>
<li><a href="https://kaimux.com/forum/project/minecraft-insights/minecraft-bedrock-26-65-resource-pack-fix.1063">Minecraft Bedrock 26.65: the resource pack security fix | KAIMUX</a></li>
<li><a href="https://minecraft.pl/en/news/minecraft-bedrock-mojang-patches-resource-pack-security-hole">Minecraft Bedrock: Mojang patches resource pack security</a></li>

</ul>
</details>

**Tags**: `#Minecraft Bedrock`, `#security vulnerability`, `#resource packs`, `#game security`, `#Mojang patch`

---

<a id="item-tech-news-10"></a>
### [Microsoft expands in-box Windows drivers for printers, audio, and buses](https://www.techspot.com/news/114721-microsoft-wants-replace-most-third-party-device-drivers.html) ⭐️ 7.0/10

At Ignite 2026, Microsoft confirmed it is developing new drivers for entire hardware classes and shifting more reliance to in-box Windows drivers, with some third-party code potentially replaced by built-in functionality to reduce third-party code in the kernel. Printers are the first focus; the recently launched Windows Ready Print mode is intended to replace legacy third-party print drivers. Windows product manager Mehmet Kucukgoz said SoundWire and SDCA audio drivers will soon become in-box components, while I3C bus, USB Ethernet, and MIPI camera drivers are in development; Microsoft also recently introduced a Driver Quality Initiative \(DQI\) to raise reliability, quality, and security standards and encourage third-party developers and OEMs to use in-box drivers where possible.

telegram · zaihuapd · Nov 28, 02:09

**「Background」** Windows hardware drivers generally run in kernel mode, so a faulty or malicious third-party driver can crash the system or widen its attack surface; Microsoft therefore favors drivers shipped and maintained as part of Windows. The company had already introduced the Windows Ready Print mode to replace legacy third-party printer drivers, and at Ignite 2026 it said it is extending that in-box approach to audio, I3C bus, USB Ethernet, and MIPI camera classes.

**「Impact」** Printer vendors and OEMs face the most immediate change: Windows Ready Print is positioned to replace legacy third-party print drivers, so they need to verify their devices against the in-box path. For audio, I3C, USB Ethernet, and MIPI camera hardware, Microsoft is steering developers toward built-in class drivers but has not published timelines, so third-party maintainers should plan compatibility testing rather than assume an immediate cutoff.

<details><summary>References</summary>
<ul>
<li><a href="https://windowsforum.com/news/microsoft-expands-windows-11-class-drivers-to-reduce-crashes-and-kernel-risks.453854/">Microsoft Expands Windows 11 Class Drivers to Reduce Crashes ...</a></li>
<li><a href="https://www.techspot.com/news/114721-microsoft-wants-replace-most-third-party-device-drivers.html">Microsoft wants to replace most third-party device drivers ...</a></li>

</ul>
</details>

**Tags**: `#Windows drivers`, `#Microsoft`, `#kernel security`, `#hardware ecosystem`, `#driver quality`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China&\#x27;s State Council Calls for Stronger &\#x27;National Team&\#x27; Market Stabilization](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 8.0/10

A State Council executive meeting chaired by Premier Li Qiang on Nov. 27 called for greater use of the &quot;national team&quot; to stabilize China&\#x27;s capital market and for further optimizing Central Huijin&\#x27;s quasi-&quot;stabilization fund&quot; function, with sufficient liquidity to be provided. The readout also urged listed companies to increase dividends and buybacks and asked for better policies to channel long-term money — insurance, enterprise annuity and social security funds — into equities, without giving figures or a timeline.

telegram · zaihuapd · Nov 27, 05:35

**「Background」** China’s State Council executive meeting is a cabinet-level session chaired by Premier Li Qiang. The “national team” is shorthand for state-backed buyers used to support share prices, and Central Huijin’s “quasi-stabilization fund” role refers to that backstop function, which the meeting said should be further optimized.

**「Impact」** If implemented, the measures would give equity investors a stronger official backstop during selloffs and push listed companies to raise dividends and buybacks.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cls.cn/detail/2546318">cls.cn/detail/2546318</a></li>
<li><a href="https://finance.eastmoney.com/a/202611273941564045.html">finance.eastmoney.com/a/202611273941564045.html</a></li>
<li><a href="https://www.cls.cn/detail/2528462">A股，这些重要托举变量正在集聚</a></li>
<li><a href="https://pro.huxiu.com/article/4781521.html">起底救 市 旗手 中 央 汇 金 - 妙投</a></li>

</ul>
</details>

**Tags**: `#中国资本市场`, `#国常会`, `#中央汇金`, `#平准基金`, `#中长期资金入市`

---

<a id="item-finance-news-2"></a>
### [央行将大额存单个人起购门槛下调至10万元](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

中国人民银行11月27日公布《大额存单管理办法》，将个人投资人认购起点从20万元下调至不低于10万元，机构投资人从1000万元下调至不低于500万元，两个门槛均减半，新规自2027年3月21日起施行。同日央行还发布《人民币存贷款利率管理规定》，要求金融机构自主确定存贷款利率、不得通过高息揽储等不正当手段吸收存款，同样自2027年3月21日起施行。

telegram · zaihuapd · Nov 27, 11:36

**「Background」** The previous thresholds came from the 2015 interim rules, which set the individual minimum at 200,000 yuan and the institutional minimum at 10 million yuan; the new rules replace those measures and a 2016 announcement.

**「Who is affected」** Households holding 100,000–200,000 yuan in savings will become eligible for large-denomination certificates of deposit that previously required at least 200,000 yuan, while banks will be barred from using high-interest offers to attract deposits once both rules take effect on March 21, 2027.

**Tags**: `#大额存单`, `#央行监管`, `#存款利率`, `#银行业`, `#个人金融`

---