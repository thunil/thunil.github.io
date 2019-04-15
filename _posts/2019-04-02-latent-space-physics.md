---
layout: post
title: "Leveraging Learned Latent-spaces of Deep Neural Networks for Physics Predictions"
description: 
headline: 
modified: 2019-04-02
category: RNNs
tags: [latent-space-physics]
imagefeature: 
mathjax: 
chart: 
comments: false
featured: true
---

Our work on running physical simulation via latent spaces of neural networks was first online on arXiv in February 2018. It will now be presented at Eurographics 2019 in Geneva, and by now finally also some introductory
training data and trained 2D models are available. You can find source code, data and models at:

<https://github.com/wiewel/LatentSpacePhysics>

The main idea of this paper is a very general one: we train an _autoencoder_ network that yields a
specialized compression scheme for the data at hand. The bowtie shaped network compresses the original,
high-dimensional data into a much smaller latent-space, and at the same time gives us a decoder
network that restores the original function from a point in latent space. The _encoder_ and _decoder_
of the autoencoder are visiable as blue funnels in the overview image below.

![LSP-overview]({{ site.url }}/images/posts/latent-space-physics-overview.jpg)

We then train a second network that purely works on these latent space points (yellow circles)
in the image. We specifically focus on networks to _predict future states_ of the pressure
field in the flow. Here we employ an LSTM network that receives several latent space points and predict one
or more future pressure states. Once we have a future latent space point, the decoder from the autoencoder network
is used to retrieve the full field-based data set.

For detailed evaluations of the resulting accuracies
w.r.t. the pressure and surface positions, you can check out the paper at: <https://arxiv.org/pdf/1802.10123.pdf>

Or the video <https://www.youtube.com/watch?v=DZzVeDkX5-c>

In general, this can yield very fast data-driven methods that work in compressed spaces
that are specific to the targeted space of solutions. However, a key requirement is that
enough training data is available to accurately represent the space of solutions. Here
numerical simulations are especially useful, as they typically allow us to produce arbitrary
amounts of reliable data - at least if we're patient enough to wait for the data generation to
finish!

_Paper Abstract_: Our work explores methods for the data-driven inference of temporal evolutions of physical functions with deep learning techniques. More specifically, we target Navier-Stokes / fluid flow problems, and we propose a novel network architecture to predict the changes of the pressure field over time. The central challenge in this context is the high dimensionality of Eulerian space-time data sets. Key for arriving at a feasible algorithm is a technique for dimensionality reduction based on convolutional neural networks, as well as a special architecture for temporal prediction. We demonstrate that dense 3D+time functions of physics system can be predicted with neural networks, and we arrive at a neural-network based simulation algorithm with practical speed-ups. We demonstrate the capabilities of our method with a series of complex liquid simulations, and with a set of single-phase simulations. Our method predicts pressure fields very efficiently. It is more than two orders of magnitudes faster than a regular solver. Additionally, we present and discuss a series of detailed evaluations for the different components of our algorithm.  

Further info at: <https://ge.in.tum.de/publications/latent-space-physics/>
