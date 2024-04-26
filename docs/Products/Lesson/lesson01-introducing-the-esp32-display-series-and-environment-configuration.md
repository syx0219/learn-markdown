---
title: Lesson01 Introducing the ESP32 Display series and environment configuration
---

## **HMI (human-machine interface)**
-----

HMI (Human-Machine Interface) refers to the interface that interacts between humans and machines or equipment through software and hardware. It can help people easily grasp the running status of machines or equipment, control their execution actions, etc., making human-computer interaction simpler and more intuitive. HMI is commonly used in industrial and automation control systems to monitor and control production processes and equipment. The components of HMI include: display, touch screen, control buttons, indicator lights, alarm system, data transmission interface, etc. In terms of software, HMI is mainly composed of human-computer interaction interface, control logic program, communication protocol and so on. Users can control the running status of the equipment through the touch screen, control buttons and other operation interfaces, and at the same time observe the feedback information such as the running status of the equipment. The advantage of HMI is that it can make the control system more efficient, accurate, and reliable, while saving human resources and time costs. HMIs are also often used in home automation systems, such as smart home control panels, to allow occupants to control home devices more conveniently. In short, HMI is an interface that realizes the interaction between human and machine or equipment through the combination of software and hardware. It can help users better grasp and control the operating status of equipment, and improve work efficiency and performance.

## **Introduction to compatible hardware for this series of courses**
-----

