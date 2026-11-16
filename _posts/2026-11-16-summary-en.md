---
layout: default
title: "Horizon Summary: 2026-11-16 (EN)"
date: 2026-11-16
lang: en
---

> From 36 items, 7 important content pieces were selected

---

**Technology News**
1. [Meituan open-sources LongCat-2.5, a 1.6T agent model trained on Huawei Ascend](#item-tech-news-1) ⭐️ 8.0/10
2. [Sebastian Raschka explains positional embeddings in modern LLMs](#item-tech-news-2) ⭐️ 7.0/10
3. [MacBook Pro OLED PWM flicker and flicker-sensitive users](#item-tech-news-3) ⭐️ 7.0/10
4. [Protomaps Makes Self-Hosted Map Tiles Cheap and Easy](#item-tech-news-4) ⭐️ 7.0/10
5. [Meta FAIR/NYU: Vision Encoder Pretraining Optional, Vision-Only Weights Required](#item-tech-news-5) ⭐️ 7.0/10

**Financial News**
1. [Lutnick faces scrutiny over Cantor Fitzgerald&\#x27;s Nvidia ties](#item-finance-news-1) ⭐️ 7.0/10
2. [U.S. Judge Denies Micron, Samsung and SK Hynix Bid to Dismiss DRAM Price-Fixing Suit](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Meituan open-sources LongCat-2.5, a 1.6T agent model trained on Huawei Ascend](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

Meituan&\#x27;s LongCat team published the weights for LongCat-2.5, a 1.6-trillion-parameter agent model, about a week after its official launch. The model is open-weight under the MIT license, permits commercial use, accepts text, image, and video input, and activates roughly 48 billion parameters per token. The team says training used only Chinese chips—Huawei Ascend accelerators—and no Nvidia GPUs, a vendor claim not independently verified in the supplied material. On Terminal Bench v2.1 the model scored 88.4, slightly below Claude Opus 5&\#x27;s 89.1.

telegram · zaihuapd · Nov 15, 11:08

**「Background」** LongCat-2.5 is the successor to Meituan&\#x27;s LongCat-2.0, an earlier trillion-parameter coding model that shipped with a natively supported 1M-token context window under an MIT license. The no-Nvidia claim rests on Huawei&\#x27;s Ascend line: the Ascend 910C is manufactured on SMIC&\#x27;s 7nm process and, according to one report, delivers roughly 60 percent of an Nvidia H100&\#x27;s performance per chip.

**「Impact」** The MIT license lets organizations use and modify LongCat-2.5 commercially, so teams evaluating coding agents can test it directly rather than through a proprietary API and compare results against the reported Claude Opus 5 score on Terminal Bench v2.1. Deployment still requires infrastructure sized for the full 1.6-trillion-parameter weight set, even though only about 48 billion parameters are active per token.

<details><summary>References</summary>
<ul>
<li><a href="https://thesynthesis.ai/journal/the-delivery">The Delivery: Meituan &#x27;s 1 . 6 - Trillion - Parameter AI Model Trained ...</a></li>
<li><a href="https://chatforest.com/builders-log/meituan-longcat-2-0-owl-alpha-openrouter-chinese-asic-coding-model-builder-guide/">LongCat - 2 .0: The Trillion - Parameter Coding Model... — ChatForest</a></li>

</ul>
</details>

**Tags**: `#open-source AI`, `#LLM agents`, `#Huawei Ascend`, `#model release`, `#AI hardware`

---

<a id="item-tech-news-2"></a>
### [Sebastian Raschka explains positional embeddings in modern LLMs](https://magazine.sebastianraschka.com/p/understanding-positional-embeddings) ⭐️ 7.0/10

Sebastian Raschka&\#x27;s article is a technical explainer on positional embeddings in modern large language models, aimed at AI/ML practitioners rather than announcing a new model or capability. It covers how positional information is handled in transformer architectures and includes rotary embeddings among current approaches, according to the item&\#x27;s analysis. No source text was provided, so the article&\#x27;s specific claims and examples could not be independently checked.

hackernews · vismit2000 · Nov 15, 12:14 · [Discussion](https://news.ycombinator.com/item?id=50506376)

**「Background」** The prerequisite is the distinction between absolute position tables and relative position schemes: the article traces how transformer designs moved from learned absolute position tables toward relative formulations such as RoPE inside attention. It also covers how modern architectures adapt or omit explicit positional mechanisms, providing context for the implementation walkthrough.

**「Community discussion」** Commenter programjames argued that the article focuses on implementation and that a fuller understanding requires treating positional embeddings as group representations, citing rotary embeddings as representations of the translation group. This is a theoretical framing offered in the comments, not a claim established by the article.

<details><summary>References</summary>
<ul>
<li><a href="https://magazine.sebastianraschka.com/p/understanding-positional-embeddings">Understanding Positional Embeddings in Modern LLMs</a></li>
<li><a href="https://techbytes.app/posts/understanding-positional-embeddings-in-modern-llms/">Understanding Positional Embeddings in Modern LLMs</a></li>

</ul>
</details>

**Tags**: `#positional embeddings`, `#LLMs`, `#transformer architecture`, `#rotary embeddings`, `#machine learning education`

---

<a id="item-tech-news-3"></a>
### [MacBook Pro OLED PWM flicker and flicker-sensitive users](https://macanorak.com/the-macbook-pros-oled-pwm-problem-when-a-better-display-becomes-worse-to-use/) ⭐️ 7.0/10

A MacAnorak analysis examines PWM flicker in the MacBook Pro&\#x27;s OLED display and argues that a panel can be technically better on image quality while being worse for flicker-sensitive users. The article centers on the display&\#x27;s PWM behavior and frames the issue as an accessibility tradeoff rather than a simple defect. Its frequency claims are contested in the accompanying discussion.

hackernews · MacAnorak · Nov 15, 13:15 · [Discussion](https://news.ycombinator.com/item?id=50506719)

**「PWM dimming context」** PWM dimming is not the same as refresh rate: it rapidly switches the display&\#x27;s light output on and off to lower brightness, and flicker-sensitive users can perceive that modulation as eye strain, headaches, or nausea. Notebookcheck&\#x27;s lab test of the new 14-inch MacBook Pro, reported in early November 2026, measured 240 Hz PWM whenever brightness was set to 99% or lower, with roughly 56% flicker depth; AppleInsider reported the same 240 Hz rate and 56% amplitude.

**「Impact」** Flicker-sensitive buyers should treat the OLED panel as a compatibility risk rather than a straightforward upgrade, and the article gives them PWM frequency as a concrete specification to check before purchase.

**「Community Discussion」** Commenters dispute the 240Hz PWM figure: one says the article&\#x27;s source suggests 480Hz worst case and possibly 960Hz effective because the tandem OLED layers are driven out of phase, while others broaden the thread to CRI, motion blur, and post-concussion screen sensitivity. The discussion mixes measurement questions with personal experience and does not establish a consensus.

<details><summary>References</summary>
<ul>
<li><a href="https://www.appleheadlines.com/macbook-pro-oled-eye-strain-pwm-flicker/">MacBook Pro OLED Eye Strain &amp; PWM Flicker: 7 Moves - AH</a></li>
<li><a href="https://appleinsider.com/articles/26/11/10/if-youre-getting-dizzy-using-proled-macbook-pro-you-are-not-alone">Pulse width modulation on MacBook Pro with PROLED - AppleInsider</a></li>

</ul>
</details>

**Tags**: `#OLED`, `#PWM flicker`, `#MacBook Pro`, `#display hardware`, `#accessibility`

---

<a id="item-tech-news-4"></a>
### [Protomaps Makes Self-Hosted Map Tiles Cheap and Easy](https://bruceroettgers.eu/blog/protomaps/) ⭐️ 7.0/10

A practical blog post explains how Protomaps makes self-hosted map tiles inexpensive and accessible for developers, with PMTiles as the underlying format. It is a tooling and infrastructure resource rather than a product announcement, and the supplied material provides no version, pricing, or benchmark figures. In the Hacker News thread, commenters point to OpenFreeMap as a similar project with a free public instance and describe using Protomaps for a live-rendered walking game and for private map infrastructure behind Cloudflare R2.

hackernews · bcye · Nov 15, 19:26 · [Discussion](https://news.ycombinator.com/item?id=50509837)

**「Background」** Protomaps&\#x27; PMTiles format stores a pyramid of map tiles in a single-file archive that can be hosted on commodity object storage such as S3, rather than requiring a custom tile server or third-party provider. Clients fetch the needed portions through HTTP range requests, which is what makes low-cost, zero-maintenance self-hosting possible.

**「Impact」** The reported caveat is storage: basemaps are small enough to host cost-effectively, but high-resolution satellite imagery grows expensive quickly. One developer capped a North America satellite mosaic at zoom level 17 because of projected storage requirements and said global high-resolution coverage can reach hundreds of terabytes.

**「Community discussion」** Commenters offered alternatives and implementation notes: OpenFreeMap was cited as a similar project whose public instance has no request limits, registration, API keys, or cookies, while another commenter reported that PMTiles tiles larger than 128 MB and some raster formats were failing in their viewer. A Cartes.app commenter said the project used to pay Maptiler, though the supplied excerpt cuts off before the comparison is complete.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/protomaps/PMTiles">GitHub - protomaps/PMTiles: Pyramids of map tiles in a single ...</a></li>
<li><a href="https://protomaps.com/">Protomaps - The open source map in a file</a></li>
<li><a href="https://docs.protomaps.com/pmtiles/">PMTiles Concepts | Protomaps Docs</a></li>

</ul>
</details>

**Tags**: `#Protomaps`, `#map tiles`, `#self-hosting`, `#open source`, `#PMTiles`

---

<a id="item-tech-news-5"></a>
### [Meta FAIR/NYU: Vision Encoder Pretraining Optional, Vision-Only Weights Required](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 7.0/10

A Reddit post by a co-author describes a Meta FAIR + NYU study that trained more than 200 multimodal LLMs from scratch on the same data to separate three choices usually bundled in a vision encoder: separate pretraining, vision-only parameters, and placement before the LLM. Using Qwen3-1.7B and 4B backbones with 0.4B vision parameters, a 0.6B–6.4B scaling ladder, 16 Cambrian VQA benchmarks at 448 px, and 12 language benchmarks, the authors report that encoder pretraining is optional at matched lifetime compute, while vision-only parameters are required: encoder-free models trail at every size and need about 3x the compute to catch up. They also report that placement is optional—an “in-fusion” design with zero-initialized vision-only weights in the LLM’s first eight layers matches the encoder from 1.7B to 6.4B with about 13% lower time to first token—though these are author-reported results from a Reddit post and linked paper, not independently verified here.

reddit · r/MachineLearning · /u/trungh98 · Nov 15, 17:38

**「Background」** Most multimodal language models route images through a pretrained vision encoder placed ahead of the language backbone, while some recent recipes train that encoder from scratch alongside the LLM or remove it entirely. As the paper&\#x27;s framing notes, the standard design bundles three separable choices — an upstream visual prior from pretraining, parameters used only by vision tokens, and pre-fusion placement before the multimodal backbone — and because published models also differ in data, architecture, and compute, comparing them cannot isolate which of the three actually matters.

**「Impact」** For MLLM developers, the reported ablation suggests separate vision-encoder pretraining and a pre-LLM encoder can be dropped without losing VQA accuracy at matched compute, but vision-only capacity should be preserved; the authors’ in-fusion alternative is the concrete option, claiming parity from 1.7B to 6.4B and about 13% lower time to first token. The caveat is scope: the evidence covers 448 px Cambrian VQA and 12 language benchmarks on the listed Qwen3 backbones, so teams should validate on their own resolution, data, and latency setup before treating the result as a general recipe.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/pdf/2611.17334v1">Unbundling Multimodal Vision Encoding - arXiv.org</a></li>
<li><a href="https://huggingface.co/papers/2611.17334">Paper page - Unbundling Multimodal Vision Encoding</a></li>

</ul>
</details>

**Tags**: `#multimodal LLMs`, `#vision encoders`, `#model pretraining`, `#scaling experiments`, `#research paper`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Lutnick faces scrutiny over Cantor Fitzgerald&\#x27;s Nvidia ties](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 7.0/10

CNBC reported that Commerce Secretary Howard Lutnick faces questions over his former firm Cantor Fitzgerald&\#x27;s ties to Nvidia, after the firm reported a 49% decline in the Nvidia shares it held between September 2025 and March 2026 — a period when U.S. intelligence officials were pressing Lutnick to crack down on suspected Nvidia chip smuggling to China. CNBC said there is no evidence of wrongdoing, and Cantor said its Nvidia positions were immaterial and entered into in the ordinary course of client swap transactions.

rss · CNBC Finance · Nov 15, 19:58

**「Background」** Howard Lutnick ran the Wall Street firm Cantor Fitzgerald until he became Commerce Secretary in February 2025, and Commerce is the department that administers the entity list, which restricts which foreign companies may buy U.S. technology. Cantor is now led by his sons Brandon and Kyle, and the scrutiny follows Nvidia CEO Jensen Huang&\#x27;s resignation on Thursday amid questions about his ties to a suspected Chinese spy.

**「What happens next」** The dispute is moving to Congress: Commerce Secretary Howard Lutnick is due to testify before the Senate about his agency&\#x27;s handling of AI-chip export controls, putting the licensing decisions that govern Nvidia&\#x27;s China sales and its customers under public scrutiny.

<details><summary>References</summary>
<ul>
<li><a href="https://nypost.com/2026/11/13/business/howard-lutnick-to-testify-before-senate-on-nvidia-megaspeed-fiasco/">Howard Lutnick to testify before Senate on Nvidia , Megaspeed fiasco</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#export controls`, `#conflict of interest`, `#Commerce Department`, `#China chip smuggling`

---

<a id="item-finance-news-2"></a>
### [U.S. Judge Denies Micron, Samsung and SK Hynix Bid to Dismiss DRAM Price-Fixing Suit](https://www.tomshardware.com/tech-industry/big-tech/judge-denies-motion-to-dismiss-dram-price-fixing-lawsuit-against-micron-samsung-and-sk-hynix-says-chipmakers-acted-like-hawks-flying-in-formation-finds-evidence-of-dram-collusion-plausible-after-500-percent-price-surge) ⭐️ 7.0/10

U.S. judge Noël Wise denied a motion by Micron, Samsung and SK Hynix to dismiss a DRAM price-fixing class action, finding the plaintiffs&\#x27; collusion allegations plausible. The 17 individual and small-business plaintiffs allege the three suppliers made four parallel moves within a year to restrict DRAM supply, pushing prices up by as much as 500%; the companies must respond by Dec. 7, with a case management conference set for January 2027.

telegram · zaihuapd · Nov 15, 16:39

**「Background」** The ruling came at the motion-to-dismiss stage in a proposed class action by 17 individuals and small businesses, so it keeps the case alive without deciding whether Micron, Samsung and SK Hynix actually fixed DRAM prices.

**「Impact」** The ruling keeps the class action alive, so the three suppliers face continued litigation costs and potential damages claims from buyers alleging overcharges; the decision does not establish liability.

<details><summary>References</summary>
<ul>
<li><a href="https://www.tomshardware.com/tech-industry/big-tech/judge-denies-motion-to-dismiss-dram-price-fixing-lawsuit-against-micron-samsung-and-sk-hynix-says-chipmakers-acted-like-hawks-flying-in-formation-finds-evidence-of-dram-collusion-plausible-after-500-percent-price-surge">Judge denies motion to dismiss DRAM price - fixing lawsuit against...</a></li>
<li><a href="https://litnews.ai/articles/garciaguirre-samsung-sk-hynix-micron-dram-conspiracy-suit-survives-dismissal">Judge Refuses to Dismiss DRAM Supply Conspiracy Suit Against...</a></li>

</ul>
</details>

**Tags**: `#DRAM`, `#antitrust`, `#Micron`, `#Samsung`, `#SK Hynix`

---