---
layout: post
title: Encrypt Until The Bleeding Stops
date: 2025-12-01
jumbotron: Encrypt Until The Bleeding Stops
regular_date: December 1, 2025
summary:  Diving into more about malware encryption, including how to recognize which algorithm is used.
---

<figure style="text-align:center;">
<img src="https://s3.amazonaws.com/NARAprodstorage/opastorage/live/85/5147/514785/content/arcmedia/media/images/18/2/18-0147a.gif" 
     alt="black and white photograph of U.S. Marine Corps code-talker recruits being sworn in from the National Archives (identifier 295175)" 
     title="World War II Navajo Code Talkers"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          First 29 Navajo U.S. Marine Corps Code-Talker Recruits being Sworn in at Fort Wingate, NM (NAID: 295175)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 


### Class Notes
Hmmmm....., two for loops that go up until 0x100 (256)? that doesn't seem suspicious at all. That's [RC4's music!!](https://en.wikipedia.org/wiki/RC4) Key-scheduling algorithm consists of two for loops that go up to 256. They key is in the second for loop.  The key is used to create an s-box array (S[i]).  

Next is the psuedo-random generation algorithm (sometimes the third for-loop). The s-box array is used to generate a constant key stream K.  This is stream is XOR'd with the plaintext to obtain the ciphertext.     

The take away from this section is that identifying encryption algorithms in malware requires understanding how encryption algorithms work. The lecture cites RC4 as an example.  Comparing the algorithm definition with the decompiled code, it becomes clear that RC4 is exactly what is going on there.  

Once an analyst identifies the algorithm, the next section is to decrypt it using Python or binary refinery. It's not too hard; the lecture explained pretty well how to do it. 

### My Turn at Breaking the Code

I successfully completed half the decoding exercise.  After the lecture, there's an exercise.  I got the first half done using Cyber Chef and Python. For the second half of the exercise, I'll need to dive into the custom base_address function.  It doesn't look hard, but I don't have time this afternoon.  I'll finish up tomorrow night. 

### Saved Rounds

My malware studies focus entirely on Windows samples, but I did catch this analysis from [Cyfirma on ELF (Linux) malware from APT36](https://www.cyfirma.com/research/apt36-python-based-elf-malware-targeting-indian-government-entities/). The use of a desktop icon was particularly clever.

> Threat actors often use .desktop shortcut files as an intermediary delivery mechanism to conceal malicious intent and meet the prerequisites required for downloading and executing ELF malware from specific locations with appropriate privileges. Unlike directly sending an ELF binary which is more easily detected, the shortcut appears legitimate to Linux users while silently running embedded commands. This method enables dynamic retrieval of the latest payload, reduces reliance on static signatures, and limits forensic traces. Overall, using a .desktop file increases stealth, execution success, and operational flexibility for the attacker. 



