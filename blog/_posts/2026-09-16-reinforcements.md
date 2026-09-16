---
layout: post
title: Here Comes the Reinforcements
date: 2026-09-16
jumbotron: Here Comes the Reinforcements
regular_date: September 16, 2026
summary:  Let's learn about reinforcement learning. And maybe some human feedback. 

---

<figure style="text-align:center;">
<img src="https://catalog.archives.gov/medialz/stillpix/185-cz/185-cz-23-28-b-04-013c.jpg" 
     alt="Black and white photograph of steel reinforcements (identifier: 202803177)" 
     title="Steel reinforcements"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          Photo of steel reinforcements at some construction project in the Panama Canal. (NAID: 202803177)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 

### Reinforcement Learning

"RLHF was the technique that enabled the massive success of the release of ChatGPT." This banger quote comes from Nathan Lambert's book [Reinforcement Learning from Human Feedback](https://rlhfbook.com/).  The book is free and well done, so let's dive into it. 


### General
Reinforcement learning from human feedback (RLHF) is one part of the post-training cycle for a large language model. The purpose of post-training is to make "language models more useful for downstream tasks."

RLHF helped AI models move beyond academic settings and laboratory benchmarks to achieve widespread public use as a general tool. Unlike instruction fine-tuning, RLHF "tunes completions on the response level," and it provides the model "what a better response looks like, rather than the specific response it should learn." Yet RLHF is much more costly than instruction fine-tuning (usually have to build a separate reward model), and it presents its own challenges such as over-optimization.

Training a language model requires "large technical teams of 10s to 100s of poeple and millions of dollars in data and compute costs."

### Case Study of the Bad Conversationalist
A friend of mine, who we'll call Algernon, is a nice guy and very smart and a bad conversationalist. Good conversation is a tennis match where speakers swap stories, listen to each other concerns, and reinforce friendly bonds. It's a exercise in taking turns of blowing off steam and talking about ourselves. 

Not so for Algernon.

**Neill**: Hey Algernon, how's it going?

**Algernon**: [1,000 word reply]

**Neill**:  oh wow, thanks. I have to go now. 

In the give and take of conversation, ALgernon is all take and no give. He's clueless as to subtle cues.  

My friend Algernon is just like a large language model fresh from training. Neither of them are aware of human preferences for conversation, and both are likely to spew information at you. This is where RLHF comes in. It fixes this problem for LLMs, thus making for a better converational experience. 

"RLHF is what takes [LLM] answers and crafts them into the reliable, warm, and engaging answers we now expect from language models." RHLF is a way of incorporating stylistic preferences and behavior into LLMs.

### RLHF Process

1. **Question-Answering Model**: transition from a base model that completes text to an instruction-following model that can handle Q&A. Train the model on high-quality responses. Claude says that this is done using supervised fine tuning. There isn't actually a separate model. 

2. **Reward Model**: train a reward model that captures human preferences. "This involves fine-tuning a language model ... on a dataset of preference relations between text."

3. **Actual RL Process**: Take a bunch of prompts, generate a bunch of completions, have the reward model rank them, then use RL to figure out how to improve the underlying model. "Shift parameters to make good tokens more likely, and do so iteratively to maintain the general capabilities of the initial model." 

Lambert uses an analogy of Formula 1 racing teams maximizing performance out of a given chassis. So too under the elicitation interpretation of post-training. In AI development, "one can extract a ton of performance out of a static base model." Base models have a lot of intelligence, but they need training to get them to work in a Q&A format. Under the elicitation theory, "base models determine the vast majority of the potential in a final model, and post-training's job is to cultivate all of it."

Lambert disclaims the LIMA paper / Superficial Alignment Hypothesis. He says that it's wrong because it undersells the work of post-training alignment. In any event, he explains that "RL methods are becoming an increasingly large share of the compute needed to train frontier language models." When RLHF came out, there was quite a debate about its value, and companies that adopted it early won out in the end. Reinforcement learning with verifiable rewards (RLVR) is now the cutting edge of post-training research, but Lambert wrote the book on RLHF to capture the stable literature. 

### Parting Thoughts

Okay, those are my notes from the first half of Chapter 1. The book is good, but there's a lot to process. I'll try to get into more chapters as I can.  I need to write up some governance paper on Chinese / EU approaches to apocalyptic AI.  

Before I go, I will link to a paper that I'll look at later: "[The Alignment Problem from a Deep Learning Perspective](https://arxiv.org/abs/2209.00626)," by Ngo, Chan, and Mindermann. This paper is Doomer AI in paper form, but unlike the screeds on Twitter, it is well-organized, detailed, and substantiated.  What caught my eye was the claim that "Although RLHF is the cornerstone for aligning recent state-of-the-art models, we argue that it will encourage the emergence of three problematic properties." It's a paper worth engaging in.  


