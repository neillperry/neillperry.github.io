---
layout: post
title: More Malware Encryption
date: 2025-11-21
jumbotron: More Malware Encryption
regular_date: November 21, 2025
summary:  Diving into more about malware encryption, including how to recognize which algorithm is used.
---

<figure style="text-align:center;">
<img src="https://s3.amazonaws.com/NARAprodstorage/opastorage/live/85/5147/514785/content/arcmedia/media/images/18/2/18-0147a.gif" 
     alt="World War II-era public service announcment about the importance of OPSEC from the National Archives (identifier 514785)" 
     title="World War II Poster on Keeping Secrets"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          Searching the National Archives Catalog for secrets, one of the images that came up was that of a World War II era cartoon admonishing service members to not share secrets with vivacious women. (NAID: 514785)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 

Welcome everyone to a human-written blog on cybersecurity. I am posting this a day later than expected because I refuse to sacrifice quality to satisfy my editor's arbitrary deadlines.  

### How to Find Encyrption in Malware

Anuj Soni explains [his techniques for finding encryption in malware](https://www.youtube.com/watch?v=rZ6hJcJUN88).  This is the second video of his that I've watched, and I've been impressed so far.  He explains that all his video focus on the same malware sample (WannaCry); diving into one sample illustrates just how complex analysis can be.  

1. **Look at strings and APIs** -- in Ghidra, go to Defined Strings view to see strings. These may reveal any calls to WinAPI APIs that deal with encryption.  You can also look for imports by going to the Symbol References view.  

2. **Plugins and Scripts** -- there's a Find Crypt plugin available for both Ghidra and IdaPro. You can configure Ghidra's Analysis settings to include Find Crypt in its Auto Analyze process. Check the Symbol Tree under C for CRYPT to find the results.

3. **capa** -- tool to find interesting behavior in malware.  Download the capa scripts from GitHub.  Anju prefers using the capa_ghidra.py script.  

4. **Yara** -- rule-based tool for identifying and classifying malware. Create your own Yara rules or use pre-existing rules to find encryption. 

5. **Manual Searches** -- not as glamorous as the other four options.  Search manually for mathematical functions, such as shift left or rotate left.  The other mathematical functions are too common in the program to be useful. 

### Identifying Encryption Types

Exploring more the analysis of encryption APIs.  WinAPI encryption APIs can either generate a key or import a key. in both cases, it will refer to an key Id. Go find that.  

The [CryptGenKey API](https://learn.microsoft.com/en-us/windows/win32/api/wincrypt/nf-wincrypt-cryptgenkey) -- has a ALG_ID parameter -- specifies the algorithm that will generate the key; it accepts a wide variety of hashing and encrypting algorithms. Note the API is deprecated. 

The [CryptImportKey API](https://learn.microsoft.com/en-us/windows/win32/api/wincrypt/nf-wincrypt-cryptimportkey), which is also deprecated, takes a BYTE array.  

Now that you found encyrption code, how do you determine which type of encyrption it is implementing (sym vs asym) and the algorithm? 

The RC4 algorithm is identified via two for loops that go up to 255, i.e., "for i from 0 to 255."  The first loop initializes the sbox values; the second for loop scrambles the values. 

The AESENC instruction -- used in statically linked libraries -- signals likely use of the AES algorithm. Also, AES uses s-boxes or t-boxes; identify AES by initialization values for these boxes.  Automatic tools have to do this.  S-box may be created via algorithm, i.e.,  [the rotate left](https://learn.microsoft.com/en-us/cpp/intrinsics/rotl8-rotl16?view=msvc-170) (ROTL8) done 4 times. 

You can also recognize these other algorithms:

RSA - bi_permanent constant

Salsa20 - the string "expand 32-byte k"

CRC32 - 0xedb88320 used with XOR operand in a loop

BCRYPT - "OrpheanBeholder"


I haven't finished my study of encryption methods, but this blog post is already a day late, so I have to publish.  I would like to go over this paper, "[A Taxonomy of Encryption and Encoding Algorithms Used by Advanced Persistent Threats with Emphasis on Bespoke Encryption Algorithms](https://eprints.glos.ac.uk/12874/3/12874%20BENTLEY%20Peter%20%282023%29%20A%20taxonomy%20of%20encryption%20technical%20report.pdf)."




### Fellowship Opportunities
The AI boom has spawned a flurry of fellowship opportunities in the AI policy space.  Here are some organizations to watch if you're interested in that field:

* [Institute for AI Policy and Strategy](https://www.iaps.ai/fellowship)
* [GovAI](https://www.governance.ai/post/winter-fellowship-2026)
* [Pivotal Research](https://www.pivotal-research.org/fellowship)
* [Tech Congress](https://techcongress.io/)


[Responsible Tech and AI Job Board](https://alltechishuman.org/responsible-tech-job-board) lists other opportunities.  


This is career field worth watching given the explosion of AI applications.

Here [is a promising blog post about NPM malware](https://www.aikido.dev/blog/the-malware-dating-guide-understanding-the-types-of-malware-on-npm).  I am tossing it here as a reminder to myself to read and blog on it later. 







