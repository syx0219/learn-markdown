---
title: ESP32 Display 2.8-inch HMI MicroPython Tutorial
---

This tutorial will demonstrate how to program the ESP Terminal SPI via MicroPython.

The project of this tutorial is a smart light. When the ambient light intensity is lower than 60%, the LED will light up, otherwise, the LED will go out.

## Hardware Preparation
-----

| **ESP32 Display 2.8-inch**                                   | **Crowtail-Light Sensor**                                    | **Crowtail-LED**                                             | **USB-A(or USB-C) to USB-C cable**                           | **2\* 4-Pin HY2.0 Cables**                                   |
| :------------------------------------------------------------: | :------------------------------------------------------------: | :------------------------------------------------------------: | :------------------------------------------------------------: | :------------------------------------------------------------: |
| ![28-ecp32dispaly-mainpic.png](https://wiki.elecrow.com/images/thumb/8/8c/28-ecp32dispaly-mainpic.png/300px-28-ecp32dispaly-mainpic.png){ loading=lazy } | ![Crowtail- Digital Light Sensor1.JPG](https://wiki.elecrow.com/images/thumb/e/e2/Crowtail-_Digital_Light_Sensor1.JPG/200px-Crowtail-_Digital_Light_Sensor1.JPG){ loading=lazy } | ![Crowtail-LED1.JPG](https://wiki.elecrow.com/images/thumb/4/4f/Crowtail-LED1.JPG/200px-Crowtail-LED1.JPG){ loading=lazy } | ![USB-C-CABLE.jpg](https://wiki.elecrow.com/images/thumb/3/3d/USB-C-CABLE.jpg/200px-USB-C-CABLE.jpg){ loading=lazy } | ![CROWTAIL-CABLE.jpg](https://wiki.elecrow.com/images/thumb/3/35/CROWTAIL-CABLE.jpg/200px-CROWTAIL-CABLE.jpg){ loading=lazy } |
| [**Get one now**](https://www.elecrow.com/esp32-display-2-4-inch-intelligent-spi-tft-lcd-touch-screen-hmi-display.html) | [**Get one now**](http://www.elecrow.com/crowtail-digital-light-sensor-p-1488.html) | [**Get one now**](http://www.elecrow.com/crowtail-led-p-1224.html) | [**Get one now**](https://www.elecrow.com/usb-type-a-to-type-c-fast-charge-cable-1-meter.html) | [**Get one now**](https://www.elecrow.com/4-pin-crowtail-cable5-pcs-p-1561.html) |

## Software Preparation
-----

### **Download software**

Go to https://thonny.org/ and download the corresponding software version (take the Windows version as an example).    
![Download-thonny.jpg](https://wiki.elecrow.com/images/thumb/0/00/Download-thonny.jpg/800px-Download-thonny.jpg){ loading=lazy }

Double-click the downloaded exe file to install the software. (Go to the next step and install directly)

### **Download firmware**

Open the Thonny software and click Tools→Options   
![THONNY-OPTIONS.jpg](https://wiki.elecrow.com/images/thumb/4/4c/THONNY-OPTIONS.jpg/500px-THONNY-OPTIONS.jpg){ loading=lazy }

Click "Interpreter" and select "MicroPython(ESP32)"   
![Micropython-esp32.jpg](https://wiki.elecrow.com/images/thumb/d/d9/Micropython-esp32.jpg/400px-Micropython-esp32.jpg){ loading=lazy }

Select the serial port number (you need to press the hardware BOOT key and then connect to the computer, if no com number is displayed, check whether the serial port driver is installed)   
![Micropython-tutorial-SPI-port.png](https://wiki.elecrow.com/images/2/2f/Micropython-tutorial-SPI-port.png){ loading=lazy }

Click "Install or update MicroPython(esptool)" to download the firmware  
![Micropython-tutorial-SPI-firmware.png](https://wiki.elecrow.com/images/1/14/Micropython-tutorial-SPI-firmware.png){ loading=lazy }

Choose to download the firmware from local and click Install (select the firmware corresponding to the screen)   
![Micropython-tutorial-SPI-esptool.png](https://wiki.elecrow.com/images/1/1c/Micropython-tutorial-SPI-esptool.png){ loading=lazy }

![Micropython-tutorial-SPI-install.png](https://wiki.elecrow.com/images/a/a1/Micropython-tutorial-SPI-install.png){ loading=lazy }

Wait for successful installation   
![Micropython-tutorial-SP-firmware downloadingI.png](https://wiki.elecrow.com/images/f/f7/Micropython-tutorial-SP-firmware_downloadingI.png){ loading=lazy }

## Run program
--------

Click the reset button on the screen or reinsert the data cable to open the routine program.   
![Micropython-tutorial-SP-2I.png](https://wiki.elecrow.com/images/4/40/Micropython-tutorial-SP-2I.png){ loading=lazy }

Run the program   
![Micropython-tutorial-SPI-run.png](https://wiki.elecrow.com/images/a/a4/Micropython-tutorial-SPI-run.png){loading=lazy}

When the light intensity exceeds 60%, the light goes out. Light is on when the light intensity is less than 60%   
![Micropython-tutorial-SPI-result.png](https://wiki.elecrow.com/images/f/f9/Micropython-tutorial-SPI-result.png){ loading=lazy }
![Micropython-tutorial-SPI-result1.png](https://wiki.elecrow.com/images/d/dd/Micropython-tutorial-SPI-result1.png){ loading=lazy }

## Resources
------

- [2.8Micropython.zip](https://www.elecrow.com/download/product/ESP32_Display/2.8inch/2.8Micropython.zip)