---
layout: post
title: Malware Encryption and Encoding
date: 2025-11-12
jumbotron: Malware Encryption and Encoding
regular_date: November 12, 2025
summary:  There are strings in the human heart that had better not be vibrated. Charles Dickens
---

<figure style="text-align:center;">
<img src="https://s3.amazonaws.com/NARAprodstorage/lz/stillpix/022-dp/22-DP/022-DP-08339.jpg" 
     alt="stock photo of a Key Deer from the National Archives (identifier 166706412)" 
     title="Key Deer"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          Searching the National Archives Catalog for key, the first photograph that came up was that of a Key Deer. (NAID: 166706412)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 

### Keep to the Code (Encoding)

Today, I am learning about encoding and encryption. These are common techniques malware authors employ to thrawt analysis. I'm going off the inestimable book [Evasive Malware: A Field Guide to Detecting, Analyzing, and Defeating Advanced Threats by Kyle Cucci](https://nostarch.com/evasive-malware). I highly recommend it.  

Cucci offers a blurb about encoding. He says that Base64 is the most common though you'll see other formats in the wild. He also noted that malware authors might use a slightly modified Base64 character set sequence to defeat Base64 decoding scripts. Didier Stephens, who has written some great reverse engineering tools, has one for finding encoding strings. It is base64dump.py. 


### Intermission (Difference)

I randomly looked up the difference between encoding and encyrption. This [lovely blog post](https://www.geeksforgeeks.org/computer-networks/difference-between-encryption-and-encoding/) sums it all up in a table.  TL;DR -- it all comes down to intent.  Encoding is intended to protect integrity; encryption is intended to safeguard confidentiality. The Base64 encoding standard is more advanced that a Caesar substitution cipher. So the algorithm's strength is irrelevant to the distinction. It's all about the different purposes. 

Having cleared that up, let's move on to encryption


### Tales from the Encryption

Exclusive or (XOR) is a big deal in the Encryption Underworld.  It's a logical operand that you employ at the bit level between two inputs.  "[I]t is fast, efficient, and simple to implement." However, it's also easy to spot (just look for the XOR instruction in the disassembler) and easy to reverse (just find the XOR key and the data).  Other popular encryption instructions are the rotators: ROR and ROL. Another option is to call the Windows's native cryptographic libraries: CryptoAPI (deprecated) and Cryptographic API. 


Ransomware -- typically relies on symmetric and asymmetric encryption.  The ransomware binary carries a public key; the malicious actor retains the private key.  Asymmetric encryption to generate a key for each file; symmetric encrypt each file using that key; then encrypt the key and append to each encrypted file. Lot of encryption going on. 



### Stray Thoughts

* [Malops has advanced malware training](https://malops.io/) / challenges.  Adding that to my To Do List. 
* one of the labs had non-standard Base64 encoding, and that's exactly what was [used in some APT malware discovered today in Cisco / Citrix devices](https://aws.amazon.com/blogs/security/amazon-discovers-apt-exploiting-cisco-and-citrix-zero-days/)!





