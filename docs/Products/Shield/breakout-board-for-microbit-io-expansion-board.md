---
title: Breakout Board for micro:bit IO Expansion Board
---

## Introduction
------------

Microbit expansion board is an IO port expansion board that supports micro:bit. It can draw out all resources on the micro:bit and also has its own buzzer. Not only can it be connected to the P0 pin through a jumper cap, but it can also be released through the jumper cap. The small and unique size is very suitable for various small projects of micro:bit.

**Model: [DTS02018B](https://www.elecrow.com/breakout-board-for-micro-bit-io-expansion-board.html)**

![Breakout board for microbit.png](https://wiki.elecrow.com/images/6/68/Breakout_board_for_microbit.png){ loading=lazy }

## Features
--------

- All IO ports are led out
- Comes with buzzer
- With LEGO compatible latch holes
- 3PN interface distinguished by yellow, red and black

## Usage
-----

For use with micro:bit, the connection is as shown below:

![Micto-bit Connection.png](https://wiki.elecrow.com/images/f/fb/Micto-bit_Connection.png){ loading=lazy }

Then log in to the makecode website [https://makecode.microbit.org/](https://makecode.microbit.org/) and click on New Project.

![New project.png](https://wiki.elecrow.com/images/d/de/New_project.png){ loading=lazy }

### Example 1 digital output

1\. Connect the positive and negative poles of the power supply and the IO port

![Connection IO.png](https://wiki.elecrow.com/images/3/35/Connection_IO.png){ loading=lazy }

2\. Write a light program.

![Light program.png](https://wiki.elecrow.com/images/5/5d/Light_program.png){ loading=lazy }

3\. Running result

![Result 1.png](https://wiki.elecrow.com/images/4/44/Result_1.png){ loading=lazy } 
![Result 2.png](https://wiki.elecrow.com/images/3/38/Result_2.png){ loading=lazy }  
### Example 2 I2C mode

1\. Add the i2c program module to makecode. Here we take oled as an example. Click "Extensions", enter OLED in the search box, and select the "oled-ssd1306" module.

![Extensions.png](https://wiki.elecrow.com/images/c/cd/Extensions.png){ loading=lazy }

![Oled-ssd1306.png](https://wiki.elecrow.com/images/3/3d/Oled-ssd1306.png)

2\. Connection module I2C interface

![I2C.png](https://wiki.elecrow.com/images/e/e2/I2C.png)

3\. Write a program to display "Micro:bit"

![Display micro bit.png](https://wiki.elecrow.com/images/thumb/b/bd/Display_micro_bit.png/400px-Display_micro_bit.png)

4\. Run and check the display effect

![Display effect.png](https://wiki.elecrow.com/images/8/8b/Display_effect.png){ loading=lazy }