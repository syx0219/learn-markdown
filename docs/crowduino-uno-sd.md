---
title: Crowduino Uno-SD
---

## Description
-----------

The Crowduino Uno-SD mainboard is a microcontroller board that completely compatible with the Arduino UNO. It is based on the Atmega328P, which is widely also used in the Arduino Uno and other Arduino compatible boards. Compared to the previous Crowduino with Atmega328, the Uno SD mainboard uses the Atmega16U2, instead of the FTDI232 for the USB2UART conversation, which makes the program downloading much faster. Besides, there is a SD card slot on the Uno-SD board, making this board more convenient for applications such as data logging/ environment monitoring.

Same as the crowduino with Atmega168, the Uno-SD board also has 14 digital input/output pins (of which 6 can be used as PWM outputs), 6 analog inputs, a 16 MHz ceramic resonator, a USB connection, a power jack, an ICSP header, a reset button, and of course a Mini USB cable, simply connect it to a computer with a USB cable or power it with a AC-to-DC adapter or battery to get started.

**Model: [MCA02328UNO](https://www.elecrow.com/crowduino-unosd-v15-p-840.html)**

![Crowduino Uno-SD1.JPG](https://wiki.elecrow.com/images/thumb/9/9d/Crowduino_Uno-SD1.JPG/600px-Crowduino_Uno-SD1.JPG){loading=lazy}

## Summary
-------

| **Microcontroller** | **ATmega328** |
|:-:|:-:|
| Operating Voltage | 3.3V or 5v |
| Input Voltage (recommended) | 7-12V |
| Input Voltage (limits) | 6-20V |
| Digital I/O Pins | 14 (of which 6PINs provide PWM output) |
| Analog Input Pins | 6 |
| DC Current per I/O Pin | 40mA |
| DC Current for 3.3V Pin | 50 mA |
| Flash Memory | 32 KB (ATmega328) of which 0.5 KB used by bootloader |
| SRAM | 2 KB (ATmega328) |
| EEPROM | 1 KB (ATmega328) |
| Clock Speed | 16 MHz |

## Features
--------

- On-board SD card slot;
- Flat DC Jack.
- Inherits all of Arduino Uno's features.
- Compatible to Uno's pin layout, screw hole and dimensions.
- Evolved with SMD components.
- Dimensions(mm):70.0(L)x55.0(W)x11.8(H)

## Interface Function
------------------

![Crowduino Uno-SD interface.jpg](https://wiki.elecrow.com/images/8/83/Crowduino_Uno-SD_interface.jpg){loading=lazy}

## Usage
-----

The Crowduino Uno-SD board has almost the same usage with that of Crowduino with Atmega328, except the follows:

### **Program Downloading**

With the Atmega16U2, downloading program to the Uno-SD board would be much faster than that of Crowudino with Atmega328, but notice that you should select the **Arduino Uno** when selecting the board.
![Uno-SD select Uno.jpg](https://wiki.elecrow.com/images/b/b9/Uno-SD_select_Uno.jpg){loading=lazy}

### **Read&amp;Write SD Card**

There is a SD card slot on the Uno-SD card board, with which you can easily use SD card to record and thus to read data on the SD card.The SD card uses the SPI interface (D10/D11/D12) plus a CS Pin (D3 or D4) to cominicate with the main microcontroller Atmega328. **First, Select the CS Pin you want to use with jumper.** To make your project more flexible, you can select either the D3 or D4 pin as your CS pin for SD card. The default is D4. If your D4 have been applied for other modules, you can select the D3, but notice to modify related files in your program, which we will discuss later.  
![CS selector.jpg](https://wiki.elecrow.com/images/thumb/a/a0/CS_selector.jpg/500px-CS_selector.jpg){loading=lazy}  
And then download the related library [here](./wireless-sdshield.md#software) to start using the SD card. Notice if your select the D3 as your SD card CS pin, you should modify a littele when initlize the SD card in your program:

```
if (!SD.begin(4)) {     // modify to SD.begin(3) when using D3 as CS pin
   Serial.println("initialization failed!");
   return;
 }
 Serial.println("initialization done.");
```

## Note
----

For version Crowduino Uno-SD V1.4, There is a little difference with Arduino UNO that the LED contact with the PB5/D13. PB5/D13 contact the LED with Reverse follower. Please have a look at the following picture.   
![PB5-D13.png](https://wiki.elecrow.com/images/7/70/PB5-D13.png){loading=lazy}  
hat will make the High and LOW values is inverted when control the LED with D13.

## Resources
---------

- [Crowduino Uno-SD Schematic in PDF ](https://wiki.elecrow.com/images/0/06/Crowduino_Uno-SD.pdf)

## Support
-------

If you have any problem about how to use it, you can connect to us at [the bottom-right of bazzer](http://www.elecrow.com/) or contact to **techsupport@elecrow.com** to get technology support.