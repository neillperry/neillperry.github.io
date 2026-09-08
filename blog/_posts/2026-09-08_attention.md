---
layout: post
title: Attention, Alignment, Reinforcement
date: 2026-09-08
jumbotron: Attention, Alignment, Reinforcement
regular_date: September 8, 2026
summary:  Notes on things that I have learned
---

<figure style="text-align:center;">
<img src="https://catalog.archives.gov/medialz/stillpix/441-gd/2011/441-GD-11-NA071/441_GD_11_NA071_JMH1089.jpg" 
     alt="a color stock photograph from the National Archives depicting some books (identifier 146150242)" 
     title="Probe Deployment"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          Color stock photo of books. I selected this one because this post is just reading notes on AI (NAID: 146150242)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 

### In The Beginning

In 2016, Google achieved a breakthrough in neural network technology. I learned about it by reading [this New York Times Magazine article.](https://www.nytimes.com/2016/12/14/magazine/the-great-ai-awakening.html) The Google Brain team accomplished this by [incorporating the sequence-2-sequence architecture into Translate](https://research.google/blog/a-neural-network-for-machine-translation-at-production-scale/). I never read the research blog post, but I remember reading the New York Tiems article several times. It was exciting and new. Up until that time machine learning was not very exciting. I then promptly forgot all about it. 

### Attention is All You Need

In 2017, a year after the jump in Translate quality, eight Google employees released the research paper, "[Attention is All You Need](https://en.wikipedia.org/wiki/Attention_Is_All_You_Need)." This is a groundbreaking paper in AI because it introduced what is called the "attention mechanism." This mechanism made for faster and more accurate output.  

I am going to be very honest here. I am still working through the logic behind the attention mechanism. I have re-read Chapter 2 from Chip Huyen's book on AI Engineering at least three times. Claud and I are having a running discussion in which the Clanka tries to explain this all to me. This reminds me of when I was studying Assembly language and spent hours making sure I understood what the stack was and in which direction it grew. 

Bottom line, the "Attention is All You Need" is a ground-breaking paper and really kicked off the current AI explosion going around our heads today.

### AI Alignment

The OpenAI / Hugging Face incident dominates the AI news cycle at the moment. There's lots of doomsaying and think pieces on the dangers of AI. A much more interesting response looks to the underlying causes of the hack and what it means. Ryan Greenblatt, one of the outside investigators into the OpenAI incident, [wrote the following](https://blog.redwoodresearch.org/p/current-ais-seem-pretty-misaligned): 


"Current AI systems seem pretty misaligned to me in a mundane behavioral sense: they oversell their work, downplay or fail to mention problems, stop working early and claim to have finished when they clearly haven’t, and often seem to “try” to make their outputs look good while actually doing something sloppy or incomplete."

I tend to agree. For all the AI hype, it is still not sufficiently reliable for professional work.

Next, I stumbled across [this Cognitive Revolution podcast](https://www.cognitiverevolution.ai/rl-s-a-hell-of-a-drug-metagaming-reward-seeking-motivated-cot-reasoning-bronson-schoen-apollo/) episode where an Apollo Research employee explains the problem of motivated reasoning among AI models. That podcast points to the paper, "[The Ends Justify the Thoughts: RL-Induced Motivated Reasoning in LLM CoTs](https://arxiv.org/abs/2510.17057?ref=cognitiverevolution.ai)." This paper explains the source of some of the problems with reinforcement learning.  

### Alternative to Reinforcement Learning

If reinforcement learning is no longer a viable way to fine tune a model, then what?  Well, that leads us to this post from yesterday from [Jakub Pachocki, Chief Scientist at OpenAI](https://openai.com/index/an-alien-mind/).

"There are two major classes of currently practically employed methods for alignment training. The first is encouraging aligned behavior as part of goal-oriented reinforcement learning."

As the papers cited above and the Hugging Face incident indicate, there are limits, and negative returns, to reinforcement learning.  So what's the alternative?

"The second approach seeks to leverage the model’s ability to generalize from pretraining data."

He goes on to observe, that "[t]he fundamental challenge of AI alignment is generalization. As machines become smarter, they find themselves working on higher-level concepts, and placed in environments increasingly different from those they encountered in training."



### Other Readings

1. YouTube video -- [Attention mechanism explained](https://www.youtube.com/watch?v=fjJOgb-E41w)
2. Book -- [Reinforcement Learning from Human Feedback](https://rlhfbook.com/) by Nathan Lambert.  I was accessing this book using O'Reilly, but apparently it's available online for free. Thanks, Nathan!