**ESP32 Terminal Series**   
**A: ESP32 Terminal- 3.5inch RGB Display**   
This Elecrow terminal is a microcontroller based on the ESP32 master. It adopts Xtensa 32-bit LX7 dual-core processor with a main frequency of up to 240Mhz, supports 2.4GHz Wi-Fi and Bluetooth 5 (LE), and can easily handle common edge terminal device application scenarios, such as industrial control, agricultural production environment detection and processing, intelligent logistics monitoring, smart home scenarios and more. This terminal also has a 3.5-inch parallel RGB interface capacitive touch screen with a resolution of 320*480 to ensure perfect image output at a frame rate (FPS) of 60. On the back of this terminal, we have introduced 4 Crowtail interfaces, which can be used with our Crowtail series sensors, plug and play, and create more interesting projects quickly and conveniently. In addition, it is also equipped with an SD card slot for extended storage (SPI leads) and a buzzer function. It support ESP-IDF and Arduino IDE development, and is compatible with Python/Micropython/Arduino. It also support LVGL, which is the most popular free and open-source embedded graphics library to create beautiful UIs for any MCU, MPU and display type.  
![Esp32rgb 1.png](https://wiki.elecrow.com/images/thumb/0/0e/Esp32rgb_1.png/650px-Esp32rgb_1.png){ loading=lazy }   
[![Alt text](../../assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/esp-terminal-with-esp32-3-5-inch-parallel-480x320-tft-capacitive-touch-display-rgb-by-chip-ili9488.html)   
**B :ESP32 Terminal- 3.5inch SPI Display**   
This handheld terminal is based on the ESP32 controller, equipped with a powerful ESP32-S3 chip, and supports 2.4GHz Wi-Fi and Bluetooth 5 (LE), providing more powerful computing and processing capabilities for IoT terminal applications. It is suitable for various scenarios, such as industrial IoT control terminals, smart agricultural terminals, personal smart home monitoring terminals, and personal DIY projects. Thanks to the scalability of the ESP32-S3-N16RB module, it can lead to various interfaces. It not only has Crowtail's digital port, analog port, UART, and IIC interface, but also integrates a MEMS microphone, camera interface, and buzzer function. It supports ESP-IDF and Arduino IDE development and is compatible with Python/Micropython/Arduino. It also supports LVGL, which is the most popular free and open-source embedded graphics library to create beautiful UIs for any MCU, MPU, and display type.   
![Esp32spi 1.png](https://wiki.elecrow.com/images/thumb/5/52/Esp32spi_1.png/650px-Esp32spi_1.png){ loading=lazy }   
[![Alt text](../../assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/esp-terminal-3-5-inch-320-480-spi-tft-capacitive-touch-display-with-ov2640-camera.html)   
**Wizee ESP32 Display Series**   

**A: Wizee-ESP32 2.4 \*Intelligent Touch Screen Wi-Fi&BLE 240\*320 HMI Display\****   
*Elecrow Wizee ESP32 2.4-inch display is a powerful HMI touch screen with a 240*320 resolution LCD display. It uses the ESP32-WROOM-32 module as the main control processor, with a dual-core 32-bit LX6 microprocessor, integrated WiFi and Bluetooth wireless functions, a main frequency of up to 240MHz, providing powerful performance and versatile applications, suitable for IoT application devices and other scenes.

The Wizee ESP32 2.4-inch display is suitable for a wide range of scenes such as automotive HMI, medical equipment, industrial control, power, civil electronics, automation, GPS, new energy, and IoT application devices. Its various interfaces and expansion functions make it able to meet the needs of different fields, providing users with a more comprehensive solution.

**Model: [DIS03024H](https://www.elecrow.com/wizee-esp32-2-4-inch-intelligent-tft-lcd-touch-screen-240-320-hmi-display-compatible-with-arduino-lvgl.html)**   
![Image.png](https://wiki.elecrow.com/images/3/34/Image.png){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/wizee-esp32-2-4-inch-intelligent-tft-lcd-touch-screen-240-320-hmi-display-compatible-with-arduino-lvgl.html)


**B:Wizee-ESP32 2.8 \*Intelligent Touch Screen Wi-Fi&BLE 240\*320 HMI Display\****   
*Elecrow Wizee ESP32 2.8-inch display is a powerful HMI touch screen with a 240*320 resolution LCD display. It uses the ESP32-WROOM-32 module as the main control processor, with a dual-core 32-bit LX6 microprocessor, integrated WiFi and Bluetooth wireless functions, a main frequency of up to 240MHz, providing powerful performance and versatile applications, suitable for IoT application devices and other scenes.

**Model: [DIS03024H](https://www.elecrow.com/wizee-esp32-2-4-inch-intelligent-tft-lcd-touch-screen-240-320-hmi-display-compatible-with-arduino-lvgl.html)**   
![Image.png](https://wiki.elecrow.com/images/3/34/Image.png){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/wizee-esp32-2-4-inch-intelligent-tft-lcd-touch-screen-240-320-hmi-display-compatible-with-arduino-lvgl.html)

**C:Wizee-ESP32 3.5 \*Intelligent Touch Screen Wi-Fi&BLE 320\*480 HMI Display\****   
*Elecrow Wizee ESP32 3.5-inch display is a powerful HMI touch screen with a 320*480 resolution LCD display. It uses the ESP32-WROOM-32 module as the main control processor, with a dual-core 32-bit LX6 microprocessor, integrated WiFi and Bluetooth wireless functions, a main frequency of up to 240MHz, providing powerful performance and versatile applications, suitable for IoT application devices and other scenes.

**Model: [DIS03024H](https://www.elecrow.com/wizee-esp32-2-4-inch-intelligent-tft-lcd-touch-screen-240-320-hmi-display-compatible-with-arduino-lvgl.html)**   
![Image.png](https://wiki.elecrow.com/images/3/34/Image.png){ loading=lazy }

[![Alt text](https://wiki.elecrow.com/images/2/2f/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/wizee-esp32-2-4-inch-intelligent-tft-lcd-touch-screen-240-320-hmi-display-compatible-with-arduino-lvgl.html)


**D:Wizee-ESP32 4.3 \*Intelligent Touch Screen Wi-Fi&BLE 480\*272 HMI Display\****   
*Elecrow Wizee ESP32 4.3-inch display is a powerful HMI touch screen with a 480*272 resolution LCD display. It uses the ESP32-S3-WROOM-1-N4R2 module as the main control processor, with a dual-core 32-bit LX6 microprocessor, integrated WiFi and Bluetooth wireless functions, a main frequency of up to 240MHz,providing powerful performance and versatile applications, suitable for IoT application devices and other scenes.

**Model: [DIS03024H](https://www.elecrow.com/wizee-esp32-2-4-inch-intelligent-tft-lcd-touch-screen-240-320-hmi-display-compatible-with-arduino-lvgl.html)**   
![Image.png](https://wiki.elecrow.com/images/3/34/Image.png){ loading=lazy }

[![Alt text](https://wiki.elecrow.com/images/2/2f/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/wizee-esp32-2-4-inch-intelligent-tft-lcd-touch-screen-240-320-hmi-display-compatible-with-arduino-lvgl.html)

## **Development environment configuration**
--------

**1)SOFTWARE DOWNLOAD**

- 1.Please go to the official website https://www.arduino.cc/ to download the Arduino IDE development tool and download the corresponding [library file](https://drive.google.com/drive/folders/1Ot7eu2HhlgfzXu_Fgvm5NCnJcG4a0Cx2?usp=sharing), install the tool, click the start icon: open as shown in the figure:

![Esp32spi 5.png](https://wiki.elecrow.com/images/thumb/7/76/Esp32spi_5.png/469px-Esp32spi_5.png){ loading=lazy }

- 2.Click the "File" menu, select "Preferences" in the drop-down menu, and then the picture will appear: Unzip [the downloaded library file](https://drive.google.com/drive/folders/1Ot7eu2HhlgfzXu_Fgvm5NCnJcG4a0Cx2?usp=sharing) and put it in the libraries folder.

![Esp32spi 6.png](https://wiki.elecrow.com/images/thumb/d/de/Esp32spi_6.png/762px-Esp32spi_6.png){ loading=lazy }

- Add the ESP32 S3 URL as follows：

https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
![Esp32spi 7.png](https://wiki.elecrow.com/images/thumb/5/5e/Esp32spi_7.png/616px-Esp32spi_7.png){ loading=lazy }

- The tool automatically downloads and updates the corresponding model, check the steps as shown in the figure:

![Esp32rgb 6.png](https://wiki.elecrow.com/images/thumb/0/06/Esp32rgb_6.png/614px-Esp32rgb_6.png){ loading=lazy } 
![Esp32rgb 7.png](https://wiki.elecrow.com/images/thumb/0/0b/Esp32rgb_7.png/609px-Esp32rgb_7.png){ loading=lazy }


**2)SOFTWARE SETTING**   
Here you need to choose different chips and settings according to different screen chips,set as shown:

![ESP32-S3-WROOM-1U-N16R8.png](https://wiki.elecrow.com/images/b/b7/ESP32-S3-WROOM-1U-N16R8.png){ loading=lazy }

![ESP32-S3-WROOM-1U-N4R8.png](https://wiki.elecrow.com/images/d/d6/ESP32-S3-WROOM-1U-N4R8.png){ loading=lazy }

![ESP32-S3-WROOM-1U-N4R2.png](https://wiki.elecrow.com/images/7/74/ESP32-S3-WROOM-1U-N4R2.png){ loading=lazy }

![ESP32-WROOM-32-XXN4.png](https://wiki.elecrow.com/images/8/8f/ESP32-WROOM-32-XXN4.png){ loading=lazy }

- Warning:

If the CH340G driver is not installed on your PC, please install the CH340G driver first, or switch the SWITCH switch to the USB position and connect it with a USB cable.

**3)Download process**

- 1.Connect the motherboard and computer through a USB to type-c data cable;

![111.png](https://wiki.elecrow.com/images/thumb/7/72/111.png/804px-111.png){ loading=lazy }

- 2.Click on the tool on the arduino software and select the corresponding serial port number;

![Esp32spi 12.png](https://wiki.elecrow.com/images/7/71/Esp32spi_12.png){ loading=lazy }

- 3.Click to open the serial port assistant, then click the boot button on the motherboard, and then press the reset button until the serial port assistant displays "waiting for download".

![Esp32spi 13.png](https://wiki.elecrow.com/images/thumb/5/57/Esp32spi_13.png/473px-Esp32spi_13.png){ loading=lazy }

- 4.Click "upload" to upload the program to the ESP32 motherboard

![Esp32spi 14.png](https://wiki.elecrow.com/images/thumb/e/e7/Esp32spi_14.png/87px-Esp32spi_14.png){ loading=lazy }

- Until the prompt upload is successful, as shown in the figure:

![Esp32spi 15.png](https://wiki.elecrow.com/images/thumb/e/e6/Esp32spi_15.png/564px-Esp32spi_15.png){ loading=lazy }

## **Summarize**
------

In the first lesson, we learned the basic concepts and applications of the Human Machine Interface (HMI), while introducing the related ESP32 terminal screen family. We also learned how to configure the Arduino environment, which is an important step in the development of ESP32, which provides us with a convenient development platform. By using these screens and the related software environment, we can easily develop various graphical interfaces and user interfaces. In the following lessons, we will learn more deeply how to use various software and ESP32 to build various applications, so as to achieve richer and more complex functions.

## **Resources**
-------

- [esp terminal libraries](https://drive.google.com/drive/folders/1Ot7eu2HhlgfzXu_Fgvm5NCnJcG4a0Cx2?usp=sharing)

## **HMI Display Tutorial Contents**
-------

- Lesson01 Introducing the ESP32 Display series and environment configuration
- [Lesson02 Start the ESP32 DISPLAY GUI drawing via LovyanGFX Graphics Library](./lesson02-start-the-esp32-display-gui-drawing-via-lovyangfx-graphics-library.md)
- [Lesson03 How to Display Pictures on ESP32 Boards](./lesson03-how-to-display-pictures-on-esp32-boards.md)
- [Lesson04 LVGL Basics: How to install LVGL for ESP32 Displays](./lesson04-lvgl-basics-how-to-install-lvgl-for-esp32-displays.md)
- [Lesson05 Introduction to the 5 categories of LVGL GUI library Widgets](./lesson05-introduction-to-the-5-categories-of-lvgl-gui-library-widgets.md)
- [Lesson06 Use Squareline Studio to start your 1st human machine interface project](./lesson06-use-squareline-studio-to-start-your-1st-human-machine-interface-project.md)
- [Lesson07 How to implement text information input with Squareline Studio](./lesson07-how-to-implement-text-information-input-with-squareline-studio.md)
- [Lesson08 How to make the menu and a progress bar with Squareline Studio](./lesson08-how-to-make-the-menu-and-a-progress-bar-with-squareline-studio.md)
- [Lesson09 How to make an analysis report on ESP32 Display](./lesson09-how-to-make-an-analysis-report-on-esp32-display.md)
- [Lesson10 Create a 3D Printer UI Project on ESP32 Display](./lesson10-create-a-3d-printer-ui-project-on-esp32-display.md)
- [Lesson11 How to Make a Mixer Interface on ESP32 Display](./lesson11-how-to-make-a-mixer-interface-on-esp32-display.md)
- [Lesson12 Make Your ESP32 Display the Lantern Control terminal](./lesson12-make-your-esp32-display-the-lantern-control-terminal.md)
- [Lesson13 DIY Electronic Control Terminal on ESP32 Display with Squareline Studio](./lesson13-diy-electronic-control-terminal-on-esp32-display-with-squareline-studio.md)
- [Lesson14 Create Car Control Screen on ESP32 Display: A Step-by-Step Guide](./lesson14-create-car-control-screen-on-esp32-display-a-step-by-step-guide.md)
- [Lesson15 Smart Agriculture Monitoring: IoT-Based Real-Time ESP32 Display Project](./lesson15-smart-agriculture-monitoring-lot-based-real-time-esp32-display-project.md)
- [Lesson16 ESP32 Display for Smart Home Central Control: A Home Automation Solution](./lesson16-esp32-display-for-smart-home-central-control-a-home-automation-solution.md)



## **[Back to Main Content](../../Tutorials/lvgl-esp32-display-tutorial-a-step-by-step-guide-to-lvgl-gui-development.md)**
------