---
layout: default
title: "Horizon Summary: 2026-11-15 (EN)"
date: 2026-11-15
lang: en
---

> From 39 items, 7 important content pieces were selected

---

**Technology News**
1. [Lovable-built apps exposed passport data and 200K messages](#item-tech-news-1) ⭐️ 8.0/10
2. [PyPI rolls out redesigned project pages with clearer security and provenance signals](#item-tech-news-2) ⭐️ 7.0/10
3. [Show HN: DeepSeek V3 in ~200 lines of pure JAX](#item-tech-news-3) ⭐️ 7.0/10
4. [Project Zero plans 90-, 60-, and 30-day vulnerability disclosure windows](#item-tech-news-4) ⭐️ 7.0/10
5. [Cloudflare open-sources Kitesurf, a stateless browser for AI agents](#item-tech-news-5) ⭐️ 7.0/10
6. [Italy fines Meta €805M over Facebook Android gallery access](#item-tech-news-6) ⭐️ 7.0/10
7. [Tesla Cybercab terms require $299 monthly autonomy subscription](#item-tech-news-7) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Lovable-built apps exposed passport data and 200K messages](https://www.crissyfield.de/research/lovable-en/) ⭐️ 8.0/10

Security researchers reported that apps built with Lovable exposed sensitive user data, including passport details and more than 200,000 private messages, because of insufficient Row-Level Security. Lovable Head of Security Igor Andri said the root cause was insufficient RLS and that Lovable automatically scans every app before publish, offers a deeper SAST scan free to all users, and lets users apply fixes, enable auto-fix, or block publishing when findings appear. The disclosure also prompted discussion of Supabase defaults, with commenters saying a fix announced for October 30 may not apply to existing projects.

hackernews · armcat · Nov 14, 17:43 · [Discussion](https://news.ycombinator.com/item?id=50499017)

**「Background」** Supabase is a hosted Postgres platform that developers can use without running their own database. Postgres Row-Level Security lets developers define which rows each database role may access; when those policies are missing or too permissive, an app&\#x27;s public API can expose records beyond what its UI shows.

**「Developer action」** Developers publishing Lovable apps should verify Row-Level Security table by table rather than assume the platform prevents cross-user data exposure; the reported leaks stemmed from insufficient RLS. Lovable&\#x27;s control to block publishing when critical issues are found is available on all plans but off by default, so teams need to enable it and run the built-in SAST scans before exposing user data.

**「Community discussion」** Commenters debated responsibility beyond Lovable: one argued that Supabase&\#x27;s historical defaults are a major cause and that existing projects may still retain them, while another said AI-generated apps mainly lower the skill barrier and increase the number of exposed targets. The blog author and Lovable&\#x27;s Head of Security both participated, with the latter describing the vendor&\#x27;s scanning and fix workflow.

<details><summary>References</summary>
<ul>
<li><a href="https://supabase.com/database">Database | Supabase</a></li>
<li><a href="https://github.com/supabase/supabase">GitHub - supabase / supabase : The Postgres development platform. ...</a></li>
<li><a href="https://docs.lovable.dev/features/security">Security overview - Lovable Documentation</a></li>
<li><a href="https://latchdog.com/guides/is-my-lovable-app-secure">Is my Lovable app secure ? What Lovable checks, and... | LatchDog</a></li>

</ul>
</details>

**Tags**: `#security vulnerability`, `#Row-Level Security`, `#Supabase`, `#AI-generated code`, `#data exposure`

---

<a id="item-tech-news-2"></a>
### [PyPI rolls out redesigned project pages with clearer security and provenance signals](https://blog.pypi.org/posts/2026-11-06-ui-updates-complete/) ⭐️ 7.0/10

PyPI has launched redesigned project pages that surface security and provenance information more clearly. The pages are now live for Python package consumers and maintainers, with the change focused on how project and file-level trust signals are presented. It is an incremental UI and security-signaling update rather than a new package format or signing mechanism.

hackernews · rbanffy · Nov 14, 15:40 · [Discussion](https://news.ycombinator.com/item?id=50497892)

**「Background」** PyPI&\#x27;s provenance attestations record details such as the source repository and commit used to build a file, and are produced when a package is published through a Trusted Publisher. A 2026 survey of package registries places this in the broader adoption of signing, provenance attestations, and trusted publishing, while a May 2026 report found malicious npm and PyPI packages shipped with valid SLSA Level 3 attestations—showing that provenance verifies origin and build path, not package safety.

**「Impact」** Python users can now use a project page&\#x27;s file listing to compare provenance status before installing, so packages published with provenance are visibly distinguishable from those without it. The signal does not by itself establish that a project is safe, and packages without it are not necessarily untrustworthy.

**「Community discussion」** Commenters debated whether tying trust signals to large CI and cloud providers centralizes PyPI security and promotes lock-in, while others welcomed Sigstore-style keyless signing and wanted third-party CI services to support OIDC. One commenter stressed that provenance can help detect a compromised formerly benign project but does not detect malicious projects, and another asked for trusted publishing to support reusable workflows.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.pypi.org/using-pypi/package-security/provenance/">Checking Provenance (package origin) - PyPI User Documentation</a></li>
<li><a href="https://nesbitt.io/2026/10/30/signing-and-attestations-across-package-registries.html">Signing and Attestations Across Package Registries | Andrew Nesbitt</a></li>
<li><a href="https://matrixgard.com/blog/npm-pypi-provenance-attestation-supply-chain-2026/">Valid Provenance , Malicious Package: What Attestations Buy You</a></li>

</ul>
</details>

**Tags**: `#PyPI`, `#Python packaging`, `#supply chain security`, `#software provenance`, `#open source infrastructure`

---

<a id="item-tech-news-3"></a>
### [Show HN: DeepSeek V3 in ~200 lines of pure JAX](https://github.com/Vaibhaav-Tiwari/deepseek-v3-jax) ⭐️ 7.0/10

A Show HN project offers a roughly 200-line pure-JAX reimplementation of DeepSeek V3, aimed at readers who want to study the model or experiment locally. The item does not establish correctness, completeness, or parity with the original model, and it provides no benchmark results. One commenter reports that the project ran end-to-end on an AMD RX 7600 XT 16GB under Fedora and ROCm.

hackernews · VaibhaavTiwari · Nov 14, 15:04 · [Discussion](https://news.ycombinator.com/item?id=50497589)

**「Background」** DeepSeek V3 is a large language model, and JAX is a Python library for array computation and automatic differentiation. A roughly 200-line reimplementation is therefore a compact educational exercise in model architecture and inference, not a production runtime.

**「Impact」** For developers on AMD GPUs, that report points to a possible ROCm/JAX path without CUDA; the same commenter says it required two environment variables, including an HSA override of 11.0.0, so this is a single hardware anecdote rather than confirmed support.

**「Community discussion」** Commenters largely treat the project as a learning resource: one values rebuilding a model from first principles, another asks for a roadmap for engineers comfortable with Java and Python, and another plans to recreate it for study. The thread contains no substantive disagreement about correctness or performance.

**Tags**: `#JAX`, `#DeepSeek V3`, `#LLM inference`, `#open-source implementation`, `#ROCm`

---

<a id="item-tech-news-4"></a>
### [Project Zero plans 90-, 60-, and 30-day vulnerability disclosure windows](https://projectzero.google/2026/11/disclosure-policy.html) ⭐️ 7.0/10

Google Project Zero is reported to be adopting a &quot;Full 90&quot; policy, disclosing vulnerabilities 90 days after they are reported to the vendor, according to a policy statement quoted in the discussion. The same statement schedules a move to &quot;Full 60&quot; on February 2, 2027, and &quot;Full 30&quot; on January 3, 2028. The item provides no full source text, so the dates and scope are not independently confirmed here; they describe an announced phased plan rather than a currently shipped 30-day policy.

hackernews · hacb · Nov 14, 11:13 · [Discussion](https://news.ycombinator.com/item?id=50496051)

**「Background」** Project Zero is a Google security research team, and coordinated disclosure gives vendors time to patch a reported flaw before technical details become public. The policy quoted in the discussion sets a staged schedule: 90 days from report now, 60 days starting February 2, 2027, and 30 days starting January 3, 2028.

**「Shorter deadlines for vendors」** Vendors and open-source maintainers receiving Project Zero reports would face a progressively tighter patch deadline: per the policy text quoted in comments, the 90-day window stays in force until February 2, 2027, drops to 60 days from that date, and to 30 days from January 3, 2028. A 30-day target is materially harder for projects with slow release cycles, and one commenter singled out Ubuntu as needing &quot;a LOT more time,&quot; suggesting downstream distributions may have to ship or backport fixes before their normal stable-release cadence. Because the item carries no source text, the exact terms of the policy beyond those quoted dates remain unverified.

**「Community Discussion」** Commenters disagreed on whether the shorter window is workable: one said Ubuntu would need much more time, while another argued for immediate disclosure because vendors otherwise lack pressure to fix bugs. A separate comment raised whether bug-finding companies should give vendors access to the products used to discover flaws, but that point was speculative.

**Tags**: `#vulnerability disclosure`, `#Project Zero`, `#cybersecurity policy`, `#coordinated disclosure`, `#software security`

---

<a id="item-tech-news-5"></a>
### [Cloudflare open-sources Kitesurf, a stateless browser for AI agents](https://www.phoronix.com/news/Cloudflare-Kitesurf-Open-Source) ⭐️ 7.0/10

Cloudflare has open-sourced Kitesurf under Apache 2.0, a stateless browser for AI agents built on Cloudflare Workers. It parses HTML, handles CSS, and executes JavaScript without requiring a browser container, and the code is available on GitHub. Cloudflare says the goal is a lightweight, efficient browser that uses less CPU and memory than Chromium and scales on its global Workers network; no benchmarks or independent performance results were provided.

telegram · zaihuapd · Nov 14, 09:33

**「Background」** Kitesurf is an experimental browser engine rather than a containerized Chromium instance: Cloudflare built it to run on Workers, its serverless runtime, so pages can be handled without launching a full browser. The project&\#x27;s GitHub repository says it uses Cloudflare Dynamic Workers to create isolated workers for each page, a capability included in the Workers Paid plan, and Cloudflare&\#x27;s blog notes that the code can be run locally or deployed as your own instance on Cloudflare Workers.

**「Impact」** Developers can test an Apache-2.0 alternative to Chromium-based automation inside Workers without managing browser containers, but Cloudflare has not published benchmarks, so the claimed CPU and memory advantage over Chromium remains a vendor claim.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.cloudflare.com/kitesurf-open-source/">Kitesurf is now open source | Cloudflare Blog</a></li>
<li><a href="https://github.com/cloudflare/kitesurf">GitHub - cloudflare / kitesurf : Kitesurf is an experimental browser ...</a></li>

</ul>
</details>

**Tags**: `#Cloudflare`, `#AI agents`, `#open source`, `#browsers`, `#serverless`

---

<a id="item-tech-news-6"></a>
### [Italy fines Meta €805M over Facebook Android gallery access](https://www.garanteprivacy.it/home/docweb/-/docweb-display/docweb/10321080) ⭐️ 7.0/10

Italy’s privacy regulator fined Meta €805 million after finding that Facebook’s Android app accessed the photos, videos, and metadata of about 20 million Italian users without specific consent. The case concerns a photo-recommendation feature launched in 2023 that was enabled by default and used a broad consent prompt, according to the Garante.

telegram · zaihuapd · Nov 14, 14:37

**「Background」** The dispute centers on how Facebook’s Android app obtained and disclosed access to users’ photo galleries. According to the BBC, Facebook requested gallery access through a single app-wide authorization, and the Italian regulator said the preceding notice did not make clear that this would also allow Facebook to generate suggestions based on photos in the gallery.

**「Impact」** Meta has 60 days to make the feature default-off and obtain separate consent; otherwise it may not enable the feature for users who have not validly authorized it.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bbc.com/news/articles/cwn83gxemk35o">Italy fines Meta € 805 m over accessing users&#x27; photos</a></li>

</ul>
</details>

**Tags**: `#隐私监管`, `#Meta`, `#移动应用权限`, `#平台合规`, `#意大利`

---

<a id="item-tech-news-7"></a>
### [Tesla Cybercab terms require $299 monthly autonomy subscription](https://www.tesla.com/configurator/api/v4/terms?category=autonomy_subs&amp;amp;locale=en_US&amp;amp;model=cc&amp;amp;saleType=Sale) ⭐️ 7.0/10

Tesla&\#x27;s published Cybercab terms set a $29,990 vehicle price and a mandatory $299 monthly autonomy subscription, according to a Telegram post citing Tesla, Electrek and Reuters. The terms state the car cannot operate without the subscription and let Tesla change the price with one month&\#x27;s notice. They also allow suspension or cancellation for nonpayment or misuse, impose a one-week autonomous-driving disablement after three warnings, restrict operation to designated areas, and prohibit unauthorized use on ride-hailing, delivery or rental platforms. Electrek noted that the Cybercab and robotaxi Model Y share AI4 hardware and autonomous software, while FSD for ordinary owners still requires human supervision.

telegram · zaihuapd · Nov 15, 01:10

**「Background」** Tesla has been operating a Robotaxi service in Texas and Florida, and Electrek reports that the personal Cybercab is limited to those same service-area geofences, which are smaller than Tesla advertises. The Verge reports that Tesla announced the offer through its Robotaxi account on X and is inviting select customers to order the vehicle.

**「Impact」** For owners, the terms bar unauthorized ride-hailing, delivery or rental use, so the Cybercab cannot be freely deployed as a commercial vehicle even after the $29,990 purchase.

<details><summary>References</summary>
<ul>
<li><a href="https://electrek.co/">Electrek | EV and Tesla News, Green Energy, Ebikes, and more</a></li>
<li><a href="https://www.theverge.com/transportation/1033844/tesla-personal-cybercab-orders-299-subscription-fine-print">Tesla is inviting some people to buy a Cybercab ‘for... | The Verge</a></li>

</ul>
</details>

**Tags**: `#Tesla`, `#Cybercab`, `#autonomous driving`, `#subscription`, `#robotaxi`

---