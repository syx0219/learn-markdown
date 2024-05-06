---
title: Crowduino-Nano-V3.1
---

## Introduction
------------

The Nano 328 is a small, complete, and breadboard-friendly board based on the ATmega328 (Arduino Nano 3.0) or ATmega168 (Arduino Nano 2.x).It have an integrated on-board USB. As the function, It has almost all the analog and digital pins that the UNO or Duemilanove has and the same function as Duemilanove or UNO. This Nano 328(Arduino compatible) can go with the IO Shield for Arduino Nano, it would be more friendly and convenient for users to enter the Arduino world and make use of Arduino to make their dream into reality.  
As an upgrade version of Arduino Nano, This Nano 328 is 100% compatible to Arduino Nano and its shield and IDEs. On the hardware part, remarkable changes are taken to improve the flexibility and user experience.

**Model: [MCA03328A](http://www.elecrow.com/nano-328arduino-compatible-p-340.html)**  
![Nano 328(Arduino Compatible).JPG](https://wiki.elecrow.com/images/thumb/4/48/Nano_328%28Arduino_Compatible%29.JPG/600px-Nano_328%28Arduino_Compatible%29.JPG){ loading=lazy }

## Features
--------

Power OK red LED, Green (TX), green (RX) and green (L) LED  
Upgraded 5V voltage sourcing, more powerful drive capability  
Mini-B USB for programming and serial monitor, TX&amp;RX breakout for application as USB-UART convertor  
Surface-Mount ICSP header  
Standard 2.54mm spacing DIP (breadboard friendly)

## Specifications
--------------

Microcontroller: ATmega328  
Operating Voltage(logic level): 5V  
Input Voltage(recommended): 7-12 V  
Input Voltage(limits): 6-20 V  
Digital I/O Pins: 14 (of which 6 provide PWM output)  
Analog Input Pins: 8  
DC Current per I/O Pin: 40 mA  
Flash Memory: 16 KB (ATmega168) or 32 KB (ATmega328) of which 2 KB used by bootloader  
SRAM: 1 KB (ATmega168) or 2 KB (ATmega328)  
EEPROM: 512 bytes (ATmega168) or 1 KB (ATmega328)  
Clock Speed: 16 MHz  
Dimension(mm):45.0(L)x18.0(W)x18.7(H)  

## Power
-----

The Arduino Nano can be powered via the Mini-B USB connection, 6-20V unregulated external power supply (pin 30), or 5V regulated external power supply (pin 27). The power source is automatically selected to the highest voltage source.  
The FTDI FT232RL chip on the Nano is only powered if the board is being powered over USB. As a result, when running on external (non-USB) power, the 3.3V output (which is supplied by the FTDI chip) is not available and the RX and TX LEDs will flicker if digital pins 0 or 1 are high.

## Memory
------

The ATmega168 has 16 KB of flash memory for storing code (of which 2 KB is used for the bootloader); the ATmega328 has 32 KB, (also with 2 KB used for the bootloader). The ATmega168 has 1 KB of SRAM and 512 bytes of EEPROM (which can be read and written with the EEPROM library); the ATmega328 has 2 KB of SRAM and 1 KB of EEPROM.

## Resources
---------

- [Schematic](https://wiki.elecrow.com/images/e/ea/Arduino_Nano.pdf)
- [Arduino Nano](https://www.arduino.cc/en/Main/ArduinoBoardNano)