---
title: Soil Moisture Sensor
---

## Description
-----------

This Moisture Sensor can be used to detect the moisture of soil or your pet plant's water level, let the plants in your garden reach out for human help. With the Octopus Electronic Bricks interface can very easy to used with [the sensor shield V4.0](https://www.elecrow.com/sensor-shield-v40-for-arduino-p-335.html).  
This sensor uses the two probes to pass current through the soil, and then it reads that resistance to get the moisture level. More water makes the soil conduct electricity more easily (less resistance), while dry soil conducts electricity poorly (more resistance).  
**Module：[SPM32100S](https://www.elecrow.com/soil-moisture-sensor-p-509.html)**

![13995200420 1.jpg](https://wiki.elecrow.com/images/thumb/4/45/13995200420_1.jpg/500px-13995200420_1.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){loading=lazy}](https://www.elecrow.com/soil-moisture-sensor-p-509.html?wiki "Title text")

## Specification
-------------

| **Item** | **Value** |
|---|---|
| Power supply | 3.3v or 5v |
| Output voltage signal | 0~4.2v |
| Current | 35mA |

## Interface
---------

![Moisture port.png](https://wiki.elecrow.com/images/thumb/2/25/Moisture_port.png/300px-Moisture_port.png){ loading=lazy }

## Platforms Supported
-------------------

| **Arduino** |
|:-:|
| ![Arduino.png](https://wiki.elecrow.com/images/6/63/Arduino.png){ loading=lazy } |

## Usage
-----

### **Hardware**

STEP1 Prepare the below stuffs:  

| **Crowduino Uno**                                            | **Sensor Shield For Arduino**                                | **Moisture Sensor**                                          |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![Crowduino 2.jpg](https://wiki.elecrow.com/images/thumb/d/d4/Crowduino_2.jpg/300px-Crowduino_2.jpg) | ![13995196110 2.jpg](https://wiki.elecrow.com/images/thumb/0/0f/13995196110_2.jpg/300px-13995196110_2.jpg) | ![13995200420 1.jpg](https://wiki.elecrow.com/images/thumb/4/45/13995200420_1.jpg/300px-13995200420_1.jpg) |
| [**Get one now**](https://www.elecrow.com/crowduino-unosd-v15-p-840.html) | [**Get one now**](https://www.elecrow.com/sensor-shield-v40-for-arduino-p-335.html) | [**Get one now**](https://www.elecrow.com/soil-moisture-sensor-p-509.html) |

STEP2 Plug Sensor Shield For Arduino into Crowduino;  
STEP3 Plug Moisture Sensor into A0 port on the Sensor Shield with cable;  
STEP4 Connect Crowduino to PC via a Mini USB cable.  
![20220607095448.png](https://wiki.elecrow.com/images/thumb/3/33/20220607095448.png/600px-20220607095448.png){ loading=lazy }

| ==**NOTE**== |
|---|
| ==If we don't have Sensor Shield For Arduino, We also can directly connect this module to Crowduino Uno as below.== |

| **Crowduino Uno** | **Moisture Sensor** |
|:-:|:-:|
| A0 | SIG |
| 5V | VCC |
| GND | GND |

## Software
--------

STEP1 Download [MoistureSample.zip](https://wiki.elecrow.com/images/e/e0/MoistureSample.zip)  
STEP2 Configure controller board&amp;communication port  
On top of the Arduino IDE, click “Tools&gt;Board&gt;” and select “Arduino Uno” from the available options  
![SELECT BOARD.png](https://wiki.elecrow.com/images/thumb/c/c5/SELECT_BOARD.png/700px-SELECT_BOARD.png){ loading=lazy }  
Select the COM port that indicates Arduino Uno. Please note that the actual numbers after the “COM” word will vary from computer to computer, so they could be different from the ones shown in the figure.  
![S 2 2.png](https://wiki.elecrow.com/images/thumb/d/d5/S_2_2.png/700px-S_2_2.png){ loading=lazy }  
STEP3 Load the program in the Arduino IDE  
![Moisture sample.png](https://wiki.elecrow.com/images/8/84/Moisture_sample.png){ loading=lazy }  
STEP4 Click the ![Upload.png](../../assets/images/30px-Upload.png){ loading=lazy } to upload the code to the Crowduino board  
STEP5 After the program is downloaded, open the Serial Monitor of Arduino IDE, set baud rate to 9600, and the value of soil moisture will be printed  
STEP6 Put the sensor in different environments, look at the printed value, in different environments, the value will change    
1.Put the sensor in the air, and the printed value is 0;  
2.Put the sensor in the water to read the value;  
![Moisture sensor data1.png](https://wiki.elecrow.com/images/thumb/4/4d/Moisture_sensor_data1.png/600px-Moisture_sensor_data1.png){ loading=lazy }  
3.Touch the sensor with your hand
![Moisture sensor data2.png](https://wiki.elecrow.com/images/thumb/c/cd/Moisture_sensor_data2.png/600px-Moisture_sensor_data2.png){ loading=lazy }

## FAQs
----

You can list you question here or contact with techsupport@elecrow.com for technology support.

## Resources
---------

[Moisture\_Sensor\_Eagle\_file.zip](https://wiki.elecrow.com/images/0/0c/Crowtail-_Moisture_Sensor_Eagle_file.zip)  
[MoistureSample.zip](https://wiki.elecrow.com/images/e/e0/MoistureSample.zip)