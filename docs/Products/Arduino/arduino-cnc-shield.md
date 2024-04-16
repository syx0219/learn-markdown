---
title: Arduino CNC Shield
---

## Description
-----------

What projects can this be used for?   
-Small CNC routers, DIY Laser Cutters, 3D Printers and almost any project where you need to control a stepper motors with high precision.   
At Protoneer we designed this simple Arduino CNC shield kit (Arduino Extension Board) with the following features:   
New with Version 3.51:  
Added circuitry for End-Stop and Probe signal filtering. This eliminates false triggers and makes it possible use non-shielded cable for end-stops/probes.  
Bigger Solder pads making it easier to assemble.  
Probe pin labels have been updated to make it easier to install a probe.  
**Model: [CDP03051C](https://www.elecrow.com/arduino-cnc-shield-v3-51-grbl-v0-9-compatible-uses-pololu-drivers.html)**  

![Arduino shield351 1.jpg](https://wiki.elecrow.com/images/thumb/a/a8/Arduino_shield351_1.jpg/500px-Arduino_shield351_1.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/arduino-cnc-shield-v3-51-grbl-v0-9-compatible-uses-pololu-drivers.html?wiki "Title text")

## Features
--------

- Includes Noise Filers on all endstops and the probing pin.(New in V3.51)
- GRBL 0.9 compatible. (Open source firmware that runs on an Arduino UNO that turns G-code commands into stepper signals [https://github.com/grbl/grbl](https://github.com/grbl/grbl))
- 4-Axis support (X, Y, Z , A-Can duplicate X,Y,Z or do a full 4th axis with custom firmware using pins A4 and A3)
- 2 x End stops for each axis (6 in total)
- Coolant enable
- Uses removable Pololu A4988 compatible stepper drivers. (A4988, DRV8825 and others)(Not Included)
- Jumpers to set the Micro-Stepping for the stepper drivers. (Some drivers like the DRV8825 can do up to 1/32 micro-stepping )
- Compact design.
- Stepper Motors can be connected with 4 pin molex connectors or soldered in place. .
- Runs on 12-36V DC. (At the moment only the Pololu DRV8825 drivers can handle up to 36V so please consider the operation voltage when powering the board.)

## FAQS
----

- What is a CNC router? [http://en.wikipedia.org/wiki/CNC\_router](http://en.wikipedia.org/wiki/CNC_router)
- What is GRBL?An open source, embedded, high performance g-code-parser and CNC milling controller written in optimized C that runs on an Arduino UNO. [ttps://github.com/grbl/grbl](https://github.com/grbl/grbl)
- What is Arduino? [http://en.wikipedia.org/wiki/Arduino](http://en.wikipedia.org/wiki/Arduino)
- What Pololu stepper driver can it use? Pololu A4988 - [http://www.pololu.com/catalog/product/1182 ](http://www.pololu.com/catalog/product/1182)or Pololu DRV8825 [http://www.pololu.com/catalog/product/2133](http://www.pololu.com/catalog/product/2133) works well. Both of these driver are available at Elecrow.
- A4988 Stepper Motor Driver [https://www.elecrow.com/a4988-stepper-motor-driver-module.html](https://www.elecrow.com/a4988-stepper-motor-driver-module.html)
- For more question, please visit [forum.protoneer.co.nz](https://forum.protoneer.co.nz/)