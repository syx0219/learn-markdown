---
title: ESP32 Display 2.4'' Intelligent Touch Screen Wi-Fi&BLE 240*320 HMI Display
---

## Description
-----------

Elecrow ESP32 2.4-inch display is a powerful HMI touch screen with a 240\*320 resolution LCD display. It uses the ESP32-WROOM-32 module as the main control processor, with a dual-core 32-bit LX6 microprocessor, integrated WiFi and Bluetooth wireless functions, a main frequency of up to 240MHz, providing powerful performance and versatile applications, suitable for IoT application devices and other scenes.

The module includes a 2.4-inch LCD display and a driver board. The display screen uses resistive touch technology and comes with a resistive touch pen, making the screen usage more flexible. In addition, the board has reserved a TF card slot, multiple peripheral interfaces, USB interface, speaker interface, battery interface, etc., providing more expansion possibilities. It supports development environments such as Arduino IDE, Espressif IDF, Lua RTOS, and Micro Python, and is compatible with the LVGL graphics library. This enables developers to not only customize their own UI interfaces but also to create interesting projects quickly and easily, greatly shortening the development cycle.

The ESP32 2.4-inch display is suitable for a wide range of scenes such as automotive HMI, medical equipment, industrial control, power, civil electronics, automation, GPS, new energy, and IoT application devices. Its various interfaces and expansion functions make it able to meet the needs of different fields, providing users with a more comprehensive solution.

