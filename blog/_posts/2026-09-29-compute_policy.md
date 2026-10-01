---
layout: post
title: Weekly -- Compute Policy
date: 2026-09-29
jumbotron: Weekly -- Compute Policy
regular_date: September 29, 2026
summary:  Let's procrastinate doing the weekly reading and read some other AI policy things. 

---

<figure style="text-align:center;">
<img src="https://catalog.archives.gov/medialz/stillpix/111-sc/Batch0015/Box776/111-SC-103055_001.jpg" 
     alt="Black and white photograph of a soldier peering through what looks like surveying equipment. The title of the photograph is 'Balloon Reading' but there is no balloon in frame (NAID: 329590735)" 
     title="Do you see what I see?"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          Black and white photograph of a soldier peering through what looks like surveying equipment. The title of the photograph is 'Balloon Reading' but there is no balloon in frame. (NAID: 329590735)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 

### Weekly Reading

It's time again to get my weekly reading done before AI policy class later today. This week is compute policy, but I think I'll read some random stuff beforehand. 


### Model Evaluations

I am back on Chip Huyen's book AI Engineering. I am starting in Chapter 3: Evaluation Methodology. She writes that evaluating foundation models is difficult because they are open-ended. These are not the old school classification machine learning models that make binary distinctions between "is a duck" and "is not a duck." There is no scoresheet to grade them against. It's also hard to grade open-ended foundation models becasue they are now extremely capable. The evaluators "need to fact-check, reason, and even incorporate domain expertise." Finally, model evaluation is tricky because models are often black boxes; that means that the evaluators don't know or have access to the model architecture, training data, and training process, all which provide clues to the model's capabilities. 

The pace of AI development makes it difficult for evaluation benchmarks to keep up. She lists half a dozen benchmarks that have come and gone in the last eight years. 

As an aside, I came across the paper "[BetterBench: Assessing AI Benchmarks, Uncovering Issues, and Establishing Best Practices](https://arxiv.org/abs/2411.12990)" by Reuel et al. Benchmarking raises two issues: "what a benchmark measures and how this measurement is used." Current benchmarks have a narrow scope. AI folks tend to "overgeneralize benchmark results." The authors propose best practies for AI benchmarks. 

Reuel et al note that:
* **"Not all benchmarks are of the same quality."** -- some of them are crappy. In fact, the report says that they found a "strong discrepancies in AI benchmark quality." Relying on crappy benchmarks results in poor understanding of their capabilities. Also, government regulations rely on evaluations, so this is a problem.
* **"Most benchmarks fail to distinguish signal and noise"** -- evaluators should evaluate the same model multiple times with different random seeds or sampling temperatures and report the statistical breakdown of those tests. 
* **Insufficient implementation limits reproducibility and scrutiny of benchmarks** -- evalutors do not provide enough data on how they conduct their evaluations, which means that no one can reproduce the evaluations themselves or otherwise understand the process. 

Back to Chip Huyen....

She says that the evalution investment is trailing and a problem. "When asked how they are evaluating their AI applications, many people told me that they just eyeballed the results." 😬 She now moves on to evaluating large language models, since these are core component of most foundation models these days. 

 Huyen warns that things are about to get very mathematical here.  She identifies four metrics for LLMs: cross entropy, perplexity, bits-per-character (BPC) and bits-per-byte (BPB). 

To explain entropy, she goes back to basics. Langauge models encode "statistical information (how likely a token is to appear in a given context) about languages." "In ML lingo, a language model learns the distribution of its training data." So entropy "measures how difficult it is to predict what comes next in a language." The lower the entropy, the more predicatable the langauge. Okay, entropy is actually a numerical value. Cross entropy relates to the data set that the language model was trained on; how difficult is it for the model to predict what comes next in that dataset (versus entropy which measures predictability across the language itself). 

*Claude says that my understanding of cross entropy is off. It "measures how well a model predicts the data. It compares the model's predicted probabilities with what actually appears in the dataset."* Touche. Huyen does state that, "Cross entropy tell us how efficient a langauge model will be at compressing text."

Some mathematical formulae follow to define these relationships. 😶  Bottom line, "a language model is trained to minimize its cross entropy with respect to the training data." It's trained to accurately predict the next token. "You can think of a model's cross entropy as its approximation of the entropy of its training data." I think I have those two concepts straight.

I am skipping BPC and BPB. 

Perplexity - which is also the name of an AI company - "is the exponentional of entropy and cross entropy." It "measures the amount of uncertainty it has when predicting the next token." There's some more math formulas and something about natural log.  Let's skip to the general rules, more like guidelines:

* **More structure data gives lower expected perplexity** - HTML code is more predicatble than human language.
* **The bigger the vocabulary, the higher the perplexity** - the more tokens in the gumball machine, the less likely you are to know what is next.
* **The longer the context length, the lower the perplexity** - by looking at the previous n tokens, a model predicts the next token.  The large the value for n, then the more accurate its prediction. 

*Bottom Line: Perplexity is a good proxy for a language model's capabilities.* 

Oh my days, there's way more to this chapter, and I have not even started this week's readings. ☹️

---

### Choking off China’s Access to the Future of AI

