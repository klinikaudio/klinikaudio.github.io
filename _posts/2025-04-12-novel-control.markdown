---
layout: post
title:  "N-Segment Pendulums, 4D Hypercubes and Genetic Programming"
date:   2025-04-11 00:00:00 +0000
categories: applications, hypercube, pendulum
author: "Benny Woo"
tags: "applications, hypercube"
---

I've recently been building some control signal generators for MIDI, OSC, CV and the internal protocol around which my software suite Klinik is built.

## N-Segment Pendulum

The first of which is an n-segment pendulum, inspired by the excellent Caudal, a VCV Rack module by Vult. This generates natural, chaotic oscillations that become increasingly erratic with the addition of extra segments.

<video width="60%" loop autoplay muted playsinline>
  <source src="{{ '/assets/videos/pendulum.mp4' | relative_url }}" type="video/mp4">
  Your browser does not support the video tag.
</video>

## 4-Dimensional Hypercubes

The second, a tesseract module, displays the real-time 2D screen coordinates for each vertex (node) of a rotating hypercube.

<video width="60%" loop autoplay muted playsinline>
  <source src="{{ '/assets/videos/hypercube.mp4' | relative_url }}" type="video/mp4">
  Your browser does not support the video tag.
</video>

### Genetic Approaches to Curve Fitting

Finally, this application transforms photos of hand-drawn whiteboard curves into mathematical functions. The aim is to provide a quick workflow: sketch a shape, capture it with a photo, and generate an approximate function that can then be used to produce control voltages via a DAC, ultimately for driving modular synthesizers or similar gear. The application offers two approaches:

### Quick Fitting

This method employs non-linear least squares optimisation to fit the extracted data points to a predefined mathematical model, specifically a standard sine wave function. It works by iteratively adjusting the function's parameters (amplitude, frequency, phase, vertical offset) to minimise the difference (sum of squared errors) between the function's output and the actual data points. Fast and effective if the curve doesn’t deviate too much from a sine wave.

### Symbolic Regression

This approach uses symbolic regression to discover a suitable mathematical function without prior assumptions about its form. It starts with a set of core mathematical functions and operators and evolves a population of candidate expressions over generations, selecting and combining them based on how well they fit the data. Computationally intensive but more flexible.

![Curve Fitting]({{ '/assets/images/curvefit.jfif' | relative_url }})