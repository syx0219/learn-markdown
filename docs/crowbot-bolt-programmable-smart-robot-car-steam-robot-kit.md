---
title: CrowBot-BOLT Programmable Smart Robot Car STEAM Robot Kit
---

## Description
-----------

CrowBot BOLT is a programmable educational car that can be easily used. It is small and beautiful in shape and easy to install. It uses ESP32-WROVER-B as the MCU, with Bluetooth and WiFi functions. It has a wealth of sensors(such as photodiode, ultrasonic sensor, line Tracking Sensor), can quickly realize functions such as light chasing, line tracking, obstacle avoidance, remote control, and light show. 
As an entry-level ESP32 programmed educational robot, the cool and cute Bolt makes robot programming learning, and teaching easy and fun. It comes with 16 lessons in three languages (Letscode, Ardunio, MicroPython), provides rich programming, and allows programming beginner to learn to program in the fun of creativity. It has reserved 2 expansion interfaces, which can be expanded and used with 150+ kinds of Crowtail modules. Unlimited creativity, waiting for you to discover!

**Model: [CRB00157C](https://www.elecrow.com/crowbot-bolt-programmable-smart-robot-car-steam-robot-kit.html)**
![Crowbot-bolt-mainpic-2.png](https://wiki.elecrow.com/images/thumb/1/16/Crowbot-bolt-mainpic-2.png/650px-Crowbot-bolt-mainpic-2.png){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/crowbot-bolt-programmable-smart-robot-car-steam-robot-kit.html?wiki "Title text")  

## Features
--------

- Support for Letscode, Arduino and Python
- Can be controlled by IR remote control, Bluetooth/WiFi control
- The car is equipped with ultrasonic, infrared tracking, photodiode and other sensors
- With 16 courses, it is the best choice for the entry of ESP32
- Equipped with on board indicator LED , through which you can intuitively understand the working condition of the car
- 4Pin I2C and A/D ports are reserved to connect Crowtail sensors, creating more possibilities
- Compatible with CrowBot Joystick, provides various methods to play

## Specifications
--------------

| **Item** | **Description** |
|---|---|
| MCU | ESP32-WROVER-B（8MB） |
| Programmatically | Letscode，Ardunio，Micropython |
| Control method | Bluetooth Remote Control/Infrared Remote Control |
| Input | Button, Photodiode, Infrared Receiving Module, Ultrasonic Sensor, Line Tracking Sensor |
| Output | Buzzer, Programmable RGB\_LED, Motor |
| Wifi&amp;Bluetooth | Supported |
| Photodiode | Can realize the function of chasing light or avoiding light |
| Ultrasonic Sensor(with RGB; 4Pin interface) | When an obstacle is detected, the driving route of the car can be corrected to avoid the obstacle |
| RPR220 Line Tracking Sensor | Can make the car move along the dark/black lines, intelligently judge and correct the driving path |
| Buzzer | Can make the car sing, bringing a more direct sensory experience |
| Programmable RGB\_LED | Through programming, it can show colorful lights in different scenes |
| Infrared receiver(3Pin interface) | Receive infrared remote control signals to realize remote control |
| Interface | Type c x1，I2C port x1，A/D port x1 |
| Motor type | N20 Gear Motor(drive: L9110S) |
| Operating Voltage | 3.3V~5V(AAA battery x4) |
| Work Temperature | -10℃~+55℃ |
| Dimension | 128\*92\*64mm |
| Weight | 200g |

## IO Port Diagram
---------------

### Top Overview

![Crowbot-bolt-FRONT-OVERVIEW.png](https://wiki.elecrow.com/images/6/67/Crowbot-bolt-FRONT-OVERVIEW.png){ loading=lazy }

### Bottom Overview

![Crowbot-bolt-BACK-OVERVIEW.png](https://wiki.elecrow.com/images/3/36/Crowbot-bolt-BACK-OVERVIEW.png){ loading=lazy }

## Usage
-----

### **CrowBot-BOLT Assambly Instrustion**

**STEP 1: Preparation**  
![Crowbot-bolt-assambly-preparation1.png](https://wiki.elecrow.com/images/thumb/b/ba/Crowbot-bolt-assambly-preparation1.png/700px-Crowbot-bolt-assambly-preparation1.png){ loading=lazy }  
**STEP 2: Install battery holder**  
Install 4 AAA batteries into the battery holder, and plug the cable of the battery holder into the 2pin battery(BAT) interface on the chassis.
![Crowbot-bolt-assambly-batteryholder1.png](https://wiki.elecrow.com/images/5/5a/Crowbot-bolt-assambly-batteryholder1.png){ loading=lazy }   **STEP 3: Install acrylic plates**   
![Crowbot-bolt-assambly-acrylic plates.png](https://wiki.elecrow.com/images/thumb/7/7d/Crowbot-bolt-assambly-acrylic_plates.png/800px-Crowbot-bolt-assambly-acrylic_plates.png){ loading=lazy }  
**STEP 4: Mounting wheels**  
![Crowbot-bolt-assambly-wheels.png](https://wiki.elecrow.com/images/thumb/6/61/Crowbot-bolt-assambly-wheels.png/800px-Crowbot-bolt-assambly-wheels.png){ loading=lazy }  
**STEP 5: Connect ultrasonic sensor**  
Insert the 4pin ultrasonic sensor into ultrasonic module interface on the chassis.   
![Crowbot-bolt-assambly-ulstrasonic sensor.png](https://wiki.elecrow.com/images/thumb/4/46/Crowbot-bolt-assambly-ulstrasonic_sensor.png/800px-Crowbot-bolt-assambly-ulstrasonic_sensor.png){ loading=lazy }

**STEP 6: Finish!**  
### **Factory Procedures**

**The factory default program has been loaded and you can play with CrowBot out of the box. But if you need to re-flash the program, please download [Factory\_source\_code.zip](https://www.elecrow.com/download/Crowbot/Factory_source_code.zip) to re-upload the factory default program. The folder contains a tutorial on how to set the Arduino for ESP32.**
![Crowbot-bolt-factory procedures1.png](https://wiki.elecrow.com/images/9/9c/Crowbot-bolt-factory_procedures1.png){ loading=lazy }  
### **Programming**

**Play with Python**

![Crowbot连线-01.png](https://wiki.elecrow.com/images/thumb/0/08/Crowbot%E8%BF%9E%E7%BA%BF-01.png/850px-Crowbot%E8%BF%9E%E7%BA%BF-01.png){ loading=lazy }  
Please download [Python\_Lessons\_Code.zip](./files/Python-code-zip.md). The folder contains 16 Python Lessons code, firmware and tutorial.  
![Crowbot python code.png](https://wiki.elecrow.com/images/6/6b/Crowbot_python_code.png){ loading=lazy }  
**Play with Arduino**

![Crowbot连线2-01.png](https://wiki.elecrow.com/images/thumb/5/5e/Crowbot%E8%BF%9E%E7%BA%BF2-01.png/850px-Crowbot%E8%BF%9E%E7%BA%BF2-01.png){ loading=lazy }  
Please download [Arduino\_Lessons\_Code.zip](./files/Arduino-code-zip.md). The folder contains 16 Arduino Lessons code, library needed and tutorial.  
![Crowbot arduino code.png](https://wiki.elecrow.com/images/1/12/Crowbot_arduino_code.png){ loading=lazy }  
**Play with Letscode**

![Crowbot-letscode.png](https://wiki.elecrow.com/images/thumb/7/7c/Crowbot-letscode.png/900px-Crowbot-letscode.png){ loading=lazy }  
Please download [Letscode\_Lessons\_Code.zip](./files/Letscode-code-zip.md).  
## FAQS
----

**Q1: How to connect CrowBot with Joystick via Bluetooth?**
**A1: Turn on the Bluetooth switch on CrowBot board.**

![20221229162644.png](https://wiki.elecrow.com/images/f/f7/20221229162644.png){ loading=lazy }  
**Q2: How to re-upload the factory default code to CrowBot and joystick?**  
**A2: 1. The factory default program files are ino files. Please download [Factory\_source\_code.zip](https://www.elecrow.com/download/Crowbot/Factory_source_code.zip) to re-upload the factory default program. The folder contains a tutorial on how to set the Arduino for ESP32.**


**Q3: Is there any WiFi connection tutorial or code?**
**A3: We didn't write the code to realize WiFi control function, you can DIY a project to make it come true.**

You can post your questions on our [forum](https://forum.elecrow.com/) or contact with techsupport@elecrow.com for technology support.

## Resources
---------

[Crowbot\_BOLT\_Beginner's\_Guide.pdf](https://www.elecrow.com/download/Crowbot/Crowbot_BOLT_Beginner%E2%80%99s_Guide.pdf)  
[Python\_Lessons\_Code.zip](./files/Python-code-zip.md)  
[Arduino\_Lessons\_Code.zip](./files/Arduino-code-zip.md)  
[Letscode\_Lessons\_Code.zip](./files/Letscode-code-zip.md)  
[Factory\_Source\_Code.zip](./files/Factory-source-code-zip.md)  
[CrowBot-BOLT\_Schematic.pdf](./files/CrowBot-BOLT-Schematic-pdf-pdf.md)  
[CrowBot-BOLT\_Eagle file\_SCH&amp;PCB](./files/CrowBot-V1.4-20220909-zip.md)  
[Joystick\_for\_Crowbot\_Eagle file\_SCH&amp;PCB](./files/Joystick-for-Crowbot-V1.1-20220913-zip.md)  
[CrowBot-BOLT\_Structural\_3D\_Model\_stp.zip](./files/CrowBot-BOLT-Structural-3D-Model-STPfile-zip.md)  