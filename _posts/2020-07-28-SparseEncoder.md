---
layout: posts
title: "[ML][EN]Sparse Encoder"
excerpt: "Let us Explore Sparse Encoder one of the best functioning AutoEncoder"
categories:
- Study
- DeepLearning
- ComputerVision
tags:
- Study
- ComputerVision
- NeuralNetwork
- AutoEncoder
last_modified_at: 2020-07-28
comments: true
author: "WooLee" 
---


# Neural Network in a nutshell  
This post was written by referring Andrew Ng's lec note in Stanford University

# 0. Found at 
* **Paper** : Andrew Ng CS294A Lecture notes <https://web.stanford.edu/class/cs294a/sparseAutoencoder_2011new.pdf>


# 1. AutoEncoder and Sparsity
Suppose we have only unlabeled training examples set. An **AutoEncoder** neural network is an unsupervised learning algorithm that applies backpropagation, setting the target values to be equal to the inputs. I.e., it uses $y^{(i)}=x^{(i)}$

## 1.1. Diagram
<img src="/assets/img/2020-07-28-SparseEncoder/diag1.png" width = "300">  


> Main Concept<br>  

As autoencoder set target values to be equal to the inputs, it tries to learn a function $h_{W, b}(x) = \hat{x} \approx x$

Let's assume, we are training 100 pixels(10 by 10) images and put hidden layer in $L_2$ which has 50 units(neurons). That is, the constraints on the network is implemented. Through this, we can discover **interesting structure** about the data.


<img src="/assets/img/2020-07-28-SparseEncoder/pic1.jpg">

Here, inputs $x$ are 100 pixels image so $n = 100$.
Then, for autoencoding, 50 units were implemented which is, $s_2 = 50$, to layer $L_2$. As output ought to be 100 pixels, $y \in \mathbb{R}^{100}$, with no doubt. 

* Key idea<br>  

Parameters(or each $x_i$) are set IID Gaussian independent. Compress from 100 to 50 would be very very difficult. But if there is **structure** in the data, same to say 'some of the input features are correlated', then this algorithm can discover some of those correlatoins. That is the key idea of autoencoding

* Sparsity Implemented<br>  

There is the case the number of units in the hidden layer is larger than that in the input layer, here $s_2 = 200$. Still, we can discover interesting structure. In particular, if we impose **SPARSITY** constraints on the $s_2$, the autoencoder can discover the interesting structure in the data, even the number of hidden units is large.

* Neuron is "active/firing" or "inactive"<br>  

**for SIGMOID activation function,**
Neuron is considered <span style = "color: #ff8080
">"active" </span>or <span style = "color: #ff8080
">"firing" </span> when its outvalue is close to 1.  
Neuron is considered <span style = "color: #ff8080
">"inactive" </span> when its outvalue is close to 0. 
(If you are using a **tanh activation** function, then we think of a neuron as being inactive when it outputs values close to -1)

Here, we would like to constrain the neurons to be inactive most of the time.

* KL divergence<br> 
In KL divergence, the penalty term can be written
$\sum_{j=1}^{s_{2}} \mathrm{KL}\left(\rho \| \hat{\rho}_{j}\right)$

# Reference

