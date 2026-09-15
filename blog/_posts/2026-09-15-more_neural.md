---
layout: post
title: We Must Go Deeper
date: 2026-09-15
jumbotron: We Must Go Deeper
regular_date: September 15, 2026
summary:  Second part in a series of self-study on deep learning and neural networks. I found a textbook I like, so let's check it out. 

---

<figure style="text-align:center;">
<img src="https://catalog.archives.gov/medialive/11/1493/39149311/content/stillpix/434-lb/Installment_8/434-LB-8-XBD201410-00503.jpg" 
     alt="Undated black and white photograph of irradiated brain sections (identifier: 39149311)" 
     title="Irradiated brain sections from a government research project"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          Photo of irradiated brain sections. Maybe this ties into what the government was doing in Project X (NAID: 39149311)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 

### Back to Learning About Deep Neural Networks

This is a continuation of an earlier post in which I jot down notes while reading about deep neural networks.  For this post, I am going off the book [Deep Learning by Ian Goodfellow, Yoshua Bengio and Aaron Courville](https://www.deeplearningbook.org/). It's an MIT Press book that is available for free online or for $60 from Amazon. On the book website, you can view but not download the book. 

*However, when you view a chapter in your browser, you can right click, select Print, then print as a PDF to your computer, which is the same as downloading. So that's your workaround to a free book.*  

So far it's been really good. It's designed for university students and software engineers. I skip over the formulas. With that introduction, on to my notes.  Text in quotation marks are direct quotes from the book. 

### Introduction

AI's challenge is solving problems that humans struggle to articulate formally but can solve intuitively.  It's not feasible or possible for humans to hard-code into a computer all the information about the world, so need to create a way for computers to learn that data themselves. AI achieves this by finding patterns from raw data (machine learning). Computers use representation learning to discover the underlying data relationships themselves. 

"A major source of difficulty in many real-world artificial intelligence applications is that many of the factors of variation influence every single piece of data we are able to observe." This is where deep learning comes in because it allows the Clanka "to build the complex concepts out of simpler concepts."

The book has a Venn diagram explaining the hierarchy of terms.
1. Machine learning is a subset of artificial intelligence, and it includes logistic regression
2. Representation learning is a subset of machine learning, and it includes shallow autoencoders
3. Deep learning is a subset of representation learning, and it includes multilayer perceptrons

The chapter then goes into the history of deep learning, previously called cybernetics and connectionism. Neuroscience is an inspiration for deep learning but not a guide because we just don't know enough about the brain to accurately reproduce it digitally. One of the neuroscience inspirations is that "many computational units ... become intelligent only via their interactions with each other."

One of the primary reasons for the recent explosion in deep learning capabilities is the explosion of available data. The internet made lots of data available digitally, and all that can be fed to learning algorithms. The authors note that today's learning algorithms are nearly identical to what the field had forty years ago, but the difference in performance is attributable to more training data. 

"As of 2016, a rough rule of thumb is that a supervised deep learning algorithm will generally achieve acceptable performance with around 5,000 labeled examples per category and will match or exceed human performance when trained with a dataset containing at least 10 million labeled examples."

Also, better models helps improve performance. "Unless new technologies enable faster scaling, artificial neural networks will not have the same number of neurons as the human brain until at least the 2050s."

### Machine Learning

Deep learning is a subset of machine learning, so an understanding of the latter is needed to understand the former. "Machine learning enables us to tackle tasks that are too difficult to solve with fixed programs written and designed by human beings."

Common machine learning tasks:

1. **Classification**: given an input, specify which of given categories it belongs to.
2. **Classification with missing input**: same as above, except that some measurements are missing. This often arises in the domain of medical diagnosis. 
3. **Regression**: given an input, make a prediction in numerical value. Maybe to determine the value of a home in a neighborhood. Also used for algorithmic trading.
4. **Transcription**: "observe a relatively unstructured representation of some kind of data," then convert that into text.
5. **Machine Translation**: translate from one language into another, often for natural languages.
6. **Anomaly Detection**: given lots of data points, find ones that seem out of place.  Used for credit card monitoring.

Experience -- is a component of ML. Learning algorithms "experience an entire dataset." Learning algorithms can be supervised (labeled data) or unsupervised. There are no formal definitions for those terms, but they are useful to understand how we use these algorithms. Reinforcement learning algorithms do more than experience a data set; they also interact with an environment and learn from those interactions. They don't talk about that in this book. 

**Example**: the textbook offers up linear regression as a simple machine learning algorithm. It takes input and produces a linaer function that allows the prediction of other values of y given x. To measure the performance of the regression, we compute the mean squared error. To convert this all into a machine learning algorithm, we design an algorithm that improves the weights (parameters of the linear function) while maximizing its performance (reducing mean squared error).

"The central challenge in machine learning is that our algorithm must perform well on new, previously unseen inputs -- not just those on which our model was trained. The ability to perform well on previously unobserved inputs is called generalization."

Tying in to a quote by Jakub Pachocki, Chief Scientist at OpenAI.  [In his blog post An Alien Mind](https://openai.com/index/an-alien-mind/), he wrote, "We do not have a satisfactory theory of generalization, and it seems unlikely that we can develop one soon, at least without the help of more powerful AI. Therefore, at present, our ability to empirically validate our alignment techniques is in practice arguably even more important than the alignment techniques themselves."

There are more chapters to come in a future post. 
