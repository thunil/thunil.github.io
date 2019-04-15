---
layout: post
title: "Introducing the Physics-Based Deep Learning Blog"
description: 
headline: 
modified: 2019-04-15
category: PBDL
tags: [PBDL]
imagefeature: posts/physics-based-deep-learning-bgOnly.png
mathjax: 
chart: 
comments: false
featured: true
---

Welcome to the "PBDL" website focusing. Here, we'll summarize and discuss recent works
from the area of physics-based deep learning (PBDL). Under PBDL we understand
combinations of algorithms employing forms of deep neural networks
for physical problems and / or in conjunction with physical models. While deep learning
has been hugely successful all areas of pattern recognition, e.g., to classify
images and sounds, its application to physics problems is largely unexplored
despite the huge potential. With this website our goal is to give an overview 
of this rapidly growing field, and discuss and highlight recent works in 
this field.

Within the area of PBDL we can roughly distinguish the five categories:
- _Physics-based design_: incorporate domain knowledge about the
  system in the architecture of the learning process, e.g.,
  adapt the connectivity of a neural network such that it facilitates
  certain solutions.
- _Physics-based constraints_: guide and constrain the learning
  process with physical models, e.g., in the simplest case
  by including additional terms such as conservation laws in 
  the loss function.
- _Combined methods_: hybrid solvers that employ traditional
  numerical methods alongside deep-learning techniques to arrive
  at simulations methods that are improved in terms of, e.g.,
  efficiency, accuracy, generalization etc.
- _Outer-loop optimizations_:
  approaches that aim for higher level control or inverse
  problems, typically with an outer loop around a simulation.
  Here, fast and differentiable models exhibit particular promise.

Then, there's a fifth category that could be termed 
_Applications_: there are also many methods that apply established DL
  techniques to physical problems without really changing them. These
  works are nonetheless often highly interesting and much needed
  to establish methodologies of how DL can be best used for physical
  problems.

![PBDL-overview]({{ site.url }}/images/physics-based-deep-learning-overview.jpg)

Naturally, these categories can only serve as a rough guide to 
PBDL methods. In practice, many works
that combine aspects from more than one of these classes.

This website will be accompanied by the PBDL link list repository at
<https://github.com/thunil/Physics-Based-Deep-Learning>. There we'll collect
relevant links in a more static form, and also include those that can't be 
discussed here in more detail. For now, we'll also include a few highlight's from 
older TUM papers in the older posts below. Enjoy!

