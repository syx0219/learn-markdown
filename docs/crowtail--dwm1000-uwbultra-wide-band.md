---
title: Crowtail- DWM1000 UWB(Ultra Wide Band)
---

## Description
-----------

Crowtail- DWM1000-UWB module is a fully integrated low-power module. It uses the DW1000 chip radio transceiver module to use UWB (Ultra Wideband) technology, a short-range wireless communication similar to Wi-Fi or Bluetooth, which uses a frequency bandwidth above 1 GHz. It integrates the antenna, all RF circuits, power management, and clock circuits in one module. It can be used in 2-way ranging and TDOA positioning systems to locate assets with 10cm accuracy, and supports data rates up to 6.8 Mbps while communicating with the MCU through a standard SPI serial interface.&lt;br.

It communicates using a much broader frequency spectrum (typically hundreds of Mhz to several GHz) than traditional communication technologies. It can measure the distance between two nodes by calculating the flight time of data in the air \* Lightspeed= data flight distance, so as to perform high-precision positioning, which extremely makes up for the shortcomings of indoor fuzzy positioning of IoT products in the past. Compared with the positioning of RSSI, it achieves fast data transmission at a low power consumption level, and this new technology has advanced development prospects.

**Model: [CRT01163U](https://www.elecrow.com/crowtail-uwb-ultra-wide-band-indoor-positioning-module-dwm1000-ranging-module.html)**  
![20230117181649.png](https://wiki.elecrow.com/images/thumb/c/ca/20230117181649.png/500px-20230117181649.png){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/crowtail-uwb-ultra-wide-band-indoor-positioning-module-dwm1000-ranging-module.html?wiki "Title text")

## Feature
-------

- Integrated DW1000 chip radio transceiver
- Simple integration, no RF design required
- STM32F103 main control chip
- Support high-label density

## Specification
-------------

- Working input voltage: DC 5V-500mA
- Supports IEEE 802.15.4-2011
- 4 channels operating from 3.5 GHz to 6.5 GHz
- Programmable transmit power
- Ranging Accuracy: 10cm
- Working current of the base station: 165mA
- Support two-way ranging and TDOA
- Support serial communication
- Operating temperature: -10°C ~ 65°C
- Dimensions : 60\*19.86mm

## Usage
-----

1\. Prepare 2 Crowtail-DWM1000-UWB, set one as a base station and the other as a tag.

2\. Plug one end of the 4P 2.0mm cable into the Crowtail - DWM1000-UWB serial port, and the other end into the serial port to USB board, as shown in the following figure:

![UWB wiring.png](https://wiki.elecrow.com/images/6/67/UWB_wiring.png){ loading=lazy }  
![UWB wiring 1.png](https://wiki.elecrow.com/images/thumb/d/db/UWB_wiring_1.png/600px-UWB_wiring_1.png){ loading=lazy }  

3\. Connect the serial port board to the computer with USB cable(connect the two Crowtail-DWM1000-UWB to different computers), and open the **[serial port tool](./files/Sscom1-zip.md)** on the computer as shown below:

![SSCOM.png](https://wiki.elecrow.com/images/1/1a/SSCOM.png){ loading=lazy }  
4\. Change language to English. Select the corresponding serial port and open it. Click to select Multi\_ Strings to open the string interface. Select the command and send it:

![SSCOM2.png](https://wiki.elecrow.com/images/1/12/SSCOM2.png){ loading=lazy }
5\. Move the tag, and the distance will change.

![Distance uwb.png](https://wiki.elecrow.com/images/thumb/4/45/Distance_uwb.png/600px-Distance_uwb.png){ loading=lazy }

## Resources
---------

[serial port tool SSCOM](./files/Sscom1-zip.md)  
[Bu01-db\_AT\_Instruction\_Set.pdf](https://wiki.elecrow.com/images/c/cf/Bu01-db_AT_Instruction_Set.pdf)  
[https://docs.ai-thinker.com/en/uwb ](https://docs.ai-thinker.com/en/uwb)  
[UWB\_Indoor\_Positioning.zip](https://wiki.elecrow.com/images/4/4f/UWB_Indoor_Positioning.zip)  