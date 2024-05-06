---
title: 2 inch IPS Module
---

## Description
-----------

This product is a 2.0inch IPS display module,it has a resolution of 320x240.it uses a 4-wire SPI communication method and the inner IC is ST7789.The module contains an LCD display and PCB backboard.  
![2.0-IPS-main-1.jpg](https://wiki.elecrow.com/images/thumb/9/99/2.0-IPS-main-1.jpg/500px-2.0-IPS-main-1.jpg){ loading=lazy }

## Features
--------

- 2.0-inch color screen,support 65K color display,display rich colors
- 320X240 resolution, clear display
- IPS full view panel, super wide visual range
- Using the 4-line-SPI serial bus, it only takes a few IOs to illuminate the display
- Provide a rich STM32, C51 and MSP430 sample program
- Military-grade process standards, long-term stable work
- Provide underlying driver technical support

## Specifications
--------------

| **Item** | **Value** |
|---|---|
| Display Color | RGB 65K color |
| Size | 291(Length)\*190(Width)\*46(Height)mm |
| Screen Size | 2.0(inch) |
| Type | IPS |
| Driver IC | ST7789 |
| Power Supply | DC 12V 2A |
| Resolution | 320\*240 (Pixel) |
| Module Interface | 4-line SPI interface |
| Active Area (AA area) | 30.60x40.80 (mm) |
| Touch Screen | Unsupport |
| Module PCB Size | 36.48x61.12 (mm) |
| Angle of view | all angle |
| Operating Temperature | -10℃~60℃ |
| Storage Temperature | -20℃~70℃ |
| VCC power voltage | 3.3V |
| Rough Weight(Package containing) | 15g |

## Interface
---------

<img loading="lazy" src="https://wiki.elecrow.com/images/thumb/8/8c/22Pin_FPC_interface.jpg/500px-22Pin_FPC_interface.jpg" alt="22Pin FPC interface.jpg" style="zoom:90%;" />
<img loading="lazy" src="https://wiki.elecrow.com/images/7/70/8pinheader.jpg" alt="8pinheader.jpg" style="zoom:90%;vertical-align: top;" />

## Pin Map
-------

| **Number** | **Pin Name** | **Description** |
|---|---|---|
| 1 | GND | LCD Power ground |
| 2 | VCC | LCD power supply(3.3V) |
| 3 | SCL | LCD SPI bus clock signal |
| 4 | SDA | LCD SPI bus write data signal |
| 5 | RES | LCD reset control signal(Low level reset) |
| 6 | DC | LCD register / data selection control signal (Low level: register, high level: data) |
| 7 | CS | LCD chip select control signal (low level enable) |
| 8 | BLK | LCD backlight control signal (high level lighting, if you do not need control, please connect 3.3V) |

## Hardware Configuration
----------------------

The LCD module hardware circuit comprises two parts: an LCD display control circuit and a backlight control circuit.  
The LCD display control circuit is used to control the pins of the LCD, including control pins and data transfer pins.  
if the backlight is not required to be be on and off, can be directly connected to the 3.3V if the backlight is not required to be be on and off, can be directly connected to the 3.3V power supply.    
![Backlight control circuit.jpg](https://wiki.elecrow.com/images/thumb/c/c9/Backlight_control_circuit.jpg/700px-Backlight_control_circuit.jpg){ loading=lazy }

## Usage
-----

### Hardware Connection

| **Crowduino Uno** | **2 inch IPS Module** |
|:-:|:-:|
| GND | GND |
| 5V | VCC |
| 13 | SCL |
| 11 | SDA |
| A4 | RES |
| A3 | DC |
| A2 | CS |
| A0 | BLK |

![2INCHDISPLAY.jpg](https://wiki.elecrow.com/images/thumb/b/b1/2INCHDISPLAY.jpg/600px-2INCHDISPLAY.jpg){ loading=lazy }

### Software

STEP1 Download [2.0inch_SPI_Arduino_Demo.zip](https://www.elecrow.com/wiki/index.php?title=File:2.0inch_SPI_Arduino_Demo.zip)  
STEP2 Configure controller board&communication port  
On top of the Arduino IDE, click “Tools>Board>” and select “Arduino Uno” from the available options  
![SELECT BOARD.png](https://wiki.elecrow.com/images/thumb/c/c5/SELECT_BOARD.png/700px-SELECT_BOARD.png){ loading=lazy }  
Select the COM port that indicates Arduino Uno. Please note that the actual numbers after the “COM” word will vary from computer to computer, so they could be different from the ones shown in the figure.  
![S 2 2.png](https://wiki.elecrow.com/images/thumb/d/d5/S_2_2.png/700px-S_2_2.png){ loading=lazy }

STEP3 Install libraries :Unzip Install libraries.zip and copy folder "LCDWIKI\_GUI" and "LCDWIKI\_SPI" to the libraries directory under the Arduino installation directory  
![2inchinstalllibrary.jpg](https://wiki.elecrow.com/images/5/5f/2inchinstalllibrary.jpg){ loading=lazy }
STEP4 Load the program to Arduino IDE  
![2inchspiexamples.jpg](https://wiki.elecrow.com/images/7/79/2inchspiexamples.jpg){ loading=lazy } 
STEP5 Click the ![Upload.png](./assets/images/30px-Upload.png){ loading=lazy } to upload the code to the Crowduino board

STEP6 After the program is downloaded, run it directly and observe the running status. If it can be displayed normally, the program runs successfully.  
![2.0inchdisplay2.jpg](https://wiki.elecrow.com/images/thumb/7/78/2.0inchdisplay2.jpg/600px-2.0inchdisplay2.jpg){ loading=lazy }
![IMG 6337.JPG](https://wiki.elecrow.com/images/thumb/b/bf/IMG_6337.JPG/600px-IMG_6337.JPG){ loading=lazy }

## FAQS
----

You can list you question here or contact with techsupport@elecrow.com for technology support.

## Resources
---------

[ST7789VW\_datasheet.pdf ](./files/ST7789VW-datasheet-pdf.md)  
[2.0inch\_SPI\_Arduino\_Demo.zip ](./files/2.0inch-SPI-Arduino-Demo-zip.md)