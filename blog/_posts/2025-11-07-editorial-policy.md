---
layout: post
title: Behind the Scenes
date: 2025-11-07
jumbotron: Behind the Scenes
regular_date: November 7, 2025
summary:  You gotta crawl before you can walk. You gotta learn to wax on, wax off before you can win the Tri-Valley Tournament. This post discusses the importance of fundamentals and contains notes on calling conventions. 
---

<figure style="text-align:center;">
<img src="https://s3.amazonaws.com/NARAprodstorage/opastorage/live/71/2071/32207171/content/kansas-city/rg-075/285796/75-SR-6463_001.jpg" 
     alt="stock photo of books from the National Archives (identifier 146150242)" 
     title="Air Compressor Hammer Breaking Rock Ledge" 
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          This blog posts discusses API Hammering, so this post has a picture of an air compressor hammer (NAID 32207171)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 


### Editorial Policy

I don't use AI to write this blog. It's 100% Neill-generated. I take notes while watching the YouTube tutorials or reading the No Starch Press books. Those notes are quotes and snippets that I find interesting or illuminating.  I organize what I have into a coherent narrative, then push to my blog. I'll go back several times over a post to make edits and correct typos. There's a publish, then polish rule for this blog. 

Actually, there is a dash of AI.  I sometimes converse with ChatGPT about what I'm learning. I think there's a 2-line quote from an ChatGPT conversation in an earlier post. Going forward, I'll try to better attribute AI. 

Speaking of which, I chatted with AI today about why the entry point is different than `main()` in a C/C++ program.  Per the AI, the OS will first load the executable.  Then, there's a "`_start` or another startup routine" that will prepares the environment, such as setting the stack, initialize variables, set up the runtime library. The entry point will then call `main()`, which returns a value. 


### Blogging - Learn and Advertise

As stated moments ago and in earlier posts, writing up these notes reinforces what I learn. There's also the branding value. Potential employers and corporate recruiters might stumble upon these blogs and decide that I'm someone worth interviewing.  Yet given the brutal nature of the tech job market, and the general difficulty of breaking into a new cybersecurity discipline, that prospect is limited.  For now, malware analysis will remain a passion project. I'll finish my course by mid-December, and I'll try to analyze in-the-wild malware samples and write it up when I get the chance.  


### Reading List

There's tons of great resources on learning about Assembly. 
* [x86 Assembly Guide](https://www.cs.virginia.edu/~evans/cs216/guides/x86.html) - succinct guide produced by the Computer Science Department of the University of Virginia 20 years ago.  Still holds up.
* [The Intel Software Developer's Manuals](https://www.intel.com/content/www/us/en/developer/articles/technical/intel-sdm.html) -- over 5,000 pages of documentation. It's a lot, but is helpful to peruse, especially to look up Assembly instructions.  You'll stumble on things you didn't know existed. The font they use in that book for code is terrible though.

### API Hammering

I was reading [this Huntress write-up on Gootloader](https://www.huntress.com/blog/gootloader-threat-detection-woff2-obfuscation) where I came across the concept of API Hammering.  I had never heard of that before.  [Unit 42 did a great post](https://unit42.paloaltonetworks.com/api-hammering-malware-families/) on what exactly that entails.  

> API Hammering consists of a large number of garbage Windows API function calls. The execution time of these calls delays the execution of the real malicious routines of the malware. This allows the malware to indirectly sleep during the sandbox analysis process.

The Huntress analyst attributed API Hammering as an evasion technique to frustrate analysis and mask the malware control flow.  









