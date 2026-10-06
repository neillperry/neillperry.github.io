---
layout: post
title: Crash Course in PyTorch - Part 2
date: 2026-10-05
jumbotron: Crash Course in PyTorch -  Part 2
regular_date: October 5, 2026
summary: Second part in my crash course of learning PyTorch.

---

<figure style="text-align:center;">
<img src="https://catalog.archives.gov/medialz/kansas-city/rg-075/285796/75-SR-5950_001.jpg" 
     alt="Black and white photograph of a man using a lit torch (possibly in a garage or small factory??) (NAID: 57275178)" 
     title="The hotter the PyTorch, the stronger the inference"
     style="width:70%; height:auto;" />
     <figcaption style="font-style: italic; margin-top: 10px;">
          Do not look directly into the PyTorch. It will approximate your brain via matrix multiplication (NAID: 57275178)
     </figcaption>
</figure>

---
### Jump to Section
{:.no_toc}
* TOC
{:toc}
--- 

### Crash Course

This is part two of my efforts to crash course [PyTorch, a Python software library](https://docs.pytorch.org/tutorials/beginner/basics/intro.html) used for deep learning. 🤯🤯

Last time we covered working with data. Today it will be create models. 

The tutorial gives the following roadmap:
1. Work with data
2. Create models
3. Optimize model parameters
4. Save the trained models

### Create Models

Neural networks are a bunch of layers and modules. `torch.nn` has everything you need to build that network. With Pytorch, i tlooks like you can train a model on CPU or an accelerator, which sounds like a type of ML-specific hardware that supports CUDA, MPS, MTIA, etc. 

Define the neural network class. Here's a block of code:

     class NeuralNetwork(nn.Module):
         def __init__(self):
             super().__init__()
             self.flatten = nn.Flatten()
             self.linear_relu_stack = nn.Sequential(
                 nn.Linear(28*28, 512),
                 nn.ReLU(),
                 nn.Linear(512, 512),
                 nn.ReLU(),
                 nn.Linear(512, 10),
             )

         def forward(self, x):
             x = self.flatten(x)
             logits = self.linear_relu_stack(x)
             return logits


I have no idea what this means. I recognize ReLU() as a type of ML algorithm. Let's call in Claude. 

Claude says that it creates a class. The actual network is created with `model = NeuralNetwork()`. The class definition defines what's in the network `__init__` part and how data flows through the network, the `forward()` part. 

**init**: the first part is super().init(). I had to take out the underlines for this Markdown post. The super() thing invokes the `nn.Module` constructor.

**self.flatten=nn.Flatten()**: this flatten transform the input of 28x28 into a single row of 784 numbers "so the linear layers can process it."

**self.linear_relu_stack** the last part of the **init** function creates a `Sequential` stack "that passes data through its layers in order, so you don't have to call each one by hand."  There are layers and ReLU() activation functions. The ReLU() function applies `max(0, x)` to get rid of all negative numbers. 

The last line `nn.Linear(512, 10)` is "the output layer: 10 numbers, one per clothing category in the FashionMNIST dataset the tutorial uses." ReLU "breaks the linearity by bending the function at zero...[so] the network can learn curved, complex decision boundaries, like the difference between 'sneaker' and 'sandal'...."

Going back to the layer `nn.Linear(784, 512)` -- "Each of its 512 outputs is a weighted sum of all 784 inputs plus a bias." This layer has roughly 400,000 parameters. 

To explain the Linear syntax:  `nn.Linear(in_features, out_features)`. For each layer, the first number is how many go in, the second how many come out. Each layer's output has to match the next layer's input. 

Okay, that was a total waste of tokens. The tutorial goes on to explain what is going on.  

### Format Test for my Blog
This sentence has inline HTML <span style="color: green;">red text</span> in it.

This Kramdown text has *colored text*{: style="color: crimson"} in a sentence.