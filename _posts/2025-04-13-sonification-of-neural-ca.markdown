---
layout: post
title:  "Sonifying Neural Cellular Automata"
date:   2025-04-13 00:00:00 +0000
categories: applications, cellular automata
author: "Benny Woo"
tags: "applications, cellular automata"
---

This app simulates a Neural Cellular Automaton (NCA), a grid of cells where each cell's state updates based on its neighbours, processed through a filter kernel and an activation function. The influence of the neighbourhood is in this NCA is calculated using a convolution with a kernel (a small, 3x3 matrix of weights). The convolution essentially computes a weighted sum of the cell's neighbours (including itself, depending on the kernel center value). This is analogous to the input calculation in a neuron or a convolutional layer in a deep learning model.

<video width="80%" loop autoplay muted playsinline>
  <source src="{{ '/assets/videos/neural.mp4' | relative_url }}" type="video/mp4">
  Your browser does not support the video tag.
</video>

The result of the convolution (the weighted sum) is then passed through a non-linear activation function. This introduces non-linearity, allowing for much more complex and dynamic patterns than purely linear rules could produce. The application currently offers the following predefined activation functions:

* Sigmoid
* ReLU
* Tanh
* Gaussian
* Step
* Sin
* Inverse Gaussian
* Binary Threshold
* Cubic
* Abs
* Wavelet

Unlike CAs with discrete states (e.g., alive/dead, black/white), the cells in this NCA hold floating-point values. This allows for smoother transitions and more nuanced patterns. The behavior of this NCA is heavily determined by two main tunable components:

The kernel values (the weights for the convolution).
The choice and shape of the activation function.

Crucially, the application analyses the overall state of the grid – specifically its mean (average value) and variance (how spread out the values are) – and uses these metrics to continuously control parameters of a built-in sound synthesiser offering a variety of synthesis types (FM, granular, additive, subtractive and wavetable).