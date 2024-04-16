---
title: 3.5 Inch TFT Color Screen Module 320 X 480 Support Arduino UNO Mega2560
---

## Description
-----------

This is a 3.5-inch 320 \* 480 resolution TFT color screen. It supports working boards such as Arduino uno and Arduino mega2560 and Arduino due. Also supports STM32, 51 and other conventional microcontrollers.  
When using this screen, you do not need any wiring operations, just plug onto your arduino board, we will provide the corresponding Arduino library files, the development code is open source, you can use arduino and this screen to build some applications.The backlight always on, can not control the backlight, backlight is connect to 3.3V.  
**Model: [ARS36125D](https://www.elecrow.com/3-5-inch-tft-color-screen-module-320-x-480-support-arduino-uno-mega2560.html)**  
![3.5 inch tft color screen module 320 x 480 support arduino uno mega2560 1.jpg](https://wiki.elecrow.com/images/thumb/a/a2/3.5_inch_tft_color_screen_module_320_x_480_support_arduino_uno_mega2560_1.jpg/600px-3.5_inch_tft_color_screen_module_320_x_480_support_arduino_uno_mega2560_1.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/3-5-inch-tft-color-screen-module-320-x-480-support-arduino-uno-mega2560.html?wiki "Title text")

## Features
--------

- Supports development boards such as Arduino UNO and Mega2560 for plug-in use without wiring
- 480X320 resolution, clear display, support for touch function
- Support 16-bit RGB 65K color display, display rich colors
- 8-bit parallel bus, faster than serial SPI refresh
- On-board 5V/3.3V level shifting IC, compatible with 5V/3.3V operating voltage
- Easy to expand the experiment with SD card slot
- Provides an Arduino library with a rich sample program
- Military-grade process standards, long-term stable work
- Provide underlying driver technical support

## Specification
-------------

| **Item** | **Value** |
|---|---|
| Display Color | RGB 65K color |
| Screen Size | 3.5(inch) |
| Type | TFT |
| Driver IC | ILI9341 |
| Resolution | 480\*320(Pixel) |
| Module Interface | 8-bit parallel interface |
| Active Area | 73.44\*48.96(mm) |
| Module PCB Size | 85.49\*55.63(mm) |
| Operating Temperature | -20℃~60℃ |
| Storage Temperature | -30℃~70℃ |
| Operating Voltage | 5V/3.3V |
| Power Consumption | TBD |
| Product Weight(Package containing) | 44g |

## Pin Layout
----------

![371px-MAR3502-20.jpg](https://wiki.elecrow.com/images/a/a7/371px-MAR3502-20.jpg){ loading=lazy }

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

| **Crowduino Uno**                                            | **3.5 Inch TFT Color Screen Module**                         |
| :------------------------------------------------------------: | :------------------------------------------------------------: |
| ![Crowduino 2.jpg](https://wiki.elecrow.com/images/thumb/d/d4/Crowduino_2.jpg/500px-Crowduino_2.jpg){ loading=lazy } | ![3.5 inch tft color screen module 320 x 480 support arduino uno mega2560 1.jpg](https://wiki.elecrow.com/images/thumb/a/a2/3.5_inch_tft_color_screen_module_320_x_480_support_arduino_uno_mega2560_1.jpg/500px-3.5_inch_tft_color_screen_module_320_x_480_support_arduino_uno_mega2560_1.jpg){ loading=lazy } |
| [**Get one now**](https://www.elecrow.com/crowduino-unosd-v15-p-840.html) | [**Get one now**](https://www.elecrow.com/3-5-inch-tft-color-screen-module-320-x-480-support-arduino-uno-mega2560.html) |

STEP2 Plug 2.4 inch TFT Touch Shield into Crowduino Uno;  
![400px MAR3501-002.jpg](https://wiki.elecrow.com/images/2/28/400px_MAR3501-002.jpg){ loading=lazy }  

STEP3 Connect Crowduino Uno to PC via a Mini USB cable.

### **Software**

STEP 1 Download files[Arduino_Demo_code_ArduinoUNO&26Mega2560.zip](../../files/Arduino-Demo-code-ArduinoUNO%26Mega2560-zip.md)  

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
![3.5inch tft color screen.png](https://wiki.elecrow.com/images/thumb/3/33/3.5inch_tft_color_screen.png/300px-3.5inch_tft_color_screen.png){ loading=lazy }  

## FAQS
----

You can list you question here or contact with techsupport@elecrow.com for technology support.

## Resources
---------

[Arduino\_Demo\_code\_ArduinoUNO&amp;26Mega2560.zip](../../files/Arduino-Demo-code-ArduinoUNO%26Mega2560-zip.md)  
[ILI9341\_Datasheet.pdf](../../files/ILI9341-Datasheet-pdf.md)