---
title: 2.4 inch TFT Touch Shield for Arduino
---

## Description
-----------

The 2.4 inch TFT Touch Screen Module with micro SD card slot is now available as a SHIELD for Arduino UNO. It has a four wire resistive touch screen, a micro SD card socket, a reset switch and a convenient Arduino Uno shield footprint.  
**Model: [ACS44240D](https://www.elecrow.com/24-inch-tft-touch-shield-for-arduino-p-1383.html)**
![14410128060 1.jpg](https://wiki.elecrow.com/images/thumb/5/52/14410128060_1.jpg/600px-14410128060_1.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png)](https://www.elecrow.com/24-inch-tft-touch-shield-for-arduino-p-1383.html?wiki "Title text")  

## Features
--------

- Colorful, 18-bit 262,000 different shades
- Bright, 4 white LED backlight. On by default but you can connect the transistor to a digital pin for backlight control
- Works with any Arduino 328 or Mega (Leonardo not supported yet)
- Onboard 3.3V 300mA LDO regulator
- 4-wire resistive touchscreen
- Uses digital pins 5-13 and analog 0-3. That means you can use digital pins 2, 3 and analog 4 and 5. Pin 12 is available if not using the micro SD

## Specification
-------------

| **Item** | **Value** |
|---|---|
| Display Color | RGB 65K color |
| Screen Size | 2.4(inch) |
| Type | TFT |
| Driver IC | ILI9341 |
| Resolution | 320\*240(Pixel) |
| Module Interface | 8-bit parallel interface |
| Active Area | 48.96\*36.72(mm) |
| Module PCB Size | 72.20\*52.7(mm) |
| Operating Temperature | -20℃~60℃ |
| Storage Temperature | -30℃~70℃ |
| Operating Voltage | 5V/3.3V |
| Power Consumption | TBD |
| Product Weight(Package containing) | 39(g) |

## Pin Layout
----------

![2.4 TFT LCD pin.png](https://wiki.elecrow.com/images/thumb/2/22/2.4_TFT_LCD_pin.png/400px-2.4_TFT_LCD_pin.png){ loading=lazy }

| **No.** | **Pin Label** | **Pin Description** |
|---|---|---|
| 1 | LCD\_RST | LCD bus reset signal, low level reset |
| 2 | LCD\_CS | LCD bus chip select signal, low level enable |
| 3 | LCD\_RS | LCD bus command / data selection signal, low level:command, high level:data |
| 4 | LCD\_WR | LCD bus write signal |
| 5 | LCD\_RD | LCD bus read signal |
| 6 | GND | Power ground |
| 7 | 5V | 5V power input |
| 8 | 3V3 | 3.3V power input, this pin can be disconnected |
| 9 | LCD\_D0 | LCD 8-bit data Bit0 |
| 10 | LCD\_D1 | LCD 8-bit data Bit1 |
| 11 | LCD\_D2 | LCD 8-bit data Bit2 |
| 12 | LCD\_D3 | LCD8-bit data Bit3 |
| 13 | LCD\_D4 | LCD 8-bit data Bit4 |
| 14 | LCD\_D5 | LCD 8-bit data Bit5 |
| 15 | LCD\_D6 | LCD 8-bit data Bit6 |
| 16 | LCD\_D7 | LCD 8-bit data Bit7 |
| 17 | SD\_SS | SD card SPI bus chip select signal, low level enable |
| 18 | SD\_DI | SD card SPI bus MOSI signal |
| 19 | SD\_DO | SD card SPI bus MISO signal |
| 20 | SD\_SCK | SD card SPI bus clock signal |

## Platforms Supported
-------------------

| **Arduino** |
|:-:|
| ![Arduino.png](https://wiki.elecrow.com/images/6/63/Arduino.png){ loading=lazy } |

## Usage
-----

### **Hardware**

STEP1 Prepare the below stuffs:

|                      **Crowduino Uno**                       |          **2.4 inch TFT Touch Shield for Arduino**           |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| ![Crowduino 2.jpg](https://wiki.elecrow.com/images/thumb/d/d4/Crowduino_2.jpg/500px-Crowduino_2.jpg){ loading=lazy } | ![14410128060 1.jpg](https://wiki.elecrow.com/images/thumb/5/52/14410128060_1.jpg/500px-14410128060_1.jpg){ loading=lazy } |
| [**Get one now**](https://www.elecrow.com/crowduino-unosd-v15-p-840.html) | [**Get one now**](https://www.elecrow.com/24-inch-tft-touch-shield-for-arduino-p-1383.html) |

STEP2 Plug 2.4 inch TFT Touch Shield into Crowduino Uno;
![Plug2.4tft.png](https://wiki.elecrow.com/images/thumb/2/29/Plug2.4tft.png/500px-Plug2.4tft.png){ loading=lazy }   
STEP3 Connect Crowduino Uno to PC via a Mini USB cable.  

### **Software**

STEP 1 Download files[Arduino\_Demo\_code\_ArduinoUNO%26Mega2560.zip](../../files/Arduino-Demo-code-ArduinoUNO%26Mega2560-zip.md)  
STEP 2 Configure controller board&amp;communication port 
On top of the Arduino IDE, click “Tools&gt;Board&gt;” and select “Arduino Uno”from the available options  
![SELECT BOARD.png](https://wiki.elecrow.com/images/thumb/c/c5/SELECT_BOARD.png/700px-SELECT_BOARD.png){ loading=lazy }   
Select the COM port that indicates Arduino Uno. Please note that the actual numbers after the “COM” word will vary from computer to computer, so they could be different from the ones shown in the figure.  
![S 2 2.png](https://wiki.elecrow.com/images/thumb/d/d5/S_2_2.png/700px-S_2_2.png){ loading=lazy } 

STEP 3 Install Library: Unzip the Arduino Demo code\_ArduinoUNO&amp;Mega2560.zip file. Copy the dependent libraries in the Install libraries directory in the package (shown below) to the Libraries directory under the Arduino installation directory  
![20220606180627.png](https://wiki.elecrow.com/images/thumb/1/18/20220606180627.png/400px-20220606180627.png){ loading=lazy }  

STEP 4 Open the sample program in the Example directory of the package to test
![20220606180639.png](https://wiki.elecrow.com/images/thumb/3/38/20220606180639.png/500px-20220606180639.png){ loading=lazy }    

STEP 5 Click the ![Upload.png](../../assets/images/30px-Upload.png){ loading=lazy } to upload the code to the Crowduino board  

STEP6 After the program is downloaded, run it directly and observe the running status. If it can be displayed normally, the program runs successfully  
![20220606180702.png](https://wiki.elecrow.com/images/thumb/8/80/20220606180702.png/300px-20220606180702.png){ loading=lazy }  

## FAQS
----

You can list you question here or contact with techsupport@elecrow.com for technology support.

## Resources
---------

[Arduino_Demo_code_ArduinoUNO&Mega2560.zip](../../files/Arduino-Demo-code-ArduinoUNO%26Mega2560-zip.md)  
[ILI9341_Datasheet.pdf](../../files/ILI9341-Datasheet-pdf.md)  
[Schematic](../../files/24unosch-pdf.md)  