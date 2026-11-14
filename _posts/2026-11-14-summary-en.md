---
layout: default
title: "Horizon Summary: 2026-11-14 (EN)"
date: 2026-11-14
lang: en
---

> From 40 items, 7 important content pieces were selected

---

**Technology News**
1. [Report: TorchTitan scales 1T MoE to 384 GH200 GPUs](#item-tech-news-1) ⭐️ 8.0/10
2. [Live Airband Service from KORS Demodulates Full Band on Dual GPUs](#item-tech-news-2) ⭐️ 7.0/10
3. [Python early contributor Tim Peters dies at 74](#item-tech-news-3) ⭐️ 7.0/10
4. [Global Microsoft Outlook, Teams and Copilot outage exceeds 12 hours](#item-tech-news-4) ⭐️ 7.0/10
5. [DeepSeek opens app API with search, files, voice, and tool orchestration](#item-tech-news-5) ⭐️ 7.0/10
6. [OpenAI launches ChatGPT Wallet for agent payments in the US](#item-tech-news-6) ⭐️ 7.0/10

**Financial News**
1. [Chicago Fed&\#x27;s Goolsbee Says Central Bank Has &\#x27;Work to Do&\#x27; on Inflation](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Report: TorchTitan scales 1T MoE to 384 GH200 GPUs](https://www.reddit.com/r/MachineLearning/comments/1xvce5h/scaling_to_1t_moe_on_torchtitan_p/) ⭐️ 8.0/10

A Reddit post reports that a team working with TorchTitan and PyTorch maintainers trained a ~1T-parameter mixture-of-experts model on 384 GH200 GPUs at about 1,300 tokens/s per GPU, a 14X improvement over its starting point. The setup used 384-way FSDP plus 4-way expert parallelism kept inside each node, with full activation checkpointing, Grace CPU offload, Muon, and FlexShard whole-expert sharding. The post is a community engineering report, not a formal publication, and the supplied text is truncated; it describes lessons rather than an independently verified benchmark.

reddit · r/MachineLearning · /u/f14-bertolotti · Nov 13, 16:28

**「Background」** TorchTitan is PyTorch&\#x27;s native framework for training large models, including mixture-of-experts architectures at scale. A 1T-parameter MoE cannot fit on a single GPU, so the reported run relies on sharding techniques such as FSDP and expert parallelism across GH200 GPUs.

**「Impact」** Teams training large MoEs with FSDP2 on Hopper clusters can reuse the reported tactics—whole-expert sharding for Muon, bf16 all-to-all gradient reduction with local fp32 accumulation, and moving collective temporaries to the compute stream—but the last fix depends on FSDP2&\#x27;s private \`unshard\_async\_op\` flag, which the post says is only on its way to becoming a public API.

<details><summary>References</summary>
<ul>
<li><a href="https://www.infoq.com/news/2026/10/google-meta-torchtpu/">PyTorch Conference 2026: Google and Meta Open-Source... - InfoQ</a></li>

</ul>
</details>

**Tags**: `#mixture-of-experts`, `#distributed training`, `#PyTorch`, `#GPU scaling`, `#large language models`

---

<a id="item-tech-news-2"></a>
### [Live Airband Service from KORS Demodulates Full Band on Dual GPUs](https://orcasairband.com/) ⭐️ 7.0/10

A live airband listening service at orcasairband.com is monitoring the full airband from KORS and publishing real-time demodulated transmissions. The creator says the setup uses an ETTUS B210 SDR attached to a dual RTX 4090 machine, with a GPU polyphase channelizer and CUDA demodulation to process the entire band in real time. The site drew attention alongside the creator&\#x27;s raw, unedited transcripts of ground-stop-related chatter on Victoria Ground 126.400 and Vancouver Centre 134.800; those transcripts are not independently verified.

hackernews · mmaunder · Nov 13, 22:04 · [Discussion](https://news.ycombinator.com/item?id=50490593)

**「Background」** Airband voice traffic sits in the VHF band just above 118 MHz, split into many narrow, amplitude-modulated channels for tower, ground, approach and centre controllers. A wideband SDR such as the Ettus B210 captures a large contiguous slice of that spectrum at once, after which a polyphase channelizer — here run on CUDA across two RTX 4090 GPUs — splits the capture into individual channels and demodulates them. A ground stop, the condition the transcripts describe, halts departures into a given airport, so the relevant instructions and reasoning pass over the radio rather than through any public feed.

**「Impact」** For listeners, the service exposes any airband channel in the KORS feed without retuning a scanner, but it depends on one receiver and GPU host, so coverage and availability are tied to that single site. Developers evaluating wideband SDR should treat the GPU channelizer as a demonstrated hobby implementation, not a benchmarked or independently tested platform.

**「Community Discussion」** Commenters focused on the implementation and the live ground-stop audio: one pointed to a timestamped exchange confirming a Vancouver ground stop, while another compared the setup with a prior KiwiSDR-based project that decoded ship DSC signals and explored multi-receiver triangulation. A listener also remarked on how garbled many transmissions sound, a useful caveat that the feed is raw radio audio rather than a cleaned official channel.

**Tags**: `#software-defined radio`, `#GPU acceleration`, `#CUDA`, `#real-time signal processing`, `#aviation communications`

---

<a id="item-tech-news-3"></a>
### [Python early contributor Tim Peters dies at 74](https://x.com/Itsfoss/status/2120957452937998716) ⭐️ 7.0/10

Tim Peters, an early Python contributor, has died at 74, Python creator Guido van Rossum announced. Peters was Python&\#x27;s second real user, wrote the Timsort sorting algorithm and the Zen of Python \(PEP 20\), and served 13 years on the Python Software Foundation board.

telegram · zaihuapd · Nov 13, 09:55

**「Background」** PEP 20 is the Python Enhancement Proposal that records the “Zen of Python,” a set of design aphorisms for the language. Timsort is a sorting algorithm that Peters contributed to Python’s standard library.

**Tags**: `#Python`, `#open source community`, `#Tim Peters`, `#Timsort`, `#obituary`

---

<a id="item-tech-news-4"></a>
### [Global Microsoft Outlook, Teams and Copilot outage exceeds 12 hours](https://www.reuters.com/technology/microsoft-365-outlook-down-thousands-us-users-downdetector-shows-2026-11-12/) ⭐️ 7.0/10

Microsoft Outlook, Teams and Copilot remained disrupted globally on November 13 for more than 12 hours, affecting enterprise and government communications. Microsoft attributed the outage to a server problem, said it found no malicious activity, and reported that it had widened remediation and was seeing signs of stabilization. It was the second Microsoft 365 service interruption this year, according to the report.

telegram · zaihuapd · Nov 13, 12:21

**「Background」** Microsoft 365 is a subscription suite of cloud-hosted productivity and communication services that includes Outlook, Teams, and Copilot. The source notes that this was the second Microsoft 365 service disruption this year, but it does not describe the earlier incident.

**「Impact」** Some Australian, Japanese and U.S. government agencies were affected, Euronext&\#x27;s email was disrupted, and financial institutions in Taiwan switched to fax to confirm trades, showing that affected organizations needed manual fallbacks while Microsoft&\#x27;s recovery was incomplete.

**Tags**: `#Microsoft 365`, `#service outage`, `#cloud reliability`, `#enterprise communications`

---

<a id="item-tech-news-5"></a>
### [DeepSeek opens app API with search, files, voice, and tool orchestration](https://mp.weixin.qq.com/s/78KBHc4-4N5b2vfL9SkutQ) ⭐️ 7.0/10

DeepSeek announced a full-suite application API that lets developers enable parameters in its existing API to add deep-thinking search, file input, link reading, and voice to conversations, with the server handling tool calls and context assembly. The V4.1-Flash model is supported on three endpoints, and Search, Fetch, OCR, ASR, and TTS can each be called separately. DeepSeek also open-sourced a chat frontend demo, deepseek-ai/chat-demo, that can import past conversations and be deployed locally; the brief announcement gave no pricing, rate-limit, or detailed API-behavior information.

telegram · zaihuapd · Nov 13, 14:27

**「Background」** DeepSeek already exposes its models through an API; this update adds application-level capabilities that developers enable through parameters in that existing API. Instead of orchestrating each tool themselves, developers can let DeepSeek&\#x27;s servers perform tool calls and assemble the resulting context for search, file input, link reading, and voice interactions. The separately callable Search, Fetch, OCR, ASR, and TTS services, along with the open-source chat demo, make those building blocks available outside the bundled chat flow.

**「Impact」** Developers can now opt into DeepSeek&\#x27;s app-level tool orchestration through API parameters, so search, file reading, link fetching, and voice handling no longer require a separately built pipeline; teams needing finer control can instead call Search, Fetch, OCR, ASR, and TTS individually. The trade-off is that the built-in path runs tool calls and context assembly server-side, and V4.1-Flash is supported on only three interfaces, so existing integrations should verify model and endpoint compatibility before switching.

<details><summary>References</summary>
<ul>
<li><a href="https://api-docs.deepseek.com/news/news261113/">The full DeepSeek App experience, now via API | DeepSeek API Docs</a></li>

</ul>
</details>

**Tags**: `#DeepSeek`, `#AI APIs`, `#tool use`, `#open-source demo`, `#multimodal AI`

---

<a id="item-tech-news-6"></a>
### [OpenAI launches ChatGPT Wallet for agent payments in the US](https://openai.com/index/introducing-chatgpt-wallet/) ⭐️ 7.0/10

OpenAI has launched ChatGPT Wallet, a payment feature that lets AI agents make purchases through partnerships with American Express, Mastercard, and Visa without exposing users&\#x27; real card numbers. OpenAI says each purchase requires the user to review the item and amount and confirm with Face ID or fingerprint, while the card networks issue payment tokens that replace the actual card number. It is available starting today in the US to ChatGPT Pro subscribers aged 18 and over using a US-issued card.

telegram · zaihuapd · Nov 13, 15:43

**「Background」** ChatGPT Wallet relies on network-issued payment tokens, which substitute a token for the underlying card number so an agent or merchant never handles the real credential. OpenAI says the wallet was built with American Express, Mastercard, and Visa and is initially available through dots for US ChatGPT Pro subscribers; CNBC reports that cardholders keep their existing credit card rewards.

**「Impact」** For eligible users, the practical change is that an agent can initiate a purchase but cannot complete it without a per-transaction biometric approval. The limitation is that the feature is restricted at launch to US Pro subscribers with US-issued cards, so other ChatGPT users and cards are not covered.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/introducing-chatgpt-wallet/">Introducing ChatGPT Wallet | OpenAI</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/openai-chatgpt-wallet-dot-purchases.html">OpenAI &#x27;s ChatGPT Wallet allows &#x27; dots &#x27; AI agents to make purchases</a></li>

</ul>
</details>

**Tags**: `#OpenAI`, `#agentic payments`, `#ChatGPT`, `#payment security`, `#AI agents`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Chicago Fed&\#x27;s Goolsbee Says Central Bank Has &\#x27;Work to Do&\#x27; on Inflation](https://www.cnbc.com/2026/11/13/chicago-feds-goolsbee-says-central-bank-has-definitely-got-work-to-do-on-inflation.html) ⭐️ 7.0/10

Chicago Fed President Austan Goolsbee said the central bank &quot;has definitely got work to do&quot; to restore credibility on inflation after October producer prices rose 0.3% for the month and 6.5% from a year earlier, the fastest annual pace since November 2022.

rss · CNBC Finance · Nov 13, 14:22

**「Background」** The producer price index is a proxy for wholesale prices, and the Fed targets 2% inflation; Goolsbee is not currently an FOMC voter but will be in 2027. Markets are fully pricing a quarter-point rate increase at the Dec. 8-9 meeting, according to CME Group&\#x27;s FedWatch gauge.

**Tags**: `#Federal Reserve`, `#inflation`, `#PPI`, `#monetary policy`, `#market expectations`

---