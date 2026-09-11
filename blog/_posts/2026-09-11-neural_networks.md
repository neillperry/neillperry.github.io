---
layout: post
title: Learn, Deeply
date: 2026-09-11
jumbotron: Learn, Deeply
regular_date: September 11, 2026
summary:  What are deep neural networks? Why should you care? Who invented them? All this and more. 
---

<figure style="text-align:center;">
<img src="https://catalog.archives.gov/medialive/69/1392/23139269/content/stillpix/255-sts/STS090/STS090_ESC_JPGS/255-STS-S90E5075.jpg" 
     alt="Color photograph of stuffed animals Pinky and the Brain (identifier 23139269)" 
     title="Who is the Master? and Who is the Apprentice"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          This blog post is about neural networks, so I searched for "brain" in the Natinoal Archives and got a picture of Pinky and the Brain. Who is the Master and who is the Apprentice? (NAID: 23139269)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 

### I Write, No AI Write

[Robin Moffatt catalogs the indicia of AI-generated Medium posts](https://rmoff.net/2025/11/25/ai-smells-on-medium/), and they all looked fishily like my blog entries. My content is real human writing, I swear. The Moffatt post is a bit dated because now we can just use Pangram.  


### Interview Question

I replay job interviews in my head. What could I have said better? What was the interviewer looking for? I mentally script out a better answer than the one I gave. Not as an exercise in self-punishment, but as a way of learning and improving so that I am better prepared for the next interview.

### What are Deep Neural Networks?

The actual interview question was to explain a technical topic to a non-technical audience, and I was offered the choice of one of four concepts. I selected distributed denial of service, but deep neural networks was one of the other choices, and I realized that I couldn't quite explain that concept. So this blog post is an effort to rectify that. 

In 1943, McCulloch and Pitts publish a paper on how biological neurons could "perform complex computations using propositional logic." Their suggestion was to create artificial neurons that mimicked the biological neuron. Except this time it accepts one or more binary inputs (ON or OFF) and emits a binary output. Using this building block, they argue that one could construct a network of neruons to "compute any logical proposition you want."

(I am pulling this from Neural Networks and Deep Learning, by Aurélien Géron.)

Aside: according to Wikipedia, propositional logic "deals with propositions (whcih can be true or false) and relations between propositions." Basically what McCulloch and Pitts said was, this time from Claude AI, "brain-like networks of simple on/off units could in theory, do the same kind of reasoning that formal logic does." Let's continue reading to see if anyone does anything with this idea. 

In 1957, Rosenblatt invents the perceptron. This will come into play later when we talk about the multi-layer perceptron in the transformer model. The perceptron, in turn, contains a single layer of linear threshold units (LTU). The perceptron deals with numbers instead of boolean values (on / off).  Wikipedia calls it "an algorithm for supervised learning of binary classifiers." It also notes that the perceptron was supposed to "be a machine, rather than a program," which makes sense because this all kind of reminds me of semiconductor. Claude tells me that the analogy is apt on some levels. 

Aside 2: I am at the point where each new concept I learn leads to five more new concepts. Such as, a neural network is a collection of Mfuzgpeets. Each Mfuzgpeet consists of seven Jkixnxes and three Qkournams. Each Jkixnxes has either 42.97 or 8 billion Lsyerchos.....

The big innovation of the perceptron was that it could be trained. "In the modern sense, the perceptron is an algorithm for learning a binary classifier called a threshold function" (Wikipedia). 

"You may have recognized that the Perceptron learning algorithm strongly resembles Stochastic Gradient Descent" (Geron). Yes, I definitely noticed that.  

In 1969, Minsky and Papert rain on the perceptron parade by saying that there's a lot of things they can't learn. EXCEPT that perceptrons can learn things if you stack a bunch of them together into a multi-layer perceptron (MLP)!!  In this way, the perceptrons, now called a MLP, can solve XOR problems. "An MLP is often used for classification, with eath output corresponding to a different binary class."

An MLP has one input layer, one or more layers of LTUS, and a final layer of LTUs called the output layer.  The middle layers of LTUs are called hidden layers. Recall that a perceptron consists of an LTU. When an artificial neural network has two or more hidden layers, IT IS CALLED A DEEP NEURAL NETWORK!!! We made it.   

Let's kick it back to Claude AI for a wrap up: 

"In a deep neural network, the learning represents the iterative adjustment of connection weights (and biases) so that the network's output, computed by propagating input data forward through successive layers, comes to closely approximate the true underlying relationship between inputs and outputs in the training data."

Upon further prompting, Claude said that neural networks are functionally akin to linear regression in statistics except the "network automatically discovers nonlinear transformations of the input (via hidden layers) rather than requiring a person to specify the functional form ahead of time."

The analogy to statistical regression helps because I do remember that from Statistics. 

 

