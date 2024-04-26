---
title: Crowtail-IMU 10DOF
---

## Description
-----------

This is a 10 DOF IMU sensor which is built on MPU-9250 and BMP280, MPU-9250 is a 9-aixs motion tracking device that combines a 3-axis gyroscope, 3-axis accelerometer, 3-axis magnetometer and a Digital Motion Processor (DMP) in a 3\*3\*1mm package, finally add a barometer- BMP280, so it becomes a 10DOF IMU, it’s smaller in sizes with less power consumption, so use it with mobile phone or aircraft, smart wear devices will be more suitable.
User-programmable full-scale range (digital output) and high accuracy of temp/pressure measurement make it meet the ideal for motion tracking and environment monitoring. Its crowtail interface take easy and simple use experience for your Arduino projects.

**Model: [CRT35038I](https://www.elecrow.com/crowtail-imu-10dof.html)**  
![Crwotail-imu 10dof 1.jpg](https://wiki.elecrow.com/images/thumb/3/3b/Crwotail-imu_10dof_1.jpg/500px-Crwotail-imu_10dof_1.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png)](https://www.elecrow.com/crowtail-imu-10dof.html "Title text")

## Features
--------

- Crowtail interface
- 10 Degrees of Freedom
- 3-Axis angular rate sensor (gyro) with a sensitivity up to 131 LSB and a full-scale range of ±250, ±500, ±1000, and ±2000°/sec
- 3-Axis accelerometer with a programmable full scale range of ±2g, ±4g, ±8g and ±16g
- 3-axis compass with a full scale range of ±4800 uT
- Wide pressure detecting range of 300~1100hPa(+9000m ~ -500m relating to sea level)
- Temperaure measurement with ±1.0°C accuracy
- User-programmable full-scale range (digital output)
- Barometric pressure measurement range 300 - 1100 hPa with ±1.0 hPa accuracy
- Programmable interrupt

## Specifications
--------------

| **Item** | **Value** |
|---|---|
| Input Voltage | 5V/3.3V |
| Working Current | 6mA |
| Working Temperature | -40 – 85℃ |
| Size | 20\*40mm |
| Weight | 3g |

## Interface
---------

![IMU interface.jpg](https://wiki.elecrow.com/images/thumb/d/d1/IMU_interface.jpg/800px-IMU_interface.jpg){ loading=lazy }

## Platforms Supported
-------------------

| **Arduino** |
|:-:|
| ![Arduino.png](https://wiki.elecrow.com/images/6/63/Arduino.png){ loading=lazy } |

## Usage
-----

### Hardware

STEP1 Prepare the below stuffs:  

| **Crowduino Uno**                                            | **Base Shield**                                              | **Crowtail- IMU 10DOF**                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![Crowduino 2.jpg](https://wiki.elecrow.com/images/thumb/d/d4/Crowduino_2.jpg/300px-Crowduino_2.jpg){ loading=lazy } | ![Crowtail-base shield 2.jpg](https://wiki.elecrow.com/images/thumb/c/cb/Crowtail-base_shield_2.jpg/200px-Crowtail-base_shield_2.jpg){ loading=lazy } | ![Crwotail-imu 10dof 1.jpg](https://wiki.elecrow.com/images/thumb/3/3b/Crwotail-imu_10dof_1.jpg/250px-Crwotail-imu_10dof_1.jpg){ loading=lazy } |
| [**Get one now**](https://www.elecrow.com/crowduino-unosd-v15-p-840.html) | [**Get one now**](https://www.elecrow.com/crowtail-base-shield-p-1264.html) | [**Get one now**](https://www.elecrow.com/crowtail-imu-10dof.html) |

STEP2 Plug Crowtail-Base Shield into Crowduino Uno;  
STEP3 Plug Crowtail- IMU 10DOF into I2C port on the Crowtail-Base Shield I Port with Crowtail cable;STEP4 Connect Crowduino Uno to PC via a Mini USB cable.  

| ==**NOTE**== |
|---|
| ==If we don't have Crowtail Base Shield, We also can directly connect this module to Crowduino Uno as below.== |

### Software

STEP1 Download [IMU10lib\_Arduino\_Library.zip](../../files/IMU10lib-Arduino-Library-zip.md)  
STEP2 Configure controller board&amp;communication port  
On top of the Arduino IDE, click “Tools&gt;Board&gt;” and select “Arduino Uno” from the available options  
![SELECT BOARD.png](https://wiki.elecrow.com/images/thumb/c/c5/SELECT_BOARD.png/700px-SELECT_BOARD.png){ loading=lazy }  
Select the COM port that indicates Arduino Uno. Please note that the actual numbers after the “COM” word will vary from computer to computer, so they could be different from the ones shown in the figure.
![S 2 2.png](https://wiki.elecrow.com/images/thumb/d/d5/S_2_2.png/800px-S_2_2.png){ loading=lazy }  
STEP3 Install Library: Unzip the IMU10lib\_Arduino\_Library.zip file and copy it to the Libraries directory under the Arduino installation directory  
![IUM10lib.jpg](https://wiki.elecrow.com/images/7/70/IUM10lib.jpg){ loading=lazy }  
STEP4 Open Arduino IDE and load IMU\_10DOF\_Test：click “File→Examples→IMU10lib\_Arduino\_Library→IMU\_10DOF\_Test”  
![IMU 10DOF TEST.jpg](https://wiki.elecrow.com/images/thumb/4/49/IMU_10DOF_TEST.jpg/800px-IMU_10DOF_TEST.jpg){ loading=lazy }  
STEP5 Click the ![Upload.png](../../assets/images/30px-Upload.png){ loading=lazy } to upload the code to the Crowduino board  
STEP6 After the program is downloaded, open the Serial Monitor of Arduino IDE, set baud rate to 56700，information will be printed show as follow:  
![IMU data.jpg](https://wiki.elecrow.com/images/thumb/7/7b/IMU_data.jpg/800px-IMU_data.jpg){ loading=lazy }

## FAQS
----

You can list you question here or contact with techsupport@elecrow.com for technology support.

## Resources
---------

[IMU10lib\_Arduino\_Library.zip](../../files/IMU10lib-Arduino-Library-zip.md)  
[Crowtail-\_IMU\_10DOF\_V2.0\_Eagle\_files.zip](../../files/Crowtail-IMU-10DOF-V2.0-Eagle-files-zip.md)