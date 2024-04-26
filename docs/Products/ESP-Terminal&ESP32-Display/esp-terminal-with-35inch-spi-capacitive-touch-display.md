---
title: ESP Terminal with 3.5inch SPI Capacitive Touch Display
---

## Description
-----------

This handheld terminal is based on the ESP32 controller, equipped with a powerful ESP32-S3 chip, and supports 2.4GHz Wi-Fi and Bluetooth 5 (LE), providing more powerful computing and processing capabilities for IoT terminal applications. It is suitable for various scenarios, such as industrial IoT control terminals, smart agricultural terminals, personal smart home monitoring terminals, and personal DIY projects. Thanks to the scalability of the ESP32-S3-N16RB module, it can lead to various interfaces. It not only has Crowtail's digital port, analog port, UART, and IIC interface, but also integrates a MEMS microphone, camera interface, and buzzer function. It supports ESP-IDF and Arduino IDE development and is compatible with Python/Micropython/Arduino. It also supports LVGL, which is the most popular free and open-source embedded graphics library to create beautiful UIs for any MCU, MPU, and display type.With the 2M pixel camera, it can easily realize face/object/scene recognition and provide more creativity in cutting-edge projects such as speech recognition/voice control. The equipped screen adopts SPI serial screen with 320\*480 resolution, and the size of 3.5 inches is the best choice as a handheld/pocket terminal. The frame rate of the screen is up to 20FPS, which is sufficient for most application scenarios. If you have higher requirements for the screen, you can try this RGB screen: xxxxxxRGB link. The whole terminal is surrounded by a perfect acrylic shell, which makes the whole product look more beautiful. At the same time, it can also be fixed in other ways. With two M3 screw mounting holes, you can mount it on the wall or PLC rail. Its compatibility with the Crowtail system can provide your project with an easier implementation method and the convenience of one-stop shopping.

