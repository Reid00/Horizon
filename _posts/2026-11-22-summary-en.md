---
layout: default
title: "Horizon Summary: 2026-11-22 (EN)"
date: 2026-11-22
lang: en
---

> From 24 items, 7 important content pieces were selected

---

**Technology News**
1. [Reported Lean formal verification of the Riemann Hypothesis](#item-tech-news-1) ⭐️ 9.0/10
2. [GPGME flaw before 2.3.0 disclosed; RCE framing disputed](#item-tech-news-2) ⭐️ 8.0/10
3. [Microsoft previews RDMA over USB4 for multi-PC local AI inference](#item-tech-news-3) ⭐️ 8.0/10
4. [OpenRouter Warns MiniMax Prompts May Have Been Read by Third Party](#item-tech-news-4) ⭐️ 8.0/10
5. [Zhejiang University reports first hardware QRAM on superconducting chip](#item-tech-news-5) ⭐️ 8.0/10
6. [Muru: AI-assisted Rust server for ASGI and WSGI Python apps](#item-tech-news-6) ⭐️ 7.0/10

**Technology Blog**
1. [Good programming means avoiding catastrophic blunders](#item-tech-blog-1) ⭐️ 6.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Reported Lean formal verification of the Riemann Hypothesis](https://leanprover-community.github.io/blog/posts/riemann-hypothesis/) ⭐️ 9.0/10

The item reports a Lean formal verification of the Riemann Hypothesis, a claim that would matter to mathematicians and proof-assistant users if confirmed. No source content was supplied, so the proof’s exact scope, authorship, and confirmation status are not detailed here; the result should be treated as reported rather than independently established. The discussion focuses on independent proof checkers and AI-assisted formalization, with commenters naming con-leche and con-ron as checker implementations and saying a human expert was involved.

hackernews · g-b-r · Nov 21, 14:36 · [Discussion](https://news.ycombinator.com/item?id=50589618)

**「Background」** Lean is a proof assistant in which a small kernel mechanically checks each formal proof step, so a formalization is only as trustworthy as the kernel and the exact statement encoded. A public project page for the Riemann Hypothesis formalization lists compilation results, the verification machine, and proof-audit records \[tool-1-1\]. A video description says Levent Alpöge announced the formalization with Claude on 20 November 2026, comprising 175,187 Lean files and about 17.4 million lines \[tool-1-2\].

**「Cross-checking the proof」** For anyone assessing the claim, validation depends on cross-checking across multiple independent kernels rather than trusting a single checker: commenters point to separate implementations such as con-leche and con-ron, each with its own consistency proof. One commenter also notes that a fake Collatz refutation previously passed one independent checker, so human expert review remains a necessary part of confirming this result.

**「Community discussion」** Commenters debated how much trust to place in independent checkers: one argued that multiple kernels with self-consistency proofs, including con-leche and con-ron, make a proof that exploits a bug vanishingly unlikely, while another noted that a fake Collatz refutation previously passed one such checker and questioned how independent they really are, though a human expert was in the loop here. Others credited Levent with getting the most out of Claude and said the formalization reportedly covered a large chunk of modern mathematics.

<details><summary>References</summary>
<ul>
<li><a href="https://proveriemannhypothesis.github.io/">Verifying a Riemann Hypothesis Formalization in Lean</a></li>
<li><a href="https://www.youtube.com/watch?v=CaI-nCHt7iQ">The Riemann Theorem: the first complete graduate-level... - YouTube</a></li>

</ul>
</details>

**Tags**: `#Lean`, `#formal verification`, `#Riemann Hypothesis`, `#AI-assisted mathematics`, `#proof assistants`

---

<a id="item-tech-news-2"></a>
### [GPGME flaw before 2.3.0 disclosed; RCE framing disputed](https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html) ⭐️ 8.0/10

A disclosed GPGME vulnerability affects versions before 2.3.0, and patches have been issued. The disclosure was described as an RCE in GnuPG, but discussion identifies the underlying bug as a double free and disputes the RCE characterization. A GitLab representative said Johan Carlsson discovered the issue and that disclosure was moved to 2026-11-20 from a planned 2026-11-25 coordinated date because of the Ruby2Shell bug. According to commenters, all software using GPGME before 2.3.0 is affected whether linked as a shared library, DLL, or statically, including signed-commit paths in GitLab and many mail and XMPP clients.

hackernews · gdgghhhhh · Nov 21, 08:32 · [Discussion](https://news.ycombinator.com/item?id=50587208)

**「Background」** GPGME is the library through which applications invoke GnuPG, and the advisory covers all software using versions before 2.3.0, whether linked as a shared library, Windows DLL, or statically. The root cause is in two internal GPGME functions that read status lines and key listings from gpg. Disclosure was originally scheduled for 2026-11-25 but moved to 2026-11-20 because GitLab needed to update earlier amid the Ruby2Shell bug.

**「Impact」** All software using GPGME before 2.3.0—whether as a shared library, DLL, or static link—is affected, so maintainers and packagers should upgrade to a fixed release rather than assuming only the gpg binary needs attention. The flaw, tracked as CVE-2026-129975, is triggered by an OpenPGP key with a crafted very long user ID; the resulting double free can exfiltrate data from applications processing signed data, and published analysis says RCE cannot be ruled out.

**「Community discussion」** Commenters disputed the &quot;RCE&quot; label, with one saying the bug is a double free rather than an RCE chain, while another argued that code execution in GitLab&\#x27;s signed-commit path would still be serious. A commenter also said Red Hat fixed the issue five years ago in its packaging but upstream missed it, and another asked whether core tools such as apt are unaffected because the flaw is in gpgme.

<details><summary>References</summary>
<ul>
<li><a href="https://thehackernews.com/2026/11/gnupg-warns-critical-gpgme-flaw-could.html">GnuPG Warns Critical GPGME Flaw Could Expose App Data via...</a></li>
<li><a href="https://www.openwall.com/lists/oss-security/2026/11/20/13">oss-security - Fwd: GnuPG Security Advisory for GPGME ...</a></li>
<li><a href="https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html">[Announce] GnuPG Security Advisory for GPGME ...</a></li>
<li><a href="https://thehackernews.com/2026/11/gnupg-warns-critical-gpgme-flaw-could.html">GnuPG Warns Critical GPGME Flaw Could Expose App Data via...</a></li>
<li><a href="https://www.phoronix.com/news/GnuPG-GPGME-Critical">GnuPG&#x27;s GPGME Affected By Critical Security Bug In Turn... - Phoronix</a></li>

</ul>
</details>

**Tags**: `#security-vulnerability`, `#GPGME`, `#GnuPG`, `#double-free`, `#coordinated-disclosure`

---

<a id="item-tech-news-3"></a>
### [Microsoft previews RDMA over USB4 for multi-PC local AI inference](https://videocardz.com/newz/microsoft-brings-rdma-over-usb4-to-windows-allowing-multiple-pcs-to-run-one-local-ai-model) ⭐️ 8.0/10

Microsoft released a developer preview of RDMA over USB4 for Windows, rolling out through Windows Insider, that lets multiple PCs share memory and GPU compute over ordinary USB4 connections without specialized network cards or switches. In a demo, three AMD Ryzen AI Max+ 395 systems ran a 4-bit quantized Qwen3-235B-A22B model at about 18.5 tokens per second. The performance figure comes from Microsoft&\#x27;s demo as summarized by the source, not independent testing.

telegram · zaihuapd · Nov 21, 06:13

**「Background」** RDMA lets one machine read and write another machine&\#x27;s memory directly, bypassing much of the operating system&\#x27;s networking stack to reduce latency; it has traditionally required data-center-class network adapters and switches. USB4 is a consumer connection standard that can carry PCIe traffic over a USB-C cable.

**「Impact」** Developers evaluating local inference can test pooling several USB4-connected Windows machines instead of buying specialized RDMA networking gear, but the capability is a Windows Insider developer preview and not yet a production deployment path.

**Tags**: `#RDMA over USB4`, `#Windows`, `#local AI inference`, `#distributed inference`, `#Microsoft`

---

<a id="item-tech-news-4"></a>
### [OpenRouter Warns MiniMax Prompts May Have Been Read by Third Party](https://news.ycombinator.com/item?id=50585962) ⭐️ 8.0/10

According to a Telegram post relaying an OpenRouter email, prompts sent to MiniMax models may have been read by a third party. The post says security researchers sent prompts containing test URLs to MiniMax models between July and October 2026, and the third party accessed those URLs 40 to 130 hours later. OpenRouter attributed the issue to MiniMax and its forwarders AtlasCloud, Novita, and StreamLake, removed the &quot;zero data retention&quot; labels from affected endpoints, and advised users with sensitive credentials to rotate API keys and passwords. The warning had not been published on OpenRouter&\#x27;s public website at the time of the report.

telegram · zaihuapd · Nov 21, 06:53

**「Background」** OpenRouter is a routing layer that sends each request to one of several upstream providers and lets users pin or exclude providers; its MiniMax M2.5 listing names Venice, StreamLake, AtlasCloud, GMICloud and DigitalOcean as providers. A separate report on the incident described the affected “zero retention” endpoints as relays: AtlasCloud, Novita and StreamLake confirmed to OpenRouter that they forwarded requests to MiniMax, including when the MiniMax API was called directly.

**「Impact」** Users who relied on the zero-data-retention label for MiniMax requests should treat those prompts as potentially exposed and rotate any API keys or passwords included in them; affected endpoints no longer carry that label.

<details><summary>References</summary>
<ul>
<li><a href="https://openrouter.ai/minimax/minimax-m2.5">MiniMax M2.5 - API Pricing &amp; Benchmarks | OpenRouter</a></li>
<li><a href="https://1275.ru/news/minimax-metka-zero-retention-okazalas-releem_53059">MiniMax : метка zero retention оказалась релеем | SEC-1275-1</a></li>

</ul>
</details>

**Tags**: `#LLM API security`, `#AI privacy`, `#OpenRouter`, `#MiniMax`, `#data retention`

---

<a id="item-tech-news-5"></a>
### [Zhejiang University reports first hardware QRAM on superconducting chip](https://finance.sina.com.cn/stock/2026-11-21/doc-iniznhsk3530826.shtml) ⭐️ 8.0/10

Researchers at Zhejiang University say they have demonstrated QRAM on a real superconducting quantum chip, the self-developed Tianmu 2, for the first time, with the work published in Nature Physics. The prototypes retrieved 4-bit and 8-bit data with 80.9% and 60.4% accuracy, respectively, and used circuit depths more than 30% lower than an unoptimized approach. The team also reports the first validation that the architecture has local noise resilience. It plans to scale up the QRAM work next.

telegram · zaihuapd · Nov 21, 08:31

**「What QRAM is」** QRAM \(quantum random-access memory\) is a proposed memory architecture that lets a quantum algorithm address many stored data entries in superposition, making it a key component for loading classical data into quantum computations. The approach has largely remained theoretical or limited to small proof-of-principle demonstrations, which is the gap the Zhejiang University team says its superconducting-chip prototype addresses.

**「Scaling cost」** The accuracy drop from 80.9% for the 4-bit prototype to 60.4% for the 8-bit one shows retrieval fidelity degrading as address space grows, so the team&\#x27;s stated next step of scaling QRAM will need error mitigation before the memory is dependable for algorithms that require correct data lookup. The reported reduction of more than 30% in circuit depth is the concrete lever for that work, since shallower circuits accumulate less noise on the same superconducting hardware.

**Tags**: `#quantum computing`, `#QRAM`, `#superconducting qubits`, `#hardware`, `#research`

---

<a id="item-tech-news-6"></a>
### [Muru: AI-assisted Rust server for ASGI and WSGI Python apps](https://simonwillison.net/2026/Nov/21/muru/) ⭐️ 7.0/10

Graham Dumpleton, creator of mod\_wsgi, has launched Muru, an AI-assisted Rust server intended to run ASGI and WSGI Python applications in both development and production. The project is early-stage: the source describes it as aiming to provide the best tools for those workloads, not as a finished or production-proven server. Dumpleton has published 18 detailed design and development posts between November 4 and November 21, 2026, covering its worker model, combined WSGI/ASGI support, releases without restarts, canaries, Kubernetes integration, scale-to-zero, and a tracing toolbar.

rss · Simon Willison · Nov 21, 23:56

**「Background」** Muru is a new server from Graham Dumpleton, who has spent 20 years on mod\_wsgi, a long-standing way to serve Python web applications. WSGI and ASGI are the two interfaces Python web apps use to connect to a server; Muru is aimed at both, and Dumpleton frames the project as his next step after mod\_wsgi.

**「Impact」** For Python deployment teams, Muru is currently a design reference and evaluation candidate rather than a proven server: the posts describe mechanisms such as import-once-fork-many and releases without restarts, but the source gives no versioned release, benchmarks, or compatibility guarantees.

**Tags**: `#Python web servers`, `#ASGI/WSGI`, `#Rust`, `#mod\_wsgi`, `#open source`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Good programming means avoiding catastrophic blunders](https://seangoedecke.com/to-code-well-avoid-blunders/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 22, 00:00

**「Background」** Many engineers imagine that good programming means producing brilliant insights or elegant new abstractions. Sean Goedecke argues the opposite: the main skill is avoiding catastrophic mistakes, particularly when working in large commercial codebases with big teams.

**「Solution」** Goedecke compares programming to chess and tennis: a player who never hangs pieces or who reliably returns the ball will beat most opponents without needing spectacular moves. Programming is especially unforgiving because there is no durable winning advantage; one blunder can turn an elegant codebase into a janky one. His examples include introducing a parallel system for the same task, creating a second source of truth, turning safe synchronous work into delicate asynchronous work, adding subtle failure points, and complicating a key interface. The underlying sins are inconsistency and unnecessary requirements. Inconsistency breaks trust, forcing engineers to hunt for surprises instead of assuming the sensible behavior. Unnecessary requirements are sticky because later engineers lack the context to remove them, and they interact combinatorially with every new feature. His practical heuristics are to fit work into the codebase as normally as possible and trim the task to the smallest set of requirements. Clever patterns and “extra credit” features are warning signs that attention has drifted from avoiding blunders. He notes that coding agents are roughly human-level at consistency but worse at avoiding unnecessary requirements. The essay is brief and anecdotal, offering engineering judgment rather than case-study evidence.

**「Takeaway」** Goedecke’s core thesis is that great programming depends less on cleverness than on disciplined attention to consistency and restraint in requirements. Avoiding blunders, not producing brilliant abstractions, is what protects a codebase’s long-term health.

**Tags**: `#software engineering`, `#code quality`, `#maintainability`, `#technical debt`, `#engineering judgment`

---