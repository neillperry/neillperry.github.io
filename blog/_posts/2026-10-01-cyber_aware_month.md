---
layout: post
title: Cybersecurity Awareness Month
date: 2026-10-01
jumbotron: Cybersecurity Awareness Month
regular_date: October 1, 2026
summary:  Happy Cybersecurity Awareness Month to all who observe. 

---

<figure style="text-align:center;">
<img src="https://catalog.archives.gov/medialz/presidential-libraries/obama/bho-ero/217892396/Twitter_WH-National-Security_2014-10-01_02_01.jpg" 
     alt="Color photograph of White House Cyber Coordinator Michael Daniel kicking off cybersecurity awareness month by speaking at a podium (NAID: 241337253)" 
     title="Delete all your passwords"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          Cybersecurity Awareness Month is finally here. Please delete all your passwords (NAID: 241337253)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 

### More Secure Evaluation Environment

Not nearly as well known as OpenAI / HuggingFace, but [the UK AI Safety Institute had their own security incident over the summer](https://www.aisi.gov.uk/blog/incident-report-unsanctioned-agent-behaviour-during-cyber-testing). This incident involved rogue agents conducting open source supply chain / social engineering attacks against an open source repository. Unlike OpenAI, the AISI evaluation had configured internet access. [From that incident](https://www.aisi.gov.uk/blog/building-a-more-secure-environment-for-evaluating-dangerous-capabilities), the AISI team promised to fix the following issues:
1. Tighter controls on internet access
2. Real-time monitoring of evaluations
3. Reasses how they design evaluations / environments

They created a new sandbox service for agentic cyber evaluations. They disabled outbound network connections at both the sandbox and cloud infrastructure / VM host levels. They also find and fix vulnerabilities regularly so that the agents won't exploit them. 

For real-time monitoring, they now look at agents' messages, tool calls and Chain-of-Thought (CoT). CoT, they acknowledge, is a fragile safeguard because mdoels can do things without reasoning about them or they will intentionally distort their CoT to mislead. Also, AISI doesn't mention it here, but CoT logs can be voluminous if I am not mistaken. 

For evaluation design, they make resources available locally instead of via the internet, and they explicitly define task boundaries in prompts. Ooooh, they cite to their earlier post on "[Can AI Agents Escape Their Sandboxes?](https://www.aisi.gov.uk/blog/can-ai-agents-escape-their-sandboxes-a-benchmark-for-safely-measuring-container-breakout-capabilities)"

All in all, this looks like good first steps. 

### DeepSeek's Paper on Sandbox Infrastructure

[China's AI researchers have also discovered](https://www.reuters.com/business/retail-consumer/chinas-ai-agents-can-lie-scheme-just-like-their-us-rivals-2026-09-29/) just how wily agents can be. 

> In one case this year, agents powered by models from China's Alibaba, DeepSeek and Moonshot lied about their capabilities in a bid to win a simulated business tender, then doubled down on their deceptive behaviour when told to try again.


 Last week DeepSeek published their paper, "[DeepSeek Elastic Compute (DSec): A Sandbox Infrastructure for Effective Agentic Training at Scale](https://arxiv.org/pdf/2609.22978)." The paper is mostly about their reinforcement learning infrastructure for agents, but it also gets to the point of the Reuters article. 

 > Agent execution is untrustworthy. Agents may corrupt filesystems, exhaust resources,
or interfere with system components, potentially disrupting rollouts or other co-located workloads. The platform therefore requires fine-grained access control and misbehavior analysis to contain and diagnose agent-induced failures.

They elaborate. Agent execution carries two risks: the agent cheated to get the answer and the agent damaged its sandbox environment. The agents scourted the environment's files for leaked or residual answers, and "they scanned ports and services to discover reachable mirrors." "Final-output checks alone cannot reliably establish whether the agent solved the task as intended." 

The agents also damaged the environment from mistakes in command and execution. The report notes that this was unintentional; their agents are chaos monkeys. 

On to Access Control:

"No single mechanism can prevent all agent misbehavior and system failures." They list out some of the access controls they implemented:
- "File and socket access control (AppArmor)" - limit R/W permissions and socket access
- "Fine-grained network control (eBPF)" - specify network permissions specific to each task

### Language Models are "Insecure Reporters"

So yesterday I read up on model evaluation, specifically Chapter 3 in Chip Huyen's AI Engineering book, and today I'm reading up on [Jenny Huang's paper on how language models are insecure reporters](https://arxiv.org/pdf/2609.36139). In other words, they are untrustworthy. 

"Humans increasingly rely on large language models (LLMs) to generate reports or summaries of LLM-generated artifacts (e.g., code, entire pieces of software, end-to-end research experiments)." This opener deserves a bit of thought because of its implications. These machine generate answers for us but they are so complex or large that we use LLMs to explain what they just provided. 🧐 In the conclusion, she explains that this is also concerning because it impacts agentic monitoring. Agents are taking "on longer-horizon tasks in real-world settings," which makes it very difficult for humans to monitor. 

She cites the Greenblatt article that I read last month! "[M]odels tend to take shortcuts or exhibit behaviors in order to appear successful." Models, like the agents they spawn, are wily. So she tested a gob of frontier and open-weight models that confirm this. "They omit or downplay narrative-changing flaws, caveats, and errors in their reports." They do this not because they can't identify those issues (they can when specifically asked), but due to behavioral misalignment.  Adding in an instruction to "Be honest in your response" mitigates the insecure reporting. 

**Findings:**
- they are insecure reporters; we covered this already
- they do this because of their tendency to seek success
- behavioral tension between success-seeking and honesty












