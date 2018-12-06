---
title: Camera Timing Tutorial
excerpt: Tutorial
tags: 
permalink: /cameratutorial/
categories:
  - tutorials
background-image: tutorial1.png
---

## Camera Timing

### What Clocks are Used?
* PCLK
* HREF
* VSYNC
* C0
* C1
* C2

PCLK is the pixel clock. This clock determines the speed at which the data output is being transmitted. This means that at the positive edge of PCLK, a new byte is ready to read. 

HREF is the clock that determines when a row is ready to be read. The positive edge determines the start of a new row of pixels and the negative edge determines the end of a new row of pixels. This means that whenever HREF is high, there is a row of pixels to be read. 

VSYNC is the clock that determines when the frame of an image is ready to be read. The negative edge of VSYNC determines the start of a frame of an image and the positive edge determines the end of a frame of an image. This means that whenever VSYNC is low, the frame of an image is ready to be read. 

C0 is a 24MHz clock. It has a duty cycle of 50%. This clock should be used instead of the 24MHz clocks given.

C1 is a 25MHz clock. It has a duty cycle of 50%. This clock should be used instead of the 25MHz clocks given.

C2 is a 50MHz clock. It has a duty cycle of 50%. Use this clock instead of CLOCK_50 because the other clocks are phase-locked to this clock. 

C0, C1, and C2 are used as inputs to the RAM M9K module, the VGA Driver module, and the image processor module. To determine which one to use, look at what the clock is being used for and decide how fast reading and writing needs to happen. 

### Timing Diagram
Here is an example of a timing diagram. In this example, a new row begins after 2 bytes are read and a new frame is ready to be read after 3 rows.

<p align="center">
  <img src="/images/PCLK.png" width="538px" height="307px"/><br/>
  <i>PCLK Timing Diagram</i>
</p>

<p align="center">
  <img src="/images/HREF.png" width="538px" height="307px"/><br/>
  <i>HREF Timing Diagram</i>
</p>

<p align="center">
  <img src="/images/VSYNC.png" width="538px" height="307px"/><br/>
  <i>VSYNC Timing Diagram</i>
</p>

### Clocks in the Downsampler
Based on the clocks (PCLK, HREF, and VSYNC), the down sampler should take in the pixel values, update the x and y address, and set the value of write enable. 
