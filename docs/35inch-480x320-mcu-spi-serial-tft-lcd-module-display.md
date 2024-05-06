---
title: 3.5inch 480x320 MCU SPI Serial TFT LCD Module Display
---

## Description
-----------

It is the cutest, little display for the Raspberry Pi. It features a 3.5" display with 480x320, support 65K color display.

**Model:[DIS03501R](https://www.elecrow.com/3-5inch-480x320-mcu-spi-serial-tft-lcd-module-display.html)**

[![Alt text](./assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/3-5inch-480x320-mcu-spi-serial-tft-lcd-module-display.html?wiki "Title text")

## Features
--------

- 3.5-inch color screen,support 65K color display,display rich colors
- 480X320 resolution, optional touch function
- Using the SPI serial bus, it only takes a few IOs to illuminate the display
- Easy to expand the experiment with SD card slot
- Provide a rich sample program
- Military-grade process standards, long-term stable work
- Provide underlying driver technical support

## Specifications
--------------

- Display Color: RGB 65K color
- Screen Size: 3.5(inch)
- Type: TFT
- Driver IC: ILI9488
- Resolution: 480\*320 (Pixel)
- Module Interface: 4-wire SPI interface
- Active Area (AA area): 48.96x73.44(mm)
- Module PCB Size: 56.34x98(mm)
- Operating Temperature: -20℃~60℃
- Storage Temperature: -30℃~70℃
- VCC power voltage: 3.3V~5V
- Logic IO port voltage: 3.3V(TTL)
- Power Consumption: TBD
- Rough Weight: 45 (g)

## Interface Definition
--------------------

![3.5inch SPI Module ILI9488 1.png](https://wiki.elecrow.com/images/b/b9/3.5inch_SPI_Module_ILI9488_1.png){ loading=lazy }
[650px]("File:3.5inch SPI Module ILI9488 9.png")

## How to use with Arduino
-----------------------

### **1: Run Arduino Demo in SPI model**

When we directly connected the SPI display module without the on-board level conversion module to the Arduino, we found that it could not run at all. This is because the SPI module's pin can only input a 3.3V high level, while the Arduino output has a high level of 5V. To run successfully, there are two Method: short circuit method and external level conversion module method. The short-circuit method has the advantages of simple operation, short wiring, and no need for external devices. The disadvantage is that the module generates a large amount of heat during operation.Will affect the life of the module. The external level conversion module method is a normal operation, and the advantage is that the module generatesless heat and runs stably during operation, and the disadvantage is that the operation is slightly complicated. (An external level shifting module is required) to increase the cost (additional level conversion module is required). In summary, it is recommended to use the external level shifting module method.

Step 1: Short-Circuit Method
The short-circuit method is to short the J1 component position (shown below) with solder on the back of the module.After shorting, the runtime module VCC The pin must be connected to a 5V power supply (not connected to 3.3V).   
![3.5inch SPI Module ILI9488 2.png](https://wiki.elecrow.com/images/thumb/1/19/3.5inch_SPI_Module_ILI9488_2.png/500px-3.5inch_SPI_Module_ILI9488_2.png){ loading=lazy }


Step 2: External Level Conversion Module Method  
The so-called external level conversion module method is to connect the Arduino and the display module through an external level conversion module, so that The 5V high level of the Arduino output is converted to 3.3V by the level conversion module and then input to the display module. As shown below:   
![3.5inch SPI Module ILI9488 3.png](https://wiki.elecrow.com/images/thumb/8/8d/3.5inch_SPI_Module_ILI9488_3.png/500px-3.5inch_SPI_Module_ILI9488_3.png){ loading=lazy }

### **2: First download the sample code. Then copy the libraries that the examples depend on to the libraries folder of the Arduino project file directory.**

![3.5inch SPI Module ILI9488 4.png](https://wiki.elecrow.com/images/thumb/f/ff/3.5inch_SPI_Module_ILI9488_4.png/500px-3.5inch_SPI_Module_ILI9488_4.png){ loading=lazy }

### **3: Select the example you want to test, open it and click Tools button to select the board model and port number, as shown below:**

![3.5inch SPI Module ILI9488 5.png](https://wiki.elecrow.com/images/thumb/6/65/3.5inch_SPI_Module_ILI9488_5.png/500px-3.5inch_SPI_Module_ILI9488_5.png){ loading=lazy }

### **4: Connect the pins with the Arduino pins with Dupont wires according to the pin definitions in the program. (The example is a short-circuit method)**

![3.5inch SPI Module ILI9488 6.png](https://wiki.elecrow.com/images/thumb/8/85/3.5inch_SPI_Module_ILI9488_6.png/500px-3.5inch_SPI_Module_ILI9488_6.png){ loading=lazy }

### **5: Click the Upload button to compile and download. When “Done Uploading” is displayed, the program had been successfully downloaded to the development board, as shown below:**

![3.5inch SPI Module ILI9488 7.png](https://wiki.elecrow.com/images/thumb/c/c1/3.5inch_SPI_Module_ILI9488_7.png/500px-3.5inch_SPI_Module_ILI9488_7.png){ loading=lazy }

### **6: If the module can display normally, the program runs successfully:**

![3.5inch SPI Module ILI9488 8.png](https://wiki.elecrow.com/images/thumb/4/46/3.5inch_SPI_Module_ILI9488_8.png/500px-3.5inch_SPI_Module_ILI9488_8.png){ loading=lazy }