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
          Color photograph of two soldiers computing artillery firing solutions. (NAID: 329590735)
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

I am back on Chip Huyen's book AI Engineering. I am starting in Chapter 3: Evaluation Methodology. She writes that evaluating foundation models is difficult because they are open-ended. These are not the old school classification machine learning models that make binary distinctions between "is a duck" and "is not a duck." There is no scoresheet to grade them against. It's also hard to grade these models becasue they are now extremely capable. The evaluators "need to fact-check, reason, and even incorporate domain expertise." Finally, model evaluation is tricky because models are often black boxes; that means that the evaluators don't know or have access to the model architecture, training data, and training process, all which provide clues to the model's capabilities. 

The pace of AI development makes it difficult for evaluation benchmarks to keep up. She lists half a dozen benchmarks that have come and gone in the last eight years. 

As an aside, I came across the paper "[BetterBench: Assessing AI Benchmarks, Uncovering Issues, and Establishing Best Practices](https://arxiv.org/abs/2411.12990)" by Reuel et al. Benchmarking raises two issues: "what a benchmark measurs and how this measurement is used." Current benchmarks have a narrow scope. AI folks tend to "overgeneralize benchmark results." The authors propose best practies for AI benchmarks. They note that:
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

*Bottom Line: Perplexity is a good proxy for a model's capabilities.* 

Oh my days, there's way more to this chapter, and I have not even started this week's readings. ☹️

---

Testing out markdown:


I need to highlight these ==very important words==.
H~2~O
X^2^
~~The world is flat.~~


