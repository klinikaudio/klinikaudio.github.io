---
layout: post
title:  "Tk UI Builder"
date:   2025-04-20 00:00:00 +0000
categories: applications, GUI
author: "Benny Woo"
tags: "applications, GUI"
---

I’m currently building a [Tk](https://www.tcl-lang.org/) based UI designer as a means of designing front-ends for KMOD patches (the graphical DSP patching environment at the core of my experimental computer music suite, Klinik). It’s designed as a simple, drag-and-drop WYSIWYG editor with the standard array of Tk widgets (buttons, sliders, etc) and scripting capabilities for the canvas.

An embedded Python scripting engine handles canvas drawing, with Google Gemini API integration allowing for the generation of scripts from natural language prompts (obligatory Mandelbrot fractal for illustrative purposes).

![tkbuilder]({{ '/assets/images/tkbuilder.png' | relative_url }})

Sidenote: the Gemini API has an infuriating habit of pushing Python code with backticks prefixing comments. No amount of instruction, begging or threats seem to have any effect. Plz fix Google :/