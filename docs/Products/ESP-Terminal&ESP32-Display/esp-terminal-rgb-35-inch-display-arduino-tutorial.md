---
title: ESP Terminal RGB 3.5-inch Display Arduino Tutorial
---

## Overall
------

This tutorial introduces how to configure the Arduino programming environment and how to set up the board.

The tutorial examples include the lvgl demo example (When you first received it, the demo it demonstrated after you powered it up), and how to connect the esp terminal to some sensors/modules.

## Development environment configuration
-------

- 1.Please go to the official website https://www.arduino.cc/ to download the Arduino IDE development tool and download the corresponding [libraries](https://drive.google.com/drive/folders/1FCtqplozHlWF6Fn1isYb3hYmU6ssp-AA?usp=sharing), install the tool, click the start icon: open as shown in the figure:

![Esp32rgb 3.png](https://wiki.elecrow.com/images/thumb/d/d8/Esp32rgb_3.png/469px-Esp32rgb_3.png){ loading=lazy }

- 2.Download the [libraries](https://www.elecrow.com/download/product/DLC35010R/Arduino_RGB.zip) provided by Elecrow. Copy them to the library folder in the Arduino installation directory.

If you don't know the path of Arduino library directory, you can open Arduino IDE→Files→Preferences:
![Arduino-sketchbook-location.jpg](https://wiki.elecrow.com/images/thumb/0/00/Arduino-sketchbook-location.jpg/600px-Arduino-sketchbook-location.jpg){ loading=lazy }



- Add the ESP32 S3 URL as follows：

https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json  
![Esp32rgb 5.png](https://wiki.elecrow.com/images/thumb/7/75/Esp32rgb_5.png/616px-Esp32rgb_5.png){ loading=lazy }

- The tool automatically downloads and updates the corresponding model, check the steps as shown in the figure:

![Esp32rgb 6.png](https://wiki.elecrow.com/images/thumb/0/06/Esp32rgb_6.png/614px-Esp32rgb_6.png){ loading=lazy }
![Esp32rgb 7.png](https://wiki.elecrow.com/images/thumb/0/0b/Esp32rgb_7.png/609px-Esp32rgb_7.png){ loading=lazy }

## Board settings
------

- 1.Under the "Tools" menu, see "Development Board ESP32" and select ESP32S3 DEV MODULE as shown in the figure.

![Esp32rgb 8.png](https://wiki.elecrow.com/images/thumb/2/21/Esp32rgb_8.png/613px-Esp32rgb_8.png){ loading=lazy }

- 2.Under the "Tools" menu, see "Flash Mode" and select QIO 80MHz

![Esp32rgb 9.png](https://wiki.elecrow.com/images/thumb/4/4d/Esp32rgb_9.png/560px-Esp32rgb_9.png){ loading=lazy }

- 3.Under the "Tools" menu, see "Flash Size" and select 16MB (128Mb)

![Esp32rgb 10.png](https://wiki.elecrow.com/images/thumb/0/0d/Esp32rgb_10.png/562px-Esp32rgb_10.png){ loading=lazy }

- 4.Under the "Tools" menu, see "PSRAM OPI PSRAM" and select OPI PSRAM

![Esp32rgb 11.png](https://wiki.elecrow.com/images/thumb/f/fa/Esp32rgb_11.png/586px-Esp32rgb_11.png){ loading=lazy }

- warn:

If the CH340G driver is not installed on your PC, please install the CH340G driver first, or switch the SWITCH switch to the USB position and connect it with a USB cable.

## Download process
--------

- 1.Connect the motherboard and computer through a USB to type-c data cable;

![111.png](https://wiki.elecrow.com/images/thumb/7/72/111.png/804px-111.png){ loading=lazy }

- 2.Click on the tool on the arduino software and select the corresponding serial port number;

![Esp32rgb 15.png](https://wiki.elecrow.com/images/2/20/Esp32rgb_15.png){ loading=lazy }

- 3.Click to open the serial port assistant, then click the boot button on the motherboard, and then press the reset button until the serial port assistant displays "waiting for download".

![Esp32rgb 16.png](https://wiki.elecrow.com/images/thumb/0/0b/Esp32rgb_16.png/473px-Esp32rgb_16.png){ loading=lazy }

- 4.Click "upload" to upload the program to the ESP32 motherboard

![Esp32rgb 17.png](https://wiki.elecrow.com/images/thumb/b/bc/Esp32rgb_17.png/87px-Esp32rgb_17.png){ loading=lazy }

- Until the prompt upload is successful, as shown in the figure:

![Esp32rgb 18.png](https://wiki.elecrow.com/images/thumb/e/e5/Esp32rgb_18.png/564px-Esp32rgb_18.png){ loading=lazy }

- 5.Press the "Reset" button and the code will run on the display.

## LVGL Widgets Demo
-------

Download LVGL routines, and display UI components (LVGL tools are required to generate corresponding codes before use)

- After downloading the [LVGL_RGB.ino code](https://wiki.elecrow.com/images/f/f5/LVGL_RGB_.zip), restart the screen to realize the function.

![Esp32rgb 31.png](https://wiki.elecrow.com/images/thumb/2/20/Esp32rgb_31.png/682px-Esp32rgb_31.png)

- Running result:

![Esp32rgb 32.png](https://wiki.elecrow.com/images/thumb/d/dd/Esp32rgb_32.png/500px-Esp32rgb_32.png) 
![Esp32rgb 33.png](https://wiki.elecrow.com/images/thumb/a/ab/Esp32rgb_33.png/513px-Esp32rgb_33.png){ loading=lazy }

## Connect With Crowtails
-------

### **Hardware Preparation**

| **ESP Terminal RGB**                                         | **Crowtail-OLED**                                            | **Crowtail-LED**                                             | **Crowtail- Light Sensor**                                   | **USB-A(or USB-C) to USB-C cable**                           | **2\* 4-Pin HY2.0 Cables**                                   |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![Esp32rgb 1.png](https://wiki.elecrow.com/images/thumb/0/0e/Esp32rgb_1.png/300px-Esp32rgb_1.png){ loading=lazy } | ![Crowtail-oled-main-pic.png](https://wiki.elecrow.com/images/thumb/5/51/Crowtail-oled-main-pic.png/200px-Crowtail-oled-main-pic.png){ loading=lazy } | ![Crowtail-LED1.JPG](https://wiki.elecrow.com/images/thumb/4/4f/Crowtail-LED1.JPG/200px-Crowtail-LED1.JPG){ loading=lazy } | ![Crowtail- Light Sensor.JPG](https://wiki.elecrow.com/images/thumb/1/16/Crowtail-_Light_Sensor.JPG/200px-Crowtail-_Light_Sensor.JPG){ loading=lazy } | ![USB-C-CABLE.jpg](https://wiki.elecrow.com/images/thumb/3/3d/USB-C-CABLE.jpg/200px-USB-C-CABLE.jpg){ loading=lazy } | ![CROWTAIL-CABLE.jpg](https://wiki.elecrow.com/images/thumb/3/35/CROWTAIL-CABLE.jpg/200px-CROWTAIL-CABLE.jpg){ loading=lazy } |
| [**Get one now**](https://www.elecrow.com/esp-terminal-with-esp32-3-5-inch-parallel-480x320-tft-capacitive-touch-display-rgb-by-chip-ili9488.html?wiki) | [**Get one now**](https://www.elecrow.com/crowtail-oled-p-1276.html) | [**Get one now**](http://www.elecrow.com/crowtail-led-p-1224.html) | [**Get one now**](https://www.elecrow.com/crowtail-light-sensor-p-1244.html) | [**Get one now**](https://www.elecrow.com/usb-type-a-to-type-c-fast-charge-cable-1-meter.html) | [**Get one now**](https://www.elecrow.com/4-pin-crowtail-cable5-pcs-p-1561.html) |

- **Example 1** display screen color
- After the [B-ScreenColor.ino code](https://wiki.elecrow.com/images/e/ec/RGB-B-ScreenColor.zip) is downloaded, the restart screen will display different colors.

![Esp32rgb 19.png](https://wiki.elecrow.com/images/c/cd/Esp32rgb_19.png){ loading=lazy }

- Running result:

![Esp32rgb 20.png](https://wiki.elecrow.com/images/thumb/6/66/Esp32rgb_20.png/445px-Esp32rgb_20.png){ loading=lazy }

- **Example 2** Display pictures and read TF card pictures
- After the [F-photo.ino code](https://wiki.elecrow.com/images/f/fa/RGB-F-photo.zip) is downloaded, the photo screen will be displayed on the restart screen.
- Running result:

![Esp32rgb 21.png](https://wiki.elecrow.com/images/thumb/a/a3/Esp32rgb_21.png/404px-Esp32rgb_21.png){ loading=lazy }

- **Example 3**Adjust IO40 to control the flashing time of the external LED light as shown in the figure below.
- After downloading the [D-D-PortOut.ino code](https://wiki.elecrow.com/images/b/be/RGB-D-D-PortOut.zip), restart the screen and the LED will flash alternately.

![Esp32rgb 22.png](https://wiki.elecrow.com/images/3/3b/Esp32rgb_22.png){ loading=lazy }

- Running result:

![Esp32rgb 23.png](https://wiki.elecrow.com/images/thumb/0/04/Esp32rgb_23.png/547px-Esp32rgb_23.png){ loading=lazy }

- **Example 4** Control the display of an external OLED screen through I2C
- After downloading the [E-IIC.ino code](https://wiki.elecrow.com/images/e/e6/RGB-E-IIC.zip), restart the screen to realize the peripheral OLED display.

![Esp32rgb 24.png](https://wiki.elecrow.com/images/7/7f/Esp32rgb_24.png){ loading=lazy }

- Running result:

![Esp32rgb 25 1.png](https://wiki.elecrow.com/images/thumb/c/c1/Esp32rgb_25_1.png/476px-Esp32rgb_25_1.png){ loading=lazy }

- **Example 5** reads the external ADC through the A port as shown in the figure below.
- After downloading the [A-ADC.ino code](https://wiki.elecrow.com/images/b/b9/RGB-A-ADC.zip), restart the screen to realize the ADC function.

![Esp32rgb 26 1.png](https://wiki.elecrow.com/images/thumb/6/6c/Esp32rgb_26_1.png/678px-Esp32rgb_26_1.png){ loading=lazy }

- Running result:

![Esp32rgb 27.png](https://wiki.elecrow.com/images/1/1f/Esp32rgb_27.png){ loading=lazy }

- **Example 6**, control the buzzer to make a sound.
- After downloading the [A-BUZZER.ino code](https://wiki.elecrow.com/images/4/44/RGB-A-BUZZER.zip), restart the screen to realize the buzzer function.

![Esp32rgb 28.png](https://wiki.elecrow.com/images/e/ea/Esp32rgb_28.png){ loading=lazy }



- **Example 7**, set WIFI name and password to connect automatically.
- After downloading the [A-WIFI.ino code](https://wiki.elecrow.com/images/8/81/RGB-A-WIFI.zip), restart the screen to realize the WiFi connection.

![Esp32rgb 29.png](https://wiki.elecrow.com/images/2/2b/Esp32rgb_29.png){ loading=lazy }

- Running result:

![Esp32rgb 30.png](https://wiki.elecrow.com/images/5/51/Esp32rgb_30.png){ loading=lazy }


## Resource
------

- [Libraries&LVGL_Widgets_Demo](https://www.elecrow.com/download/product/DLC35010R/Arduino_RGB.zip)

- [ESP Terminal 3.5 RGB code](https://wiki.elecrow.com/images/3/3c/ESP_Terminal_3.5inch_RGB_code.zip)

- [Video Tutorial](https://www.youtube.com/watch?v=ugoiicPM6U0&t=1s)