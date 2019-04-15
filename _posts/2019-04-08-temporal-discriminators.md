---
layout: post
title: "Adversarial Training with Temporal Discriminators"
description: 
headline: 
modified: 2019-04-08
category: GANs
tags: [generative-adversarial-networks]
imagefeature: 
mathjax: 
chart: 
comments: false
featured: true
---

One aspect of recent PBDL works at TUM that has worked extremely well is to use generative
adversarial networks to supervise time related aspects of the target functions.

This temporal discriminator was first demonstrated in the ACM ToG / SIGGRAPH paper
from August 2018, dubbed _tempoGAN_. This architecture uses two discriminator
networks, one that can focus on spatial detail, and a second one to supervise the
temporal evolution. This work focuses on the inference of high-resolution 
scalar transport phenomena such as smoke, but the general approach self-supervise
for temporal coherence is interesting for a variety of GAN applications.

Effectively, the tempoGAN architecture trains two "learned" loss functions
based on the given data, which 
are then used to guide the training of the generator network. However, a 
fair amount of regularization is still required to guide and stabilize the generator training.

![tempoGAN result]({{ site.url }}/images/posts/tempoGAN-overview.jpg)

The full source code in conjunction with training data generators and archives
as well as trained models can be found here:
<https://github.com/thunil/TempoGan>

![tempoGAN result]({{ site.url }}/images/tempoGAN.jpg)

Recently, this idea was extended to video super-resolution with a modified, recurrent
architecture. I.e., in this version the output of one frame is the input
for the inference of the next one. (Interestingly, the tempoGAN does quite
well for smoke without this, but the problem is also better posed in this
setting.)
Via a spatio-temporal discriminator this recurrent network is able to generate
very fine structures based on fairly coarse and pixelated inputs.
<https://github.com/thunil/TecoGan>

![TecoGAN result]({{ site.url }}/images/TecoGAN.jpg)

The scales on the lizard below are also a good example. The network recovers their
outlines purely based on a pattern of rough inputs on the left. It's even nicer in motion,
as these structures are preserved over the course of many frames. 

![TecoGAN result]({{ site.url }}/images/posts/TecoGAN-lizard.jpg)

Overall, these results show that deep learning algorithms can successfully learn 
complex temporal changes, and more specifically, that GANs with temporal discriminator
architectures are powerful tool for the inference of functions over time.
For both papers you can find the supplemental videos that contain the examples shown 
in the images above in addition to a variety of other results on YouTube:
tempoGAN: <https://www.youtube.com/watch?v=i6JwXYypZ3Y>
TecoGAN: <https://www.youtube.com/watch?v=pZXFXtfd-Ak>

Further info and additional papers at: <https://ge.in.tum.de/publications/>
