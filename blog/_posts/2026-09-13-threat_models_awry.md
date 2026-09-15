---
layout: post
title: Crappy Threat Models
date: 2026-09-13
jumbotron: Crappy Threat Models
regular_date: September 13, 2026
summary:  Doomer AI predictions, aka, threat models, don't stand up to scrutiny because they are not realistic. 
---

<figure style="text-align:center;">
<img src="https://catalog.archives.gov/medialive/64/9490/6949064/content/arcmedia/stillpix/306-ppb/306-ppb-163-2011-001-pr.jpg" 
     alt="Color image of a little kid being threatened by a bayonet with hammer and sickle shadow overhead (identifier: 6949064)" 
     title="The Commies are Coming For Us!"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          This blog post is about threat models, so I searched for "threat" in the National Archives and got a picture of anti-communist media. This image singlehandedly won the Cold War (NAID: 6949064)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 


### Frontier AI is Coming For Us

Jacob Coxon, the erstwhile Anthropic engineer, [appeared on CBS News and warned that frontier AI](https://www.youtube.com/watch?v=CNut8Ub-lvQ) "could be copying itself over to other computers. Like it's not that difficult to find yourself because an AI is just code. It could transfer itself over the internet to a different place and then you unplug it here, but it's actually still over there and maybe it makes 10,000 copies of itself and they're all cooperating."

Dario Amodei, the Anthropic co-founder, [wrote that he worried](https://darioamodei.com/post/we-must-pace-the-frontier) that "the accelerating rate of AI capability development, it’s my worry that in 6–12 months such a swarm could be capable of taking over the entire internet with a persistent botnet (potentially causing hundreds of billions of dollars in damage), and that the scale of damage would continue to increase from there if AI becomes more powerful without the necessary guardrails."


### Threat Modelling

In some sense, what Coxon and Amodei are doing is engaging in threat modelling. [Threat modelling](https://en.wikipedia.org/wiki/Threat_model) is a mental exercise common in the field of cybersecurity. It is a process of identifying potential threats, prioritizing those threats, and matching those threats to appropriate countermeasures.

**Threat Modelling**:
1. What can go wrong?
2. What can we do about it?
3. Did we do enough?

To make this concept accessible to this blog's only reader (Hi, Mom), let's do an abbreviated threat model of someone's home. Ordinarily engineers would threat model a web application or digital infrastructure, but modelling a home makes this relatable.

Okay, so we will now threat model a home.  Let's first ask ourselves what are the threats to a home.  Just enumerate as many as you can without worrying about likelihood.

**Home threats**:
1. Burn down as part of a forest fire
2. Someone steals an Amazon package off the front porch
3. Burglar breaks in and steals things
4. Army of ninja assassins assaults the house

Looking over that list, it's faily apparent that some of the risks are more likely than others. It's also clear that some of those risks are more consequential than others. In cybersecurity, as in life, you can't defend against everything, so you prioritize the most important ones and accept hte risks for the unlikely ones.

Mitigations:

1. **Forest fire**: install smoke alarm, interior sprinkler system, buy fire extinguisher
2. **Steals package**: Ring camera installed on front door or just ship packages to pick up box
3. **Burglar**: locks on doors and windows, fence, guard dog, security system
4. **Ninja Army**: because this risk is so improbable, it's not worth defending against. Accept the risk.

### Evaluating the Coxon and Amodei Threats

So both Coxon and Amodei identified potential threats from AI systems, but how realistic are they?

[On X / Twitter, Daniel Jeffries](https://twitter.com/Dan_Jeffries1/status/2098411466697097235) goes through why Coxon's scenarios is unlikely.  A frontier AI model is very much NOT like a computer virus. A frontier AI model consumes terabytes of memory, requires state of the art computer chips, and devours energy. Unlike a computer virus, it can't just replicate itself to any computer. It's like if someone decided to make a copy of Mount Everest. Something that large is not going to stay hidden very long. People will notice quickly. So too with frontier AI models. The digital infrastructure and power requirements to support such a model are immense and cannot be easily hidden. 

[On LinkedIn, Ciaran Martin](https://www.linkedin.com/pulse/ai-pacing-call-claim-ciaran-martin-wmjfe/) contests Amodei's doomsday scenario.  Amodei's scenario "assumes no monitoring of systems, no anti-virus, no DDoS protection, no network segmentation, no incident management, no nothing of any kind of the cyber security on the global Internet of the type that has developed over the last 30 years. For a claim of this magnitude, there is neither evidence for the contention nor a credible account of a path to this outcome." So Amodei's hypothetical ignores the digital safeguards, procedures and institutions that have developed over the past thirty years. 

So in both cases, the Anthropic folks are engaging in wild conjecture on how AI could wreak havoc. These individuals are likely brilliant AI scientists, but their knowledge of actual cybersecurity threats seems limited. 

In his LinkedIn post, Martin goes on to call attention to the Anthropic report on real-world AI misuse. Those scenarios are not only realistic, they are happening right now, and thus deserve our attention more than hyperbole.

### I Ain't Reading All That

But wait, there's more threats out there. Coxon and Amodei are not the only ones to offer catastrophic AI outcomes. There's a growing body of literature to these. This list is taken from Oliver Habryka: 

AI 2027: http://ai-2027.com 

Paul Christiano's scenario (Former Head of Safety @ AISI, 2019): https://lesswrong.com/posts/HBxe6wdjxK239zajf/what-failure-looks-like

Gwern Branwen's scenario (widely known independent AI researcher, 2022): https://lesswrong.com/posts/a5e9arCnbDac9Doig/it-looks-like-you-re-trying-to-take-over-the-world

Holden Karnofsky's high-level explanation (RSP Lead @ Anthropic, 2022): https://cold-takes.com/ai-could-defeat-all-of-us-combined/

Joshua Clymer's scenario (ex-OpenAI, 2025): https://lesswrong.com/posts/KFJ2LFogYqzfGB3uX/how-ai-takeover-might-happen-in-2-years

I am not going to analyze all this. [Dr. Heidy Khlaaf of the AI Now Institute rebuts](https://twitter.com/HeidyKhlaaf/status/2099481477641601182) this type of fiction by noting that these doomers "cannot have it both way[s]. These claims are unfalsifiable, have no evidence, and they contrive unscientific explanations for not need to provide either."

### Where A.I. Is Not Intelligent

(I might make this a separate blog post)

On Sept 12, 2026, Paul Ford published an essay in the New York Times called, [“A.I. Slopware Is Everywhere Now. Nobody Is Using It.”](https://www.nytimes.com/2026/09/12/opinion/ai-software-coding-apps.html) There he notes that the “number of mobile apps available on Apple’s App Store was up 30 percent last year,” but app downloads are up only 3%. AI, he argues, excels at reproducing what came before, but fails at creating something new. 

The METR team published a paper called ["Measuring AI Ability to Complete Long Software Tasks."](https://arxiv.org/abs/2503.14499) The paper describes their methodology for benchmarking AI models. They create a series of real-world software engineering tasks, they ask human engineers and AI models to complete them, then they compare the results. So far, so good. 

However, the paper mistakenly assumes that large software applications are inherently economically valuable. A software engineer’s job is not writing code; it’s generating value for customers. Typing out code is the easy part of the job. The number of lines of code does not determine economic value; an application's value is determined by how much people use it. 

METR's decision to use software tasks to measure AI performance gives a fall sense of AI capabilities. The software tasks are something that can be quantified easily but are not probative as to the ultimate question of capabilities. 

A better, more accurate assessment of AI capabilities would be tasking the agents to build a mobile application that achieves 1 million downloads in three months. A better benchmark would be to task AI to create a feature length film that generates $100 million in ticket sales and earns a spot on several year-end top ten lists.
 
There is a great deal of interest in predicting future capabilities of AI models based on current trends, but AI researchers and policymakers need to broaden their definition of intelligence.  

### Links
* [David Bellamy explains why the idea](https://twitter.com/DavidRBellamy/status/2099187370407112758) of AI creating world-destroying viruses is nonsense. 


