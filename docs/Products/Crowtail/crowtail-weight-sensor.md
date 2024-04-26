---
title: Crowtail-Weight Sensor
---

## Description
-----------

This is a crowtail series of load cell kits, by using it, you can DIY their own electronic scales, and it is compatible with Arduino, it is also very convenient to use, in your Arduino project, and it can serve as a good Own role. It uses the **HX711** amplifier, **HX711** is a precision 24-bit analog-to-digital converter (ADC) designed for weighING scales and industrial control applications to interface directly with a bridge sensor and the measurement range of weight sensor is 0-3000g

**Model: [CRT94077W](https://www.elecrow.com/crowtail-weight-sensor.html)**
![Crowtail-weight sensor.jpg](https://wiki.elecrow.com/images/thumb/5/5b/Crowtail-weight_sensor.jpg/600px-Crowtail-weight_sensor.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png)](https://www.elecrow.com/crowtail-weight-sensor.html?wiki "Title text")

## Features
--------

- Crowtail interface
- Low standby current
- High accuracy

## Specifications
--------------

| **Item** | **Value** |
|---|---|
| Working Voltage | DC 5V |
| Working Current | 400mA |
| Standby current | 200uA |
| Operation temperature range | -40℃ to +85℃ |
| Weight sensor capacity | 3kg |
| Dimensions(mm) | 40.0(L)x20.0(W)x6.8(H) |

## Interface
---------

![Weight sensor interface.jpg](https://wiki.elecrow.com/images/thumb/7/77/Weight_sensor_interface.jpg/800px-Weight_sensor_interface.jpg){ loading=lazy }

## Platforms Supported
-------------------

| **Arduino** |
|:-:|
| ![Arduino.png](https://wiki.elecrow.com/images/6/63/Arduino.png){ loading=lazy } |

## Usage
-----

### Hardware

STEP1 Prepare the below stuffs:

| **Crowduino Uno**                                            | **Base Shield**                                              | **Crowtail-Weight Sensor**                            |
| :------------------------------------------------------------: | :------------------------------------------------------------: | :------------------------------------------------------------: |
| ![Crowduino 2.jpg](https://wiki.elecrow.com/images/thumb/d/d4/Crowduino_2.jpg/300px-Crowduino_2.jpg){ loading=lazy } | ![Crowtail-base shield 2.jpg](https://wiki.elecrow.com/images/thumb/c/cb/Crowtail-base_shield_2.jpg/200px-Crowtail-base_shield_2.jpg){ loading=lazy } | ![Crowtail-weight sensor 2.jpg](https://wiki.elecrow.com/images/thumb/4/47/Crowtail-weight_sensor_2.jpg/250px-Crowtail-weight_sensor_2.jpg){ loading=lazy } |
| [**Get one now**](https://www.elecrow.com/crowduino-unosd-v15-p-840.html) | [**Get one now**](https://www.elecrow.com/crowtail-base-shield-p-1264.html) | [**Get one now**](https://www.elecrow.com/crowtail-weight-sensor.html) |

STEP2 Plug Crowtail-Base Shield into Crowduino Uno;  
STEP3 Set Crowtail-Weight Sensor to I²C port of Crowtail-Base Shield;  
STEP4 Plug acrylic board to ABCD interface of Crowtail-Weight Sensor;  
STEP5 Connect Crowduino Uno to PC via a Mini USB cable.
![Weight sensor connection.jpg](https://wiki.elecrow.com/images/thumb/e/e1/Weight_sensor_connection.jpg/600px-Weight_sensor_connection.jpg){ loading=lazy }  

| ==**NOTE**==                                                    |
| ------------------------------------------------------------ |
| ==If we don't have Crowtail Base Shield, We also can directly connect this module to Crowduino Uno as below.== | 

| **Crowduino Uno** | **Weight Sensor** |
|:-:|:-:|
| A4(J7) | SDA |
| A5(J7) | SCL |
| 5V | VCC |
| GND | GND |

### Software

STEP 1.Download program files[WeightSensorProgramFiles.zip](../../files/WeightSensorProgramFiles-zip.md)  
STEP2 Configure controller board&amp;communication port  
On top of the Arduino IDE, click “Tools&gt;Board&gt;” and select “Arduino Uno” from the available options  
![SELECT BOARD.png](https://wiki.elecrow.com/images/thumb/c/c5/SELECT_BOARD.png/700px-SELECT_BOARD.png){ loading=lazy }  
Select the COM port that indicates Arduino Uno. Please note that the actual numbers after the “COM” word will vary from computer to computer, so they could be different from the ones shown in the figure.  
![S 2 2.png](https://wiki.elecrow.com/images/thumb/d/d5/S_2_2.png/700px-S_2_2.png){ loading=lazy }  
STEP3 Install Library: Unzip the WeightSensorProgramFiles.zip file and copy folder hx711 to the Libraries directory under the Arduino installation directory  
![Weight sensor libraries.jpg](https://wiki.elecrow.com/images/thumb/f/f2/Weight_sensor_libraries.jpg/600px-Weight_sensor_libraries.jpg){ loading=lazy }  
STEP4 Load the program file SerialScale.ino to Arduino IDE  

```
// Hx711.DOUT - pin #A1
// Hx711.SCK - pin #A0

#include "HX711.h"

//Hx711 scale(SCL, SDA);

void setup() {
  Init_Hx711();
    Get_Maopi();   //clear the weight 
        delay(3000);

  Serial.begin(9600);

}

void loop() {

  Serial.print(abs(Get_Weight()), 1);
  Serial.println(" g");

  //delay(10);
}
```

STEP5 Click the ![Upload.png](../../assets/images/30px-Upload.png){ loading=lazy } to upload the code to the Crowduino board  
STEP6 After the program is burned, open the serial port monitor of Arduino IDE, set baud rate to 9600, and put no weight on the acrylic board, then the serial port print will be 0G, as shown in the figure:  
![WEIGHT SENSOR DATA1.jpg](https://wiki.elecrow.com/images/thumb/1/1e/WEIGHT_SENSOR_DATA1.jpg/600px-WEIGHT_SENSOR_DATA1.jpg){ loading=lazy }  
STEP7 Put the weight on the acrylic plate, and the serial port will print the corresponding weight. For example, if I put a 50g weight, the serial port will print 50g, and the serial port print value is consistent with the actual value, as shown in the figure:  
![WEIGHT SENSOR CON2.jpg](https://wiki.elecrow.com/images/thumb/0/08/WEIGHT_SENSOR_CON2.jpg/600px-WEIGHT_SENSOR_CON2.jpg){ loading=lazy }    
![WEIGHT SENSOR DATA2.jpg](https://wiki.elecrow.com/images/thumb/e/e1/WEIGHT_SENSOR_DATA2.jpg/600px-WEIGHT_SENSOR_DATA2.jpg){ loading=lazy }  

## FAQS
----

You can list you question here or contact with techsupport@elecrow.com for technology support.

## Resources
---------

[Crowtail-Weight\_Sensor-V2.0-Eagle.zip](../../files/Crowtail-Weight-Sensor-V2.0-Eagle-zip.md)  
[WeightSensorProgramFiles.zip](../../files/WeightSensorProgramFiles-zip.md)