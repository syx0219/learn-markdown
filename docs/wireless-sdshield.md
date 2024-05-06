---
title: Wireless SDshield
---

## Description
-----------

The Wireless SD card shield allows an Arduino board to communicate wirelessly using a wireless module, and adds storage to your Arduino project. The XBee Shield is based on the Xbee modules from Digi,but can use any Bee module with the same footprint. It supports SD, SDHC, or MicroSD TF cards. Use the on-board toggle switch to select the SD card type. And when you want plug a sd card on it, you should select the switch to the right direction. About the wireless module, it only uses you two pins from PD0 to PD7. With two jump wire, you can select the wireless module to communicate with USB-to-serial converter or with the microcontroller. About the storage, It just uses the SPI ports of Arduino to transfer data with SD , and you can plug more other shield on it. When using the SD Library to access the card, Pin 10 is CS and cannot be used otherwise. SPI also relies on pins 11, 12, and 13 for communication.

**Model: (Discontinued)**

![Wireless SD Shield.jpg](https://wiki.elecrow.com/images/thumb/f/fb/Wireless_SD_Shield.jpg/600px-Wireless_SD_Shield.jpg){ loading=lazy }

## Features
--------

- Arduino , Seeeduino and Crowduino compatible
- XBee, Bluetooth Bee, RF Bee and other with the same footprint module compatible
- SD card, Micro SD card and SDHC card supportable
- 3.3v and 5v logical voltage compatible
- 2.6~3.6v DC power supply

## Specification
-------------

<table border="1" cellspacing="0" width="100%">
  <tbody>
    <tr>
      <th scope="col" align="center">Item</th>
      <th scope="col" align="center">Min</th>
      <th scope="col" align="center">Typical</th>
      <th scope="col" align="center">Max</th>
      <th scope="col" align="center">Unit</th>
    </tr>
    <tr>
      <th scope="row">Voltage</th>
      <td align="center">2.7</td>
      <td align="center">3.3</td>
      <td align="center">3.6</td>
      <td align="center">V</td>
    </tr>
    <tr>
      <th scope="row">Current</th>
      <td align="center">0.159</td>
      <td align="center">40</td>
      <td align="center">200</td>
      <td align="center">mA</td>
    </tr>
    <tr>
      <th scope="row">Supported Card Type</th>
      <td align="center" colspan="3">SD card(<=2G); Micro SD card(<=2G); SDHC card(<=16G)</td>
      <td align="center">/</td>
    </tr>
    <tr>
      <th scope="row">Supported Card Type</th>
      <td align="center" colspan="3">XBee, Bluetooth Bee, RF Bee, GPS Bee.</td>
      <td align="center">/</td>
    </tr>
    <tr>
      <th scope="row">Dimension</th>
      <td align="center" colspan="3"> </td>
      <td align="center">mm</td>
    </tr>
    <tr>
      <th scope="row">Net Weight</th>
      <td align="center" colspan="3"> </td>
      <td align="center">g</td>
    </tr>
  </tbody>
</table>

## Interface function
------------------

![Wireless Sd Interface.jpg](https://wiki.elecrow.com/images/thumb/f/f8/Wireless_Sd_Interface.jpg/600px-Wireless_Sd_Interface.jpg){ loading=lazy }

PD0~PD7 –Can be used to communicate with USB-to-serial converter or with the microcontroller.  
D10 – Used for CS of SPI  
D11 – Used for MOSI of SP  
ID12 – Used for MISO of SPI  
D13 – Used for SCK of SPI

## Usage
-----

### **How to use SD card**

#### **Hardware Installation**

![Wireless SD Shield.jpg](https://wiki.elecrow.com/images/thumb/f/fb/Wireless_SD_Shield.jpg/400px-Wireless_SD_Shield.jpg){ loading=lazy }

Plug the SD Card Shield onto the Arduino; Insert your SD card into the socket and make sure the card selector pointing to the right way (Standard card or micro).And then Connect the Arduinoto PC using USB cable.   
<font color="red">**Warning:** Don't insert SD card and microSD card into the shield at the same time.</font>

#### **Software**

Format the SD card as FAT16 or FAT32 if it is necessary.  
![Format SD.jpg](https://wiki.elecrow.com/images/thumb/b/b1/Format_SD.jpg/400px-Format_SD.jpg){ loading=lazy }
![Format SD2.jpg](https://wiki.elecrow.com/images/thumb/b/b8/Format_SD2.jpg/200px-Format_SD2.jpg){ loading=lazy }

1. Download the [SdFat for Arduino1.0](http://code.google.com/p/beta-lib/downloads/detail?name=SdFatBeta20120327.zip&can=2&q=) or [SD for Arduino1.0](http://www.elecrow.com/wiki/images/5/5c/SD_for_arduino1.0.zip).
2. Uncompress this package and put it in Arduino-1.0 program: ..\\arduino-1.0\\libraries.
3. Select the corresponding Arduino board, like Arduino UNO or Duemilanove or others, and the COM port you are using.
4. Upload the sketch **Sdinfo**.The follow image is the result from the serial monitor. Of course you can upload other sketches.

![SD card software.jpg](https://wiki.elecrow.com/images/thumb/6/66/SD_card_software.jpg/400px-SD_card_software.jpg){ loading=lazy }

1. If an error occurs, please recheck all the steps, and make sure the SD card is working. If none of that fixes the problem, try replacing the SD card.

With that done, you can take a look at the other library examples for reading, writing. Enjoy!

## How to use XBee shield
----------------------

Please visit our [XBee Shield wiki](./xbee-shield.md)

## FAQ
---

1. SD card can't be initialized .

- Please reformat SD card to FAT/FTA32 .If it still can't work ,suggest to download the [SD Formatter](https://www.sdcard.org/downloads/formatter/) and reformat SD card by this software.

## Resource
--------

- [Wireless SD Shield Schematic in PDF](http://www.elecrow.com/wiki/images/a/ab/Wireless_SD_Shield_v1.02.pdf)
- [SD library for Arduino1.0.](http://www.elecrow.com/wiki/images/5/5c/SD_for_arduino1.0.zip)
- [SdFat for Arduino1.0](http://code.google.com/p/beta-lib/downloads/detail?name=SdFatBeta20120327.zip&can=2&q=)
- [SoftwareSerial library for arduino1.0](http://www.elecrow.com/wiki/images/d/d3/SoftwareSerial.zip)