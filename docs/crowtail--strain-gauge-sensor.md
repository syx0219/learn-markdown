---
title: Crowtail- Strain Gauge sensor
---

## Description
-----------

A strain gauge is a device used to measure strain on an object. This strain gauge module uses the strain gauge BF350-3AA to detect the strain, with the amplifier and potentiometer on the board to adjust the measured results, users can easily get the result with any microcontroller such as Arduino. This module can be positively used in measuring deformation (for example, across a bridge by loading positions and effects) in engineering and in physical distortions proportional to loading or thermal environments. In everyday, this module can be used to applications such as gating a traffic light into a new sequence when a car on a lightly traveled side-street enters a Tee-intersection. For better using on our crowduino, we add a crowtail port so that you can plug and use directly.


**Model: [CT0070SGS](https://www.elecrow.com/crowtail-strain-gauge-sensor-p-1562.html)**
![Crowtail-strain gauge sensor.png](https://wiki.elecrow.com/images/thumb/d/d2/Crowtail-strain_gauge_sensor.png/600px-Crowtail-strain_gauge_sensor.png){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png)](https://www.elecrow.com/crowtail-strain-gauge-sensor-p-1562.html?wiki "Title text")

## Features
--------

- Working Voltage: 5VDC
- Analog Output: 0~3.5VDC
- Potentiometer to adjust the zero point
- Dimension: 32mm X 17mm

## Interface
---------

![Strain gauge sensor interface.png](https://wiki.elecrow.com/images/thumb/c/cd/Strain_gauge_sensor_interface.png/800px-Strain_gauge_sensor_interface.png){ loading=lazy }
![Strain gauge sensor SCH.png](https://wiki.elecrow.com/images/5/53/Strain_gauge_sensor_SCH.png){ loading=lazy }

## Platforms Supported
-------------------

| **Arduino** |
|:-:|
| ![Arduino.png](https://wiki.elecrow.com/images/6/63/Arduino.png){ loading=lazy } |

## Usage
-----

### Hardware

STEP1 Prepare the below stuffs:  

| **Crowduino Uno**                                            | **Base Shield**                                              | **Crowtail- Strain Gauge Sensor**                            |
| :------------------------------------------------------------: | :------------------------------------------------------------: | :------------------------------------------------------------: |
| ![Crowduino 2.jpg](https://wiki.elecrow.com/images/thumb/d/d4/Crowduino_2.jpg/300px-Crowduino_2.jpg){ loading=lazy } | ![Crowtail-base shield 2.jpg](https://wiki.elecrow.com/images/thumb/c/cb/Crowtail-base_shield_2.jpg/200px-Crowtail-base_shield_2.jpg){ loading=lazy } | ![Crowtail-strain gauge sensor.png](https://wiki.elecrow.com/images/thumb/d/d2/Crowtail-strain_gauge_sensor.png/300px-Crowtail-strain_gauge_sensor.png){ loading=lazy } |
| [**Get one now**](https://www.elecrow.com/crowduino-unosd-v15-p-840.html) | [**Get one now**](https://www.elecrow.com/crowtail-base-shield-p-1264.html) | [**Get one now**](https://www.elecrow.com/crowtail-strain-gauge-sensor-p-1562.html) |

STEP2 Plug Crowtail-Base Shield into Crowduino Uno;STEP3 Plug Crowtail-Strain Gauge Sensor to A0 slot of Crowtail-Base Shield via 4 pin Crowtail Cable;STEP4 Connect Crowduino Uno to PC via a Mini USB cable.  

| ==**NOTE**==                                                    |
| ------------------------------------------------------------ |
| ==If we don't have Crowtail Base Shield, We also can directly connect this module to Crowduino Uno as below.== |

| **Crowduino Uno** | **Crowtail- Strain Gauge Sensor** |
|:-:|:-:|
| ANALOG 0 | SIG |
| 5V | VCC |
| GND | GND |

### **Software**

STEP1 Download program files [Strain\_gauge\_sensor.zip](./files/Strain-gauge-sensor-zip.md)  
STEP2 Configure controller board&amp;communication port  
On top of the Arduino IDE, click “Tools&gt;Board&gt;” and select “Arduino Uno” from the available options  
![SELECT BOARD.png](https://wiki.elecrow.com/images/thumb/c/c5/SELECT_BOARD.png/700px-SELECT_BOARD.png){ loading=lazy }  
Select the COM port that indicates Arduino Uno. Please note that the actual numbers after the “COM” word will vary from computer to computer, so they could be different from the ones shown in the figure.  
![S 2 2.png](https://wiki.elecrow.com/images/thumb/d/d5/S_2_2.png/700px-S_2_2.png){ loading=lazy }  
STEP3 Open the program in the Arduino IDE  
![S 3.png](https://wiki.elecrow.com/images/5/52/S_3.png){ loading=lazy }  
```
const int sensor=A5;
int sensorValue = 0;   
void setup()
{
  Serial.begin(9600); 
}
void loop()
{
  sensorValue = analogRead(sensor);
   Serial.print("sensor value= " );
  Serial.println(sensorValue); 
  delay(500);
}
```

STEP4 Click the ![Upload.png](./assets/images/30px-Upload.png){ loading=lazy } to upload the code to the Crowduino board  
STEP5 After the program is burned, open the serial monitor of Arduino IDE. Adjust the sliding rheostat until the serial monitor prints about 300. Then gently bend the strain gauge and you will see the serial monitor output changes from 0 to 700.

## FAQS
----

You can list you question here or contact with techsupport@elecrow.com for technology support.

## Resources
---------

[Strain\_gauge\_sensor.zip](./files/Strain-gauge-sensor-zip.md)  
[Crowtail-\_Strain\_Gauge\_sensor\_v2.0-Eagle.zip](./files/Crowtail-Strain-Gauge-sensor-v2.0-Eagle-zip.md)  
[datasheet](./files/Coding-System-of-Strain-Gauges-AGS-TECH-Version-pdf.md)  