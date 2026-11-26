---
layout: default
title: "Horizon Summary: 2026-11-26 (EN)"
date: 2026-11-26
lang: en
---

> From 35 items, 10 important content pieces were selected

---

**Technology News**
1. [1Password says attacker pushed code to backend, stole some account data](#item-tech-news-1) ⭐️ 8.0/10
2. [Shorter Lean version of Anthropic&\#x27;s GRH proof reportedly cuts 17M lines to 76K](#item-tech-news-2) ⭐️ 8.0/10
3. [Minecraft Java 1.20.5+ exposed to RCE via resource-pack fonts](#item-tech-news-3) ⭐️ 8.0/10
4. [Aaronson post points to claimed &\#x27;nine fourths&\#x27; matrix multiplication exponent](#item-tech-news-4) ⭐️ 7.0/10
5. [Google Research posts Cogentic papers on factoring and discrete logs](#item-tech-news-5) ⭐️ 7.0/10
6. [SemiAnalysis&\#x27;s GDPx scores recent frontier models on 11 high-impact domains](#item-tech-news-6) ⭐️ 7.0/10
7. [Tencent open-sources Hy4 flash GGUF weights, down to 64GB Mac mini](#item-tech-news-7) ⭐️ 7.0/10
8. [Samsung, SK Hynix reportedly to adopt YMTC Xtacking NAND tech](#item-tech-news-8) ⭐️ 7.0/10

**Financial News**
1. [Report: US Commerce Department pressured Intel to hand over 10% stake without payment](#item-finance-news-1) ⭐️ 9.0/10
2. [US Reportedly Plans New Section 301 Tariffs on 14 Trading Partners](#item-finance-news-2) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [1Password says attacker pushed code to backend, stole some account data](https://1password.com/blog/update-on-nov-2026-security-incident) ⭐️ 8.0/10

1Password disclosed a security incident in which an attacker accessed internal systems and downloaded some customer account information: names, email addresses, account identifiers, and account creation and last-login times. The company said customer vaults and their contents were not affected. 1Password said it began investigating on Nov. 19 after signs that an employee’s corporate GitHub account had been compromised, and that the attacker used that access to reach source code and push malicious code to backend services, leading to the data download. It did not disclose how many users were affected; it said it disabled the involved account, rotated or revoked potentially exposed internal credentials, and strengthened verification codes for invitation and recovery emails, while users do not need to change their accounts but should watch for phishing.

hackernews · lxhrstn · Nov 25, 17:18 · [Discussion](https://news.ycombinator.com/item?id=50644817)

**「Background」** The incident turns on a development path rather than vault encryption: an employee’s GitHub account can provide access to source code, and code pushed to backend services can change how a hosted service handles data. 1Password’s update describes that path but does not detail the deployment controls that were in place.

**「Impact」** For 1Password customers, the exposed account metadata can make phishing messages more convincing, so unexpected login or account-related emails should be verified through 1Password directly rather than through embedded links.

**「Community discussion」** Commenters focused on the code-push path: one described a compromised employee device leading to GitHub access and production deployment as a standard SaaS breach pattern, while another asked whether branch protection or push-to-main controls were missing or bypassed—a question the update did not address. A longtime user who keeps a local-only vault said the incident reinforced concerns about hosted vaults, and another commenter reported a convincing phishing email that used details apparently tied to the breach.

**Tags**: `#security incident`, `#password managers`, `#SaaS security`, `#supply chain security`, `#phishing`

---

<a id="item-tech-news-2"></a>
### [Shorter Lean version of Anthropic&\#x27;s GRH proof reportedly cuts 17M lines to 76K](https://github.com/lsernau/grh-lean) ⭐️ 8.0/10

A new Lean repository by lsernau presents a much shorter, more readable version of Anthropic&\#x27;s GRH formal verification, with community commenters reporting a reduction from about 17 million lines to roughly 76,000 lines. The version is said to include a clear split between &quot;known math&quot; and &quot;new math&quot; plus human-readable documentation throughout. The repository is not presented as an official or peer-reviewed result, so the reduction and its long-term significance remain community-reported rather than independently validated.

hackernews · nb-t · Nov 25, 21:48 · [Discussion](https://news.ycombinator.com/item?id=50648050)

**「Background」** Lean is a proof assistant in which mathematical arguments are checked by machine, so a formalization can be verified independently of whether readers have digested the underlying proof. The original GRH verification was released as a Lean archive rather than a conventional paper; one analysis of the roughly 17.4-million-line, 175,187-file archive reported that it compiled with zero errors on a single 18-core Mac.

**「Impact」** Readers who want to inspect or build on the GRH verification have a more navigable artifact, but because the repository is unofficial and not peer-reviewed, it should not be treated as a validated replacement for the original proof without independent review.

**「Community Discussion」** Commenters welcomed the clearer known-math/new-math split and documentation, while one asked whether smarter LLMs that can golf and explain proofs already address Terence Tao&\#x27;s recent concern about huge proofs lacking insight. Another said they still want a conventional mathematical paper in which mathematicians explain the core argument.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=aDl7-MWFLVc">17 Million Lines Claim to Prove Riemann. We Ran Them. - YouTube</a></li>

</ul>
</details>

**Tags**: `#Lean`, `#formal verification`, `#proof engineering`, `#AI-assisted mathematics`, `#GRH`

---

<a id="item-tech-news-3"></a>
### [Minecraft Java 1.20.5+ exposed to RCE via resource-pack fonts](https://github.com/bikini/minecraft2shell) ⭐️ 8.0/10

A publicly disclosed exploit, minecraft2shell, shows that a crafted TrueType font in a server resource pack can trigger an out-of-bounds write in FreeType 2.14.3 and earlier and execute arbitrary code on a Minecraft Java Edition 26.3 Windows client. Minecraft Java Edition 1.20.5 through 1.21.10 and 26.1 through 26.4 snapshots are affected; 1.20.4 and earlier and Bedrock Edition are not. Mojang has no official patch and still ships lwjgl-freetype 3.4.3, while a community fix, m2sfix 1.0.0, released Nov. 24, disables hinting via a Java agent or mod.

telegram · zaihuapd · Nov 25, 12:46

**「Background」** FreeType is a font library that applications use to render TrueType fonts; Minecraft Java Edition reaches it through the LWJGL native binding lwjgl-freetype. The source says a server resource pack can supply a crafted TrueType font, and Mojang&\#x27;s client still uses lwjgl-freetype 3.4.3, with the vulnerable FreeType range being 2.14.3 and earlier.

**「Impact」** Until an official fix ships, server operators and players should set multiplayer server resource-pack permissions to &quot;Disabled&quot; or install m2sfix 1.0.0; the disclosure warns against adding any resource pack before patching.

<details><summary>References</summary>
<ul>
<li>FreeType-2.14.3 - Linux From Scratch!</li>

</ul>
</details>

**Tags**: `#security`, `#RCE vulnerability`, `#Minecraft`, `#FreeType`, `#mitigation`

---

<a id="item-tech-news-4"></a>
### [Aaronson post points to claimed &\#x27;nine fourths&\#x27; matrix multiplication exponent](https://scottaaronson.blog/?p=10379) ⭐️ 7.0/10

Scott Aaronson&\#x27;s blog post, discussed on Hacker News, points readers to a paper titled &quot;The matrix multiplication exponent is nine fourths&quot; and to a separate HN thread. For complexity-theory and algorithms researchers, the item is a pointer to a claimed result, not a verified one: the supplied excerpt contains no proof, authorship details, or independent confirmation. The hyperbolic headline reflects reaction to a purported advance, and the source does not establish any specific AI contribution.

hackernews · Kotlopou · Nov 25, 19:11 · [Discussion](https://news.ycombinator.com/item?id=50646108)

**「What the matrix multiplication exponent measures」** The matrix multiplication exponent, written ω, describes how the number of arithmetic operations required to multiply two square matrices grows as their dimensions increase; matrix multiplication itself was first described by Jacques Philippe Marie Binet in 1812 to represent composition of linear maps. The claim the blog post points to is a preprint titled &quot;The matrix multiplication exponent is nine fourths,&quot; dated November 24, 2026 and hosted in OpenAI&\#x27;s GitHub math repository, which would place ω at 2.25. The source item itself supplies only a link to that paper and to a Hacker News thread about it, so the technical substance of the result is not established by the item.

**「Community discussion」** Commenters debated what the claimed result implies: one argued that AI&\#x27;s strength in axiomatic math does not show it will solve other fields, while another said humans are underreacting to a cognitive handoff. Others asked whether Lean, MathLib, and large-scale compute without LLMs could have produced the advance, suggesting the timing may reflect corporate compute subsidies.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Matrix_multiplication">Matrix multiplication - Wikipedia</a></li>
<li><a href="https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf">math/preprints/The- matrix - multiplication - exponent -is...</a></li>
<li><a href="https://interestingengineering.com/culture/openai-exact-2-25-matrix-multiplication-exponent">OpenAI establishes exact 2.25 exponent for matrix multiplication</a></li>

</ul>
</details>

**Tags**: `#AI and mathematics`, `#matrix multiplication`, `#complexity theory`, `#Hacker News discussion`, `#Scott Aaronson`

---

<a id="item-tech-news-5"></a>
### [Google Research posts Cogentic papers on factoring and discrete logs](https://github.com/google-research/google-research/tree/master/cogentic_research_papers) ⭐️ 7.0/10

Google Research has posted a collection of papers on integer factorization, discrete logarithms, and related topics in its public google-research repository. The supplied item provides only a repository link: no abstracts, results, or independent verification are available. Hacker News discussion treats the collection as potentially significant for public-key cryptography, but the comments are largely speculative and do not establish a breakthrough.

hackernews · rgwohlbold · Nov 25, 13:33 · [Discussion](https://news.ycombinator.com/item?id=50642086)

**「Why these problems matter」** Integer factorization and discrete logarithms are the computational problems whose assumed hardness underpins much of deployed public-key cryptography. Classical algorithms for both follow a broadly similar structure — collecting congruence relations and then solving a large linear-algebra step — as described in the computational number-theory literature.

**「Impact」** Cryptography practitioners should treat the repository as a reading pointer rather than evidence of a practical attack; the supplied material contains no abstracts, results, or claims about affected key sizes or schemes.

**「Community Discussion」** Commenter fidotron said there are rumors from credible people that this is “the tip of something bigger,” while others connected the papers to broader AI-driven advances in mathematics; neither claim is substantiated in the supplied material.

<details><summary>References</summary>
<ul>
<li>[PDF] Integer factorization and discrete logarithm problems - CRIStAL</li>

</ul>
</details>

**Tags**: `#cryptography`, `#integer factorization`, `#discrete logarithms`, `#Google Research`, `#research papers`

---

<a id="item-tech-news-6"></a>
### [SemiAnalysis&\#x27;s GDPx scores recent frontier models on 11 high-impact domains](https://newsletter.semianalysis.com/p/evaluating-recent-model-releases) ⭐️ 7.0/10

SemiAnalysis has released GDPx, a benchmark for frontier models that covers 11 high-impact domains—chip design, cybersecurity, biology, finance, legal, quant trading, recursive self-improvement, hardware design, materials science, alignment, and software engineering—using 206 tasks built with 14 specialist data partners. The benchmark is deliberately hard: Opus 5.5, the highest-scoring model on release day, scored 12%, and the article uses GDPx to evaluate recent releases from Anthropic and OpenAI, Google&\#x27;s Gemini 4 series, and Alibaba and Moonshot. SemiAnalysis notes that safety classifiers on Fable 5.2 and GPT-6.2 Astra can depress scores in cyber, biology, and alignment, and also publishes an alternative leaderboard excluding those domains and using partial grading in legal and finance; the supplied excerpt does not include the final leaderboard.

rss · Semianalysis · Nov 26, 00:05

**「Background」** GDPx is a SemiAnalysis benchmark launched on November 1 that scores agentic models across 11 high-impact domains, built with 14 specialized data partners into 206 tasks. It positions itself against comprehensive benchmarks such as OpenAI&\#x27;s GDPVal and Agent&\#x27;s Last Exam, which SemiAnalysis says select domains by percentage of GDP or the O\*NET taxonomy.

**「Impact」** The headline GDPx rankings are not a clean model comparison: for Fable 5.2 and GPT-6.2 Astra, safety classifiers can suppress scores in cyber, biology, and alignment, so SemiAnalysis provides an alternative leaderboard that excludes those domains and uses partial grading in legal and finance. Readers comparing those models should use the adjusted view when the omitted domains matter.

**Tags**: `#AI benchmarks`, `#frontier models`, `#model evaluation`, `#agentic AI`, `#GDPx`

---

<a id="item-tech-news-7"></a>
### [Tencent open-sources Hy4 flash GGUF weights, down to 64GB Mac mini](https://mp.weixin.qq.com/s/o0xxShVQX6g2UllrrEv1WQ) ⭐️ 7.0/10

Tencent Hunyuan has open-sourced GGUF quantized weights for its 224B-parameter Hy4 flash model through its AngelSlim compression toolkit. The original weights are about 410.27GiB, while the smallest IQ2-AH version is 125.73GiB, roughly 30% of the original, and can run on a 64GB Mac mini using the Strata offload framework. The post reports 89 tokens per second at 10K context on a device with 48GB of VRAM, and 47 tokens per second at 32K context with the Q3\_K version on a 128GB M5 Max; it also says Q3\_K scores within 0.4 points of the original model on evaluations including DeepSWE v1.1. The post is a brief aggregator summary and does not provide the primary repository or license terms.

telegram · zaihuapd · Nov 25, 09:29

**「Background」** GGUF is a quantized model file format used for local inference; quantization lowers weight precision to shrink the file and memory footprint, with some accuracy trade-off. Offload frameworks such as Strata let a machine run a model whose weights exceed available memory by moving parts of the model between storage and compute.

**「What this means for local deployment」** The practical constraint for local users is memory capacity, not compute: Tencent&\#x27;s model card lists Hy4 flash at 220B total parameters with only 12B active per token, so the 125.73GiB IQ2-AH file still exceeds a 64GB Mac mini&\#x27;s RAM and must be streamed through Strata offload rather than held resident. Developers should treat the 64GB Mac mini result as a capacity demonstration, since the published throughput figures — 89 tokens/s at 10K context on a 48GB-VRAM device and 47 tokens/s at 32K context on a 128GB M5 Max with Q3\_K — come from hardware that fits more of the weights in fast memory. Where quality matters and 128GB is available, Q3\_K is the safer pick, as the source reports it trails the original model by no more than 0.4 points on evaluations including DeepSWE v1.1.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/tencent/Hy4-flash">tencent / Hy 4 - flash · Hugging Face</a></li>

</ul>
</details>

**Tags**: `#Tencent Hunyuan`, `#model quantization`, `#GGUF`, `#local inference`, `#Apple Silicon`

---

<a id="item-tech-news-8"></a>
### [Samsung, SK Hynix reportedly to adopt YMTC Xtacking NAND tech](https://tech.ifeng.com/c/8yLRPKxQy4L) ⭐️ 7.0/10

Samsung Electronics and SK Hynix have reportedly agreed, through cross-licensing arrangements, to use parts of Yangtze Memory Technologies&\#x27; Xtacking technology in 3D NAND flash. Xtacking manufactures the memory-cell array and the CMOS control circuitry on separate wafers and then bonds them together, allowing the two parts to be produced and optimized independently. An Omdia senior analyst said this approach lets a manufacturer make the memory array itself while assigning logic circuitry to a foundry, enabling use of more advanced processes. Samsung, SK Hynix, and YMTC all declined to comment, so the cross-licensing and adoption claims remain unconfirmed.

telegram · zaihuapd · Nov 25, 14:33

**「What Xtacking does」** Xtacking is Yangtze Memory&\#x27;s 3D NAND stacking approach: the memory cells and the CMOS control circuitry are fabricated on separate wafers and then bonded into one chip, allowing the two parts to be produced and optimized independently. The source contrasts this with conventional NAND manufacturing, where the array and control circuitry are not made on separate wafers and joined by bonding.

**「Manufacturing impact」** If the reported licensing is confirmed, Samsung and SK Hynix would bring wafer-bonding into their 3D NAND production flows: the memory array and CMOS logic are fabricated on separate wafers and joined afterward, rather than through a conventional NAND process sequence.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Yangtze_Memory_Technologies">Yangtze Memory Technologies - Wikipedia</a></li>
<li><a href="https://www.techpowerup.com/355199/samsung-and-sk-hynix-to-license-ymtcs-xtacking-technology">Samsung and SK hynix to License YMTC &#x27;s Xtacking ... | TechPowerUp</a></li>

</ul>
</details>

**Tags**: `#3D NAND`, `#semiconductor manufacturing`, `#Xtacking`, `#Samsung`, `#SK Hynix`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Report: US Commerce Department pressured Intel to hand over 10% stake without payment](https://www.wired.com/story/inside-trumps-demands-to-another-chips-ceo/) ⭐️ 9.0/10

Court filings cited by WIRED reportedly show that US Commerce Department pressure in August 2025 led Intel’s board to give the US government a 10% equity stake, now worth about $11 billion, without payment.

telegram · zaihuapd · Nov 25, 13:25

**「Background」** The pressure is described in unsealed filings from an Intel shareholder lawsuit: in an August 2025 call, a Commerce Department lawyer told Intel’s CFO that the 10% demand was not a negotiation and that rejecting it would bring consequences the administration could not predict. The filings say the demand came after Intel had received $8.9 billion in federal subsidies.

**「Impact」** The no-payment transfer makes the US government a major Intel shareholder, directly changing the chipmaker&\#x27;s ownership structure and giving officials a stake in a company central to domestic semiconductor production.

<details><summary>References</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/wired-commerce-lawyer-warned-intel-cfo-rejecting-us-10-stake-would-carry">Court records: Commerce threatened Intel CFO over 10% US stake</a></li>
<li><a href="https://www.gate.com/news/detail/us-commerce-department-threatened-intel-over-10-equity-stake-for-89b-25860002">U.S. Commerce Department Threatened Intel Over 10% Equity ...</a></li>
<li><a href="https://finance.biggo.com/news/1eea079d-982e-483f-be72-28381b50b545">Unsealed Filings Allege White House Pressured Intel Board ...</a></li>
<li><a href="https://www.cnbc.com/2025/08/22/intel-goverment-equity-stake.html">U.S. takes 10% stake in Intel Trump expands control of ... - CNBC</a></li>

</ul>
</details>

**Tags**: `#Intel`, `#US government equity stake`, `#semiconductor policy`, `#corporate governance`, `#industrial policy`

---

<a id="item-finance-news-2"></a>
### [US Reportedly Plans New Section 301 Tariffs on 14 Trading Partners](https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html) ⭐️ 8.0/10

The US is reportedly planning country-specific Section 301 tariffs on 14 trading partners, including China and the EU, over structural manufacturing overcapacity. China would face an additional 20% on top of the 25% imposed in 2018, and the new China tariff could rise to 40% if it breaches the October 2025 Busan trade truce, according to the report.

telegram · zaihuapd · Nov 25, 13:59

**「Background」** Section 301 of the Trade Act of 1974 allows the US trade representative to act against foreign practices deemed unreasonable and burdensome to US commerce; USTR has determined that the 14 economies&\#x27; manufacturing overcapacity policies are actionable and has proposed the tariffs. The possible 40% China rate is tied to the Busan truce, a one-year US-China agreement reached in October 2025 to lower tariffs and export controls.

**「Impact」** If implemented, the proposed duties would raise costs for US importers of affected manufactured goods, with Chinese products facing the reported additional 20% charge.

<details><summary>References</summary>
<ul>
<li><a href="https://ustr.gov/about/policy-offices/press-office/press-releases/2026/november/ustr-makes-determinations-and-proposes-actions-14-section-301-investigations-relating-structural">USTR Makes Determinations and Proposes Actions in 14 Section ...</a></li>
<li><a href="https://www.cfr.org/articles/united-states-and-china-agree-trade-truce">United States and China Agree to Trade Truce | Council on ...</a></li>

</ul>
</details>

**Tags**: `#US trade policy`, `#Section 301 tariffs`, `#US-China trade`, `#global trade`, `#manufacturing overcapacity`

---