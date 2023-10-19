---
layout: post
title: "We introduce: the VM-1"
subtitle: A Raspberry_Pi based Video Mixer
categories: []
banner:
  image: "assets/images/banners/20231019_VM-1_2.jpg"
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
  # subheading_style: "color: gold"
tags: []
sidebar: []
---

## The idea for the vm-1

In the work with students at the "Ernst Busch" Academy of Dramatic Arts in Berlin as well as in the work with the independent theater scene, there is a constant and still growing need for accessible video technology. This mostly involves the usage of pre-produced videos, the use of live cameras, or a combination of both. Multiple projectors and large screens are often used as output media, on which different image sources are to be shown.

Common software for live video (OBS-Studio, MadMapper, Isadora, TouchDesigner, vvvv, ...) is often too complex for these "simple" applications, does not quite meet the needs or is even too expensive for further use.

Out of this need the idea for a Video Mixer "VM-1" based on a Raspberry Pis was born.

## Functional description of the idea:

The VM-1 is a hardware and software system adapted on a Raspberry Pi to easily switch different image and media sources to different output devices.

One or two live cameras can be connected to the VM-1 via HDMI. The media data of a connected USB stick is automatically recognized and loaded. A button matrix can be used to direct the image sources to up to two connected HDMI devices. The principle of the matrix-based video mixer has already proven useful for stage use in a "Video Mixer" software developed at HfS in 2018 with OpenFrameworks, as it is easy to understand and clearly laid out. This should become even more accessible via the Raspberry Pi in terms of ease of use, the economic footprint of procuring multiple devices, and the resulting sustainability of artists being able to procure the open-source devices on their own, even at a small price.

The Raspberry Pi with a price of about 50€-150€/piece forms the technical basis and enables the described functions. The different versions of the Raspberry Pi result in three versions of the VM-1:

1. based on a **Raspberry Pi 4**:
   1x camera input, 2x video output
2. based on a **Raspberry Pi 5**:
   2x camera input, 2x video output
