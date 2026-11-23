---
layout: default
title: "Horizon Summary: 2026-11-23 (EN)"
date: 2026-11-23
lang: en
---

> From 28 items, 7 important content pieces were selected

---

**Technology News**
1. [OpenAI Post Examines Perplexity as an Intelligence Predictor](#item-tech-news-1) ⭐️ 8.0/10
2. [O&\#x27;Reilly essay asks Silicon Valley to optimize for human flourishing](#item-tech-news-2) ⭐️ 7.0/10
3. [Windows Server 2028 to omit WoW64 by default, reinstallable via FoD](#item-tech-news-3) ⭐️ 7.0/10

**Technology Blog**
1. [When in Doubt, Flail: Experimenting Under Uncertainty](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [US tech selloff prompts Asian market stabilization measures](#item-finance-news-1) ⭐️ 9.0/10
2. [China Asks U.S. to Withdraw Limits on Phone Number Access for Chinese Carriers](#item-finance-news-2) ⭐️ 7.0/10
3. [Record El Niño sea-temperature reading adds pressure to food aid](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [OpenAI Post Examines Perplexity as an Intelligence Predictor](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 8.0/10

OpenAI published a post examining the relationship between perplexity and model intelligence, but the supplied material does not include the article itself, so its specific claims, data, and novelty cannot be verified. The accompanying Hacker News discussion treated the post as evidence of a cross-entropy/perplexity trend tied to capability and debated how much that trend matters amid reinforcement learning and increasingly complex benchmarks.

hackernews · acossta · Nov 22, 17:06 · [Discussion](https://news.ycombinator.com/item?id=50601525)

**「Background」** Perplexity is a standard language-model metric derived from cross-entropy: lower values mean the model assigns higher probability to the actual next tokens, with 1 as the theoretical floor and vocabulary size as the ceiling for a random predictor. OpenAI&\#x27;s post examines how that pretraining metric relates to model capability, a connection that becomes less obvious once models are post-trained with reinforcement learning.

**「Community Discussion」** One commenter said it was shocking that cross-entropy loss still tracks capability given reinforcement learning and welcomed a simpler benchmark, while another argued the perplexity/intelligence link is unsurprising because prediction and compression capture world-model quality; a third noted the post did not define perplexity and supplied a definition. A commenter also relayed an unverified claim that Microsoft’s Mustafa Suleyman said MAI models would be added to the chart and that Microsoft would share pre-training progress on a common held-out evaluation set with OpenAI’s permission.

**Tags**: `#LLM evaluation`, `#perplexity`, `#cross-entropy`, `#OpenAI`, `#model intelligence`

---

<a id="item-tech-news-2"></a>
### [O&\#x27;Reilly essay asks Silicon Valley to optimize for human flourishing](https://www.oreilly.com/radar/what-happened-to-silicon-valley/) ⭐️ 7.0/10

The O&\#x27;Reilly Radar essay “What Happened to Silicon Valley?” argues that Silicon Valley’s market and incentive mechanisms shaped the industry’s trajectory and calls for rethinking what the technology sector should optimize for. Its central proposal is to treat mechanism design as “reverse game theory”: ask what game should be played, then aim the system at human flourishing rather than shareholder value or corporate profit. The piece is an argumentative industry analysis, not a report of a shipped product or measured technical result.

hackernews · greenyouse · Nov 22, 19:20 · [Discussion](https://news.ycombinator.com/item?id=50602947)

**「Background」** The essay&\#x27;s argument rests on mechanism design: the idea that market outcomes are produced by rules and incentives that people choose, rather than by a natural market order that should be left alone. O&\#x27;Reilly had made a related case in an Oct. 16, 2026 lecture at Johns Hopkins University, arguing that Silicon Valley rewards extraction over creation and that AI needs new market rules aimed at human flourishing.

**「Community discussion」** Commenters largely engaged with the mechanism-design thesis: one described governance attempts as futile until the market is treated as a built machine whose designers are held accountable, while another said the article’s most important idea is asking what humanity should collectively optimize for. A separate commenter attributed the current dynamics to the end of the zero-interest-rate era and argued that tech companies are now cannibalizing core competencies on the back of AI; another questioned Milton Friedman’s shareholder-profit framing by asking over what time frame it applies.

<details><summary>References</summary>
<ul>
<li><a href="https://www.oreilly.com/radar/what-happened-to-silicon-valley/">What Happened to Silicon Valley? – O’Reilly</a></li>
<li><a href="https://oreillyradar.substack.com/p/what-happened-to-silicon-valley">What Happened to Silicon Valley? - oreillyradar.substack.com</a></li>
<li><a href="https://news.lavx.hu/article/tim-o-reilly-traces-silicon-valley-s-shift-from-value-creation-to-extraction">Tim O&#x27;Reilly Traces Silicon Valley&#x27;s Shift From Value ...</a></li>

</ul>
</details>

**Tags**: `#Silicon Valley`, `#tech industry`, `#mechanism design`, `#capitalism`, `#AI`

---

<a id="item-tech-news-3"></a>
### [Windows Server 2028 to omit WoW64 by default, reinstallable via FoD](https://www.windowslatest.com/2026/11/23/32-bit-apps-days-are-numbered-as-microsoft-strips-support-bit-by-bit-starting-with-windows-server-2028-but-windows-11-is-safe-for-now/) ⭐️ 7.0/10

Microsoft announced at Ignite 2026 that Windows Server 2028 will not include the WoW64 compatibility subsystem by default, so 32-bit applications will not run out of the box on the server OS. The release is planned for fall 2027 alongside Windows 11 27H2. Administrators can add WoW64 back as a Feature on Demand, typically via PowerShell or DISM on Server Core; Microsoft says the change reduces attack surface and blocks 32-bit malware. Windows 11 still includes WoW64, and Microsoft has not announced a removal plan.

telegram · zaihuapd · Nov 23, 03:03

**「What WoW64 does」** WoW64 \(Windows 32-bit on Windows 64-bit\) is the compatibility layer that lets 32-bit applications run on 64-bit Windows installations, and it has long shipped as a standard part of the 64-bit OS. According to Windows Central&\#x27;s reporting, Windows Server 2028 is the first Windows Server release that will not support 32-bit Windows apps out of the box, with WoW64 instead offered as an optional component that administrators install manually. Microsoft outlined the plan at Ignite 2026, framing the change around reducing the malware attack surface.

**「Impact」** Enterprise administrators running 32-bit legacy applications will need to add the WoW64 Feature on Demand during or after installation and validate it in deployment images before migrating, because a default Windows Server 2028 install will not run those applications.

<details><summary>References</summary>
<ul>
<li><a href="https://www.windowscentral.com/microsoft/windows-11/microsoft-is-removing-32-bit-app-support-from-the-next-version-of-windows-server-wow64-subsystem-to-become-optional-component-to-reduce-malware-attack-surface">Windows Server 2028 to remove 32-bit app support for improved ...</a></li>
<li><a href="https://mezha.net/eng/news/mezha-568ac4f109c1bdf3a06d55a8_32-bit_windows_apps/">32-bit Windows apps won&#x27;t run by default on Windows Server 2028</a></li>
<li><a href="https://undercodenews.com/microsoft-plans-to-remove-32-bit-app-support-by-default-in-windows-server-2028-citing-growing-security-risks/">Microsoft Plans to Remove 32-Bit App Support by Default in ...</a></li>

</ul>
</details>

**Tags**: `#Windows Server 2028`, `#WoW64`, `#32-bit compatibility`, `#Microsoft`, `#enterprise IT`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [When in Doubt, Flail: Experimenting Under Uncertainty](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 23, 00:00

**「Background」** When guidance is unclear and the right move is unknown, Sean Goedecke argues that cautious waiting is usually worse than deliberate experimentation. He calls this &quot;flailing,&quot; while acknowledging that doing it badly can damage an engineer&\#x27;s reputation.

**「Solution」** Goedecke&\#x27;s method is to try many different things, pay close attention to feedback from people and from reality, and ruthlessly drop approaches that are not working. Trying many things provides direct contact with reality, increases the chance that one idea succeeds, and prevents over-investment in any single plan. He applies this to product work, where marginal experiments can reveal unexpected traction: at GitHub Models, an integration allowing AI inference from a GitHub Actions token proved surprisingly sticky and became the seed of &quot;Continuous AI.&quot; For difficult engineering systems, he favors speculative changes over trying to understand everything first, then dropping changes that do not improve matters. For organizational problems, senior engineers can automate manual work, volunteer for tasks, or propose long-term plans; here feedback is especially critical, because dropping failing plans builds trust while pressing on can direct others&\#x27; frustration at you. Goedecke notes that flailing feels like repeated failure from the inside, even when managers see a proactive engineer experimenting.

**「Takeaway」** Goedecke&\#x27;s broader point is that effective engineers must push through the unpleasant feeling of acting without sufficient information. So long as they stay sensitive to feedback and abandon failing plans quickly, broad experimentation can be the fastest route to traction in unclear technical and organizational situations.

**Tags**: `#engineering judgment`, `#uncertainty`, `#experimentation`, `#feedback loops`, `#organizational engineering`

---

## Financial News

<a id="item-finance-news-1"></a>
### [US tech selloff prompts Asian market stabilization measures](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 9.0/10

US AI technology stocks sold off sharply on Friday, with the Nasdaq down 5.28% and the Philadelphia Semiconductor Index falling nearly 11%, according to the report. Ahead of the reopening, mainland China lowered its minimum margin ratio to 80%, South Korea eased daily buyback order limits for three months from Nov. 24, and Taiwan banned short-selling below the previous close from Nov. 23 while raising short-selling margin to 150%.

telegram · zaihuapd · Nov 22, 13:24

**「Background」** The measures followed a Friday rout in US AI-related technology shares—the Nasdaq fell 5.28% and the Philadelphia Semiconductor Index nearly 11% in one session—and a 5.2% one-day drop in South Korea’s Kospi, which had already prompted Seoul to prepare a market-stabilization fund.

**「Impact」** Traders in mainland China and Taiwan face changed margin and short-selling rules, while South Korean listed companies get a three-month relaxation of daily buyback limits, as regulators respond to the US tech selloff.

<details><summary>References</summary>
<ul>
<li>South Korea prepares stock market stabilization fund after Kospi plunges 5.2%</li>

</ul>
</details>

**Tags**: `#US tech selloff`, `#Asian markets`, `#margin trading rules`, `#short-selling restrictions`, `#market stabilization`

---

<a id="item-finance-news-2"></a>
### [China Asks U.S. to Withdraw Limits on Phone Number Access for Chinese Carriers](https://www.bloomberg.com/news/articles/2026-11-22/china-objects-to-us-curbs-on-telecoms-access-to-phone-numbers) ⭐️ 7.0/10

China&\#x27;s Commerce Ministry on Nov. 22 urged the U.S. to withdraw a measure that blocks China Mobile, China Telecom and China Unicom from directly obtaining U.S. phone numbers, saying it violates non-discrimination and fair-competition principles and that the FCC cited national security risks without factual basis. The FCC voted on Nov. 19 to tighten security requirements for voice-over-internet providers seeking direct access to U.S. numbers, adding a national security certification intended to keep entities, equipment and services on its Covered List off U.S. networks; the ministry said the moves are pushing the two countries toward decoupling in telecom, communications and testing and certification.

telegram · zaihuapd · Nov 22, 06:44

**「Background」** The U.S. Federal Communications Commission, which regulates U.S. telecom networks, voted on Nov. 19 to bar China Mobile, China Telecom, China Unicom and other IP-enabled service providers from direct access to U.S. phone numbers, adding a national-security certification requirement.

**「Affected parties」** The restriction directly affects China Mobile, China Telecom and China Unicom by cutting off their direct access to U.S. numbering resources for voice services, and it adds a national-security certification hurdle for other IP-enabled providers on the FCC’s Covered List.

<details><summary>References</summary>
<ul>
<li>FCC votes to ban Chinese telecoms from direct access to US phone numbers | Reuters</li>
<li>FCC Votes to Ban Chinese Telecoms From Direct Access to US Phone Numbers</li>
<li><a href="https://www.jpost.com/international/article-915665">China slams US FCC ban on direct phone number access for...</a></li>

</ul>
</details>

**Tags**: `#美中电信政策`, `#FCC监管`, `#中国运营商`, `#国家安全`, `#电信脱钩`

---

<a id="item-finance-news-3"></a>
### [Record El Niño sea-temperature reading adds pressure to food aid](https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/) ⭐️ 7.0/10

A key Pacific sea-temperature measure of El Niño strength reached 3.5°C in October, beating the previous record of about 2.75°C, and the World Food Programme warned the event could push an additional 49 million people into acute food insecurity by the end of 2027.

telegram · zaihuapd · Nov 22, 14:09

**「Background」** El Niño is a periodic warming of the central tropical Pacific that can disrupt rainfall and crops. The World Food Programme warned in August that this event could push an additional 49 million people into acute food insecurity—severe hunger that threatens lives or livelihoods—by the end of 2027, bringing the total to 274 million.

**「Impact」** Food-aid-dependent households, especially in Somalia, face reduced coverage: WFP&\#x27;s reach there fell from 10 million people to under 1 million during a similar drought, while global aid funding in 2025 is 30% below its 2022 peak.

<details><summary>References</summary>
<ul>
<li><a href="https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/">How This Year’s Super El Niño Will Worsen Global Hunger | WIRED</a></li>

</ul>
</details>

**Tags**: `#El Niño`, `#food insecurity`, `#humanitarian funding`, `#climate risk`, `#WFP`

---