**Model: [DIS03024H](https://www.elecrow.com/esp32-display-2-4-inch-intelligent-spi-tft-lcd-touch-screen-hmi-display.html)**   
![Main-picture-24.jpg](https://wiki.elecrow.com/images/thumb/d/dc/Main-picture-24.jpg/400px-Main-picture-24.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){loading=lazy}](https://www.elecrow.com/esp32-display-2-4-inch-intelligent-spi-tft-lcd-touch-screen-hmi-display.html "Title text")

## Feature
-------

- Integrated ESP32-WROOM-32 module, built-in wireless communication 2.4 GHz Wi-Fi (802.11 b/g/n) and Bluetooth 5.0;
- Support development environment Arduino IDE, Espressif IDF, Lua RTOS, Micro python and compatible with LVGL graphics library;
- Built-in LVGL demo interface and Arduino example, plug and play;
- LCD 240\*320 2.4 inches TFT-LCD with driver IC ILI9341V;
- Rich peripheral interfaces and expansion functions enable it to meet the needs of different fields.

## Specification
-------------

- Model: 2.4 inches ESP32 display
- Main Processor: ESP32-WROOM-32-N4
- Resolution: 240\*320
- ColorDepth: 262K
- Touch Type: Resistive Touch Screen
- Touch Panel: TN Panel
- Screen: TFT-LCD Screen
- Display driver: ILI9341V
- Interface: 1\*TF Card Slot, 1\* I2C, 1\* GPIO, 1\*Speak, 1\* UART1, 1\*UART0
- Button: BOOT Button and Reset Button
- Active Area: 36.72\*48.96mm(W\*H)

## PinOut
------

![2.4.png](https://wiki.elecrow.com/images/thumb/3/31/2.4.png/600px-2.4.png){ loading=lazy }

| SPK | Output audio signal,connected with speakers.The motherboard comes with a power amplifier chip circuit. |
|---|---|
| PWR | Power LED. |
| RST | Reset button.Push it to reset the system. |
| BOOT |  |
| GPIO\_D | Digital and artificial I/O interface. |
| I2C | Build the communication among micro controller and peripheral devices. |
| TF | Provide off-line save and extra storage space. |
| UART1 | Build the communication among Logic modules, including serial communication module and print module. |
| BAT | Connect with the lithium battery. Can charge the battery |
| UART0 | Provide serial communication, supply voltage(transform USB to UART0) and serial information printing. |

| **2.4-inch HMI Port** | **Pin Number** |
|:-:|:-:|
| GPIO\_D | IO25; IO32 |
| UART | RX(IO16); TX(IO17) |
| I2C | SDA(IO22); SCL(IO21) |

## Platforms Supported
-------------------

| **Arduino** | **SquareLine** | **PlatformIO** | **Home Assistant** | **ESPHome** | **MicroPython** | **ESP-IDF** |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| ![Arduino.png](https://wiki.elecrow.com/images/thumb/6/63/Arduino.png/150px-Arduino.png){ loading=lazy } | ![2a80b24a-38ae-4639-bbb1-af8b6c26891e.png](https://wiki.elecrow.com/images/thumb/9/9b/2a80b24a-38ae-4639-bbb1-af8b6c26891e.png/150px-2a80b24a-38ae-4639-bbb1-af8b6c26891e.png){ loading=lazy } | ![PlatformIO logo.svg.png](https://wiki.elecrow.com/images/thumb/8/82/PlatformIO_logo.svg.png/150px-PlatformIO_logo.svg.png){ loading=lazy } | ![Home Assistant Logo.svg.png](https://wiki.elecrow.com/images/thumb/0/08/Home_Assistant_Logo.svg.png/150px-Home_Assistant_Logo.svg.png){ loading=lazy } | ![Cd827929-5fbc-468f-be2a-5ddba0f92996.png](https://wiki.elecrow.com/images/thumb/3/3f/Cd827929-5fbc-468f-be2a-5ddba0f92996.png/150px-Cd827929-5fbc-468f-be2a-5ddba0f92996.png){ loading=lazy } | ![MicroPython new logo.svg.png](https://wiki.elecrow.com/images/thumb/c/c9/MicroPython_new_logo.svg.png/150px-MicroPython_new_logo.svg.png){ loading=lazy } | ![38b1d992-8f73-42bb-a922-318053d9042a.png](https://wiki.elecrow.com/images/thumb/5/5c/38b1d992-8f73-42bb-a922-318053d9042a.png/150px-38b1d992-8f73-42bb-a922-318053d9042a.png){ loading=lazy } |

<table>
    <tbody>
        <tr>
            <td style="text-align: center;height:5em;width:6em;background:#7595F8;color:white"><b>NOTE</b></td>
            <td style="text-align: center;background:#B0C4DE;color:black;width:27em">Please click on the titles to switch to the tutorial page.</td>
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

## [LVGL ESP32 Display Tutorial-A Step-by-Step Guide to LVGL GUI Development](../../Tutorials/index.md#lesson01-introducing-the-esp32-display-series-and-environment-configuration)
------------------------------

## [Play with Arduino (the factory demo code)](./2.4-inch-esp32-dispaly-arduino-tutorial.md)
---------------------------------------------------------------------------------------------------------------------------------

## [Play with PlatformIO](./2.4-inch-esp32-dispaly-platformio-tutorial.md)
---------------------------------------------------------------------------------------------------------------

## [Play with HomeAssistant](https://www.elecrow.com/download/product/ESP32_Display/2.4inch/HomeAssistant-esphome_24.zip)
----------------------------------------------------------------------------------------------------------------------

## [Play with ESPHome](./2.4-inch-esp32-dispaly-homeAssistant-tutorial.md)
---------------------------------------------------------------------------------------------------------------

## [Play with MicroPython](./esp32-display-24-inch-micropython-tutorial.md)
-----------------------------------------------------------------------------------------------------------------

## [Play with ESP-IDF](https://www.elecrow.com/download/product/ESP32_Display/2.4inch/ESP-IDF_2.4.zip)
---------------------------------------------------------------------------------------------------

## FAQS
----

- [Click here to see the frequently asked questions of ESP32 display.](https://forum.elecrow.com/discussion/492/esp-terminal-esp32-hmi-display-faqs)
- [The tutorial video on uploading code for ESP32 displays.](https://www.youtube.com/watch?v=EARkhr3ABEY)
- [How to upload the factory program.](https://forum.elecrow.com/discussion/495/how-to-upload-the-esp32-display-factory-program-by-arduino-ide)
- [How to install factory firmware](https://forum.elecrow.com/discussion/510/how-to-install-the-factory-demo-firmware-with-flash-download-tool/p1?new=1)
- You can list your question at [the forum](https://forum.elecrow.com/) or contact techsupport@elecrow.com for technology support.

## Resource
--------

- [2.4-Screen-Specification](https://www.elecrow.com/wiki/images/f/f2/QD241801_specification.pdf)
- [2.4-SCH+PCB.zip](https://wiki.elecrow.com/images/c/cf/DIS03024H-SCH%2BPCB.zip)
- [2.4-2.8-3.5-Arduino Example CODE.zip](https://www.elecrow.com/wiki/images/1/15/2.4-2.8-3.5-WIKI%E4%BB%A3%E7%A0%81.zip)
- [Arduino Libraries&amp;LVGL Demo](https://www.elecrow.com/download/product/ESP32_Display/2.4inch/Arduino_24.zip)
- [PlatformIO\_24.zip](https://www.elecrow.com/download/product/ESP32_Display/2.4inch/PlatformIO_24.zip)
- [HomeAssistant-esphome\_24.zip](https://www.elecrow.com/download/product/ESP32_Display/2.4inch/HomeAssistant-esphome_24.zip)
- [2.4Micropython.zip](https://www.elecrow.com/download/product/ESP32_Display/2.4inch/2.4Micropython.zip)
- [ESP-IDF\_2.4.zip](https://www.elecrow.com/download/product/ESP32_Display/2.4inch/ESP-IDF_2.4.zip)
- [SquareLine - 2.4/2.8/3.5-inch](https://youtu.be/Ls0uLyeAgiw)