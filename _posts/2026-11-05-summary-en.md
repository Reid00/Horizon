---
layout: default
title: "Horizon Summary: 2026-11-05 (EN)"
date: 2026-11-05
lang: en
---

> From 47 items, 13 important content pieces were selected

---

**Technology News**
1. [A thousand fewer paths to root](#item-tech-news-1) ⭐️ 8.0/10
2. [Tencent releases Hy4 open-weight model with science and game-dev spin-offs](#item-tech-news-2) ⭐️ 8.0/10
3. [Moonshot AI releases Kimi K3.1 Pro open weights](#item-tech-news-3) ⭐️ 8.0/10
4. [Anthropic reports progress on cryptographic proofs for LLM inference](#item-tech-news-4) ⭐️ 8.0/10
5. [Go Announces New encoding/json/v2 API](#item-tech-news-5) ⭐️ 8.0/10
6. [USTC publishes structure-guided RNA foundation model structRFM in Nature](#item-tech-news-6) ⭐️ 8.0/10
7. [AI Bug Discovery Is Exposing Decades of Security Debt, IEEE Spectrum Argues](#item-tech-news-7) ⭐️ 7.0/10
8. [OpenAI to acquire Pierre Computer Company](#item-tech-news-8) ⭐️ 7.0/10
9. [Co-op working in DOS Wing Commander after a decade of reverse engineering](#item-tech-news-9) ⭐️ 7.0/10
10. [Looped Huginn on B200: weight sharing saves storage, not HBM reads](#item-tech-news-10) ⭐️ 7.0/10
11. [Huawei tells Ascend 960DT buyers to source Samsung, SK Hynix HBM](#item-tech-news-11) ⭐️ 7.0/10
12. [Bluetooth SIG adopts HDT, raising LE peak to 7.5 Mbps](#item-tech-news-12) ⭐️ 7.0/10

**Financial News**
1. [Premarket movers: Trump Media, Tesla fall after Democratic midterm wins; Novo Nordisk rises on earnings beat](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [A thousand fewer paths to root](https://openai.com/index/a-thousand-fewer-paths-to-root/) ⭐️ 8.0/10

OpenAI&\#x27;s cybersecurity team describes work reducing Linux kernel privilege-escalation attack paths, prompting substantial technical discussion about kernel complexity and vulnerability counts.

hackernews · dangelosaurus · Nov 4, 23:33 · [Discussion](https://news.ycombinator.com/item?id=50372929)

**Tags**: `#Linux kernel`, `#privilege escalation`, `#vulnerability discovery`, `#AI security`, `#open source`

---

<a id="item-tech-news-2"></a>
### [Tencent releases Hy4 open-weight model with science and game-dev spin-offs](https://hy.tencent.ai/research/hy4) ⭐️ 8.0/10

Tencent has released Hy4, an open-weight foundation model, alongside two open-sourced scientific models: HyCell for single-cell representation and HyPDE for physical field modeling, which a quoted passage says were co-developed by Hy4 and Hyra 2.0. The release also includes adaptations for game development in Unreal Engine, Unity, and Godot, including multiplayer work, according to a Tencent passage quoted in the discussion. Tencent acknowledges in that quoted passage that Hy4 still trails top proprietary models on internal benchmarks for research-level mathematics, long-horizon coding, model self-improvement, and advanced visual question answering. The supplied material provides no independent benchmark results or license details.

hackernews · Philpax · Nov 4, 14:11 · [Discussion](https://news.ycombinator.com/item?id=50365780)

**「Prior context」** Tencent had already put out a Hy4 preview, which model-hosting listings group with its earlier text models such as the Hy-MT2 series; the new release is the full model that follows that preview. Tencent&\#x27;s announcement stated that model weights and system cards would be published &quot;in the coming days,&quot; so full open-weight availability depended on artifacts still to be posted at the time of the launch.

**「Community discussion」** Commenters welcomed the open-sourcing of HyCell and HyPDE as a contrast with closed commercial AI efforts, and one highlighted the Unreal Engine, Unity, and Godot game-development work. One practitioner reported that Hy4 landed between GPT-6.1 Sol and GPT-6.1 Terra on Plotly&\#x27;s data-analytics benchmark but was “verrrry slow,” averaging about 26 queries per question and sometimes 64.

<details><summary>References</summary>
<ul>
<li><a href="https://www.tencent.com/tencent-launches-hy4-joining-the-ranks-of-the-worlds-leading-open-source-ai-models/">Tencent Launches Hy 4 , Joining the Ranks of the... - Tencent</a></li>
<li><a href="https://openrouter.ai/tencent/hy4">Hy 4 - API Pricing &amp; Benchmarks | OpenRouter</a></li>

</ul>
</details>

**Tags**: `#open-weight models`, `#foundation models`, `#Tencent`, `#AI research`, `#game development`

---

<a id="item-tech-news-3"></a>
### [Moonshot AI releases Kimi K3.1 Pro open weights](https://huggingface.co/moonshotai/Kimi-K3.1-Pro) ⭐️ 8.0/10

Moonshot AI has published open weights for Kimi K3.1 Pro on Hugging Face, the first model in its K3.1 series. The native multimodal agent model has 2.8T total parameters with 104B active, a context window of about 1 million tokens, and weights released in MXFP4 quantization. Moonshot also offers the model through its API at platform.kimi.ai as kimi-k3.1-pro, with OpenAI- and Anthropic-compatible interfaces.

hackernews · abrarthought · Nov 4, 15:30 · [Discussion](https://news.ycombinator.com/item?id=50366999)

**「Background」** Open-weight releases publish downloadable model parameters that organizations can self-host, rather than offering the model only through a vendor API. Kimi K3.1 Pro is the first model in Moonshot AI&\#x27;s K3.1 series and is released in MXFP4 quantized form with 2.8T total parameters and 104B active parameters, so self-hosting requires substantial infrastructure while the hosted API remains an alternative.

**「Impact」** Teams can try the hosted model by switching the model identifier in OpenAI- or Anthropic-compatible clients, but self-hosting is constrained by the 2.8T-parameter footprint; one commenter estimated an 8× B300-class node would be needed. Third-party providers including OpenRouter are already listing it, and commenters report throughput differences at the same price, suggesting room for inference-cost competition.

**「Community discussion」** Commenters split on whether K3.1 Pro is “benchmaxxed”: one argued it does not clearly outperform DeepSeekV4.1-Flash and scores poorly on Hy4’s internal benchmarks, while another said their testing showed a very strong open model slightly behind the frontier. Discussion also focused on practical access, with commenters citing third-party hosting and throughput differences at the same price point.

**Tags**: `#open-weight LLMs`, `#Kimi K3.1 Pro`, `#model release`, `#inference cost`, `#benchmark debate`

---

<a id="item-tech-news-4"></a>
### [Anthropic reports progress on cryptographic proofs for LLM inference](https://www.anthropic.com/research/provable-inference) ⭐️ 8.0/10

Anthropic has published a research update on provable inference for large language models, using cryptographic commitments and proofs to make a provider&\#x27;s inference checkable by a client. The report describes research progress rather than an announced production service. Commenters quoting the post cite a commitment valid for about 16 million requests, a roughly 6.5 MB client download, and proof checking that takes 17 seconds on 24 threads or 21 seconds on one, alongside a 90–100x compute overhead that keeps the approach far from routine serving economics.

hackernews · ltononro · Nov 4, 17:17 · [Discussion](https://news.ycombinator.com/item?id=50368626)

**「Background」** Provable inference relies on cryptographic commitments to a model&\#x27;s weights plus a per-request proof that the returned output came from running exactly those weights, letting a client check the computation without redoing it. An earlier open project, VerInf, demonstrated the approach at scale: it proved a 1,093-token forward pass of the full 400-billion-parameter Llama-4-Maverick mixture-of-experts model in 19.3 hours on a single consumer NVIDIA DGX Spark, using only hash-based commitments with no trusted setup, and a Rust verifier sharing no code with the prover accepted the result. Commenter Levi Neuwirth states that he developed VerInf as a MARS fellow and that the new work draws on it with little attribution — a provenance claim the source item itself does not address.

**「Impact」** The guarantee FlashProve offers is narrow but concrete: a provider commits to a specific set of weights, and each later response is checked against that commitment, so a customer can detect a provider serving a different model than the one it committed to while the weights stay hidden. The cost falls on the verifier — a commenter quoting the post reports a client-side commitment of about 6.5 MB that covers roughly 16 million requests before the provider must re-commit, plus one proof per response whose check takes 17 seconds on 24 threads \(21 seconds single-threaded\). That makes spot audits, batch verification, and dispute resolution practical, but not inline verification of every API call in a latency-sensitive application, and it does not give users the ability to reproduce or inspect the model itself.

**「Community discussion」** Commenters raised both technical alternatives and attribution concerns: neuwirth says the work builds on his VerInf project with &quot;very little attribution,&quot; while nemo1618 argues open-weight models can be verified more cheaply by redoing deterministic inference, and vessenes says four independent providers could produce a cheaper probabilistic proof for closed models. notrealyme123 also objects that the first elaborated real-world case is aimed at stopping people from training their own models.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/JamesPetrie/VerInf">GitHub - JamesPetrie/VerInf</a></li>
<li><a href="https://github.com/JamesPetrie/VerInf/blob/main/analysis/paper.md">VerInf/analysis/paper.md at main · JamesPetrie/VerInf · GitHub</a></li>
<li><a href="https://levineuwirth.org/essays/verified-inference/">Verified Inference Between Adversaries — Levi Neuwirth</a></li>
<li><a href="https://www.anthropic.com/research/provable-inference">Progress on provable inference for large language models \ Anthropic</a></li>
<li><a href="https://interestingengineering.com/ai-robotics/anthropic-flashprove-cryptographic-model-verification">Anthropic unveils cryptographic tool to verify model outputs</a></li>
<li><a href="https://techcrunch.com/2026/11/03/anthropic-is-working-on-a-system-to-prove-ai-models-identity/">Anthropic is working on a system to prove AI models... | TechCrunch</a></li>

</ul>
</details>

**Tags**: `#verifiable inference`, `#LLM security`, `#zero-knowledge proofs`, `#AI trust`, `#cryptography`

---

<a id="item-tech-news-5"></a>
### [Go Announces New encoding/json/v2 API](https://go.dev/blog/jsonv2) ⭐️ 8.0/10

The Go project has announced \`encoding/json/v2\`, a new API for JSON handling in the standard library, via the official Go blog. The available material identifies it as a significant update to one of Go&\#x27;s most widely used packages but does not include the post&\#x27;s version, release timeline, or detailed compatibility guarantees. Go developers using \`encoding/json\` will need to assess migration, and commenters are already flagging specific friction points.

hackernews · olexsmir · Nov 4, 17:52 · [Discussion](https://news.ycombinator.com/item?id=50369106)

**「Background」** The v2 API is not entirely new: Go 1.25 shipped an experimental \`encoding/json/v2\` and \`encoding/json/jsontext\`, described in a September 2025 Go blog post. The current announcement says those packages are now stable and generally available in Go 1.27, turning the earlier experiment into a supported standard-library API.

**「Impact」** For Go teams that emit human-readable JSON, migration may require extra work: a commenter reports that the v2 equivalent of \`MarshalIndent\` is complicated and non-obvious, so code relying on that helper should be checked before switching.

**「Community discussion」** Some commenters welcomed the new API while focusing on migration costs; one specifically criticized the loss of \`MarshalIndent\` as a pain for quick, readable JSON output. Another reported using the \`jsontext\` package for clients that need specific parse errors while retaining strong performance.

<details><summary>References</summary>
<ul>
<li><a href="https://go.dev/blog/jsonv2">A new Go API for JSON - The Go Programming Language</a></li>
<li><a href="https://go.dev/blog/jsonv2-exp">A new experimental Go API for JSON - The Go Programming Language</a></li>

</ul>
</details>

**Tags**: `#Go`, `#JSON`, `#standard library`, `#API design`, `#software engineering`

---

<a id="item-tech-news-6"></a>
### [USTC publishes structure-guided RNA foundation model structRFM in Nature](https://news.ustc.edu.cn/info/1048/96798.htm) ⭐️ 8.0/10

Researchers at the University of Science and Technology of China published structRFM, a structure-guided RNA foundation model, online in Nature on November 5. The model incorporates base-pairing information from RNA secondary structure into sequence pretraining and was trained on about 21 million sequence–structure pairs. The team also reported MUSES, which integrates multiple secondary-structure predictions to reduce bias, and Zfold, a 3D structure prediction module whose performance it said was comparable to AlphaFold 3; these performance claims have not been independently verified here. The data, model weights, and code are open.

telegram · zaihuapd · Nov 5, 04:49

**「Background」** The Nature paper follows an earlier bioRxiv preprint that introduced structRFM as a structure-guided RNA foundation model pretrained on millions of RNA sequences and secondary structures, incorporating base-pairing interactions into masked language modeling through a pair-matching operation. A public GitHub repository describes the project as fully open-source.

**「Practical impact」** Because the data, weights, and code are open, RNA researchers can directly test structRFM and its Zfold module on their own targets without retraining the model. The reported parity with AlphaFold 3 is the authors&\#x27; result, however, and independent evaluations have found that AlphaFold 3&\#x27;s RNA prediction reliability varies across targets, so users should benchmark structRFM on representative test sets before relying on it for novel RNA structures.

<details><summary>References</summary>
<ul>
<li><a href="https://www.biorxiv.org/content/10.1101/2025.08.06.668731v1">A fully-open structure-guided RNA foundation model for... | bioRxiv</a></li>
<li><a href="https://github.com/heqin-zhu/structRFM">heqin-zhu/ structRFM : structRFM : A fully open structure-guided RNA ...</a></li>
<li><a href="https://www.biorxiv.org/content/10.64898/2026.11.02.763690v1">AlphaFold 3 Prediction Accuracy and Reliability across RNA ...</a></li>

</ul>
</details>

**Tags**: `#RNA foundation models`, `#AI for science`, `#RNA structure prediction`, `#open source models`, `#structural biology`

---

<a id="item-tech-news-7"></a>
### [AI Bug Discovery Is Exposing Decades of Security Debt, IEEE Spectrum Argues](https://spectrum.ieee.org/ai-in-cybersecurity-php2shell-vulnerability) ⭐️ 7.0/10

An IEEE Spectrum analysis argues that AI-driven vulnerability discovery is forcing software teams to pay down roughly 40 years of accumulated security debt, with the PHP2Shell vulnerability as a central example. The article frames the current wave of bug-finding and patching as a short-term burden that could eventually lead to more robust software, rather than as a single product release or incident. The supplied material presents this as commentary and community debate, not as an independently measured result or a new disclosure with patch details.

hackernews · pseudolus · Nov 4, 11:52 · [Discussion](https://news.ycombinator.com/item?id=50364336)

**「Background」** AI vulnerability discovery is drawing attention because it can surface flaws in code that has been trusted for years, not just in newly written features. The current discussion follows other recent decoder flaws: search results describe an October 2026 “HTTP2Shell” issue in Brotli’s C decoder, which is built into Node.js, and a Node.js security release addressing a Brotli decoder out-of-bounds write \(CVE-2026-111497\). Those cases illustrate the same pattern the IEEE Spectrum piece attributes to PHP2Shell: old, widely deployed code becoming a source of urgent patching.

**「Impact」** Software teams maintaining PHP or related HTTP/Brotli components face a heavier triage and patching burden if AI-driven discovery continues at the pace the article describes; the supplied discussion cites PHP2Shell and HTTP2Shell/Brotli2Shell but gives no versions, patch guidance, or timelines.

**「Community discussion」** Commenters largely expect short-term patching pain to produce more secure software, but they disagree on the mechanism: one argues HTTP2Shell/Brotli2Shell was arguably worse than PHP2Shell and that its timeline shows humans, not AI, sitting on vulnerabilities for months or years, while another invokes Gödel, Escher, Bach to argue that perfect security is theoretically impossible. A separate commenter says they invested in an AI security seed fund because knowledgeable people expected a wave of major security problems.

<details><summary>References</summary>
<ul>
<li>Critical &#x27;HTTP2Shell&#x27; Brotli vulnerability triggers emergency ...</li>
<li>PHP2Shell Exploit Reliability; Node.js Brotli Decode… - YouTube</li>

</ul>
</details>

**Tags**: `#AI security`, `#vulnerability discovery`, `#technical debt`, `#software security`, `#PHP`

---

<a id="item-tech-news-8"></a>
### [OpenAI to acquire Pierre Computer Company](https://openai.com/index/openai-to-acquire-pierre/) ⭐️ 7.0/10

OpenAI announced plans to acquire Pierre Computer Company, the developer-tools company associated with git-based code-storage and diff tooling. The supplied announcement is a link-only post and does not state purchase terms, a closing date, or how Pierre&\#x27;s products will be integrated. The item frames the deal around Pierre&\#x27;s git/code-storage tooling and its relevance to AI coding systems, but provides no product or availability details.

hackernews · itunpredictable · Nov 4, 15:21 · [Discussion](https://news.ycombinator.com/item?id=50366863)

**「Background」** Pierre Computer Company is the startup behind Code Storage, an AI-focused repository. OpenAI had already integrated tools from Pierre into its Codex coding platform before announcing the acquisition, so the deal extends an existing integration rather than introducing a new product.

**「Customer uncertainty」** Teams that rely on Pierre&\#x27;s API-only Code.Storage to create repositories for end users—including products such as Lovable and Bolt—face uncertainty over whether availability, pricing, or API terms will change under OpenAI ownership. The announcement provides no details on continuity or integration plans, so those customers should treat service terms as an open question until OpenAI publishes them.

**「Community discussion」** Commenters connected the deal to OpenAI&\#x27;s prior work on scaling Git and noted that Pierre was founded by Bootstrap creators Jacob Thornton and Mark Otto; one praised Pierre&\#x27;s diffs library while questioning whether such acquisitions also help build datasets around how software is made. Another commenter quoted Pierre&\#x27;s claim that Code.Storage supports large agentic workloads for customers including Lovable, Bolt, and Amp.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/openai-to-acquire-pierre/">OpenAI to acquire Pierre Computer Company , Inc. | OpenAI</a></li>
<li><a href="https://www.theverge.com/openai">OpenAI | The Verge</a></li>
<li><a href="https://www.findhost.app/code-storage/">Code Storage — Git hosting — FindHost</a></li>
<li><a href="https://bytes.dev/archives/514">Bytes #514 - The Git War of 2026</a></li>

</ul>
</details>

**Tags**: `#OpenAI`, `#acquisitions`, `#AI coding agents`, `#Git infrastructure`, `#developer tools`

---

<a id="item-tech-news-9"></a>
### [Co-op working in DOS Wing Commander after a decade of reverse engineering](https://fireflyk64.github.io/wcmulti/) ⭐️ 7.0/10

A Show HN project by daniel\_rh reports co-op multiplayer working in the DOS version of Wing Commander, allowing the author and his brother to fly the game&\#x27;s story missions together. The author says the effort began in 2015, when he noticed while playing in DOSBox that the game state fit in a 64k data segment, and that over ten years they mapped the relevant variables, injected calls into game functions, and synchronized game state over a network. The account is the author&\#x27;s own description of the project; no independent verification is provided.

hackernews · daniel\_rh · Nov 4, 18:51 · [Discussion](https://news.ycombinator.com/item?id=50369895)

**「Background」** Reverse-engineering a DOS game usually involves finding the memory locations that hold game state and then reading or modifying them while the program runs. The author says Wing Commander&\#x27;s state fit within a 64k data segment, which made systematic probing of those locations feasible.

**「Impact」** For retrocomputing and reverse-engineering readers, the project is a concrete case study in reusing a single-player DOS game&\#x27;s existing state and functions to add networked co-op without source code.

**「Community Discussion」** Commenters largely shared nostalgia for Wing Commander, while EmX\_3000 described an earlier practice of editing saved game values to identify inventory, stats, and quest state, drawing a parallel to the project&\#x27;s memory-probing method. Tepix asked why the project uses the data channel for voice instead of the RTC stream; the supplied comments do not include an answer.

**Tags**: `#reverse engineering`, `#DOS gaming`, `#multiplayer networking`, `#retrocomputing`, `#memory hacking`

---

<a id="item-tech-news-10"></a>
### [Looped Huginn on B200: weight sharing saves storage, not HBM reads](https://www.reddit.com/r/MachineLearning/comments/1xnskvt/do_looped_transformers_save_hbm_traffic_profiling/) ⭐️ 7.0/10

A blog post profiling the Huginn looped transformer on an NVIDIA B200 reports that reusing the same weights across iterations saves storage but does not by itself reduce per-iteration HBM reads. In a microbenchmark, a chain of eight matmuls sharing one 72 MiB weight ran 24% faster than eight identical copies and read almost nothing from HBM; at 288 MiB, above L2 capacity, the difference disappeared. In the full Huginn Core teaching implementation with random weights, eight iterations took about eight times as long as one and read about eight times as much data from HBM. The results come from a single B200 and a teaching implementation, so they are preliminary rather than a general claim about all looped transformers.

reddit · r/MachineLearning · /u/2dayyy6 · Nov 4, 16:26

**「Looped transformer context」** Huginn is a looped transformer that reuses the same weights across depth; a LessWrong discussion of the architecture notes it was trained with up to 32 loops and scaled to 64 loops at test time. Because those loops reapply shared parameters, analyses of looped models distinguish resident parameter counts from unrolled parameter applications, which measure computation under weight reuse. The post’s eight-iteration Huginn Core is a teaching implementation with random weights, so it profiles this reuse pattern at reduced scale.

**「Impact」** For developers building looped or recurrent-weight models, the profile indicates that weight sharing alone is not a bandwidth optimization: unless the weights are kept resident on chip—for example through a persistent kernel, which the author asks about but does not demonstrate—each iteration can still re-read them from HBM. The 72 MiB versus 288 MiB contrast also makes L2 capacity the practical boundary in this setup.

<details><summary>References</summary>
<ul>
<li><a href="https://www.lesswrong.com/posts/PLisnSFir8y5AHkmP/how-concerned-should-we-be-about-astra-s-recurrent">How concerned should we be about Astra&#x27;s recurrent architecture ?</a></li>
<li><a href="https://huskydoge.github.io/husky-blog/posts/recursive_models/towards-looped-models-done-right/">Towards Looped Models Done Right | Husky&#x27;Log</a></li>

</ul>
</details>

**Tags**: `#transformer-architectures`, `#gpu-memory-bandwidth`, `#performance-profiling`, `#looped-transformers`, `#hardware`

---

<a id="item-tech-news-11"></a>
### [Huawei tells Ascend 960DT buyers to source Samsung, SK Hynix HBM](https://thenextweb.com/news/huawei-hbm-smuggling-samsung-sk-hynix-ascend-960dt) ⭐️ 7.0/10

The Information reported that Huawei has told some customers its next flagship AI chip, Ascend 960DT, will mainly use Samsung and SK Hynix HBM and that customers must arrange memory sourcing themselves because Chinese HBM capacity is insufficient. The report describes HBM being welded to low-performance processors, declared under processor codes and shipped to Hong Kong, then carried into mainland China and removed by heating; a Shenzhen chip broker said a single HBM3E part has risen from hundreds of dollars a year ago to about $4,000. These are report claims relayed by a short aggregator post, not independently verified by the source item, and no shipment volume or customer names were provided.

telegram · zaihuapd · Nov 4, 14:52

**「Background」** High-bandwidth memory \(HBM\) is stacked DRAM used by AI accelerators; U.S. export controls restrict direct HBM supply to China, while domestic Chinese HBM production remains insufficient. Earlier reporting described HBM being packaged with low-performance processors to exploit export loopholes and routed to China, with much of that smuggled memory reaching Huawei customers.

**「Procurement burden」** For Ascend 960DT buyers, memory procurement becomes a separate, high-cost compliance task: Huawei is directing them to source Samsung and SK Hynix HBM themselves, and the report describes a grey-market route charging about $4,000 per HBM3E unit. Buyers should budget for that cost and assess export-control exposure before committing to deployments.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theinformation.com/articles/smugglers-get-expensive-memory-chips-china-south-korea">How Smugglers Get Expensive Memory Chips to China from South ...</a></li>
<li><a href="https://www.trendforce.com/news/2026/11/03/news-china-reportedly-obtains-smuggled-hbm-via-server-packages-huawei-960dt-faces-domestic-hbm-shortage/">[News] China Reportedly Obtains Smuggled HBM via Server ...</a></li>

</ul>
</details>

**Tags**: `#Huawei Ascend`, `#HBM supply chain`, `#AI chips`, `#semiconductor industry`, `#export controls`

---

<a id="item-tech-news-12"></a>
### [Bluetooth SIG adopts HDT, raising LE peak to 7.5 Mbps](https://www.bluetooth.com/press/bluetooth-high-data-throughput-opens-a-new-chapter-in-wireless-performance/) ⭐️ 7.0/10

The Bluetooth SIG announced on November 4 that it has adopted Bluetooth HDT \(High Data Throughput\), raising Bluetooth LE&\#x27;s peak rate from 2 Mbps to 7.5 Mbps—about four times—while improving capacity, energy efficiency, and reliability. HDT is an optional feature of Bluetooth Core 7.0 and can coexist with older devices. The first standardized application is high-end wireless audio with lossless and high-resolution support, expected to launch in 2027.

telegram · zaihuapd · Nov 5, 01:39

**「Background」** Bluetooth Low Energy is the low-power variant of Bluetooth, and before HDT its maximum supported bit rate was 2 Mbps. HDT is a new physical layer for Bluetooth LE rather than just an audio codec, and it is an optional feature of Bluetooth Core 7.0, allowing devices to adopt the higher rate while older products continue using existing Bluetooth LE modes.

**「Impact」** Hardware and audio developers will need to implement HDT as an optional Core 7.0 feature; the first standardized lossless/high-resolution audio use case is targeted for 2027.

<details><summary>References</summary>
<ul>
<li><a href="https://www.androidpure.com/bluetooth-hdt-high-data-throughput/">Bluetooth HDT Promises Up to 7.5 Mbps, First Audio Gear Due ...</a></li>
<li><a href="https://audioxpress.com/news/bluetooth-sig-adopts-high-data-throughput-setting-the-stage-for-standardized-lossless-wireless-audio">Bluetooth SIG Adopts High Data Throughput, Setting the Stage ...</a></li>

</ul>
</details>

**Tags**: `#Bluetooth`, `#wireless standards`, `#audio`, `#hardware`, `#Bluetooth LE`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Premarket movers: Trump Media, Tesla fall after Democratic midterm wins; Novo Nordisk rises on earnings beat](https://www.cnbc.com/2026/11/04/stocks-making-the-biggest-moves-premarket-djt-tsla-crwv-nvo.html) ⭐️ 7.0/10

Democrats won control of Congress in the midterm elections, sending Trump Media down 11% and Tesla and SpaceX lower. Novo Nordisk rose over 6% after earnings of 5.79 Danish kroner per share beat the 5.10 expected and it raised its fiscal 2026 outlook, while CVS Health fell more than 2% on a plan to split into two public companies by the first half of 2028.

rss · CNBC Finance · Nov 4, 13:32

**「Background」** The moves followed the 2026 U.S. midterms, in which Democrats won control of the House and Senate, giving Congress a check on President Trump’s policies. All 435 House seats and 35 Senate seats were contested, and voters rejected data-center measures on all but one ballot.

**「Impact」** The election results are expected to create hurdles for data-center projects, affecting AI infrastructure operators such as CoreWeave, Tesla and SpaceX.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/2026_United_States_elections">2026 United States elections - Wikipedia</a></li>
<li><a href="https://www.cnbc.com/2026/11/04/2026-midterm-election-results-live-updates.html">2026 midterm election results: House , Senate live updates</a></li>

</ul>
</details>

**Tags**: `#premarket movers`, `#earnings`, `#midterm elections`, `#data centers`, `#corporate restructuring`

---