**Model: [DLC35020S](https://www.elecrow.com/esp-terminal-3-5-inch-320-480-spi-tft-capacitive-touch-display-with-ov2640-camera.html)**  
![TERMINAL-SPI-MAINPIC.jpg](https://wiki.elecrow.com/images/thumb/a/a3/TERMINAL-SPI-MAINPIC.jpg/500px-TERMINAL-SPI-MAINPIC.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){loading=lazy}](https://www.elecrow.com/esp-terminal-3-5-inch-320-480-spi-tft-capacitive-touch-display-with-ov2640-camera.html?wiki "Title text")

## Feature
-------

- Integrated ESP32-S3 module, which is support 2.4 GHz Wi-Fi and Bluetooth 5 (LE)
- 3.5 inch TFT 320\*480 resolution touch LCD display
- Support, USB, UART, SPI, I2C, PWM, I2S communication protocols
- Supports 1T1R mode, data rate up to 150 Mbps, Wireless Multimedia (WMM)
- Compatible with Arduino/Micropython/Python
- Supports hardware accelerated encryption (AES, SHA2, ECC, RSA-4096)
- Support TYPE-C USB power supply and polymer lithium battery power supplyWith 6 Crowtail interfaces (4P 2.0 connector) , plug and play with various Crowtail sensor

## Specification
-------------

![Esp32spi 4.png](https://wiki.elecrow.com/images/thumb/d/d1/Esp32spi_4.png/600px-Esp32spi_4.png){ loading=lazy }

## Hardware Infomation
-------------------

### **Overview**

![700x](https://wiki.elecrow.com/images/thumb/2/22/Esp32spi_3.png/700px-Esp32spi_3.png){ loading=lazy }

- **REST button** Press this button to reset the system.
- **LiPo port** Lithium battery charging interface (lithium battery not included)
- **BOOT button** Hold down the Boot button and press the RESET button to initiate firmware download mode. Users can download firmware through the serial port
- **5V Power/Type C interface** It serves as the power supply for the development board and the communication interface between the PC and ESP-WROOM-32.
- **6 Crowtail interfaces**(2\*Ana,2\*Dig,1\*UART,1\*IIC) Users can program the ESP32-S3 to communicate with peripherals connected to the Crowtail interface.

### **IO ports**

![Esp32spi 35.png](https://wiki.elecrow.com/images/thumb/a/a1/Esp32spi_35.png/622px-Esp32spi_35.png){ loading=lazy }

| **ESP Terminal Port** | **Pin Number** |
|:-:|:-:|
| A1 | IO19 |
| A2 | IO20 |
| D1 | IO11 |
| D2 | IO40 |
| UART | RX(IO44); TX(IO43) |
| I2C | SDA(IO2); SCL(IO1) |

## Platforms Supported
-------------------

| **Arduino** | **SquareLine** | **PlatformIO** | **Home Assistant** | **MicroPython** | **ESP-IDF** |
|:-:|:-:|:-:|:-:|:-:|:-:|
| ![Arduino.png](https://wiki.elecrow.com/images/6/63/Arduino.png){ loading=lazy } | ![2a80b24a-38ae-4639-bbb1-af8b6c26891e.png](https://wiki.elecrow.com/images/thumb/9/9b/2a80b24a-38ae-4639-bbb1-af8b6c26891e.png/200px-2a80b24a-38ae-4639-bbb1-af8b6c26891e.png){ loading=lazy } | ![PlatformIO logo.svg.png](https://wiki.elecrow.com/images/thumb/8/82/PlatformIO_logo.svg.png/200px-PlatformIO_logo.svg.png){ loading=lazy } | ![Home Assistant Logo.svg.png](https://wiki.elecrow.com/images/thumb/0/08/Home_Assistant_Logo.svg.png/200px-Home_Assistant_Logo.svg.png){ loading=lazy } | ![MicroPython new logo.svg.png](https://wiki.elecrow.com/images/thumb/c/c9/MicroPython_new_logo.svg.png/200px-MicroPython_new_logo.svg.png){ loading=lazy } | ![38b1d992-8f73-42bb-a922-318053d9042a.png](https://wiki.elecrow.com/images/5/5c/38b1d992-8f73-42bb-a922-318053d9042a.png){ loading=lazy } |
| ![Alt text](https://wiki.elecrow.com/images/thumb/9/93/GetStarted.png/150px-GetStarted.png){ loading=lazy } | [![Alt text](https://wiki.elecrow.com/images/thumb/9/93/GetStarted.png/150px-GetStarted.png)](https://www.elecrow.com/wiki/index.php?title=File:SquareLine_Tutorial.pdf "Title text") | [![Alt text](https://wiki.elecrow.com/images/thumb/9/93/GetStarted.png/150px-GetStarted.png)](./esp-terminal-35-inch-display-platformio-tutorial.md "Title text") | [![Alt text](https://wiki.elecrow.com/images/thumb/9/93/GetStarted.png/150px-GetStarted.png)](https://www.elecrow.com/download/product/DLC35020S/HomeAssistant_3.5SPI.zip "Title text") | [![Alt text](https://wiki.elecrow.com/images/thumb/9/93/GetStarted.png/150px-GetStarted.png)](./esp-terminal-spi-35-inch-display-micropython-tutorial.md "Title text") | [![Alt text](https://wiki.elecrow.com/images/thumb/9/93/GetStarted.png/150px-GetStarted.png)](https://www.elecrow.com/download/product/DLC35020S/ESP-IDF_SPI.zip "Title text") |

<table>
    <tbody>
        <tr>
            <td style="text-align: center;height:5em;width:6em;background:#7595F8;color:white"><b>NOTE</b></td>
            <td style="text-align: center;background:#B0C4DE;color:black;width:27em">Please click on the "Get Started" or titles below to switch to the tutorial page.</td>
        </tr>
    </tbody>
</table>

<table>
    <tbody>
        <tr>
            <td style="text-align: center;height:5em;width:6em;background:#D83E3E;color:white"><b>For Beginners</b></td>
            <td style="text-align: center;background:#F57171;color:black;width:27em">Please first click on 'Play with Arduino' to compile and run the factory demo program.</td>
        </tr>
    </tbody>
</table>

## [LVGL ESP32 Display Tutorial-A Step-by-Step Guide to LVGL GUI Development](../../Tutorials/lvgl-esp32-display-tutorial-a-step-by-step-guide-to-lvgl-gui-development.md#lesson01-introducing-the-esp32-display-series-and-environment-configuration)
-------------------------------

- [Lesson01 Introducing the ESP32 Display series and environment configuration](../Lesson/lesson01-introducing-the-esp32-display-series-and-environment-configuration.md)
- [Lesson02 Start the ESP32 DISPLAY GUI drawing via LovyanGFX Graphics Library](../Lesson/lesson02-start-the-esp32-display-gui-drawing-via-lovyangfx-graphics-library.md)
- [Lesson03 How to Display Pictures on ESP32 Boards](../Lesson/lesson03-how-to-display-pictures-on-esp32-boards.md)
- [Lesson04 LVGL Basics: How to install LVGL for ESP32 Displays](../Lesson/lesson04-lvgl-basics-how-to-install-lvgl-for-esp32-displays.md)
- [Lesson05 Introduction to the 5 categories of LVGL GUI library Widgets](../Lesson/lesson05-introduction-to-the-5-categories-of-lvgl-gui-library-widgets.md)
- [Lesson06 Use Squareline Studio to start your 1st human machine interface project](../Lesson/lesson06-use-squareline-studio-to-start-your-1st-human-machine-interface-project.md)
- [Lesson07 How to implement text information input with Squareline Studio](../Lesson/lesson07-how-to-implement-text-information-input-with-squareline-studio.md)
- [Lesson08 How to make the menu and a progress bar with Squareline Studio](../Lesson/lesson08-how-to-make-the-menu-and-a-progress-bar-with-squareline-studio.md)
- [Lesson09 How to make an analysis report on ESP32 Display](../Lesson/lesson09-how-to-make-an-analysis-report-on-esp32-display.md)
- [Lesson10 Create a 3D Printer UI Project on ESP32 Display](../Lesson/lesson10-create-a-3d-printer-ui-project-on-esp32-display.md)
- [Lesson11 How to Make a Mixer Interface on ESP32 Display](../Lesson/lesson11-how-to-make-a-mixer-interface-on-esp32-display.md)
- [Lesson12 Make Your ESP32 Display the Lantern Control terminal](../Lesson/lesson12-make-your-esp32-display-the-lantern-control-terminal.md)
- [Lesson13 DIY Electronic Control Terminal on ESP32 Display with Squareline Studio](../Lesson/lesson13-diy-electronic-control-terminal-on-esp32-display-with-squareline-studio.md)
- [Lesson14 Create Car Control Screen on ESP32 Display: A Step-by-Step Guide](../Lesson/lesson14-create-car-control-screen-on-esp32-display-a-step-by-step-guide.md)
- [Lesson15 Smart Agriculture Monitoring: IoT-Based Real-Time ESP32 Display Project](../Lesson/lesson15-smart-agriculture-monitoring-lot-based-real-time-esp32-display-project.md)
- [Lesson16 ESP32 Display for Smart Home Central Control: A Home Automation Solution](../Lesson/lesson16-esp32-display-for-smart-home-central-control-a-home-automation-solution.md)

## [Play with Arduino IDE (the factory demo code)](./esp-terminal-spi-35-inch-display-arduino-tutorial.md)
----------------------------------

This tutorial introduces how to configure the Arduino programming environment and how to set up the board.

The tutorial examples include the lvgl demo example (When you first received it, the demo it demonstrated after you powered it up), and how to connect the esp terminal to some sensors/modules.

- [Development environment configuration](./esp-terminal-spi-35-inch-display-arduino-tutorial.md#development-environment-configuration)
- [Board settings](./esp-terminal-spi-35-inch-display-arduino-tutorial.md#board=settings)
- [Download process](./esp-terminal-spi-35-inch-display-arduino-tutorial.md#download-process)
- [Connect With Crowtails](./esp-terminal-spi-35-inch-display-arduino-tutorial.md#connect-with-crowtails)
- [LVGL Widgets Demo](./esp-terminal-spi-35-inch-display-arduino-tutorial.md#lvgl-widgets-demo)

## [Play with PlatformIO](./esp-terminal-35-inch-display-platformio-tutorial.md)
---------------------------------------------------

## [Play with HomeAssiatant](https://www.elecrow.com/download/product/DLC35020S/HomeAssistant_3.5SPI.zip)
------------------------------------------------------------------------------------------------------

## [Play with MicroPython](./esp-terminal-spi-35-inch-display-micropython-tutorial.md)
----------------------------------------------------------------------------------------------------------------------------

This tutorial will demonstrate how to program the ESP Terminal SPI via MicroPython.

The project of this tutorial is a smart light. When the ambient light intensity is lower than 60%, the LED will light up, otherwise, the LED will go out.

## [Play with ESP-IDF](https://www.elecrow.com/download/product/DLC35020S/ESP-IDF_SPI.zip)
---------------------------------------------------------------------------------------

## FAQs
----

- [Click here to see the frequently asked questions of ESP32 display.](https://forum.elecrow.com/discussion/492/esp-terminal-esp32-hmi-display-faqs)
- [The tutorial video on uploading code for ESP32 displays.](https://www.youtube.com/watch?v=7rstSmn_YKM)
- [How to upload the factory program.](https://forum.elecrow.com/discussion/495/how-to-upload-the-esp32-display-factory-program-by-arduino-ide)
- [How to install firmware](https://forum.elecrow.com/discussion/510/how-to-install-the-factory-demo-firmware-with-flash-download-tool/p1?new=1)
- You can list your question at [the forum](https://forum.elecrow.com/) or contact techsupport@elecrow.com for technology support.

## Resource
--------

- [ESP\_Terminal\_3.5inch\_SPI\_code](https://wiki.elecrow.com/images/8/8f/ESP_Terminal_3.5inch_SPI_code.zip)
- [ESP32-\_3.5\_TFT\_Display(SPI)V1.0\_Schematic&amp;PCB\_Eagle.zip](https://wiki.elecrow.com/images/e/e7/ESP32-_3.5_TFT_Display%28SPI%29V1.0_20230116_Eagle.zip)
- [SquareLine\_Tutorial](https://wiki.elecrow.com/images/5/5e/SquareLine_Tutorial.pdf)
- [PlatformIO\_Tutorial](https://www.elecrow.com/download/product/DLC35020S/PlatformIO_SPI.zip)
- [MicroPython\_Tutorial](https://www.elecrow.com/download/product/DLC35020S/Micropython.zip)
- [ESP-IDF\_SPI.zip](https://www.elecrow.com/download/product/DLC35020S/ESP-IDF_SPI.zip)