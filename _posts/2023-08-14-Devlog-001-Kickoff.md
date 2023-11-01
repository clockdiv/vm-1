---
layout: post
title: "Kickoff"
subtitle: How video playback and camera input works on the Raspberry Pi
categories: []
banner:
  image: "assets/images/banners/20231019_VM-1_2.jpg"
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  # heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
  # subheading_style: "color: gold"
tags: []
sidebar: []
---

# Devlog 001
## Kickoff Meeting
Since we want to make an accessible, yet capable piece of hardware, we decided to use the Raspberry Pi 4 as a starting point. The RPi4 comes at an affordable price and has the capabilities that we defined as the bare minimum for our project:

- 2 video HDMI video output with at least 1080p at 30fps
- parallel hardware decoding of min. 2 video streams
- live capturing of at least 1 external HDMI device (e.g. camera, computer)

And with the Pi 5 on the horizon we figured there might be enough headroom in computing power for further iterations of the project, without having to change too much of our development process

The first two requirements are implementable with the help of a vanilla Raspberry Pi 4 device, but capturing HDMI devices is not supported out of the box. Luckily there is a little hardware extension available which allows connecting HDMI devices to the RPi’s camera port (CSI). This adaptor allows for capturing HDMI input streams with up to 1080p at 30fps. It is not a breathtaking bandwidth but it satisfies our minimum requirements.

<!--- excerpt-start -->
Now that we knew what the hardware platform is going to look like, it was time to think about how the software pipeline might come to life. So one weekend in August we got together for a little kickoff meeting. The goal was to explore the video capabilities of the Raspberry Pi.

We found hardware accelerated video players like the omxplayer, that support the hardware accelerated video decoding pipeline of the RPi4. There’s also a tool called rpivid that is able to capture camera/HDMI devices. But unfortunately both tools are deprecated since RPi OS “Bullseye”. They only work if the RPi is configured to run in “Legacy Camera Mode”, which is only available for 32bit versions of RPi-OS. But since we are looking for a future-proof solution, this was not an option for us. Currently the RPi-Foundation is in the process of switching the complete camera stack to v4l2. Using a v4l2-based video/camera pipeline seemed to be the way to go. Popular tools like vlc and ffmpeg are supporting hardware accelerated video decoding (h.264/h.265), but it looks like the new camera stack is not yet supported on the Rasberry Pi. The RPi-Foundation created the libcamera software library in order to fill that gap. Unfortunately the HDMI input device we are using is not yet supported.
<!--- excerpt-end -->

Further research showed that GStreamer supports both hardware accelerated video decoding AND v4l2-based input sources, like the Pi-Camera. That’s why we took a closer look at the GStreamer-Pipeline. 

We’re going to share our findings from experiments with the gst-launch-1.0 command-line tool and how that evolved into a first Python application in the next episode of this devlog.

### HDMI to CSI adaptor
https://www.waveshare.com/hdmi-to-csi-adapter.htm

### libcamera
https://www.raspberrypi.com/documentation/computers/camera_software.html#libcamera-and-libcamera-apps
