---
layout: post
title: Even More Neural
date: 2026-10-03
jumbotron: Even More Neural
regular_date: October 3, 2026
summary:  Let's read about feedforward networks, a subtopic of neural networks. 

---

<figure style="text-align:center;">
<img src="https://catalog.archives.gov/medialive/41/7219/7721941/content/arcmedia/stillpix/406-nsb/406-NSB-119/406-NSB-119-RockBandsAndLayers.jpg" 
     alt="Color photograph of gray and yellow bands of rock form the sides of Willis Canyon, Utah (NAID: 7721941)" 
     title="Layers come in the form of rocks or neural network nodes. All layers"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          Rock layers in Willis Canyon, Utah. Those very different layers than the ones I study here. (NAID: 7721941)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 

### Back to Learning Neural Networks

Let's read Chapter 6: Deep Feedforward Networks. I am learning heavily on Claude to explain what is going on.  I will try to *italicize* Clanka text; text from the book are in quotes. 


### Into the Book

Deep feedforward networks are also called feedforward neural networks. They are "the quintessential deep learning models." Their purpose is "to approximate some function." "These models are called feedforward because information flows through the function being evaluated from x, through the intermediate computationss used to define f, and finally to the output y. There are no feedback connections in whcih outputs of the model are fed back into itself." 

In a feedforward network, information flows in one direction only. Recurrent neural networks are models that include feedback connections.

They're called networks "because they are typically represented by composing together many different functions." So each layer of the network is a separate function. 

"During neural network training, we drive f(x) to match f*(x)." So Clanka analogizes a neural network to an assembly line. Each layer is a workstation. *Nobody tells station 1 what to do. Over many rounds, each station adjusts based on how the final product fell short, and the stations end up with some workable division of tasks.*

**Output layer**: the final layer of a feedforward network. Its size is fixed by the task.
**Hidden Layers**: all the other layers. 
**Input layer:**: its size is fixed by the incoming data.

"Each hidden layer of the network is typically vector valued." -- this means that each layer's output is a list of numbers, aka, a vector. So it might be something like h = [0.2, 5.3, 0.0. 1.2].

*directed acyclic graph*: set of points connected by one-way arrows. You can never loop back to where you started. There are no cycles. 

1. **Choosing the optimizer**: the optimizer is *the algorithm that adjusts the parameters to reduce the loss.* This is gradient descent.
2. **Choosing the cost function**: this is just the loss function; we need to measure how wrong the model is. 
3. **Choosing the form of the output units**:


### Cost Functions

"An important aspect of the design of a deep neural network is the choice of the ost function"

"One recurring theme throughout neural network design is that the gradient of the cost function must be large and predictable enough to serve as a good guide for the learning algorithm."

**When designing a neural network, what factors go into deciding how many layers to create?**

According to Claude, these factors play a role:
- amount of training data
- ease of training
- compute and speed -- *each layer adds training time, memory, and prediction latency*
- existing architecture -- usually AI scientists go off an existing architecture; they don't select number of layers in isolation from scratch

### Universal Approximation Theorem

"The universal approximation theorem means that regardless of what function we are trying to learn, we know that a large MLP will be able to represent this function. We are not guaranteed, however, that the training algorithm will be able to learn that function"

Claude dumbed this down for me. 

*If you give a network just one hidden layer and enough units in it, it can mimic basically any function you care about, as closely as you want*

"In summary, a feedforward network with a single layer is sufficient to represent any funtion, but the layer may be infeasibly large and may fail to learn and generalize correctly."

### Depth vs Width

So the Universal Approximation Theorem mentions depth, so I asked Claude to explain this. I have no idea if any of this is correct.

Summarized from Clanka: both width and depth add capability to a neural network but in different ways. 

**Width**: *how manyunits are in a layer: how many features the network computes side by side at one stage.*

**Depth**: *how many layers there are: how many times the network can build new features out of the previous ones.*

Width: compute things simultaneously; Depth: compute things in sequence.

*In principle, width alone is enough; in practice, depth is often far more efficient.*

There's a folding paper example. Depth adds complexity more quickly. 

*[I]mages, speech, and language all have layered structure that deep networks can exploit*

From the textbook: "Empirically, greater depth does seem to result in better generalization for a wide variety of tasks"

- network can be too narrow
- deep networks are harder to train
- wide layers are hardware-friendly

This is a very difficult chapter that requires multiple reads and frequent back and forth with AI. 
