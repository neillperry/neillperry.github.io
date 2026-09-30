---
layout: post
title: Policy Basics
date: 2026-09-26
jumbotron: Policy Basics
regular_date: September 26, 2026
summary:  Let's go through a laundry list of AI policy terms and concepts and see how well I can explain them.    

---

<figure style="text-align:center;">
<img src="https://catalog.archives.gov/medialive/0/3873/6387300/content/arcmedia/stillpix/330-cfd/1985/DF-SC-85-09643.jpeg" 
     alt="Color image of the painting called 'Basics at Lackland' by Shannon Hogan. The painting is of three Air Force trainees navigating an obstacle course station (NAID: 6387300)" 
     title="Basic training flashbacks"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          Color image of a painting of three Air Force trainees climbing over an obstacle at basic training. (NAID: 6387300)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 

### Background

I recently applied for an AI fellowship. That application included a familiarity assessment that asked how well I understood a dozen AI terms and concepts.  To check my math, I am going to try to explain them here. I will cite outside sources and quote from any Clanka explanations. As always, this post is written by me, but I sometimes do Q&A with Claude to clarify what is going on. 

On to the concepts!

### Compute Governance

Compute governance is the subject of this week's policy readings, and I feel pretty strongly about this one. This issue deals with ensuring that a country has sufficient compute to train models and run inferences. From that goal flow secondary concerns of access to advanced semiconductors, construction of data centers, and access to sufficient electrical power. 

In the United States, this often involves the topics of industrial policy, such as the CHIPS Act, which promotes research and domestic onshoring of semiconductor fabrication. It also involves export controls to limit certain nations' access to advanced chips. Understanding compute governance also involves a fundamental understanding of the technology behind semiconductor production and the specific hardware required for AI models. 

### Model weights

My answer to this was that the weights are the coefficients that correspond to the values that go into modelling the phenomenon, i.e., the large language. 

Let's check my work. Chapter 5: Machine Learning Basics of [Deep Learning by Ian Goodfellow, Yoshua Bengio and Aaron Courville](https://www.deeplearningbook.org/) covers this. It defines a set termed *w* as a vector of parameters. 

"We can think of *w* as a set of weights that determine how each feature affects the prediction. If a feature [x subscript i] receives a positie weight [w subscript i], then increasing the value of that feature increases the value of our prediction [y-hat]." If the weight is negative, then there is an inverse predictive relationshp. The numerical size of the weight relates its predictive impact. 

Going off of Chip Huyen's book AI Engineering, she notes that during model pre-training "model weights are randomly initialized."  The RAND report "Securing AI Model Weights" introduces the concept as "the learnable parameters that encode the core capabilities of an AI Model." These parameters are "derived by training the model on massive datasets." They "stem from large investments in data, algorithms, compute (i.e., the processing power and resources used to process data and run calculations)."

On this one, I felt like I understood the concept but not able to articulate as clearly. 

Moving on. 


### Gradient Licensing

Concept does not exist. This is likely a foil to catch unscrupulous applicants.  

### Red-teaming

Red-teaming is a concept in cybersecurity in which an internal team plays the role of bad guys to stress test the effectiveness of security controls. This is useful because the it identifies what actual bad guys might do to compromise a system, which blue team (the company's IT defenders) can use to improve their security configurations and infrastructure. Red teaming is like getting an inactivated vaccine that contains a dead virus. 


### Capability offset credits

Concept does not exist. This is a real thing that employers do to catch folks in assessment tests. 


### Risk tiers in the EU AI Act

So the [European Union enacted its AI Act](https://www.europarl.europa.eu/topics/en/article/20230601STO93804/eu-ai-act-first-regulation-on-artificial-intelligence#ai-act-different-rules-for-different-risk-levels-6), which went into law in August 2024. 

1. **Unacceptable Risk** -- the Act generally prohibits these risks. They include social scoring, cognitive manipulation (telling children to do something dangerous), exploitation of vulnerabilities. Biometric identification and categorisation are also banned. 
2. **High** -- [according to this Irish government website](https://enterprise.gov.ie/en/what-we-do/innovation-research-development/artificial-intelligence/eu-ai-act/#risk), there are actually two categories of AI systems that fall into this category. The first category includes systems are regulated, and they include AI incorporated into devices subject to product safety rules, i.e., toys, aviation, cars, medical devices. The second category are the use cases enumerated in Annex III of the Act. 
3. **Limited** -- these only have transparency requirements.
4. **Minimal** -- these are not regulated.

Somewhat frustrating but the EU doesn't have handy resources on explaining the EU Act, or perhaps that is Google downranking official documents. I had to resort to the Wikipedia article to get an explanation.

From what little I saw, most of the Act focuses on the high risk category.  These applications "must comply with security, transparency and quality obligations, and undergo conformity assessments" ([Wikipedia](https://en.wikipedia.org/wiki/Artificial_Intelligence_Act)).


### Frontier model

Frontier models are the most advanced AI model currently available. They are typically considered a class of models instead of a reigning champion.  

I haven't found a good definition of frontier because the books I'm consulting are more advanced than that.  I may come back to this. 


### Inference tariff harmonization

Concept does not exist, but it sounds plausible. 


### Evaluation sandbagging

When the model takes a dive during a test was my guess, which is basically correct.

There's a paper called "[AI Sandbagging: Language Models Can Strategically Underperform on Evaluations](https://arxiv.org/pdf/2406.07358)" by van der Weijj, Hofstatter, Jaffe, Brown, and Ward. The title pretty much sums it up. There's a way for AI developers to build a model that underperforms on evaluations. The benefit to this is that evaluators will grade the model as less capable, hence less dangerous. 

This sandbagging trick is old wine in new bottles. [Volkswagen intentially programmed its cars](https://en.wikipedia.org/wiki/Volkswagen_emissions_scandal) to cheat on emission tests about a decade ago. 

I did not realize that some sandbagging may be unintentional. The paper notes that "an AI system may underperform on an evaluation, even without the developer's intent." Some agents "may develop goals which incentivise strategically underperforming because it is instrumentally useful."


### RLHF

I feel fairly good about this one based on my reading of Nathan Lambert's book [Reinforcement Learning from Human Feedback](https://rlhfbook.com/).  That being said, I need to dive back into reading it. 

### Latent capability bonding

Concept does not exist.

### Mechanistic interpretability

This is a real thing, introduced in an August 2024 paper, "[Mechanistic Interpretability for AI Safety: A Review](https://arxiv.org/pdf/2404.14082)" by Bereska and Gavves. The paper defines the concept as "reverse engineering the computational mechanisms and representations learned by neural networks into human-understandable algorithms and concepts to provide a granular, causal understanding."  There's a handy chart to distinguish among behavioral, attributional, concept-based, and mechanistic intepretability paradigms. 

Mechanistic interpretability "aims to completely specify a neural network’s computation, potentially in a format as explicit as pseudocode."

Six months later, Anthropic published its paper on [Circuit Tracing: Revealing Computational Graphs in Language Models](https://transformer-circuits.pub/2025/attribution-graphs/methods.html). 

I asked Claude about this concept, and it suggested searching for the terms "attribution graphs," "circuit training," or "sparse autoencoders."


