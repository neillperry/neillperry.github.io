---
layout: post
title: Encrypt Until The Bleeding Stops
date: 2025-12-01
jumbotron: Encrypt Until The Bleeding Stops
regular_date: December 1, 2025
summary:  Diving into more about malware encryption, including how to recognize which algorithm is used.
---

<figure style="text-align:center;">
<img src="https://s3.amazonaws.com/NARAprodstorage/opastorage/live/15/5934/593415/content/harvest/593415-07428/07428_2003_001_AC.jpg" 
     alt="black and white photograph of Corporal Henry Bake [Bahe], Jr., (left) and Private First Class George H. Kirk, Navajo Indians serving with a Marine Signal Unit, operate a portable radio set in a clearing they've hacked in the dense jungle close behind the front lines.(identifier NAID: 532396)" 
     title="World War II Navajo Code Talkers"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          Corporal Henry Bake [Bahe], Jr., (left) and Private First Class George H. Kirk, Navajo Indians serving with a Marine Signal Unit, operate a portable radio set in a clearing they've hacked in the dense jungle close behind the front lines. (NAID: 532396)
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

Update: still stuck on decrypting the second layer of the malware sample.  AI has been helpful understanding the code. 

```
psVar1 = (short * )( * local_18)(0, local_c, 0x1000, 0x40);
```

I pasted that into AI, and it suggested tha tit is a call to [VirtualAlloc](https://learn.microsoft.com/en-us/windows/win32/api/memoryapi/nf-memoryapi-virtualalloc).


```
LPVOID VirtualAlloc(
  [in, optional] LPVOID lpAddress,
  [in]           SIZE_T dwSize,
  [in]           DWORD  flAllocationType,
  [in]           DWORD  flProtect
);
```

1. 0 - NULL, let the system choose the address
2. local_c, the size of the memory to allocate
3. 0x1000, the MEM_COMMIT flag
4. 0x40, the PAGE_EXECUTE_READWRITE protection

The MEM_COMMIT flag "[a]llocates memory charges (from the overall size of memory and the paging files on disk) for the specified reserved memory pages. The function also guarantees that when the caller later initially accesses the memory, the contents will be zero."

[PAGE_EXECUTE_READWRITE](https://learn.microsoft.com/en-us/windows/win32/Memory/memory-protection-constants) "[e]nables execute, read-only, or read/write access to the committed region of pages."

The next function that I came across is a memory copy operation:

```
  for (i=0; i < local_c; i = i +1) {
     * (undefined *)((int)psVar1 + i) = * (undefined *)(local_8 + i);
  }
```

in the above, local_8 is the source address, and local_c is the length to copy. 

in any event, I have more work to do.  I'll go back and re-watch the videos from earlier.  



### Saved Rounds

My malware studies focus entirely on Windows samples, but I did catch this analysis from [Cyfirma on ELF (Linux) malware from APT36](https://www.cyfirma.com/research/apt36-python-based-elf-malware-targeting-indian-government-entities/). The use of a desktop icon was particularly clever.

> Threat actors often use .desktop shortcut files as an intermediary delivery mechanism to conceal malicious intent and meet the prerequisites required for downloading and executing ELF malware from specific locations with appropriate privileges. Unlike directly sending an ELF binary which is more easily detected, the shortcut appears legitimate to Linux users while silently running embedded commands. This method enables dynamic retrieval of the latest payload, reduces reliance on static signatures, and limits forensic traces. Overall, using a .desktop file increases stealth, execution success, and operational flexibility for the attacker. 



