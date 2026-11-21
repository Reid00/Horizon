---
layout: default
title: "Horizon Summary: 2026-11-21 (EN)"
date: 2026-11-21
lang: en
---

> From 40 items, 13 important content pieces were selected

---

**Technology News**
1. [Thinking Machines releases Inkling 2 Mini open-weights model](#item-tech-news-1) ⭐️ 8.0/10
2. [Terry Tao Discusses Unforced Fluid Singularities and Generalized Riemann Hypothesis](#item-tech-news-2) ⭐️ 8.0/10
3. [Levent Alpöge posts claimed Claude-assisted proof of Generalized Riemann Hypothesis](#item-tech-news-3) ⭐️ 8.0/10
4. [Unverified GitHub claim of finite-time Navier–Stokes blow-up](#item-tech-news-4) ⭐️ 8.0/10
5. [KVM CVE-2026-99312 exposes AMD host memory to guests](#item-tech-news-5) ⭐️ 8.0/10
6. [arXiv Paper Claims LLMs Can Rewrite Their Own Weights](#item-tech-news-6) ⭐️ 7.0/10
7. [Signal discusses restricting AI agents from capturing mobile data](#item-tech-news-7) ⭐️ 7.0/10
8. [India&\#x27;s AI sector courts spillover as US tightens chip exports](#item-tech-news-8) ⭐️ 7.0/10
9. [Report: TSMC suspends 16nm-and-below orders from Chinese firms](#item-tech-news-9) ⭐️ 7.0/10

**Technology Blog**
1. [Why Caching LLM Outputs Barely Saves Tokens](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [Warsh wants Fed officials to talk less. Instead, they’re talking more](#item-finance-news-1) ⭐️ 7.0/10
2. [U.S. Companies Shift From Buybacks to Equity Issuance](#item-finance-news-2) ⭐️ 7.0/10
3. [Beijing Proposes Barring Deposit Deductions for Normal Wear and Tear](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Thinking Machines releases Inkling 2 Mini open-weights model](https://thinkingmachines.ai/news/inkling-2-mini/) ⭐️ 8.0/10

Thinking Machines released Inkling 2 Mini, an open-weights model built on a looped-transformer architecture and aimed at local inference. Community testers report about 27 tokens/s decode on a Ryzen 395 using llama.cpp Vulkan and about 10 tokens/s on a 32GB M1 Pro with q4 xl, and a GGUF build is said to be available for Ollama/llama.cpp. Commenters also relay that training was done end-to-end in nvfp4 and compare its benchmarks to Qwen3.8-27B, but those performance and benchmark claims have not been independently verified in the supplied material.

hackernews · jasondavies · Nov 20, 20:12 · [Discussion](https://news.ycombinator.com/item?id=50581260)

**「Background」** A looped transformer reuses its middle layers for additional passes, spending more computation per token instead of adding more unique layers; Thinking Machines says Inkling 2 Mini uses this design to reason more per token and reach answers in fewer tokens. The model is a 26B-parameter image-text-to-text mixture-of-experts system with 5.4B active parameters, according to its Hugging Face listing and Artificial Analysis.

**「Running it locally」** Local users are reporting that llama.cpp needs several unmerged PRs \(32694, 32657, 32429, 32704\), plus a small llama-graph.cpp patch one commenter says gives roughly a 30% speed boost; a GGUF build for Ollama/llama.cpp is also circulating. Reported throughput in community tests was about 27 tokens/s on a Ryzen 395 with the Vulkan backend and about 10 tokens/s on a 32GB M1 Pro at q4, though these figures are community measurements rather than independently verified results.

**「Community discussion」** Commenters report mixed local results: one called a Python CSV-sorting task successful while a coin-identification test failed after about 12,000 tokens, and another reported roughly 27 tokens/s on a Ryzen 395 with llama.cpp Vulkan plus a small patch for about a 30% speed boost. Several commenters treat the looped architecture and open weights as notable, while cautioning that the benchmark comparisons to Qwen3.8-27B depend on whether they hold up in real-world use.

<details><summary>References</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>
<li><a href="https://huggingface.co/thinkingmachines/Inkling-2-Mini">thinkingmachines/Inkling-2-Mini - Hugging Face</a></li>
<li><a href="https://artificialanalysis.ai/articles/inkling-2-mini">Thinking Machines has released Inkling 2 Mini, an open ...</a></li>

</ul>
</details>

**Tags**: `#open-weight models`, `#looped transformers`, `#local inference`, `#llama.cpp`, `#model release`

---

<a id="item-tech-news-2"></a>
### [Terry Tao Discusses Unforced Fluid Singularities and Generalized Riemann Hypothesis](https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/) ⭐️ 8.0/10

Terry Tao has published a post on unforced Euler and Navier–Stokes singularities and the generalized Riemann Hypothesis. The supplied item contains only the title, metadata, and Hacker News comments, not the post&\#x27;s argument or results, so any claimed proof or Lean verification cannot be confirmed from the available material. The Hacker News discussion frames the post around formal verification and AI-assisted mathematics.

hackernews · archon1410 · Nov 20, 17:21 · [Discussion](https://news.ycombinator.com/item?id=50578358)

**「Background」** Tao’s October 4, 2026 post examined classical solutions and singularity formation in incompressible fluids, framing the question as whether smooth initial data can evolve regularly for a time and then break down at a finite positive time. The November 20 post returns to that setting for unforced Euler and Navier–Stokes flows and links the new singularity results to the Generalized Riemann Hypothesis; a secondary summary attributes the work to Levent Alpöge, Tristan Buckmaster, and Matei Coiculescu with heavy AI assistance, though the primary post’s full methods were not supplied.

**「Community Discussion」** Commenters debated whether AI-assisted proof work can create new mathematical abstractions or mainly exploits existing ones, and one reader asked how a large Lean development can establish that it proves the intended theorem rather than a trivial statement. Another commenter reported that two independent Lean kernels accepted the result, which they said makes kernel-bug exploitation unlikely; others described mixed excitement and anxiety about AI&\#x27;s role in research.

<details><summary>References</summary>
<ul>
<li><a href="https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/">Unforced Euler singularity, unforced Navier-Stokes ...</a></li>
<li><a href="https://todayforai.com/en/items/art-87f06889-96c">Tao Reports AI-Assisted Proofs on Euler and Navier-Stokes ...</a></li>
<li><a href="https://terrytao.wordpress.com/2026/10/04/on-classical-solutions-and-singularity-formation-in-incompressible-fluids/">On classical solutions and singularity formation in ...</a></li>

</ul>
</details>

**Tags**: `#mathematics`, `#Lean theorem proving`, `#AI in mathematics`, `#formal verification`, `#research`

---

<a id="item-tech-news-3"></a>
### [Levent Alpöge posts claimed Claude-assisted proof of Generalized Riemann Hypothesis](https://alpo.ge/remark.pdf) ⭐️ 8.0/10

Levent Alpöge has posted a claim that he and Claude discovered a proof of the Riemann Hypothesis, that the method extends to the Generalized Riemann Hypothesis, and that they formalized the arguments in Lean without assumptions. He adds that he expects the Extended Riemann Hypothesis to follow with more time. The PDF is a personal announcement rather than a peer-reviewed paper; commenters report a roughly 1.3 GB, ~15 million-line Lean development and link to a purported human proof, but independent verification remains uncertain.

hackernews · iamronaldo · Nov 20, 14:16 · [Discussion](https://news.ycombinator.com/item?id=50574968)

**「Background」** The classical Riemann Hypothesis concerns the nontrivial zeros of the Riemann zeta function and asserts that they all lie on the critical line Re\(s\) = 1/2. The Generalized Riemann Hypothesis extends the same assertion to Dirichlet L-functions, which encode arithmetic information such as primes in arithmetic progressions. Lean is an interactive theorem prover that checks a proof against formal definitions and prior theorems, so a complete Lean development would be machine-checkable rather than relying on ordinary peer review alone.

**「Verification burden shifts to Lean build」** Because the argument is distributed as a roughly 1.3 GB, ~15-million-line Lean 4 development split across 14 archive parts, assessing the claim becomes a build-and-check task: mathematicians and formal-verification groups must download, compile, and audit the project rather than read a short paper, and until independent Lean checks are published the Generalized Riemann Hypothesis claim remains unverified. Commenters also point to a separate human-written proof, so anyone relying on the result should track which of the two arguments has actually been machine-checked.

**「Community discussion」** Commenters report that the Lean proof is about 1.3 GB and ~15 million lines, and one links to a separate purported human proof. Opinion is divided: one commenter says multiple formal checks leave no doubt, while another quotes Terence Tao&\#x27;s recent skepticism that current AI could tackle the Riemann Hypothesis, and others debate the pace of AI progress and a possible pause.

**Tags**: `#formal verification`, `#Lean theorem prover`, `#Riemann Hypothesis`, `#AI-assisted mathematics`, `#mathematical proof`

---

<a id="item-tech-news-4"></a>
### [Unverified GitHub claim of finite-time Navier–Stokes blow-up](https://github.com/tristanbuckmaster/navier-stokes/) ⭐️ 8.0/10

A GitHub-hosted item claims a finite-time blow-up result for the Navier–Stokes equations, a claim that would be a major mathematical result if verified. The supplied material includes no proof details, peer review, or independent confirmation, and the item is described as unverified. It is drawing attention on Hacker News, though its relevance to core software engineering and AI audiences is indirect.

hackernews · trotro · Nov 20, 15:34 · [Discussion](https://news.ycombinator.com/item?id=50576232)

**「Background」** The Navier–Stokes existence and smoothness problem asks whether smooth initial data for the three-dimensional equations can develop a singularity in finite time; it is one of the Clay Mathematics Institute&\#x27;s Millennium Prize problems. An earlier 2026 claim attributed to OpenAI reported finite-time blow-up only for a forced version of the equations, in which a smooth external force drives the flow. Tristan Buckmaster has said OpenAI began pursuing its proof after learning about his work with Anthropic researcher Levent Alpöge.

**「Verification burden」** The immediate consequence for researchers is a verification burden: the argument is a GitHub-hosted claim rather than a peer-reviewed proof, so it cannot yet be treated as settling the Navier–Stokes regularity problem. Commenters distinguish this unforced construction from OpenAI&\#x27;s earlier reported blow-up example, which relied on a designed external force, making independent checking of the construction the practical next step.

**「Community discussion」** Commenters treat the claim as potentially significant but disagree about its standing: one describes it as the “unforced” Navier–Stokes problem and says an earlier OpenAI example relied on a carefully designed external force, making this version more “realistic.” Another commenter frames the result within rumors about an Anthropic millennium-problem effort and OpenAI “scooping” the authors; these are opinions and speculation, not verified facts.

<details><summary>References</summary>
<ul>
<li><a href="https://gadgetsnow.indiatimes.com/tech-news/navier-stokes-holds-as-openai-and-anthropic-staff-clash/articleshow/133935320.cms">Navier - Stokes Holds As OpenAI And Anthropic Staff Clash</a></li>
<li><a href="https://analyticsindiamag.com/ai-news/mathematician-alleges-openai-pursued-navierstokes-breakthrough-after-learning-of-his-work">Mathematician Alleges OpenAI Pursued Navier – Stokes Breakthrough...</a></li>
<li><a href="https://news.ssbcrack.com/openai-claims-an-artificial-intelligence-solution-to-the-navier-stokes-millennium-prize-problem/">OpenAI Claims an Artificial-Intelligence Solution to the Navier – Stokes ...</a></li>
<li>Does OpenAI solve Navier-Stokes finite time blowup problem?</li>

</ul>
</details>

**Tags**: `#Navier-Stokes equations`, `#mathematics`, `#fluid dynamics`, `#research`, `#open source`

---

<a id="item-tech-news-5"></a>
### [KVM CVE-2026-99312 exposes AMD host memory to guests](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 8.0/10

A Linux KVM vulnerability, CVE-2026-99312, lets a guest virtual machine read host memory on AMD systems when nested virtualization is enabled, according to The Hacker News. Researchers reported reading about 127 GB of host memory from inside a VM on DigitalOcean. Upstream fixes were released on November 18 in stable kernel 7.3.5 and related releases, but Debian and Ubuntu kernels remain unpatched, the report says.

telegram · zaihuapd · Nov 20, 14:23

**「Background」** KVM is the hypervisor built into the Linux kernel, and nested virtualization—enabled on the affected AMD hosts—lets a guest VM run its own virtual machines. According to DigitalOcean&\#x27;s analysis, CVE-2026-99312 is a stale-pointer bug in that nested-virtualization path; Terra Security Research says the flaw remained in the kernel for just under four years and was introduced by an earlier security fix.

**「Impact」** Operators of AMD hosts that use nested virtualization should disable it until they can run a fixed kernel; Debian and Ubuntu users in particular cannot rely on their current distribution kernels, according to the report.

<details><summary>References</summary>
<ul>
<li><a href="https://www.digitalocean.com/blog/cve-2026-99312-kvm-patch">Virtualization , Responsible Disclosure, and CVE - 2026 - 99312</a></li>
<li><a href="https://www.terra.security/blog/kvm-guest-to-host-escape">KVM Guest-to- Host Escape | Terra Security Research</a></li>

</ul>
</details>

**Tags**: `#KVM`, `#Linux kernel`, `#virtualization security`, `#CVE-2026-99312`, `#AMD`

---

<a id="item-tech-news-6"></a>
### [arXiv Paper Claims LLMs Can Rewrite Their Own Weights](https://arxiv.org/abs/2611.21885) ⭐️ 7.0/10

An arXiv paper \(2611.21885\) claims a language model can rewrite its own weights through its own reasoning and improve without gradients or training, testing edits on practice problems and submitting only those that work over eight consecutive sessions, according to a commenter quoting the abstract. The Hacker News discussion treats this as a research claim rather than a demonstrated general capability. Commenters note that the only reported self-improvement was shortening reasoning traces to avoid token limits and compare the work with prior weight-space programming and Google&\#x27;s “sleep” framework.

hackernews · lwhsiao · Nov 20, 16:29 · [Discussion](https://news.ycombinator.com/item?id=50577265)

**「Background」** The claim follows recent work on weight-space programming: a November 2026 MIT CSAIL report said GPT-6 Astra edited Qwen3.5-0.8B&\#x27;s weights and raised MATH-500 accuracy from 7.9% to 48.1% by changing 0.016% of them. Google&\#x27;s sleep framework also described offline weight updates from self-generated practice examples. Those results provide the comparison point for the paper&\#x27;s claim that a model can perform this kind of editing on its own weights.

**「Impact」** For AI-safety evaluation, the discussion identifies a specific risk to test: an autonomously self-editing model could target and suppress safety- or alignment-related activations, as one commenter warns, rather than only making benign efficiency edits. The narrow trace-shortening result means developers should not yet treat self-weight-rewriting as a general self-improvement mechanism.

**「Community discussion」** Commenters disagree mainly on scope and novelty: one warns that an autonomous model could use techniques such as sparse autoencoders to identify and suppress safety-relevant activations, while others say the demonstrated edit was just reasoning-trace shortening and overlaps with prior weight-space programming and Google&\#x27;s “sleep” work. Another commenter asks whether “no training” is meaningful when the model still tests edits and keeps only those that work.

<details><summary>References</summary>
<ul>
<li><a href="https://explainx.ai/blog/weight-space-programming-gpt-6-astra-edits-qwen3-5-0-8b-weights-math-7-9-to-48-1-mit-csail-2026">GPT-6 Astra Edits Qwen Weights : MATH-500 7.9% to... | explainx.ai</a></li>
<li><a href="https://research.google/blog/the-sleep-framework-a-new-way-for-llms-to-retain-knowledge-in-continual-learning/">The sleep framework : A new way for LLMs to retain knowledge in...</a></li>

</ul>
</details>

**Tags**: `#LLM self-modification`, `#weight editing`, `#AI safety`, `#research paper`, `#Hacker News discussion`

---

<a id="item-tech-news-7"></a>
### [Signal discusses restricting AI agents from capturing mobile data](https://signal.org/blog/protecting-your-privacy/) ⭐️ 7.0/10

Signal published a blog post on protecting privacy by restricting AI agents on mobile operating systems from capturing data. The available material does not identify specific platform changes, versions, or whether the restrictions are shipped or proposed. The post prompted discussion about app permissions, platform control, and privacy tooling.

hackernews · dotcoma · Nov 20, 09:42 · [Discussion](https://news.ycombinator.com/item?id=50572348)

**「Background」** Signal says it is restricting the latest AI agents built into mobile operating systems from potentially capturing and storing Signal data. The Verge reports that this includes limiting screenshots on Android and iOS to prevent AI agents from reading users’ messages and other data.

**「Community discussion」** Commenters welcomed Signal&\#x27;s attention to AI apps&\#x27; access to chats, with one citing a Meredith Whittaker interview warning that a contact&\#x27;s AI app could still expose a conversation. Others pressed Signal to publish its forensics findings and argued that users need more control over their operating systems, while separate complaints focused on VPN/captcha friction and screenshot blocking on Windows.

<details><summary>References</summary>
<ul>
<li><a href="https://signal.org/blog/protecting-your-privacy/">Signal &gt;&gt; Blog &gt;&gt; Signal is Serious About Protecting Your Privacy</a></li>
<li><a href="https://www.theverge.com/ai-artificial-intelligence/1038390/signal-blocking-ai-agent-screenshots-mobile-app">Signal is blocking Gemini and Siri AI from reading your... | The Verge</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#mobile-security`, `#AI-agents`, `#Signal`, `#operating-systems`

---

<a id="item-tech-news-8"></a>
### [India&\#x27;s AI sector courts spillover as US tightens chip exports](https://www.bloomberg.com/news/articles/2026-11-20/nvidia-scandal-fallout-india-ai-yotta-ambani-adani-am-intelligence-e2e-networks) ⭐️ 7.0/10

The US has tightened advanced-chip exports to Malaysia, Thailand and Singapore, and India&\#x27;s AI industry sees an opening to absorb spillover demand. Yotta says it will add about 100,000 GPUs over the next year, equivalent to roughly a 10% increase in India&\#x27;s existing compute. India has 153 data centers, ranking 14th globally, while Reliance has pledged up to $110 billion and Adani $100 billion for AI infrastructure; the sector still faces long-standing compute shortages and capital constraints.

telegram · zaihuapd · Nov 20, 07:31

**「Background」** Advanced AI chips are subject to US export licensing, so access depends on which destinations Washington permits rather than on ordinary commercial demand. India enters that contest with 153 data centers—14th globally—and a long-standing shortage of compute infrastructure and capital, even as Reliance and Adani have announced large AI-infrastructure commitments.

**「Impact」** Indian AI developers and cloud buyers are unlikely to see quick relief from the export shift: Yotta&\#x27;s planned 100,000 GPUs would add only about 10% to India&\#x27;s existing compute, and Yotta has said GPU demand in India is exceeding supply. Its $12 billion expansion plan, which includes 80,000 Nvidia Vera Rubin GPUs, indicates that added capacity will depend on capital-intensive buildouts rather than the export change alone.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/02/27/india-yotta-nvidia-ai-gpu-demand-data-centers-investment.html">India’s Yotta to build $2 billion AI hub with Nvidia GPUs ...</a></li>
<li><a href="https://www.techtimes.com/articles/327395/20260912/indias-yotta-plans-80000-vera-rubin-gpus-world-leaks-hacked-customer-server.htm">India’s Yotta Plans 80,000 Vera Rubin GPUs; World Leaks ...</a></li>

</ul>
</details>

**Tags**: `#AI infrastructure`, `#semiconductor export controls`, `#India`, `#data centers`, `#GPU compute`

---

<a id="item-tech-news-9"></a>
### [Report: TSMC suspends 16nm-and-below orders from Chinese firms](https://appleinsider.com/articles/26/11/20/apple-supplier-tsmc-cuts-off-china-chip-orders-amid-tighter-export-controls) ⭐️ 7.0/10

A Telegram aggregator report says TSMC has told customers it is suspending 16nm-and-below chip orders from Chinese companies. Under the tightened U.S. export rules described in the post, supply would require a prior U.S. export license or exemption. The report, which provides no independent verification or regulatory citation, says Chinese firms are left with older 28nm and 40nm nodes and cannot obtain the high-bandwidth memory needed for AI data centers. It adds that TSMC previously assessed exemption eligibility itself but now customers must apply in advance; Apple, AMD and Nvidia are on the U.S. approved list, no Chinese companies are listed, and TSMC says it will comply.

telegram · zaihuapd · Nov 21, 02:01

**「Regulatory context」** TSMC is a contract manufacturer, so a customer’s access to a given process node depends on whether the design and end use satisfy U.S. export rules. The source says TSMC previously could assess exemption eligibility itself, but customers must now apply in advance; the U.S. approved list includes Apple, AMD and Nvidia, with no Chinese companies listed.

**「Impact」** Chinese chip designers that rely on TSMC for 16nm-and-below production must now obtain a U.S. export license or exemption before orders can proceed; the source says they are confined to 28nm and 40nm and cannot use the HBM required for AI data centers. Because the U.S. approved-customer list cited by the report includes Apple, AMD, and Nvidia but no Chinese companies, those customers face an uncertain exemption path and should plan for node or supplier changes.

<details><summary>References</summary>
<ul>
<li><a href="https://www.trendforce.com/news/2026/11/20/news-tsmc-samsung-reportedly-pause-china-consumer-chip-shipments-under-new-u-s-rules-16nm-orders-affected/">[News] TSMC , Samsung Reportedly Pause China Consumer Chip...</a></li>

</ul>
</details>

**Tags**: `#TSMC`, `#semiconductor export controls`, `#advanced process nodes`, `#China chip industry`, `#AI hardware`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Why Caching LLM Outputs Barely Saves Tokens](https://seangoedecke.com/why-output-caching-doesnt-work/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 21, 00:00

**「Background」** LLM inference economics relies on caching inputs so the full conversation history is not recomputed for every message. Sean Goedecke asks whether outputs should be cached too, since agents often repeat code snippets, evidence documents, or sample outputs that the user could otherwise read from files.

**「Solution」** The proposed fix is to fine-tune or prompt models to emit references—file line ranges or pointers into conversation history—that the harness expands transparently. But the author argues this only optimizes visible output: in his agent histories, visible output is about 6% of output tokens, while roughly 50% are reasoning tokens and 44% are tool calls. By Amdahl&\#x27;s law, even saving two-thirds of visible output would cut only about 4% of total output tokens. He is only moderately confident that frontier models rarely repeat themselves in chain of thought, and leaves possible repetition inside tool calls as an open question. The real target is the invisible 94%, which he says depends mainly on intelligence: smarter models need fewer reasoning and tool-call tokens, so a model costing 5x more per token but using 6x fewer tokens can be cheaper overall; output tokens are also costlier than input tokens because they are generated sequentially.

**「Takeaway」** The author&\#x27;s conclusion is that output caching attacks a small, visible slice of token use, and meaningful savings must come from reducing reasoning and tool-call tokens through more capable models rather than from avoiding repetition.

**Tags**: `#LLM inference`, `#output caching`, `#token economics`, `#AI agents`, `#Amdahl&\#x27;s law`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Warsh wants Fed officials to talk less. Instead, they’re talking more](https://www.cnbc.com/2026/11/20/warsh-fed-forward-guidance-rate-hikes.html) ⭐️ 7.0/10

Fed officials are speaking more frequently and sometimes conflictingly about rate hikes as Chair Kevin Warsh avoids forward guidance, deepening an FOMC divide ahead of the December meeting.

rss · CNBC Finance · Nov 20, 21:10

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#FOMC communication`, `#Kevin Warsh`

---

<a id="item-finance-news-2"></a>
### [U.S. Companies Shift From Buybacks to Equity Issuance](https://www.cnbc.com/2026/11/20/equity-issuance-bull-market-problem.html) ⭐️ 7.0/10

U.S. companies have shifted from net share buybacks to net equity issuance, with Acadian Asset Management estimating net issuance at 3.1% of total market capitalization as of late last week, a potential headwind for the four-year bull market. Anthropic&\#x27;s IPO added $81 billion of new stock at $83 a share, above its expected range, and the stock fell Friday.

rss · CNBC Finance · Nov 20, 14:15

**「Background」** Buybacks had reduced the number of shares available and lifted earnings per share, so the reversal adds supply; Acadian cites a 2000 paper by Malcolm Baker and Jeffrey Wurgler finding that heavier equity issuance was followed by lower market returns.

**「Impact」** Equity investors and the new-issue market now face more shares to absorb, the mechanism Acadian describes as a potential headwind to the bull market.

**Tags**: `#equity issuance`, `#share buybacks`, `#bull market`, `#AI infrastructure`, `#IPO market`

---

<a id="item-finance-news-3"></a>
### [Beijing Proposes Barring Deposit Deductions for Normal Wear and Tear](https://mp.weixin.qq.com/s/PmGxh5knIyxiBRhpRoJnoQ) ⭐️ 7.0/10

Beijing has proposed clarifying in a model housing lease contract that normal wear and tear from a tenant’s ordinary use cannot be deducted from the deposit. The draft, issued by the Beijing housing commission and market regulator for public comment starting on the 20th, would also require subletting rental companies to pay rent and deposits into supervised accounts.

telegram · zaihuapd · Nov 20, 13:46

**「Background」** Beijing already has a model residential lease contract \(示范文本\), a template that landlords and tenants can adopt when signing; the draft now out for comment is a revision of that template. Because it is a template rather than a stand-alone regulation, the deposit and escrow wording would take effect through the contracts parties sign, and the draft is still at the public-consultation stage.

**「Impact」** If finalized, the draft would affect Beijing renters and landlords—especially tenants of subletting agencies—by barring deposit deductions for normal wear and requiring agency-collected deposits and rent to go into supervised accounts.

**Tags**: `#北京住房租赁`, `#押金监管`, `#租户权益`, `#政策征求意见`, `#住房租赁合同`

---