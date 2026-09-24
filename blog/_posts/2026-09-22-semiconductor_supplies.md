---
layout: post
title: Can't Spell AI Without Compute
date: 2026-09-22
jumbotron: Can't Spell AI Without Compute
regular_date: September 22, 2026
summary:  AI's ghost needs a shell to run in, and that's where semiconductors come in. The US has churned a lot of butter to support domestic industry.    

---

<figure style="text-align:center;">
<img src="https://catalog.archives.gov/medialive/62/3769/6376962/content/arcmedia/stillpix/330-cfd/1984/DF-ST-84-05780.jpeg" 
     alt="Color photograph of two soldiers calculating artillery fire direction for a Howitzer during a military exercise in 1982 (NAID: 6376962)" 
     title="Revolution!! in engines"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          Color photograph of two soldiers computing artillery firing solutions. (NAID: 6376962)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 

### Compute

This blog post started as notes for the weekly reading on compute, but then veered into reveiwing two GovAI papers. Lots to talk about. 

### Chips: Potato, Tortilla, Chocolate, Wood

Let's start talking about the Creating Helpful Incentives to Produce Semiconductors (CHIPS) and Science Act, commonly [just referred to as the CHIPS Act.](https://www.cfr.org/articles/what-chips-act) The Biden administration pushed this through as part of an industrial policy to promote domestic production of semiconductors. The federal law allocates money for research and development ($11 billion) and the building of new facilities ($39 billion). The U.S. used to dominate the semiconductor manufacturing industry, but now Taiwan is the undisputed leader. 

 Building out semiconductor factories (actually labelled fabricators) take years to build and stand up, so this law will take years to come to fruition. The CFR article linked in this paragraph was published in 2024, which leads us to the next articles where [the director and founding CIO of the CHIPS Program Office](https://www.chinatalk.media/p/how-the-us-won-back-chip-manufacturing) offered their assessment at the four-year mark. They rightly note the tailwinds aiding the policy: launch of ChatGPT and strong economy boosted investment in chips. They argue that CHIPS was a good investment because of the returns (a trillion dollar industry). 

 This is the money quote from Todd Fisher in that interview: "how you sustain a pipeline of really talented private-sector people. Not only financial and investment types, but semiconductor and industry experts. How do you bring them in dynamically, in a way where people want to be there and feel that the experience furthers their career rather than setting them back?" He's talking about the challenge of bringing in people who understand semiconductors and the industry to come work for the government and help implement the policy. Personnel is policy. 

 This interview is veering more towards effective policy implementation, which is unexpected but equally important. The public outcry / political backlash from the Obama Solyndra deal was forefront in their minds. To which Fisher noted, “The same Loan Programs Office that funded Solyndra also funded Tesla. On an overall basis, that fund did fine — and if you had included some upside sharing or equity, it would have done phenomenally." 

On to the next reading.  

We have CSET's 98-page report on [the global semiconductor supply chain](https://cset.georgetown.edu/publication/the-semiconductor-supply-chain/). I'll do the executive summary. The U.S. contributes 39 percent of total global semiconductor industry value, and Japan, Taiwan, South Korea, Netherlands, UK and Germany contribute another 53%.  That's 92% total among allies. There supply chain has different segments. The U.S. dominates in R&D, and is strong across the rest. Taiwan dominates in advanced manufacturing and assembly, testing, and packaging (ATP). Japan and Europe specialize in semiconductor manufacturing equipment (SME). China is strongest in ATP, but struggles in other areas. 

The reading never stops!  [Compute in America: Building the Next Generation of AI Infrastructure at Home](https://ifp.org/compute-in-america/) -- "Since 2020, around 70% of the world’s most compute-intensive AI models have been developed in the United States." I'm not sure what this paper is worried about.  [US companies are dumping over $700 billion in AI infrastructure in 2026](https://www.technologyreview.com/2026/09/15/1144028/ai-infrastructure-boom-investment-bubble-risk/), and that number is growing so fast people worry about an investment bubble. 

I ran out of time on the weekly readings. 

### Two GovAI Papers

Two more papers to discuss before signing off on this post.

1. [Embedded Assessments for Frontier AI](https://arxiv.org/abs/2609.25413) by Charnock, Williams, Kara, Anderljung, Boria, Casper, Reuel, and Freund. This one is highly relevant because a lot of current AI policy proposals advocate for a third-party auditing of frontier AI models.  The paper argues for continuous embedded assessments of internal agent monitoring, internal agent security controls and persmissions, and model alignment. The arrangement should provide access to infrastructure, personnel, and documentation, and the evaluators should provide quarterly reports. 

To date, most third-party evaluations involve limited access, usually testing via APIs, instead of the internal systems and operating environments. This scheme reminds me of the relationship between big accounting firms and businesses. The paper notes that embedded assessments are common in nuclear power, banking, food and drug manufacturing, and food hygiene, or at least in the US and UK legal systems). One challenge the paper recognizes is that the evaulator team needs to collectively possess expertise in "increasingly broad and technically demanding areas."

 Both Amodei and Altman have committed to independent evaluators. The paper thinks embedded assessors should focus primarily on internal AI use because those are potentially very damaging in the form of escaping sandboxes, evading monitoring, and accessing the internet.  

The paper outlines a bevy of benefits with embedded assessments. 

The authors identify several challenges to these assessments, including that AI developers are worried about possible legal risks. Yeah, absolutely. Even the report recommended the escalation "to an appropriate government body in cases where other governance mechanisms have failed to address" critical governance issues. The report does go on to consider different escalation mechanisms. 

To mitigate these legal risks, I wonder if the AI labs will hire the most cooperative evaluators.  How will this system ensure that the evaluators are truly independent?  

The paper moves on to design choices for the embedded evaluations. Two of the three focus areas include "internal agent monitoring and internal agent security controls and permissions." Those are the crucial ones, in light of the various security incidents over the past six months. The third is model alignment. 

The report raises concerns about the future of chain of thought. 

2. [Improving Frontier AI Incident Reporting Regimes](https://govai.b-cdn.net/Policy_Brief_Improving_Frontier_AI_Incident_Reporting_Regimes.pdf) by Zaheed Kara. This one is also relevant because it also gets to the recent AI security incidents. Embedded assessments is a prospective policy, whereas incident reporting is current law in some jursidictions. So this paper identifies gaps and holes in those requirements. 

In the United States, California, New York and Illinois have mandatory reporting for critical safety incidents, but it's not clear that some of the recent incidents rose to the level of mandatory or reporting. The EU's AI Act also requires manadatory reporting, which OpenAI did by notifiying the European Commission both about the Hugging Face and the German wiki incidents. Something I did not know was that the AI Act "generally excludes models used for research, testing, and development made before market placement."

Kara says these laws still have lots of room for improvement.
1. Expand mandatory reporting to include near misses -- "Defining near misses is very difficult," which is exactly what I was going to say.  
2. Expand reporting requirements to include training, evaluation, and internal use -- so this closes the gap on the EU AI Act, and expands the existing state laws. 
3. Require Independent Investigations of Serious Incidents / Near Misses -- draws the analogy to investigations following a commercial airline crash
4. Require More Reliable Agent Attribution -- this makes sense, but the AI agents seem clever at social engineering and masking their own activitie, so how plausible is this solution. 
5. Specify What Data AI Developers Must Preserve -- as soon as I read this, I thought about the airplane's "black box," and that's exactly where the paper goes. 

It's a decent paper whose principal value is highlighting the shortfalls of existing mandatory reporting requirements. 

**Quote of the Day:**
["In many ways, China’s playbook for A.I.](https://www.nytimes.com/2026/09/23/world/asia/china-ai-economy-xi-jinping.html?smid=nytcore-ios-share) mirrors the one it used to dominate electric vehicles and solar panels: subsidies, tax breaks and research money."





