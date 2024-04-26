---
title: Crowtail- LED Bar
---

## Description
-----------

The Crowtail– LED Bar is comprised of a 10 segment LED gauge bar and an MY9221 LED controlling chip. It can be used as an indicator for remaining battery life, voltage, water level, music volume or other values that require a gradient display. There are 10 LED bars in the LED bar graph: two red, three yellow,and five green bars. Demo code is available to get you up and running quickly. It lights up the LEDs sequentially from red to green, so the entire bar graph is lit up in the end. Want to go further? Go ahead and code your own effect.

**Model: [CT008463L](http://www.elecrow.com/crowtail-led-bar-p-1642.html)**

![Crowtail- LED Bar.jpg](https://wiki.elecrow.com/images/thumb/f/f3/Crowtail-_LED_Bar.jpg/600px-Crowtail-_LED_Bar.jpg){ loading=lazy }

## Features
--------

- Input Voltage: 3.3V/5V
- Each LED segment can be controlled individually via code
- Intuitive display
- Flexible power option, supports 3-5.5DC
- Available demo code
- Suli-compatible Library
- Dimensions(mm):40.0(L)x20.0(W)x11.3(H)

## Usage
-----

1.Hardware connection

Connect the Crowtail- LED Bar to U1 port on Crowtail- Base shield,and then plug the base shield onto Arduino.

![Led922541.jpg](https://wiki.elecrow.com/images/thumb/a/a8/Led922541.jpg/500px-Led922541.jpg){ loading=lazy }

2.Download Code and Upload You can download the library [LED Bar library](../../files/LED-Bar-zip.md)then extract it to libraries folder of Arduino.
Then open Arduino IDE, File -&gt; examples -&gt; LED\_Bar -&gt; Level, you can open the demo code.  
![Led03093033.jpg](https://wiki.elecrow.com/images/8/85/Led03093033.jpg){ loading=lazy }  
note: you should change the Clock pin to "1" and change the Data pin to "0" before you use this demo.

3.Download it to the Crowduino, you will see the led bar according to the order of the 2 red 3 yellow 4 green 1 bule cycle blinking.

## Resource
--------

- [MY9221\_DS\_1.0](../../files/MY9221-DS-1.0-pdf.md)
- [Crowtail- LED Bar eagle files](../../files/Crowtail-LED-Bar-eagle-files-zip.md)
- [LED Bar library](../../files/LED-Bar-zip.md)