---
title: ESP Terminal SPI 3.5-inch Display Arduino Tutorial
---

## Overview
-----

This tutorial introduces how to configure the Arduino programming environment and how to set up the board.

The tutorial examples include the lvgl demo example (When you first received it, the demo it demonstrated after you powered it up), and how to connect the esp terminal to some sensors/modules.



## Development environment configuration
------

- 1.Please go to the official website https://www.arduino.cc/ to download the Arduino IDE, click the start icon: open as shown in the figure:

![Esp32rgb 3.png](https://wiki.elecrow.com/images/thumb/d/d8/Esp32rgb_3.png/469px-Esp32rgb_3.png){ loading=lazy }

- 2.Download the [libraries](https://www.elecrow.com/download/product/DLC35020S/Arduino_SPI.zip) provided by Elecrow. Copy them to the library folder in the Arduino installation directory.

If you don't know the path of Arduino library directory, you can open Arduino IDE→Files→Preferences:   
![Arduino-sketchbook-location.jpg](https://wiki.elecrow.com/images/thumb/0/00/Arduino-sketchbook-location.jpg/600px-Arduino-sketchbook-location.jpg){ loading=lazy }


- Add the ESP32 S3 URL as follows：

https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json   
![Esp32rgb 5.png](https://wiki.elecrow.com/images/thumb/7/75/Esp32rgb_5.png/616px-Esp32rgb_5.png){ loading=lazy }

- The tool automatically downloads and updates the corresponding model, check the steps as shown in the figure:

![Esp32rgb 6.png](https://wiki.elecrow.com/images/thumb/0/06/Esp32rgb_6.png/614px-Esp32rgb_6.png){ loading=lazy }
![Esp32rgb 7.png](https://wiki.elecrow.com/images/thumb/0/0b/Esp32rgb_7.png/609px-Esp32rgb_7.png){ loading=lazy }

## Board settings

- Set as shown

![Esp32spi 9.png](https://wiki.elecrow.com/images/thumb/8/88/Esp32spi_9.png/611px-Esp32spi_9.png){ loading=lazy }

- warn:

If the CH340G driver is not installed on your PC, please install the CH340G driver first, or switch the SWITCH switch to the USB position and connect it with a USB cable.

## Download process

- 1.Connect the motherboard and computer through a USB to type-c data cable;

![Esp32spi 10.png](https://wiki.elecrow.com/images/thumb/4/4e/Esp32spi_10.png/350px-Esp32spi_10.png){ loading=lazy } 
![Esp32spi 11.png](https://wiki.elecrow.com/images/thumb/c/c9/Esp32spi_11.png/440px-Esp32spi_11.png){ loading=lazy }

- 2.Click on the tool on the arduino software and select the corresponding serial port number;

![Esp32spi 12.png](https://wiki.elecrow.com/images/7/71/Esp32spi_12.png){ loading=lazy }

- 3.Click to open the serial port assistant, then click the boot button on the motherboard, and then press the reset button until the serial port assistant displays "waiting for download".

![Esp32spi 13.png](https://wiki.elecrow.com/images/thumb/5/57/Esp32spi_13.png/473px-Esp32spi_13.png){ loading=lazy }

- 4.Click "upload" to upload the program to the ESP32 motherboard

![Esp32spi 14.png](https://wiki.elecrow.com/images/thumb/e/e7/Esp32spi_14.png/87px-Esp32spi_14.png){ loading=lazy }

- Until the prompt upload is successful, as shown in the figure:

![Esp32spi 15.png](https://wiki.elecrow.com/images/thumb/e/e6/Esp32spi_15.png/564px-Esp32spi_15.png){ loading=lazy }

- 5.Press the "Reset" button and the code will run on the display.

## LVGL Widgets Demo
--------

- After downloading the [LVGL_SPI_test.INO code](https://wiki.elecrow.com/images/8/82/LVGL_SPI_.zip), restart the screen, and you can see various function module icons.

![Esp32spi 31.png](https://wiki.elecrow.com/images/e/e4/Esp32spi_31.png){loading=lazy}

- Running result:

![Esp32spi 32.png](https://wiki.elecrow.com/images/thumb/d/d3/Esp32spi_32.png/548px-Esp32spi_32.png){ loading=lazy } 
![Esp32spi 33.png](https://wiki.elecrow.com/images/thumb/1/13/Esp32spi_33.png/556px-Esp32spi_33.png){ loading=lazy } 
![Esp32spi 34.png](https://wiki.elecrow.com/images/thumb/6/69/Esp32spi_34.png/557px-Esp32spi_34.png){ loading=lazy }

## Connect With Crowtails
-------

### **Hardware Preparation**

| **ESP Terminal SPI**                                         | **Crowtail-OLED**                                            | **Crowtail-LED**                                             | **Crowtail- Light Sensor**                                   | **USB-A(or USB-C) to USB-C cable**                           | **2\* 4-Pin HY2.0 Cables**                                   |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![TERMINAL-SPI-MAINPIC.jpg](https://wiki.elecrow.com/images/thumb/a/a3/TERMINAL-SPI-MAINPIC.jpg/300px-TERMINAL-SPI-MAINPIC.jpg)]{ loading=lazy } | ![Crowtail-oled-main-pic.png](https://wiki.elecrow.com/images/thumb/5/51/Crowtail-oled-main-pic.png/200px-Crowtail-oled-main-pic.png){ loading=lazy } | ![Crowtail-LED1.JPG](https://wiki.elecrow.com/images/thumb/4/4f/Crowtail-LED1.JPG/200px-Crowtail-LED1.JPG){ loading=lazy } | ![Crowtail- Light Sensor.JPG](https://wiki.elecrow.com/images/thumb/1/16/Crowtail-_Light_Sensor.JPG/200px-Crowtail-_Light_Sensor.JPG){ loading=lazy } | ![USB-C-CABLE.jpg](https://wiki.elecrow.com/images/thumb/3/3d/USB-C-CABLE.jpg/200px-USB-C-CABLE.jpg){ loading=lazy } | ![CROWTAIL-CABLE.jpg](https://wiki.elecrow.com/images/thumb/3/35/CROWTAIL-CABLE.jpg/200px-CROWTAIL-CABLE.jpg){ loading=lazy } |
| [**Get one now**](https://www.elecrow.com/esp-terminal-3-5-inch-320-480-spi-tft-capacitive-touch-display-with-ov2640-camera.html) | [**Get one now**](https://www.elecrow.com/crowtail-oled-p-1276.html) | [**Get one now**](http://www.elecrow.com/crowtail-led-p-1224.html) | [**Get one now**](https://www.elecrow.com/crowtail-light-sensor-p-1244.html) | [**Get one now**](https://www.elecrow.com/usb-type-a-to-type-c-fast-charge-cable-1-meter.html) | [**Get one now**](https://www.elecrow.com/4-pin-crowtail-cable5-pcs-p-1561.html) |

- Example 1 Display the screen color of the LCD
- After the [A-LCD.INO code](https://wiki.elecrow.com/images/0/00/A-LCD.zip) is downloaded, the restart screen will be in a different color.

![Esp32spi 16.png](https://wiki.elecrow.com/images/2/2f/Esp32spi_16.png){ loading=lazy }

- Running result:

![Esp32spi 17.png](https://wiki.elecrow.com/images/thumb/8/85/Esp32spi_17.png/458px-Esp32spi_17.png){ loading=lazy }

- Example 2 Display pictures and read TF card pictures
- After the [A-TF-PIC.INO code](https://wiki.elecrow.com/images/d/de/A-TF-PIC.zip) is downloaded, the restart screen will display the picture screen.

![Esp32spi 18.png](https://wiki.elecrow.com/images/thumb/3/3c/Esp32spi_18.png/571px-Esp32spi_18.png){ loading=lazy }

- Running result:

![Esp32spi 19.png](https://wiki.elecrow.com/images/thumb/9/96/Esp32spi_19.png/526px-Esp32spi_19.png){ loading=lazy }

- Example 3 touch function display
- After the [A-TOUCH.INO code](https://wiki.elecrow.com/images/9/90/A-TOUCH.zip) is downloaded, the restart screen will automatically display the XY coordinates of the touch, and the corresponding X Y values will be displayed when touching different positions

![Esp32spi 20.png](https://wiki.elecrow.com/images/b/b8/Esp32spi_20.png){ loading=lazy }

- Running result:

![Esp32spi 21.png](https://wiki.elecrow.com/images/4/4a/Esp32spi_21.png){ loading=lazy }

- Example 4 camera function display
- After downloading the [A-Camera.INO code](https://wiki.elecrow.com/images/5/53/A-Camera.zip), restart the screen and enter the camera screen.

![Esp32spi 22.png](https://wiki.elecrow.com/images/4/47/Esp32spi_22.png){ loading=lazy }

- Running result:

![Esp32spi 23.png](https://wiki.elecrow.com/images/thumb/c/c6/Esp32spi_23.png/457px-Esp32spi_23.png){ loading=lazy }

- Example 5 connect GPIO port, I2C port, UART port
- After downloading the [A-A_D_PORT.INO code](https://wiki.elecrow.com/images/e/ec/A-A_D_PORT.zip), restart the screen, automatically light up the LED on the GPIO port, and read the analog value from the analog port.

![Esp32spi 24.png](https://wiki.elecrow.com/images/5/56/Esp32spi_24.png){ loading=lazy }

- Running result:

![Esp32spi 25.png](https://wiki.elecrow.com/images/b/b0/Esp32spi_25.png){ loading=lazy }

- Example 6 Connect I2C port
- After downloading the [A-IIC.INO code](https://wiki.elecrow.com/images/3/38/A-IIC.zip), restart the screen, and the I2C port peripheral will display "ELECROW".

![Esp32spi 26.png](https://wiki.elecrow.com/images/thumb/f/f2/Esp32spi_26.png/727px-Esp32spi_26.png){ loading=lazy }

- Running result:

![Esp32spi 27.png](https://wiki.elecrow.com/images/thumb/c/c8/Esp32spi_27.png/213px-Esp32spi_27.png){ loading=lazy }

- Example 7 Buzzer function
- After the [A-BUZZER.INO code](https://wiki.elecrow.com/images/e/e0/A-BUZZER.zip) is downloaded, restart the screen and the buzzer will sound.

![Esp32spi 28.png](https://wiki.elecrow.com/images/d/da/Esp32spi_28.png){ loading=lazy }

- Example 8 Microphone
- After downloading the [A_AUDIO.INO code](https://wiki.elecrow.com/images/1/1b/A-AUDIO.zip), restart the screen.

![Esp32spi 29.png](https://wiki.elecrow.com/images/6/69/Esp32spi_29.png){ loading=lazy }

- Note: Here you need to choose esp32 2.0.3 version.

①Select Boards Manager in Tools.   
![Spi-1.png](https://wiki.elecrow.com/images/thumb/f/f1/Spi-1.png/658px-Spi-1.png){ loading=lazy }

②Select version 2.0.3.   
![Spi-2.png](https://wiki.elecrow.com/images/thumb/f/fc/Spi-2.png/658px-Spi-2.png){ loading=lazy }

③Complete as follows.   
![Spi-3.png](https://wiki.elecrow.com/images/d/d4/Spi-3.png){ loading=lazy }

- After burning, connect the arduino serial port tool, and select "serial plotter" in the tool drop-down menu.

![Esp32spi 29 1.png](https://wiki.elecrow.com/images/1/16/Esp32spi_29_1.png){ loading=lazy }

- Running result:

![Esp32spi 30 1.png](https://wiki.elecrow.com/images/thumb/5/5c/Esp32spi_30_1.png/797px-Esp32spi_30_1.png){ loading=lazy } 
![Esp32spi 30 2.png](https://wiki.elecrow.com/images/e/ef/Esp32spi_30_2.png){ loading=lazy }



## Resources
------

- [Libraries&LVGL_Widgets_Demo](https://www.elecrow.com/download/product/DLC35020S/Arduino_SPI.zip)
- [ESP_Terminal_3.5inch_SPI_code](https://wiki.elecrow.com/images/8/8f/ESP_Terminal_3.5inch_SPI_code.zip)
- [Video Tutorial](https://www.youtube.com/watch?v=ugoiicPM6U0&t=1s)