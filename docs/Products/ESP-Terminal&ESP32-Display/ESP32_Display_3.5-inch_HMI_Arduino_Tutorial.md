---
title: ESP32 Display 3.5-inch HMI Arduino Tutorial
---

## Overview
-----

This tutorial introduces how to configure the Arduino programming environment and how to set up the board.

The tutorial examples include the lvgl demo example (When you first received it, the demo it demonstrated after you powered it up), and how to connect the esp terminal to some sensors/modules.

## Development environment configuration
-----

- 1.Please go to the official website https://www.arduino.cc/ to download the Arduino IDE development tool and download the corresponding library file, install the tool, click the start icon: open as shown in the figure:

![Image (1).png](https://wiki.elecrow.com/images/3/3f/Image_%281%29.png){ loading=lazy }
![Image (2).png](https://wiki.elecrow.com/images/b/b2/Image_%282%29.png){ loading=lazy }
![Image (3).png](https://wiki.elecrow.com/images/6/6d/Image_%283%29.png){ loading=lazy }
![Esp32rgb 3.png](https://wiki.elecrow.com/images/thumb/d/d8/Esp32rgb_3.png/469px-Esp32rgb_3.png){ loading=lazy }

- 2.Download the [libraries](https://www.elecrow.com/download/product/ESP32_Display/3.5inch/Arduino_35.zip) provided by Elecrow. Copy them to the library folder in the Arduino installation directory.

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
-----

- 1.Under the "Tools" menu, see "Development Board ESP32" and select ESP32S3-WROOM-DA MODULE as shown in the figure.

![Image (9).png](https://wiki.elecrow.com/images/thumb/5/5b/Image_%289%29.png/490px-Image_%289%29.png){ loading=lazy }

- 2.Under the "Tools" menu, see "Partition scheme" and select Huge APP(3MB No OTA/1MB SPIFFS)

![Image (10).png](https://wiki.elecrow.com/images/thumb/4/47/Image_%2810%29.png/490px-Image_%2810%29.png){ loading=lazy }

- warn:

If the CH340G driver is not installed on your PC, please install the CH340G driver first, or switch the SWITCH switch to the USB position and connect it with a USB cable.

## Download process
-----

- 1.Connect the motherboard and computer through a USB to type-c data cable;

![L35.jpg](https://wiki.elecrow.com/images/thumb/b/bb/L35.jpg/320px-L35.jpg){ loading=lazy }

- 2.Click on the tool on the arduino software and select the corresponding serial port number;

![2.4inch-board setting.jpg](https://wiki.elecrow.com/images/1/10/2.4inch-board_setting.jpg){ loading=lazy }

- 3.Click "upload" to upload the program to the ESP32 motherboard

![Esp32rgb 17.png](https://wiki.elecrow.com/images/thumb/b/bc/Esp32rgb_17.png/87px-Esp32rgb_17.png){ loading=lazy }

- Until the prompt upload is successful, as shown in the figure:

![Esp32rgb 18.png](https://wiki.elecrow.com/images/thumb/e/e5/Esp32rgb_18.png/564px-Esp32rgb_18.png){ loading=lazy }

## LVGL Widgets Demo
-----

**[Click here to watch the tutorial video.](https://www.youtube.com/watch?v=EARkhr3ABEY&t=1s)**    
![Lvgl-widgets-demo.jpg](https://wiki.elecrow.com/images/thumb/2/2a/Lvgl-widgets-demo.jpg/400px-Lvgl-widgets-demo.jpg){ loading=lazy }

## Connect with Sensors/Modules
-------

### **Example 1 Let the LED to turn on or turn off .**

- Plug the LED module to GPIO-D Port.
- Upload the [A-LED_Blink](https://wiki.elecrow.com/images/3/3a/A-LED_Blink.zip) to ESP display.

![Image (21).png](https://wiki.elecrow.com/images/thumb/f/f2/Image_%2821%29.png/490px-Image_%2821%29.png){ loading=lazy }

- Running result:

![D24.jpg](https://wiki.elecrow.com/images/thumb/2/2b/D24.jpg/518px-D24.jpg){ loading=lazy }

### **Example 2 Control the display of an external OLED screen through I2C.**

- Plug the OLED screen to the I2C port.
- Please check if you have installed the library [U8g2](https://wiki.elecrow.com/images/d/d2/U8g2.zip)
- Upload the code [Download A-IIC-Screen](https://wiki.elecrow.com/images/d/df/A-IIC-Screen.zip) to the ESP display.

![Image (22).png](https://wiki.elecrow.com/images/thumb/8/84/Image_%2822%29.png/490px-Image_%2822%29.png){ loading=lazy }

- Running result:

![I24.jpg](https://wiki.elecrow.com/images/thumb/2/28/I24.jpg/518px-I24.jpg){ loading=lazy }

### **Example 3 Control the output of speaker.**

- Plug the speaker into SPK port.
- Please check if you have installed the library [XT_DAC_Audio](https://www.elecrow.com/wiki/index.php?title=File:XT_DAC_Audio.zip)
- Upload the code [SPEAK](https://wiki.elecrow.com/images/e/ef/SPEAK.zip) to the ESP display

![Image (23).png](https://wiki.elecrow.com/images/thumb/8/8a/Image_%2823%29.png/490px-Image_%2823%29.png){ loading=lazy }

- Running result:

![F24.jpg](https://wiki.elecrow.com/images/thumb/c/c4/F24.jpg/518px-F24.jpg){ loading=lazy }

### **Example 4 Initialize Micro TF Card slot.**

- Please check if you have installed the library [SD](https://wiki.elecrow.com/images/8/88/SD.zip)
- Upload the code [A-3.5-TF](https://wiki.elecrow.com/images/2/27/A-3.5-TF.zip) to the ESP display

![Image (24).png](https://wiki.elecrow.com/images/thumb/d/d3/Image_%2824%29.png/490px-Image_%2824%29.png){ loading=lazy }

- Running result:

![Image (25).png](https://wiki.elecrow.com/images/thumb/a/ad/Image_%2825%29.png/490px-Image_%2825%29.png){ loading=lazy }

### **Example 5 initialize the touch signal.**

- Please check if you have install the library [TFT_eSPI](https://wiki.elecrow.com/images/4/46/TFT_eSPI.zip)
- Upload the code [A-3.5-TOUCH](https://wiki.elecrow.com/images/e/e3/A-3.5-TOUCH.zip) to ESP display

![Image (26).png](https://wiki.elecrow.com/images/thumb/d/d4/Image_%2826%29.png/490px-Image_%2826%29.png){ loading=lazy }

- Running result:

![Image (32).png](https://wiki.elecrow.com/images/thumb/8/84/Image_%2832%29.png/490px-Image_%2832%29.png){ loading=lazy }

### **Example 6 initialize the interact communication of UART .**

- Upload the code [A-3.5-UART](https://wiki.elecrow.com/images/8/8e/A-3.5-UART.zip) to the ESP display

![Image (27).png](https://wiki.elecrow.com/images/thumb/1/18/Image_%2827%29.png/490px-Image_%2827%29.png){ loading=lazy }

### **Example 7 initialize the interact communication of Bluetooth.**

- Please check if you have installed the library [BLE](https://wiki.elecrow.com/images/e/e6/BLE.zip)
- Upload the code [A-BLE](https://wiki.elecrow.com/images/5/59/A-BLE.zip) to the ESP display.

![Image (28).png](https://wiki.elecrow.com/images/thumb/8/8a/Image_%2828%29.png/490px-Image_%2828%29.png){ loading=lazy }

- Running result:

![B.jpg](https://wiki.elecrow.com/images/thumb/5/56/B.jpg/560px-B.jpg){ loading=lazy }

### **Example 8 initialize the interact communication of WIFI.**

- Please check if you have installed the bilrary [WiFi](https://wiki.elecrow.com/images/d/d7/WiFi.zip)
- Upload the code [A-WIFI](https://wiki.elecrow.com/images/a/af/A-WIFI.zip) to the ESP display.

![Image (29).png](https://wiki.elecrow.com/images/thumb/3/39/Image_%2829%29.png/490px-Image_%2829%29.png){ loading=lazy }

- Running result:

![Image (30).png](https://wiki.elecrow.com/images/thumb/d/d1/Image_%2830%29.png/490px-Image_%2830%29.png){ loading=lazy }

## Resources
-----

- [Arduino Libraries&LVGL Demo](https://www.elecrow.com/download/product/ESP32_Display/3.5inch/Arduino_35.zip)