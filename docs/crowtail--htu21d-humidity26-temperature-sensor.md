---
title: Crowtail- HTU21D Humidity& Temperature Sensor
---

## Description
-----------

Crowtail- HTU21D Humidity &amp;Temperature sensor is a low-cost, easy to use, highly accurate, digital humidity and temperature sensor. And the work voltage range about this sensor is 1.5V-3.6V, so we need to use the AMS1117 to achieve step-down when we want it work with our crowduino which has a 5V voltage output. The sensor outputs the calibrated digital signal in standard I2C format. Diversified output mode, wide operating voltage range, while high temperature accuracy and humidity accuracy. HTU21 series module designed for low-power/small-volume application design, with good quality, fast response speed, anti-interference ability, cost-effective advantages, very low power consumption. It’s ideal for environmental sensing and data logging and perfect for a weather stations or humidor control systems. All you need is connect the specific crowtail port into the arduino/crowduino by using a crowtail cable.

**Model: [CRT02120H](https://www.elecrow.com/crowtail-htu21d-humidity-temperature-sensor.html)**
![Crowtail-htu21d humidity temperature 1.jpg](https://wiki.elecrow.com/images/thumb/f/fe/Crowtail-htu21d_humidity_temperature_1.jpg/600px-Crowtail-htu21d_humidity_temperature_1.jpg){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png)](https://www.elecrow.com/crowtail-htu21d-humidity-temperature-sensor.html?wiki "Title text")

## Specifications
--------------

| **Item** | **Value** |
|---|---|
| Input voltage | 5V |
| Humidity measurement range | 0-100% RH |
| Temperature measurement range | -40 ℃ -105 ℃ |
| Maximum power consumption | 2.7uW |
| Communication | I2C |
| Humidity accuracy range (10% RH to 95% RH) | HTU21D ± 2% RH |
| Load Weight | 1KG |
| Humidity hysteresis | ± 1% RH |
| Measurement time | 50ms |
| Annual drift | -0.5% RH / year |
| Response time | 5s |
| Dimensions(mm) | 20.0(L)x20.0(W)x9.8(H) |

## Interface
---------

![Htu21.jpg](https://wiki.elecrow.com/images/thumb/c/cf/Htu21.jpg/700px-Htu21.jpg){ loading=lazy }

## Platforms Supported
-------------------

| **Arduino** |
|:-:|
| ![Arduino.png](https://wiki.elecrow.com/images/6/63/Arduino.png){ loading=lazy } |

## Usage
-----

### **Hardware**

STEP1 Prepare the below stuffs: 

| **Crowduino Uno**                                            | **Base Shield**                                              | **Crowtail- HTU21D Humidity &amp;Temperature sensor**                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![Crowduino 2.jpg](https://wiki.elecrow.com/images/thumb/d/d4/Crowduino_2.jpg/300px-Crowduino_2.jpg){ loading=lazy } | ![Crowtail-base shield 2.jpg](https://wiki.elecrow.com/images/thumb/c/cb/Crowtail-base_shield_2.jpg/200px-Crowtail-base_shield_2.jpg){ loading=lazy } | ![Crowtail-htu21d humidity temperature 1.jpg](https://wiki.elecrow.com/images/thumb/f/fe/Crowtail-htu21d_humidity_temperature_1.jpg/300px-Crowtail-htu21d_humidity_temperature_1.jpg){ loading=lazy } |
| [**Get one now**](https://www.elecrow.com/crowduino-unosd-v15-p-840.html) | [**Get one now**](https://www.elecrow.com/crowtail-base-shield-p-1264.html) | [**Get one now**](https://www.elecrow.com/crowtail-htu21d-humidity-temperature-sensor.html) | 

STEP2 Plug Crowtail-Base Shield into Crowduino Uno;  
STEP3 Plug HTU21D Humidity&amp;Temperature Sensor into I2C port on the Crowtail-Base Shield I Port with Crowtail cable;  
STEP4 Connect Crowduino Uno to PC via a Mini USB cable.  
![Htu21con.jpg](https://wiki.elecrow.com/images/thumb/0/0b/Htu21con.jpg/700px-Htu21con.jpg){ loading=lazy }  

| ==**NOTE**== |
|---|
| ==If we don't have Crowtail Base Shield, We also can directly connect this module to Crowduino Uno as below.== |

| **Crowduino Uno** | **Weight Sensor** |
|:-:|:-:|
| A4(J7) | SDA |
| A5(J7) | SCL |
| 5V | VCC |
| GND | GND |

### **Software**

STEP 1.Download files[SparkFun\_HTU21D\_Breakout\_Arduino\_Library-master.zip](./files/SparkFun-HTU21D-Breakout-Arduino-Library-master-zip.md)  
STEP2 Configure controller board&amp;communication port  
On top of the Arduino IDE, click “Tools&gt;Board&gt;” and select “Arduino Uno” from the available options  
![SELECT BOARD.png](https://wiki.elecrow.com/images/thumb/c/c5/SELECT_BOARD.png/700px-SELECT_BOARD.png){ loading=lazy }  
Select the COM port that indicates Arduino Uno. Please note that the actual numbers after the “COM” word will vary from computer to computer, so they could be different from the ones shown in the figure.  
![S 2 2.png](https://wiki.elecrow.com/images/thumb/d/d5/S_2_2.png/700px-S_2_2.png){ loading=lazy }  
STEP 3 Install Library: Unzip the SparkFun\_HTU21D\_Breakout\_Arduino\_Library-master.zip file and copy it to the Libraries directory under the Arduino installation directory  
![20220512162348.png](https://wiki.elecrow.com/images/2/2c/20220512162348.png){ loading=lazy }  
STEP4 Open Arduino IDE and load SparkFun\_HTU21D\_RegisterReading：click “File→Examples→SparkFun HTU21D Humidity and Temperature Sensor Breakout→SparkFun\_HTU21D\_RegisterReading”  
![20220512162625.png](https://wiki.elecrow.com/images/thumb/f/f8/20220512162625.png/700px-20220512162625.png){ loading=lazy }  
STEP5 Click the ![Upload.png](./assets/images/30px-Upload.png){ loading=lazy } to upload the code to the Crowduino board  
STEP6 After the program is downloaded, open the Serial Monitor of Arduino IDE, set baud rate to 9600, and the value of humidity and temperature will be printed,such as shown in the figure
![Htu21 data.jpg](https://wiki.elecrow.com/images/thumb/9/9e/Htu21_data.jpg/600px-Htu21_data.jpg){ loading=lazy }

## FAQS
----

You can list you question here or contact with techsupport@elecrow.com for technology support.

## Resources
---------

[Crowtail-\_HTU21D\_Humidity%26Temperature\_Sensor\_eagle\_file.zip](./files/Crowtail-HTU21D-Humidity%26Temperature-Sensor-eagle-file-zip.md)  
[SparkFun\_HTU21D\_Breakout\_Arduino\_Library-master.zip](./files/SparkFun-HTU21D-Breakout-Arduino-Library-master-zip.md)  
[HTU21D\_datasheet.pdf](./files/HTU21D-datasheet-pdf.md)  