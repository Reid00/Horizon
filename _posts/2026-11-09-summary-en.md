---
layout: default
title: "Horizon Summary: 2026-11-09 (EN)"
date: 2026-11-09
lang: en
---

> From 31 items, 4 important content pieces were selected

---

**Technology News**
1. [KetchUp: Open-source SketchUp alternative built with Rust and WebGPU](#item-tech-news-1) ⭐️ 7.0/10
2. [Llama-modchip claims 284B DeepSeek on 64GB RAM without GPU](#item-tech-news-2) ⭐️ 7.0/10
3. [Outlook.com Reportedly Rejects Mail From Domains Without DMARC](#item-tech-news-3) ⭐️ 7.0/10
4. [C parser outperforms Rust in SQLite parse\_number\(\) benchmark](#item-tech-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [KetchUp: Open-source SketchUp alternative built with Rust and WebGPU](https://ketchup3d.github.io/app/) ⭐️ 7.0/10

KetchUp is an open-source, browser-based SketchUp alternative built with Rust and WebGPU. It is presented as a web-native 3D modeler for users who want SketchUp-style modeling without a desktop install. The Hacker News submission drew positive reaction, especially for how the Rust-based UI and text rendering feel in a browser.

hackernews · dcoulmbe · Nov 8, 22:35 · [Discussion](https://news.ycombinator.com/item?id=50418176)

**「Background」** SketchUp, the modeling tool KetchUp is positioned as an alternative to, originated at @Last Software in 1999, was acquired by Google in 2006, and was sold to Trimble in 2012. It currently offers a free web-based version alongside paid subscriptions for its Windows and macOS applications.

**「Impact」** Because KetchUp is built on WebGPU, users need a browser that supports the API; that is a concrete compatibility constraint for trying the app, separate from whether the modeling workflow suits them.

**「Community discussion」** Commenters welcomed a SketchUp successor and praised how polished the Rust UI feels in a browser. One user argued that AI-assisted custom tool-building may increasingly replace learning large modeling packages, while a hands-on comment flagged that drawing a rectangle prompts for an object name—an awkward default.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/SketchUp">SketchUp - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#open-source`, `#Rust`, `#WebGPU`, `#3D modeling`, `#SketchUp alternative`

---

<a id="item-tech-news-2"></a>
### [Llama-modchip claims 284B DeepSeek on 64GB RAM without GPU](https://github.com/synchopate/llama-modchip) ⭐️ 7.0/10

A GitHub project called llama-modchip claims it can run a 284B-parameter DeepSeek model on a machine with 64GB of RAM and no GPU. The repository&\#x27;s approach relies on aggressive quantization and memory optimization, but the evidence is early and the project&\#x27;s novelty is disputed.

hackernews · joshcsimmons · Nov 8, 10:22 · [Discussion](https://news.ycombinator.com/item?id=50411961)

**「Background」** The approach relies on two established techniques: quantization, which stores model weights at lower precision to reduce memory use, and CPU-first offloading, which keeps inference in system RAM instead of GPU memory. The project&\#x27;s README lists version 2.4.0 and claims 284B DeepSeek-V4-Flash runs under 59 GiB of RAM at 256K context on pure CPU.

**「Impact」** For anyone considering the setup, the practical trade-off is memory capacity versus quality: the 64GB footprint depends on aggressive quantization, and commenters cited evidence that model quality generally peaks at 4-bit and drops significantly below that.

**「Community Discussion」** Commenters questioned the project&\#x27;s novelty, with aappleby reporting that on a 16-core Ryzen 7945HX with 96GB DDR5 it ran about the same as plain llama.cpp on CPU except for faster prefill, and that the DeepSeek configuration was untested. kennywinker argued the floor for functional local AI keeps falling, describing sub-$800 systems that reach roughly 20 tok/s output, while armcat cautioned that quantization benefits are non-linear and peak around 4-bit.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/synchopate/llama-modchip">GitHub - synchopate/llama-modchip: Run 284B DeepSeek-V4 ...</a></li>
<li><a href="https://www.promptzone.com/mei_bui/llama-modchip-run-284b-deepseek-on-64gb-ram-no-gpu-required-3plk">Llama-modchip: Run 284B DeepSeek on 64GB RAM, No GPU Required</a></li>

</ul>
</details>

**Tags**: `#local LLM inference`, `#quantization`, `#memory optimization`, `#llama.cpp`, `#DeepSeek`

---

<a id="item-tech-news-3"></a>
### [Outlook.com Reportedly Rejects Mail From Domains Without DMARC](https://mailroute.net/blog/outlook-rejecting-email-without-dmarc) ⭐️ 7.0/10

Outlook.com is reportedly rejecting email from domains that do not publish DMARC records, according to a Mailroute blog post discussed on Hacker News. The item provides no confirmation from Microsoft, no effective date, and no details on whether the rejection is a permanent 5xx failure or a silent drop. For senders, the reported behavior makes DMARC publication a deliverability prerequisite for reaching Outlook.com recipients.

hackernews · xmddmx · Nov 8, 19:20 · [Discussion](https://news.ycombinator.com/item?id=50416158)

**「Background」** DMARC is the policy layer that tells receiving mail servers how to handle messages that fail SPF or DKIM authentication; a domain without a DMARC record gives receivers no explicit handling instruction. Microsoft support guidance has already attributed some Outlook.com rejections to senders failing newer authentication requirements, so the reported behavior extends an existing enforcement trend rather than introducing a new standard.

**「Impact」** Senders to Outlook.com, Hotmail.com, and Live.com should publish SPF, DKIM, and DMARC; Microsoft&\#x27;s 2025 enforcement policy targets high-volume senders \(5,000+ messages per day\) and diverts non-compliant mail to junk or rejects it. If the reported rejection is broader than that threshold, low-volume and self-hosted senders would also need to verify their DMARC records, and the report does not specify the exact threshold.

**「Community Discussion」** Commenters disagreed on whether the rejections are silent: one said Outlook.com returns 5xx permanent delivery failures, while another reported mail being accepted in logs but never reaching the inbox. A separate complaint focused on nonpublic blocklists that can block an entire VPS provider with no apparent appeal, even when the sender&\#x27;s authentication is configured.

<details><summary>References</summary>
<ul>
<li><a href="https://learn.microsoft.com/en-in/answers/questions/5790042/outlook-com-rejecting-email-messages-for-security">outlook . com rejecting email messages for security... - Microsoft Q&amp;A</a></li>
<li><a href="https://techcommunity.microsoft.com/blog/microsoftdefenderforoffice365blog/strengthening-email-ecosystem-outlook%E2%80%99s-new-requirements-for-high%E2%80%90volume-senders/4399730">Strengthening Email Ecosystem: Outlook’s New Requirements for ...</a></li>
<li><a href="https://www.dmarcs.com/what-microsofts-dmarc-enforcement-means-for-your-email-deliverability/">What Microsoft’s DMARC Enforcement Means for Your Email ...</a></li>
<li><a href="https://easydmarc.com/blog/outlook-new-email-sender-policy-update/">Microsoft Outlook New Email Sender Requirements | EasyDMARC</a></li>

</ul>
</details>

**Tags**: `#email deliverability`, `#DMARC`, `#Microsoft Outlook`, `#email infrastructure`, `#self-hosting`

---

<a id="item-tech-news-4"></a>
### [C parser outperforms Rust in SQLite parse\_number\(\) benchmark](https://simonwillison.net/2026/Nov/8/sqlite-parse-number-c-vs-rust/) ⭐️ 7.0/10

Simon Willison published a research report comparing C and Rust implementations of a SQLite loadable extension that adds parse\_number\(\), which strips currency symbols, commas, and percent signs and returns NULL for unparseable strings. The initial C build was 14 KB, versus 321 KB with Rusqlite and 298 KB with sqlite-loadable-rs, but the Rust versions were faster because Rust&\#x27;s equivalent of C&\#x27;s strtod was about twice as fast. After prompting Claude Opus 5.5 to write a custom C parser, the reported benchmark over 2 million rows showed the new C version at 19 ns per row on mixed data, 16 ns on integers, and 18 ns on decimals, compared with 46/36/55 ns for Rusqlite and 41/32/47 ns for sqlite-loadable-rs. The report describes a single generated experiment, not an independent cross-language benchmark.

rss · Simon Willison · Nov 8, 22:26

**「Background」** SQLite allows applications to register custom scalar functions, and loadable extensions package such functions in a shared library that SQLite can load at runtime. The experiment compares a C extension using the standard library&\#x27;s strtod parser with Rust extensions built on Rusqlite and sqlite-loadable-rs, which expose SQLite&\#x27;s extension API to Rust code.

**「Impact」** Developers evaluating Rust for SQLite extensions should benchmark the specific parsing path: in this experiment, the fastest result required a hand-written C parser, while the Rust builds were roughly 20 times larger.

**Tags**: `#SQLite`, `#Rust`, `#C`, `#extensions`, `#performance`

---