[Report by Gregory Allen](https://www.csis.org/analysis/choking-chinas-access-future-ai). This is a four-year old report on Biden's semiconductor policy.  The policy is design to "strangle the Chinese industry by choking off access" to AI chips, chip design software, semiconductor manufacturing equipment, and components. I did not know that there was special chip design software. 

So the policy is a revamp of the previous policy of limiting access to the Chinese military. That's not really possible, so the administration was just cut off the entire country. The U.S. got tired of all the "state-sponsored corporate espionage, forced technology transfer, market access restrictions, export control violations, human rights violations" in Xinjiang and Hong Kong. The U.S. is dropping the economic hammer. 

"NVIDIA accounts for 95 percent of AI chip sales in China." This is why NVIDIA is so keen on exceptions to the chip sanctions. It's choking off their cash flow.  

Okay, now to the chip designing software that I had never heard of: "electronic design automation (EDA)." This report states that Chinese semiconductor manufacturers are "significantly less technologically advanced" than their global counterparts. 

The report makes the point that this enforcement scheme reminisces the Huawei sanctions. 

### How US Export Controls Have (and Haven't) Curbed Chinese AI

So last summer (2025), [Chris Miller looked at what export controls had achieved](https://ai-frontiers.org/articles/us-chip-export-controls-china-ai). This is something I wonder a lot. Do these controls actually work? The semiconductor market is global and complex, and I am skeptical as to how useful these controls are. 

Miller says that the restrictions "have not prevented Chinese labs from producing highly competitive [AI] models." He also notes that Chinese cloud computing companies have nto expanded much outside of China. I'm not sure this can be attributed to the export controls. 

He starts off with some history. Current export control regime began in 2018 when the US persuaded ASML / Netherlands to not sell extreme UV lithography tools to China. These EUV tools weigh over 165 tons!   So China's SMIC was poised to run the same industrial policy playbook on its Western competitors that other Chinese state-sponsored firms have, but the export controls prevented that. The original export controls were focused on slowing China's tech growth generally, but in 2022 the focus shifted to slowing their development of AI. 

"[M]ost of the high-bandwidth memory (HBM) chips paired with Huawei's AI processors are either purchased or smuggled from abroad." Yes, there is smuggling, but the controls are sufficiently strong to limit the amount of compute available to China. Yet despite that limitation, Chinese companies are producing very capable AI models. They can train the models, but having they don't have inference compute to deploy them. 

Miller then talks about Huawei's limited share of global AI infrastructure. American firms dominate cloud computing, and this also supports AI. 

He concludes that, "export controls have given the US a commanding lead in AI." 🧐 I feel like other factors contributed to US's lead in AI development. Export controls may have contributed, but I doubt it's the predominant factor. 

### Computing Power and the Governance of AI

I am so sleepy 🥱. Two more hours until class starts. Gotta push through on this. Let's read [the GovAI paper on computing power and AI governance](https://arxiv.org/pdf/2402.08797) and try to stay awake. 

Basically, given the critical role compute plays in AI development and services, governments use compute as a lever to regulate AI. Unlike training data, algorithms or models, compute is tangible hardware that is "detectable, excludable, and quantifiable." Of course, there's more ways / needs to regulate AI use than compute allows. 

I zonked out for 4 minutes in this chair. 😴 This is not to knock the paper, which is 104 pages long. I am not going to make that, so I skipped ahead to Chapter 4: "Compute Can Enhance Three AI Governance Capacities."  

Compute can enhance AI governance by:
- "increasing the visibility of AI to policymakers"
- "allocating AI capabilities"
- "enhancing enforcement of norms and laws"

Visibility means that government can quickly identify who is building and using AI as well as measure the AI's capabilities. It's also important for international agreements. 

Allocation means that government can steer compute resources to promote or discourage particular uses of AI. They can do this via subsidies or industrial policy. 

Enforcement means that regulators can prevent or respond to rule violations. They can impose "computing caps" or other hardware based enforcement actions.  Not sure what that means. 

### Artificial Intelligence Index Report 2026

This thing is over 400 pages long! It's a [report published by Stanford's HAI](https://hai.stanford.edu/assets/files/ai_index_report_2026.pdf). That's a lot of writing. My assignment is pages 9-11. I read pages 9-11, and they were drab. The whole report is an exercise in A.I. news content curation / headline aggregation.

Instead of reading all that, let's read Kyle Chan. In the China vs US tech policy space, there's a lot of posers, but Kyle Chan is the deal real. I always love a good counter-argument, and his blog post, "[Why China is Winning the Chip War Against the U.S.](https://www.sinification.org/p/why-china-is-winning-the-chip-war)" seems deliciously iconoclastic. 

"China is trying to get around technology restrictions using a host of strategies, including open-source RISC-V architecture, older DUV lithography, advanced 3D packaging and chiplets." This is my primary concern about export controls. A lot of policy doesn't look to second order effects, and I get the same vbie with the semiconductor debate. Okay, we choked off China, now what? How are they responding?  Miller's article discussed above really didn't go into that. 

He Pengyu argues that China should focus on the legacy chips market that U.S. export sanctions don't impact. He argues that China can innovate in the legacy chip product space in an analogous way that Japan did in the 1960s / 1970s. Innovation there can bleed into the leading edge technology. "[F]or companies or countries playing catch-up, there may be opportunities to leapfrog ahead by discovering entirely new axes of innovation." Bingo. 

Be worried about the things that you don't know you don't know. I'd be very wary of evaluating the impact of export sanctions / CHIPS Act without knowing a lot more about recent developments in Chinese fabrication and research and development. They have some very smart, creative folks in that billion plus country. 








