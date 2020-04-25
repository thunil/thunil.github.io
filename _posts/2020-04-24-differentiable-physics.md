---
layout: post
title: "Differentiable Physics for Deep Learning with phiflow"
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

A recent development that is worth pointing out here is our
differentiable physics frame work for deep learning called "phiflow".
You can download the sources at: <https://github.com/tum-pbs/PhiFlow>

Philow is a research-oriented, open-source fluid simulation toolkit. It is written mostly in Python and can use both NumPy and TensorFlow for execution.

Having all functionality of a fluid simulation running in TensorFlow opens up the possibility of back-propagating gradients through the simulation as well as running the simulation on GPUs.

Features: 
- Variety of built-in fully-differentiable simulations, ranging from Burgers and Navier-Stokes to the Schrödinger equation.
- Tight integration with TensorFlow and PyTorch (experimental) allowing for straightforward neural network training with fully differentiable simulations that run on the GPU.
- Object-oriented architecture enabling concise and expressive code, designed for ease of use and extensibility.
- Reusable simulation code, independent of backend and dimensionality, i.e. the exact same code can run a 2D fluid sim using NumPy and a 3D fluid sim on the GPU using TensorFlow or PyTorch.
- Flexible, easy-to-use web interface featuring live visualizations and interactive controls that can affect simulations or network training on the fly.

This framework was e.g. used in the paper on long-term control
of PDEs: Learning to Control PDEs with Differentiable Physics
<https://ge.in.tum.de/publications/2020-iclr-holl/>.

