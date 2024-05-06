---
title: 2.9 inch e-Paper Module Three Color-Red Black White
---

## Introduction
------------

Note: The raw panel require a driver board, If you are the first time use this e-Paper, we recommend you to buy the HAT version or buy more one driver hat for easy use, otherwise you need to make the driver board yourself. And this instruction is based on the version with PCB or driver board.

296x128, 2.9inch E-Ink display module, three-color, SPI interface

**Model: [RAP20129H](http://www.elecrow.com/096-oled-128x64-blue-p-751.html)**

## Interface
---------

![2.9 inch e-Paper Module Three Color-Red Black White.jpg](https://wiki.elecrow.com/images/3/3e/2.9_inch_e-Paper_Module_Three_Color-Red_Black_White.jpg){ loading=lazy }

## Working principle
-----------------

1.Introduction

This product is an E-paper device adopting the image display technology of Microencapsulated Electrophoretic Display, MED. The initial approach is to create tiny spheres, in which the charged color pigments are suspending in the transparent oil and would move depending on the electronic charge. The E-paper screen display patterns by reflecting the ambient light, so it has no background light requirement. (Note that the e-Paper cannot support updating directly under sunlight)

2.Communication protocol

![2.9 inch e-Paper Module Three Color-Red Black White 1.png](https://wiki.elecrow.com/images/f/f6/2.9_inch_e-Paper_Module_Three_Color-Red_Black_White_1.png){ loading=lazy }

Note: Different from the traditional SPI protocol, the data line from the slave to the master is hidden since the device only has display requirement.

- CS is slave chip select, when CS is low, the chip is enabled.
- DC is data/command control pin, when DC = 0, write command, when DC = 1, write data.
- SCLK is the SPI communication clock.
- SDIN is the data line from the master to the slave in SPI communication.

SPI communication has data transfer timing, which is combined by CPHA and CPOL.

1.CPOL determines the level of the serial synchronous clock at idle state. When CPOL = 0, the level is Low. However, CPOL has little effect to the transmission.

2.CPHA determines whether data is collected at the first clock edge or at the second clock edge of serial synchronous clock; when CPHL = 0, data is collected at the first clock edge.

- There are 4 SPI communication modes. SPI0 is commonly used, in which CPHL = 0, CPOL = 0.

As you can see from the figure above, data transmission starts at the first falling edge of SCLK, and 8 bits of data are transferred in one clock cycle. In here, SPI0 is in used, and data is transferred by bits, MSB first.