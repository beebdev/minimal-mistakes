---
layout: single
title: COMP3601 23T3 - How to do this project right
date: 2023-10-10
breadcrumbs: true
categories: teaching
tags: UNSW
toc: true
---

# Intro
In 2022 T3, I had the chance to help re-design the COMP3601 Design Project A course at UNSW. The course itself is a project involving putting together a system containing electronics, FPGA, and software application for an application theme with an aim for students to learn how software interfaces with digital hardware and information in non-digital form. Having been working in the audio networking scene for a while, an audio themed project made a lot of sense!

Fast-forwarding to 2023, the course has been reused, and although I am no longer officially part of the course, I was invited to share my insights on ***how to do this project right***. You can find my slides [here](/assets/files/COMP3601_23T3_how-to-do-this-project-right.pdf).


# Historical context
Previous years we had very different projects. When I did the course as a student in 2020, we were asked to develop an IR decoding box which can be used to control software for multimedia playback. We were provided with a [Digilent Nexys A7](https://digilent.com/shop/nexys-a7-fpga-trainer-board-recommended-for-ece-curriculum/) board, some electronics components such as IR receiver diodes, ADCs, potentiometers and some documentation resources for transferring data from the Nexys FPGA to a host machine. It was a fun project. My group chose to not use the *retro-styled* software protocol (I can't even recall the name..) and integrated an ESP32 MCU to directly interface with the FPGA dev kit through SPI via the PMOD pins. There were physical controls and our system supported a few common IR protocols used in household remotes. We hosted a mini webserver on the ESP32 (using SPIFFS :P) for media playback and control which was pretty cool! For those interested, the source code of our project can be found [here](https://github.com/beebdev/COMP3601-20T3-Brown).

The next year, I was involved in the course as a tutor. However, in 2021 the primary course delivery mode was online, and this course had to align with the norm. This was unfortunate becuase a lot of students were overseas and the project was purely done through simulation. However, the project was interesting. That year students were asked to design a hardware cryptography accelerator for the post-quantum Learning With Error (LWE) algorithm and explore how approximate multiplers can be used to minimise the design (by reusing the error introduced by the multipliers for the error component in the algorithm). Interesting project, but quite challenging..

# Changes in 2022
Going into the following year and having the chance to help redesign some parts, we chose to go with a newer and much powerful board, a Xilinx Kria AI Starter Kit, which has a quad-core ARM Cortex A53 with embedded FPGA (Zynq U+!). Definetly an overkill, but the goal is to future proof. Students get to learn how software systems see hardware and familiarise with the Zynq ecosystem that will help them when they take the Project B course (COMP4601, HLS and hardware acceleration).

# The talk
This guest lecture I gave covers the things I wish I did when I developed the starter code / demo project which focuses more on the computer systems side. Enjoy!
