---
title: ESP32 Display 7.0-inch HMI Arduino Tutorial
---

## Overview
-----

This tutorial introduces how to configure the Arduino programming environment and how to set up the board.

The tutorial examples include the lvgl demo example (When you first received it, the demo it demonstrated after you powered it up), and how to connect the esp terminal to some sensors/modules.

## Development environment configuration

- 1.Please go to the official website https://www.arduino.cc/ to download the Arduino IDE development tool and download the corresponding library file, install the tool, click the start icon: open as shown in the figure:

![Image (1).png](https://wiki.elecrow.com/images/3/3f/Image_%281%29.png){ loading=lazy }
![Image (2).png](https://wiki.elecrow.com/images/b/b2/Image_%282%29.png){ loading=lazy }
![Image (3).png](https://wiki.elecrow.com/images/6/6d/Image_%283%29.png){ loading=lazy }
![Esp32rgb 3.png](https://wiki.elecrow.com/images/thumb/d/d8/Esp32rgb_3.png/469px-Esp32rgb_3.png){ loading=lazy }

- 2.Install the libraries.

Download the [libraries](https://www.elecrow.com/download/product/ESP32_Display/7.0inch/Arduino_7inch.zip) provided by Elecrow. Copy them to the library folder in the Arduino installation directory.

If you don't know the path of Arduino library directory, you can open Arduino IDE→Files→Preferences:    
![Arduino-sketchbook-location.jpg](https://wiki.elecrow.com/images/thumb/0/00/Arduino-sketchbook-location.jpg/600px-Arduino-sketchbook-location.jpg){ loading=lazy }

- Add the ESP32 S3 URL as follows：

https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json    
![Esp32rgb 5.png](https://wiki.elecrow.com/images/thumb/7/75/Esp32rgb_5.png/616px-Esp32rgb_5.png){ loading=lazy }

- The tool automatically downloads and updates the corresponding model, check the steps as shown in the figure:

![Image (7).png](https://wiki.elecrow.com/images/thumb/9/93/Image_%287%29.png/490px-Image_%287%29.png){ loading=lazy }
![Image (8).png](https://wiki.elecrow.com/images/thumb/5/5b/Image_%288%29.png/490px-Image_%288%29.png){ loading=lazy }

**NOTE: Please install esp32 version 2.0.3, if you install another version,some modules may go wrong.**

## Board settings:
------

- 1.Under the "Tools" menu, see "Development Board ESP32" and select ESP32S3 Dev MODULE as shown in the figure.

![Image1(1).png](https://wiki.elecrow.com/images/thumb/f/f1/Image1%281%29.png/490px-Image1%281%29.png){ loading=lazy }

- 2.Under the "Tools" menu, "Flash Size" select "4MB"; see "Partition scheme" and select Huge APP(3MB No OTA/1MB SPIFFS)

![Image (10).png](https://wiki.elecrow.com/images/thumb/4/47/Image_%2810%29.png/490px-Image_%2810%29.png){ loading=lazy }

- 3.Under the "Tools" menu, see "PSRAM" and select OPI PSRAM

![Image1(12).png](https://wiki.elecrow.com/images/thumb/3/36/Image1%2812%29.png/490px-Image1%2812%29.png){ loading=lazy }

- warn:

If the CH340G driver is not installed on your PC, please install the CH340G driver first, or switch the SWITCH switch to the USB position and connect it with a USB cable.

## Download process
------

- 1.Connect the motherboard and computer through a USB to type-c data cable;

![L50.png](https://wiki.elecrow.com/images/thumb/8/8e/L50.png/320px-L50.png){ loading=lazy }

- 2.Click on the tool on the arduino software and select the corresponding serial port number;

![Esp32-7inch-arduino-selectport.png](https://wiki.elecrow.com/images/thumb/f/f8/Esp32-7inch-arduino-selectport.png/500px-Esp32-7inch-arduino-selectport.png){ loading=lazy }

- 3.Click "upload" to upload the program to the ESP32 motherboard

![Esp32rgb 17.png](https://wiki.elecrow.com/images/thumb/b/bc/Esp32rgb_17.png/87px-Esp32rgb_17.png){ loading=lazy }

- Until the prompt upload is successful, as shown in the figure:

![Esp32rgb 18.png](https://wiki.elecrow.com/images/thumb/e/e5/Esp32rgb_18.png/564px-Esp32rgb_18.png){ loading=lazy }

## LVGL Widgets Demo
------

**[Click here to watch the tutorial video.](https://www.youtube.com/watch?v=iKJesBu_cg4)**    
![Lvgl-widgets-demo.jpg](https://wiki.elecrow.com/images/thumb/2/2a/Lvgl-widgets-demo.jpg/400px-Lvgl-widgets-demo.jpg){ loading=lazy }

## Connect with Sensors/Modules
------

- **Example 1**, Let the LED to turn on or turn off .

![Image1(3).png](https://wiki.elecrow.com/images/thumb/e/e9/Image1%283%29.png/490px-Image1%283%29.png){ loading=lazy }

- Running result:

![D70.png](https://wiki.elecrow.com/images/thumb/2/2d/D70.png/518px-D70.png){ loading=lazy }

- **Example 2**, Control the output of speaker.

![Image1(4).png](https://wiki.elecrow.com/images/thumb/1/16/Image1%284%29.png/490px-Image1%284%29.png){ loading=lazy }

- Running result:

![F70.png](https://wiki.elecrow.com/images/thumb/7/7c/F70.png/518px-F70.png){ loading=lazy }

- **Example 3**, Initialize Micro TF Card slot.

![Image1(5).png](https://wiki.elecrow.com/images/thumb/0/09/Image1%285%29.png/490px-Image1%285%29.png){ loading=lazy }

- Running result:

![Image1(6).png](https://wiki.elecrow.com/images/thumb/1/13/Image1%286%29.png/490px-Image1%286%29.png){ loading=lazy }

- **Example 4**, initialize the touch signal.

![Image1(7).png](https://wiki.elecrow.com/images/thumb/c/c0/Image1%287%29.png/490px-Image1%287%29.png){ loading=lazy }

- Running result:

![Image1(8).png](https://wiki.elecrow.com/images/thumb/7/77/Image1%288%29.png/490px-Image1%288%29.png){ loading=lazy }

- **Example 5**, initialize the interact communication of Bluetooth.

![Image (28).png](https://wiki.elecrow.com/images/thumb/8/8a/Image_%2828%29.png/490px-Image_%2828%29.png){ loading=lazy }

- Running result:

![B.jpg](https://wiki.elecrow.com/images/thumb/5/56/B.jpg/560px-B.jpg){ loading=lazy }

- **Example 6**, initialize the interact communication of WIFI.

![Image (29).png](https://wiki.elecrow.com/images/thumb/3/39/Image_%2829%29.png/490px-Image_%2829%29.png){ loading=lazy }

- Running result:

![Image (30).png](https://wiki.elecrow.com/images/thumb/d/d1/Image_%2830%29.png/490px-Image_%2830%29.png){ loading=lazy }

## Resource
------

- [Arduino Libraries&LVGL Widgets Demo](https://www.elecrow.com/download/product/ESP32_Display/7.0inch/Arduino_7inch.zip)
- [7.0_Example CODE.zip](https://www.elecrow.com/wiki/images/3/3f/7.0-WIKI程序.zip)
- [Factory_Program_with_helloworld.zip](https://wiki.elecrow.com/images/6/64/LvglWidgets-7.0-helloworld.zip)