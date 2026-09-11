---
layout: post
title: End of the World, Part 43
date: 2026-09-09
jumbotron: End of the World, Part 43
regular_date: September 9, 2026
summary:  The world is ending. Again.
---

<figure style="text-align:center;">
<img src="https://catalog.archives.gov/medialive/55/5240/524055/content/arcmedia/media/images/22/30/22-2936a.gif" 
     alt="black and white photograph from the National Archives depicting the ruins of San Juan (identifier 524055)" 
     title="Ruins"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          Black and white photograph of the ruins of San Juan; photo taken in 1873 (NAID: 524055)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 

### End of the World

[As is widely reported](https://www.wsj.com/tech/ai/anthropic-researcher-quits-over-out-of-control-ai-fears-707b7628), an engineer at Anthropic suddenly quit his job out of moral concerns regarding powerful AI systems. Somewhat inexplicably, Anthropic's top scientist posted on social media validating those concerns by saying that there is a greater than ten percent chance that AI could kill all humans within the next ten years. That is an extraordinary claim to make from a senior AI scientist at a frontier AI lab, and social media predictably set itself on fire.  

There's a bit of hyperbole mixed with doomerism in that prediction. Instead of hand-wringing, let's instead look at a measured article that discusses how AI will reshape society. 

### AI as Normal Technology 

[AI as Normal Technology](https://knightcolumbia.org/content/ai-as-normal-technology) is the best essay that I have read that sketches out the future impact of AI. The authors argue that the "transformative and society impacts [of AI] will be slow (on the timescale of decades)." They base this claim on current trends as well as previous examples of new technology. 

Here are some high level take aways:

1. AI diffusion in safety-critical areas is slow -- meaning that AI is not yet good enough for humans to trust it to do something dangerous like land a commercial airliner or perform open heart surgery. AI is pretty good right now, but it has a ways to go. 

2. Diffusion is limited by the speed of human, organizational, and institutional change -- the adoption of new technology is limited by organizations and institutions. The authors explain how in the late 19th century factories did not immediately adopt electricity. Instead, it took decades, and a reorganization of factories into assembly lines, before they started using the new technology. They expect similar organizational friction for AI diffusion.  

3. The external world imposes speed limits on AI innovation -- this point is somewhat related to the first one.  There's a gap between AI methods and applications. The applications of AI to specific problems is so far insufficiently reliable for mass adoption. 

4. Benchmarks do not measure real-world utility -- someone claimed that AI eliminated math by solving one of the Millenium Challenges. A counter point was made that there's a lot that mathematicians do besides construct formal proofs. In this essay, the authors discuss how AI is great at passing the bar exam (a standardized test) but struggles at the many other tasks that a lawyer engages in on a daily basis. 

This essay relies on historical precedent of previous technological innovations. Because historical analogies such as this are my favorite type of argument, I find this essay highly persuasive. It's also a nice counterbalance to the falling-sky of the Anthropic folks. 


### Cybersecurity and AI

That's not to say that AI's impact will be all positive. There will certainly, and currently are, be some negative consequences. Let's consider how AI is changing cybersecurity right now. 

While everyone was arguing about the Anthropic duo, [the Google Threat Intelligence Group](https://cloud.google.com/blog/topics/threat-intelligence/from-prompting-to-autonomy-the-evolution-of-adversarial-ai) and [Anthropic](https://www.anthropic.com/threat-intelligence-report-september-2026) each published reports on how malicious actors are using AI to attack and compromise computer networks.  

Here are some quotes from the Anthropic report: 

“the risk from AI adoption is more pronounced across the cyber kill chain, where adversaries can operate faster, across a broader and deeper surface area, with fewer resources”

“sophistication has stopped being a reliable signal of who is behind an operation” 

“multi-agent frameworks executing reconnaissance, exploitation, and data exfiltration”

“With AI, however, the pre-existing ecosystem of criminal cyber conduct has increased in scale and severity.” 

“everything connected to the internet is a potential target for exploitation”

“The actor used Claude by helping to identify, understand, and use developer and authentication APIs, create and convert privileged tokens, and build tools to enable bulk exports and cross-tenant data collection.” 

“One breach of an enterprise software company took only hours from first access to bulk data theft.” 

“Very often, the operator may not directly understand each target environment or the complexities of finding and accessing valuable information, instead deferring the specific to the AI.” 

“We have identified multiple threat actors who have effectively established automated exploit foundries with AI. In doing so, they have designed and implemented autonomous workflows by which they can direct Claude to conduct vulnerability and exploit research agentically around the clock.” 

This is all eye-opening. The adoption of and adaptation to AI capabilities is striking. I will continue reading this.

I will say that reading these reports is much more useful than debating the 10% annihilation in 10 years prediction because these are specific events happening right now.  Focusing on specifics allows policy makers and engineers to create a plan to respond. You can't respond to vague prognostications. 


### Basics

I am continuing my self-study into AI. Since my last post, I arrived at a good understanding of the attention layer. I am still reading Chip Huyen's AI Engineering book, but now I am bouncing over to Alammar and Grootendoorst's [book Hands-On Large Language Models](https://www.oreilly.com/library/view/hands-on-large-language/9781098150952/) too. It's been very helpful so far.  

Here are my notes so far from LLM:  

"A step in encoding this text was achieved through recurrent neural networks (RNNs). These are variants of neural networks that can model sequences as an additional input. To do so, these RNNs are used for two tasks, encoding or representing an input sentence and decoding or generating an output sentence."


"Embeddings are vector representations of data that attempt to capture its meaning. To do so, word2vec learns semantic representations of words by training on vast amounts of textual data, like the entirety of Wikipedia." Alammar and Grootendoorst, Hands-On Large Language Models

Creating an LLM:

There is a two-step process:

1. Language modelling -- the model is trained to recognize "grammar, context, and language patterns."  This process "takes the majority of computation and traiing time."

2. Fine-tuning -- additional training scoped to a particular task. 









