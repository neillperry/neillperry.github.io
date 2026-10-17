---
layout: post
title: Back Propagation's Back!
date: 2026-10-13
jumbotron: Back Propagation's Back!
regular_date: October 13, 2026
summary: Everbody, yeah. Rocky your body right. Back propagation's back, alright! 

---

<figure style="text-align:center;">
<img src="https://catalog.archives.gov/medialz/kansas-city/rg-075/285796/75-SR-6002_001.jpg" 
     alt="Black and white photograph of a driving a car in reverse (NAID: 57275282)" 
     title="Letting the folks in the back know about their contribution to cost"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          Since this post learns about back propagation, here is a photograph of a Driving Backwards Test (NAID: 57275282)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 

### Reading

I went on vacation last week to forested, mountained places to consider the ripples and dents in the earth. Grass was touched, trees were embraced. Back from the break. 

### METR Paper on AI Productivity

[Sean Goedecke has a blog post](https://www.seangoedecke.com/impact-of-ai-study/) about a [METR report on AI's impact to software productivity](https://arxiv.org/pdf/2507.09089). The article and post are over a year old, so maybe the findings are out of date. 


### This is a Nathan Lambert Stan Account

You should read Nathan Lambert. He runs a [Substack newsletter called Interconnects](https://www.interconnects.ai/) that is worth twice its subscription fee. There are hordes of commenters and opinion makers on AI, but Lambert is among the few with with deep technical expertise. 

The RSI "view dramatically undersells human bottlenecks in building models and allocating resources at organizations, and draws conclusions on future AI capabilities more broadly."

He says that many AI researchers have been extraordinarily preescient on predicting AI development, but that does not mean their current forecasts are accurate. 

"The biggest short-term risk could be from the AI labs not taking safety seriously enough – they haven’t hardened their own infrastructure, enabling AI misuse to proliferate"

### Back-Propagation

Whenever I miss or fail an interview question, I like to go back and study up on it. This time the question was, "What is back propagation?" I knew it was a term from neural networks, specifically how the model approximates relationships, but I couldn't explain it. So I am writing a blog post about it. 

Let's start with Chapter 6 Deep Feedforward Networks from [the open source Deep Learning book](https://www.deeplearningbook.org/), which I highly recommend. Even if you don't understand all the technical stuff, which I definitely do not, you can glean a lot of useful knowledge about how networks are created and function.

A feedforward neural network is one that accepts an input (x), then runs that through all the hidden layers until finally producing an output (ŷ). A back-propagation algorithm "allows the information from the cost to then flow backward through the network in order to compute the gradient." Backprop is not the entire learning process; it's just "method for computing the gradient." Back propagation algorithms can be used in contexts outside of multi-layer neural networks to "compute derivatives of any function." "Back-propagation is an algorithm that computes the chain rule [of calculus]." The chain rule computes "the derivatives of functions formed by composing other functions whose derivatives are known."

I got a bit loss there. "The back-propagation algorithm is very simple." 🫣 I'm sure this is one of those things that once studied is very intuitive, but on the other side of the curve, it doesn't seem that way. [Edit: after reading through the other books mentioned in this post, the paragraph above made more sense.]

The Deep Learning book was meh. Let's see what Chip Huyen has to say on this. Chapter 7 of AI Engineering.  

She describes it as "how a model’s parameters are updated during training based on the error." During the interview, after I fumbled my answer, this is essentially how the interviewer explained the concept to me (but he also went on to offer more information). Chip doesn't offer much beyond that, so on to another book.

**Deep Learning Illustrated: A Visual, Interactive Guide to Artificial Intelligence by Jon Krohn, Grant Beyleveld, Aglaé Bassens**: this is a little more beginner friendly than the Deep Learning book. According to them, backpropagation pairs with gradient descent for a neural network to approximate the desired output by tunning the underlying parameters (weights and biases).

Neural networks use loss functions (also called cost functions) to measure how wrong its estimate was. "[T]he primary approach for minimizing cost in deep learning paradigms is to pair an approach called gradient descent with another one called backpropagation." These two enable learning. The network learns by tweaking the model's parameters so that the estimated value (ŷ) gets as close as possible to whatever it's trying to model (y).

"Gradient descent is a handy, efficient tool for adjusting a model's parameters with the aim of minimizing cost...." The book has a fun illustration of a blind trilobite standing on a curvy line on a line graph. So the network wants to descend the gradient on this curve to find the lowest cost. Lower cost, more accurate representation. Okay, so this is where finding the derivative comes into play because the network needs to determine the slope of the line at a given point to know if there is lower cost elsewhere on the curve.

The illustration and accompanying walk through are elementary but very useful. The authors note that their illustration is for a single parameter model; real models have thousands, millions, and billions of parameters. "[I]t's impossible for the human mind to imagine a billion-dimensional space." Not with that attitude.  

"[G]radeient descent iteratively evaluates slopes to identify the adjustments to those parameters that correspond to the steepest reduction in cost." The authors describe backpropagation as "an ellegant application" of the calculus chain rule, which is the same rule that the Deep Learning book mentioned.

> Whereas forward propagation carries information about the input x through successive layers of neurons to approximate y with \hat{y}, backpropagation carries information about the cost C *backwards* through the layers in reverse order and, with the overarching aim of reducing cost, adjusts neuron parameters throughout the network. 

"We appreciate that this is not the lightest section of this book." I applaud the self-awareness here. They actually do a great job of explaining this technical concept using non-technical analogies and metaphors: "the cost function represents a hiking trail, and our trilobite is trying to reach basecamp."

The process of the blind trilobite moving down the curve of the function (gradient) is called adjusting the weight. "By adjusting the weight in proportion to the cost's function's gradient *with respect to that weight*, backprop adjusts that weight in a direction that reduces the cost."

Here's the money quote: 
 >remembering that neural networks are stacked with information forward propagating through their layers, we can grasp that any given weight in the network contributes to the final ŷ output, and thus the cost C. Using backpropagation, we move layer-by-layer backwards through the network, starting at the cost in the output layer, and we find the gradients of every single parameter. A given parameter’s gradient can then be used to adjust the parameter up or down (by an increment corresponding to the learning rate η)—whichever of the two directions is associated with a reduction in cost.

### Clanka Grades My Work

Claude reviewed the section above on back propagation for errors. It said that the post was accurate overall. But the Clanka suggest emphasizing that "backprop" and "gradient descent" are two separate concepts:

1. Back propagation computes the gradients
2. Gradient descent uses those gradients to update the weights

Claude offered to rewrite my entire post above, but I declined and made some small corrections. I did want to conclude with its suggested interview answer:

> “Backpropagation is the algorithm for computing the gradient of the loss with respect to every parameter in a neural network. It applies the chain rule backwards from the output, layer by layer, reusing intermediate results so it’s efficient. An optimizer like gradient descent then uses those gradients to update the weights.”