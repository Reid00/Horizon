---
layout: default
title: "Horizon Summary: 2026-11-24 (EN)"
date: 2026-11-24
lang: en
---

> From 38 items, 12 important content pieces were selected

---

**Technology News**
1. [Ladybird browser enters alpha with macOS and Linux builds](#item-tech-news-1) ⭐️ 8.0/10
2. [Z.ai releases GLM-5.4, its first looped-transformer coding model](#item-tech-news-2) ⭐️ 8.0/10
3. [Anthropic posts unverified Lean 4 formalization claiming VP ≠ VNP](#item-tech-news-3) ⭐️ 8.0/10
4. [Nvidia board reinstates Jensen Huang as CEO, citing U.S. government input](#item-tech-news-4) ⭐️ 7.0/10
5. [NariQ releases 3-bit Qwen3.8-27B GGUF quants claiming BF16 quality](#item-tech-news-5) ⭐️ 7.0/10
6. [Stalwart adds Exchange/MAPI compatibility, claims drop-in replacement](#item-tech-news-6) ⭐️ 7.0/10
7. [Codex2api suspected supply-chain compromise: backdoored releases, secrets leaked](#item-tech-news-7) ⭐️ 7.0/10

**Technology Blog**
1. [Day-0 vLLM Support for ERNIE 5.5 Flash Preview](#item-tech-blog-1) ⭐️ 7.0/10

**Financial News**
1. [AI Selloff Clouds DeepSeek and Moonshot Listing Plans](#item-finance-news-1) ⭐️ 8.0/10
2. [Fed&\#x27;s Williams says more work needed to return inflation to 2%](#item-finance-news-2) ⭐️ 7.0/10
3. [Shanghai to Adjust Metro Fares for First Time in 21 Years](#item-finance-news-3) ⭐️ 7.0/10
4. [Singapore says it won&\#x27;t be a channel for evading US chip controls](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Ladybird browser enters alpha with macOS and Linux builds](https://ladybird.org/posts/alpha/) ⭐️ 8.0/10

Ladybird released its first alpha, with installable macOS and Linux builds of its from-scratch browser engine, so users no longer need to compile it themselves. The project implements most core components itself—HTML parsing, CSS, layout, JavaScript, and WebAssembly—while using HarfBuzz, Skia, ffmpeg, and SQLite for text shaping, graphics, video, and storage. The project says this is an alpha where some sites will not work and crashes will occur; a tester found service-worker-dependent Datasette Lite broken while WebAssembly and Pyodide tools worked. Ladybird&\#x27;s October 2026 newsletter reported 2,184,722 web-platform-tests subtests passed, above Safari&\#x27;s 2,172,990 and below Firefox&\#x27;s 2,189,315 and Chrome&\#x27;s 2,244,397, with a 75,650 gain that month.

hackernews · janvdberg · Nov 23, 16:13 · [Discussion](https://news.ycombinator.com/item?id=50614249)

**「Background」** Ladybird began as the browser for the SerenityOS project and still incorporates code from it; its engine implements HTML parsing, CSS, layout, JavaScript, and WebAssembly itself while using external components such as HarfBuzz, Skia, ffmpeg, and SQLite. The alpha release provides prebuilt macOS and Linux versions, so users no longer need to compile the browser themselves.

**「Impact」** The alpha gives users on macOS and Linux a concrete way to test an independent browser engine, but it is not yet a daily-driver replacement: service-worker support is incomplete, and the project explicitly asks users to report broken sites and crashes. The browser includes an in-browser broken-site report, and after a crash users can read the report and decide whether to send it.

**「Community discussion」** Commenters reported that most sites they tried rendered correctly, with one calling it a “wonderful accomplishment”; one noted slightly jerky scrolling, while another said NoVNC was snappier than in Firefox. A separate commenter argued Ladybird should take fingerprinting seriously with spoofed or randomized JavaScript values and more granular permissions, while another asked what security precautions to take while using the alpha.

**Tags**: `#browsers`, `#open-source`, `#web-engines`, `#ladybird`, `#software-releases`

---

<a id="item-tech-news-2"></a>
### [Z.ai releases GLM-5.4, its first looped-transformer coding model](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

Z.ai has released GLM-5.4, which it describes as its first model using a looped-transformer architecture, where a group of weight-shared layers runs for multiple iterations to refine hidden states and add depth without increasing parameter count. The model is not available as open weights and cannot currently be reached through Z.ai&\#x27;s regular API; access requires its Coding Plan subscription, whose API key works with the same OpenAI-compatible Responses API at https://api.z.ai/api/v1. Simon Willison tested GLM-5.4 through that route and built an llm-glm plugin because the existing llm-zai plugin did not yet support the new model. His pelican SVG comparisons put GLM-5.4&\#x27;s output close to GLM-5.3&\#x27;s, with no clear quality jump.

hackernews · foohis · Nov 23, 10:06 · [Discussion](https://news.ycombinator.com/item?id=50609685)

**「Background」** GLM-5.4 follows earlier GLM-5.x releases, but changes the architecture: a standard Transformer runs each layer once per forward pass, while a loop transformer runs a group of weight-shared layers for multiple iterations, refining hidden states and gaining effective depth without increasing the parameter count. The approach also appeared the same week in Thinking Machines Lab&\#x27;s Inkling 2 Mini, announced November 20, which was described as running the model&\#x27;s middle layers three times per token to improve reasoning on agentic coding tasks.

**「Access and deployment constraints」** Teams planning to self-host or use their existing OpenRouter or regular Z.ai API path cannot currently access GLM-5.4: it is not available as open weights, through OpenRouter, or via the regular Z.ai API plan. Access requires a Z.ai Coding Plan subscription, whose API key works with the same OpenAI-compatible Responses endpoint at https://api.z.ai/api/v1, though existing tools such as the llm-zai plugin may need updates to select the new model.

**「Community discussion」** Commenters welcomed Zhipu&\#x27;s technical transparency, with one calling looped transformers an obvious direction despite unresolved problems. Another reported that Chinese models&\#x27; long &quot;marathon thinking&quot; makes even conceptually simple tasks slow, while a third explained looped layers as a way to cut repeated HBM-to-chip weight movement during inference.

**Tags**: `#large language models`, `#transformer architecture`, `#coding models`, `#model release`, `#AI research`

---

<a id="item-tech-news-3"></a>
### [Anthropic posts unverified Lean 4 formalization claiming VP ≠ VNP](https://github.com/anthropics/formal-math/blob/main/vp-vnp/README.md) ⭐️ 8.0/10

Anthropic has published a paper and Lean 4 formalization, “VP ≠ VNP over every field,” which the repository says was discovered by an internal research Claude model and written by AI. The paper claims a superpolynomial arithmetic-circuit lower bound for the Hamiltonian-cycle polynomial, implying VP is a proper subclass of VNP and resolving Valiant’s 1979 algebraic complexity conjecture if correct; it does not address P versus NP. The repository reports an audit against three standard axioms and an independent nanoda kernel check with no \`sorry\` outside reserved files, but no human mathematician has read it through, and Lean cannot confirm that the formal statement matches the claimed theorem; Appendix Q lists discrepancies pending independent review.

telegram · zaihuapd · Nov 24, 06:02

**「Background」** VP and VNP are the algebraic analogues of P and NP, defined through arithmetic circuits over a field rather than Boolean circuits. Leslie Valiant posed VP ≠ VNP in 1979 as the algebraic counterpart to P versus NP; a separation in this setting would not by itself settle the Boolean P versus NP problem.

**「Impact」** Independent complexity theorists and Lean reviewers now need to check Appendix Q and the formal statement against the claimed theorem before treating the result as a proof of VP ≠ VNP; a passing kernel check validates only the formalized statement, not its correspondence to the advertised claim.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=UuOiRi9T-9c">Claude&#x27;s VP VNP Proof: 47 Years Open, Still Unchecked... - YouTube</a></li>

</ul>
</details>

**Tags**: `#complexity theory`, `#Lean 4`, `#formal verification`, `#AI for mathematics`, `#Anthropic`

---

<a id="item-tech-news-4"></a>
### [Nvidia board reinstates Jensen Huang as CEO, citing U.S. government input](https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo.html) ⭐️ 7.0/10

Nvidia&\#x27;s board reinstated Jensen Huang as president, CEO and board director, according to the company newsroom announcement linked in the submission. The board statement quoted in the discussion says it received input from senior levels of the U.S. government and, based on that input, is confident Huang&\#x27;s reinstatement poses no national security risk. The item is link-only and does not supply the underlying article&\#x27;s account of the sequence of events or the terms of the decision.

hackernews · jaz · Nov 23, 14:00 · [Discussion](https://news.ycombinator.com/item?id=50611576)

**「Background」** “Reinstates” indicates that Huang had previously stopped serving as CEO, but the supplied item does not describe the earlier board action or the circumstances of his departure. Nvidia’s board is the body with authority to appoint and remove the CEO, and the company’s AI chips are subject to U.S. export-control and national-security review, which is why the board’s cited government input is central to the story.

**「Board reversal limits director exposure, muddies governance」** Huang&\#x27;s reinstatement is effective immediately, closing a leadership gap that opened less than two weeks earlier when he resigned over an extramarital affair that raised national-security concerns. For Nvidia&\#x27;s directors, the board&\#x27;s stated reliance on input from senior U.S. government officials — combined, as commenters note, with a reported Justice Department decision not to prosecute — likely lowers their personal liability exposure under Delaware&\#x27;s demanding Caremark standard, though the unanimous reversal of the board&\#x27;s own recent decision leaves investors without a clear signal of how CEO tenure is actually decided at the company.

**「Community discussion」** Commenters seized on the board&\#x27;s reference to U.S. government input, debating whether it signals a national-security clearance process or improper political influence over corporate governance. Others compared the rapid reversal to OpenAI&\#x27;s 2023 board episode, arguing that a firm&\#x27;s formal governance structure may not reflect who actually holds control.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theguardian.com/technology/2026/nov/23/jensen-huang-reinstated-as-nvidia-chief-executive">Jensen Huang reinstated as Nvidia CEO | Jensen ... | The Guardian</a></li>
<li><a href="https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Board-Reinstates-Jensen-Huang-as-President-CEO-and-Board-Director/default.aspx">NVIDIA Corporation - NVIDIA Board Reinstates Jensen Huang as...</a></li>
<li><a href="https://www.latimes.com/business/story/2026-11-23/nvidia-board-jensen-huang-ceo">Nvidia board reinstates Jensen Huang . &#x27;It&#x27;s wrong, and it&#x27;s shock...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#semiconductor industry`, `#corporate governance`, `#US tech policy`, `#AI hardware`

---

<a id="item-tech-news-5"></a>
### [NariQ releases 3-bit Qwen3.8-27B GGUF quants claiming BF16 quality](https://huggingface.co/nari-labs/Qwen3.8-27B-NariQ-GGUF) ⭐️ 7.0/10

NariQ has released 3-bit, 2.5-bit, and 2-bit GGUF quantizations of Qwen3.8-27B for local inference, billed as BF16-level quality in a 10 GB file. The project&\#x27;s self-reported benchmarks show the 3-bit and 2.5-bit variants matching or slightly beating BF16 on DeepSWE \(41.0 and 41.9 vs 39.8\), Terminal-Bench 2.1 \(63.8 and 60.2 vs 62.6\), and AIME 25+26 \(98.3 and 96.5 vs 97.7\), while the 2-bit variant falls to 28.6, 52.4, and 86.0 respectively. Decode speed is described as comparable to other quants on an RTX PRO 6000, but running the files currently requires NariQ&\#x27;s llama.cpp fork.

hackernews · toebee · Nov 23, 13:42 · [Discussion](https://news.ycombinator.com/item?id=50611402)

**「Prerequisite context」** GGUF is the file format used by llama.cpp to run models locally, and quantization stores weights at lower bit widths \(here 3-bit, 2.5-bit and 2-bit\) to cut memory use at some risk of quality loss. The base model, Qwen3.8-27B, is a 27B Apache 2.0 release with a vision encoder and 262k context, and other GGUF quantizations of it already exist on Hugging Face, including the Unsloth UD-IQ3\_XXS build NariQ benchmarks against. NariQ&\#x27;s files are not drop-in for existing setups: the release states they currently require NariQ&\#x27;s own llama.cpp fork.

**「Impact」** Users cannot run these files with upstream llama.cpp yet; they must build NariQ&\#x27;s fork, adding a compatibility and maintenance step. On Apple silicon, a commenter quotes about 3.8 tok/s at 3.0 bpw on an 18 GB M3 Pro, far slower than CUDA.

**「Community discussion」** Commenters welcomed the multiple long-horizon task types and held-out evaluation, but skepticism remained: one said high-compute QAT-style quantization can overfit benchmark-like data, another argued the plots suggest most gains come from a different harness rather than the model, and a third asked what information is actually lost as file size shrinks.

<details><summary>References</summary>
<ul>
<li><a href="https://www.yottalabs.ai/post/how-to-run-qwen-3-8-27b-locally-ollama-gguf-single-gpu-2026">How to Run Qwen 3 . 8 27 B Locally: Ollama, GGUF , and... | Yotta Labs</a></li>
<li><a href="https://huggingface.co/models?other=base_model:quantized:Qwen/Qwen3.8-27B">Quantized Models for Qwen/ Qwen 3 . 8 - 27 B – Hugging Face</a></li>

</ul>
</details>

**Tags**: `#quantization`, `#LLM inference`, `#Qwen`, `#GGUF`, `#local LLMs`

---

<a id="item-tech-news-6"></a>
### [Stalwart adds Exchange/MAPI compatibility, claims drop-in replacement](https://stalw.art/blog/microsoft-exchange-replacement/) ⭐️ 7.0/10

Stalwart, an open-source mail server, announced Exchange-compatible capabilities, including MAPI support, and is positioning itself as a drop-in replacement for Microsoft Exchange for organizations and administrators running on-premises Exchange. The claim is vendor positioning rather than an independently verified equivalence, and the supplied material gives no version, pricing, or availability details. Commenters raised concrete limits, including German GoBD archiving requirements and Outlook&\#x27;s move toward cloud-only Exchange and IMAP syncing.

hackernews · shaunpud · Nov 23, 22:32 · [Discussion](https://news.ycombinator.com/item?id=50620349)

**「Background」** Stalwart is an open-source mail and collaboration server that has supported open protocols such as JMAP, IMAP4, POP3, SMTP, CalDAV, CardDAV and WebDAV. Its Exchange-replacement claim rests on version 1.2.0 adding MAPI over HTTP, Exchange Web Services, ActiveSync and Autodiscover, which let Outlook, Apple Mail and mobile devices connect to it the way they would to an Exchange server.

**「Archiving gap to plan around」** Administrators in regulated settings should budget for a separate archiving layer: a commenter notes that Stalwart&\#x27;s regular plans and OSS variants do not include the tamper-evident, non-deletable retention that German GoBD rules require for up to 10 years, so a dedicated system such as the open-source Piler would still sit alongside it. Teams weighing the &quot;drop-in&quot; claim should also test Outlook connectivity themselves, since commenters question how far the Exchange/MAPI compatibility extends as Microsoft moves new Outlook away from on-premises Exchange.

**「Community discussion」** Commenters disputed the &quot;drop-in&quot; label: rmoriz said German GoBD archiving requirements, which require tamper-proof retention for up to 10 years, are absent from Stalwart&\#x27;s regular plans and OSS variants, while traceroute66 argued Outlook integration and Microsoft&\#x27;s new Outlook IMAP-sync behavior make the claim overstated. hobo123 also questioned how customers would use Stalwart if Outlook drops on-premises Exchange support.

<details><summary>References</summary>
<ul>
<li><a href="https://stalw.art/blog/microsoft-exchange-replacement/">Stalwart is now a drop-in replacement for Microsoft Exchange | Stalwart</a></li>
<li><a href="https://github.com/stalwartlabs/stalwart">GitHub - stalwartlabs/ stalwart : All-in-one Mail &amp; Collaboration server .</a></li>
<li><a href="https://www.cateringcat.com/en/ratgeber/rechnungsnummern-gobd">Invoice numbers &amp; cancellations: GoBD basics · Catering Cat</a></li>
<li><a href="https://www.mailpiler.org/">Piler - Open Source Email Archiving</a></li>

</ul>
</details>

**Tags**: `#email`, `#open-source`, `#microsoft-exchange`, `#interoperability`, `#mail-server`

---

<a id="item-tech-news-7"></a>
### [Codex2api suspected supply-chain compromise: backdoored releases, secrets leaked](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 7.0/10

Codex2api&\#x27;s author account was reportedly compromised, and the attacker pushed tags that bypassed the main branch so the Release pipeline built and published backdoored versions; the incident write-up says v3.1.11 stripped authentication, effectively allowing unauthenticated remote command execution. A workflow in the same campaign is said to have exfiltrated 16 GitHub Actions secrets, affecting at least 21 repositories under the same account. Anyone who installed or updated to versions 3.1.10 through 3.1.12 is advised to stop using them immediately, roll back to 3.1.9, and rotate the GitHub token, SSH keys, and any database and DeepSeek API keys exposed to the project. The claims come from a community incident retrospective describing a suspected compromise rather than an independently confirmed vendor advisory.

telegram · zaihuapd · Nov 23, 11:21

**「Background」** The incident turns on how Codex2api&\#x27;s releases are built: GitHub Actions workflows triggered by version tags produced release artifacts, and those workflows had access to repository secrets. Because the attacker pushed tags rather than committing to main, the release path could be reached without going through the main branch.

**「Rollback and rotation scope」** Anyone who installed or updated Codex2api 3.1.10–3.1.12 should treat the host as compromised: v3.1.11 removed authentication, turning the service into unauthenticated remote command execution, so stopping the service and reverting to 3.1.9 is the minimum step. Because a workflow exfiltrated 16 GitHub Actions secrets and the incident reportedly reaches at least 21 repositories under the same account, credential rotation should cover the GitHub token, SSH keys, database credentials and DeepSeek and other API keys used across those repositories, not just the Codex2api project itself.

**Tags**: `#supply-chain-security`, `#security-incident`, `#github-actions`, `#remote-code-execution`, `#open-source`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Day-0 vLLM Support for ERNIE 5.5 Flash Preview](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 7.0/10

rss · vLLM Blog · Nov 24, 00:00

**「Background」** ERNIE 5.5 Flash Preview is a sparse 280B-parameter mixture-of-experts model with 14B active parameters, a 1M-token context, a thinking mode, and tool use for long-horizon agent tasks. The Baidu ERNIE and vLLM teams report day-0 support through a standalone vLLM-ERNIE plugin rather than a model-specific fork, Docker image, or nightly wheel.

**「Solution」** The plugin is installed alongside vllm==0.32.0 and loaded through vllm.general\_plugins; it registers the ERNIE architectures plus config, tokenizer, chat renderer, reasoning, and tool-call parsers, importing model code only when a config names that architecture so other models are unaffected. The plugin supplies ERNIE model code and kernels, while attention, KV cache management, speculative decoding, parallelism, and serving come from vLLM itself. To match the model’s unusual architecture, the authors designed fused kernels for VHA cross-head mixing, Multi-Router Latent MoE, gated attention, and the MultiMax output head, folding weights and FP8 quantization into precomputed kernels and reporting 1.55x–6.53x per-kernel speedups with matching numerics in the tested cases. FlashIndexer, a pluggable indexer router, selects a few sparse indexer heads per token and adds threshold pre-filtering, which the authors describe as a 40% speedup at 1M context; the router is trained on about 1B tokens by distilling the original DSA selections. The checkpoint uses FP4 quantization-aware training for routed experts and FP8 elsewhere, with a DSpark draft model that proposes up to 7 tokens and reports mean acceptance length above 4.0 on coding and agent workloads. These are vendor-reported engineering results, and the article does not include benchmark methodology or independent comparisons.

**「Takeaway」** The plugin approach lets a new model ship on day 0 without a fork while keeping model-specific kernels and vLLM core on separate release schedules. The authors’ broader claim is that architecture-aware fused kernels plus plugin registration can make a complex long-context MoE model practical on vLLM without sacrificing upstream compatibility.

**Tags**: `#vLLM`, `#ERNIE`, `#MoE inference`, `#kernel fusion`, `#speculative decoding`

---

## Financial News

<a id="item-finance-news-1"></a>
### [AI Selloff Clouds DeepSeek and Moonshot Listing Plans](https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo) ⭐️ 8.0/10

A global AI selloff that followed Anthropic&\#x27;s $119.5 billion IPO is complicating planned share sales by Chinese AI developers DeepSeek, Moonshot AI and StepFun, according to Bloomberg. The report says Chinese tech stocks have lost $1.7 trillion in market value since the end of June, with Zhipu down more than 85% from its June peak and MiniMax falling below its offer price this month.

telegram · zaihuapd · Nov 23, 09:31

**「Background」** Anthropic&\#x27;s listing was the largest IPO — initial public offering, meaning the first sale of shares to the public — on record, and it did not stop a wider selloff in AI-related stocks \(tool-1-3, tool-1-2\). Chinese peers Zhipu and MiniMax had already listed in Hong Kong in January 2026, so DeepSeek and Moonshot would be part of a second wave of Chinese AI listings \(tool-2-2\).

**「Who is affected」** If the selloff persists, DeepSeek, Moonshot AI and GigaAI could face lower valuations or delays in the share sales they are preparing, deferring any payoff for early backers and employees paid in equity.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=xfm3Vj8W1zU">Anthropic Makes Trading Debut - YouTube</a></li>
<li><a href="https://www.cnbc.com/2026/11/20/anthropic-defies-odds-holding-ipo-despite-massively-disruptive-market.html">Anthropic beats odds holding IPO despite ‘massively disruptive’ market</a></li>
<li><a href="https://blog.prompt20.com/posts/chinese-ai-labs-complete-guide/">Chinese AI Labs: The Complete Guide to DeepSeek , Qwen, Kimi...</a></li>
<li><a href="https://www.outlookbusiness.com/deeptech/deepseek-moonshot-gigaai-why-chinas-ai-startups-are-rushing-for-ipo">DeepSeek , Moonshot , GigaAI: Why China &#x27;s AI Startups Are Rushing...</a></li>

</ul>
</details>

**Tags**: `#AI selloff`, `#China AI IPOs`, `#Anthropic IPO`, `#tech stocks`, `#market disruption`

---

<a id="item-finance-news-2"></a>
### [Fed&\#x27;s Williams says more work needed to return inflation to 2%](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 7.0/10

New York Fed President John Williams said the Fed still has &quot;work to do&quot; to bring inflation back to its 2% target and that further rate increases can unfold &quot;over time.&quot; Markets fully price a quarter-percentage-point increase at the Dec. 8-9 meeting, which would lift the target range from 3.75%-4%.

rss · CNBC Finance · Nov 23, 21:02

**「Background」** Fed officials have disagreed over how quickly to raise rates, with Williams favoring a measured approach. He said he expects inflation to move closer to 2% in 2027 and reach the goal the following year, and his remarks were expected to be the last major policy statement before the December decision.

**「Impact」** If the quarter-point increase is delivered as markets expect, households and businesses with borrowing costs tied to the Fed&\#x27;s benchmark rate, such as credit-card and variable-rate loan borrowers, would pay more interest.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#interest rates`, `#John Williams`

---

<a id="item-finance-news-3"></a>
### [Shanghai to Adjust Metro Fares for First Time in 21 Years](https://weibo.com/1699432410/5368461393397183) ⭐️ 7.0/10

Shanghai announced its first metro fare adjustment in 21 years, effective Dec. 1, with a 3-yuan base fare for 0–4 km and 1 yuan added at set distance intervals thereafter, including every 15 km beyond 50 km. To limit the effect on frequent riders, it will sell 35-, 45-, 60- and 90-ride tickets for 190, 210, 270 and 390 yuan from Nov. 26 and offer a 10% discount after 90 yuan of monthly spending on the same payment channel.

telegram · zaihuapd · Nov 23, 10:45

**「Background」** Shanghai’s metro fares had gone 21 years without adjustment, so the new distance-based schedule marks the system’s first fare change since then.

**Tags**: `#Shanghai metro`, `#public transit fares`, `#fare reform`, `#commuting costs`, `#China transport policy`

---

<a id="item-finance-news-4"></a>
### [Singapore says it won&\#x27;t be a channel for evading US chip controls](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

Singapore Prime Minister Lawrence Wong said the country will not serve as a channel for companies seeking to evade US chip export controls, and that authorities are investigating Megaspeed&\#x27;s purchases of Nvidia chips. A day earlier, the US Commerce Department added Megaspeed and six other Southeast Asian firms to its trade blacklist; the Federal Register cited a significant risk that advanced computing products could be transferred to unauthorized users.

telegram · zaihuapd · Nov 24, 05:03

**「Background」** A US trade blacklist restricts exports to the listed companies; Reuters reported that Alibaba&\#x27;s Singapore subsidiary Apex Enterprise Solutions was also among the seven, and Alibaba said it had never diverted controlled advanced computing chips.

**Tags**: `#Singapore`, `#US chip export controls`, `#semiconductors`, `#Megaspeed`, `#Alibaba`

---