---
layout: post
title:  "Image Texture Resynthesis of Spectrograms"
date:   2025-03-10 20:50:00 +0000
categories: applications, spectral
author: "Benny Woo"
tags: "spectral, imaging"
---

This work in progress application suggests an approach to audio restoration derived from Dr. Paul Harrison’s [2005 PhD thesis](https://logarithmic.net/pfh-files/thesis/dissertation.pdf) on image texture synthesis. If you’ve used Photoshop’s content-aware fill, or GIMP’s [resynthesiser plugin](https://github.com/bootchk/resynthesizer), you’ll be familiar with this technique, which, although less sophisticated than more contemporary neural-network based approaches is still pretty serviceable and much more lightweight.

These tools let you remove a selected part of an image and fill the gap with a texture synthesised by matching small patches from surrounding areas. So, what happens when we apply this technique to a spectrogram image of an audio file?

### Precision spectral repair

Well, firstly we’ll want some way to make precise selections. In this application, I’ve adapted another tool from the world of image editing - magic wand selection. Here, this tool selects a connected region of pixels in the spectrogram whose decibel (dB) values are "similar" to the pixel you initially click on. Similarity is defined by a user-adjustable Threshold. It can optionally Feather (expand) the selection boundary. Rectangular and polygon selection tools are also available.

While we can then play or export the isolated portion of audio (useful in itself for precision filtering), we can also "heal" it, removing and filling the region using a texture resynthesis algorithm.

<video width="100%" loop autoplay muted playsinline>
  <source src="{{ '/assets/videos/spectrawand.mp4' | relative_url }}" type="video/mp4">
  Your browser does not support the video tag.
</video>

In the example video, I select and "heal" a sine sweep that has been imposed over a recording of speech. The most obvious application here is audio repair (a la [Steinberg's Spectralayers](https://www.steinberg.net/spectralayers/)), although I am particularly interested in the creative applications.