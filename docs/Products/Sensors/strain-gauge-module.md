---
title: Strain Gauge Module
---

## Description
-----------

A strain gaugeis a device used to measure strain on an object. This strain gauge module uses the strain gauge BF350-3AA to detect the strain, with the amplifier and potentiometer on the board to adjust the measured results, users can easily get the result with any microcontroller such as Arduino.  
This module can be positively used in measuring deformation (for example, across a bridge by loading positions and effects) in engineering and in physical distortions proportional to loading or thermal environments. In the everyday world, this module can be used to applications such as gating a traffic light into a new sequence when a car on a lightly traveled side-street enters a Tee-intersection.

**Model:[SEN77631Y3](http://www.elecrow.com/strain-gauge-module-p-735.html)**

![Strain Gauge Module.jpg](https://wiki.elecrow.com/images/thumb/e/e5/Strain_Gauge_Module.jpg/400px-Strain_Gauge_Module.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){loading=lazy}](https://www.elecrow.com/strain-gauge-module-p-735.html?wiki "Title text")

## Specification
-------------

- Working Voltage: 5VDC
- Analog Output 0~3.5VDC
- Potentiometer to adjust the zero point;
- Dimension: 32mm X 17mm

## Usage
-----

This example just a test.
1.Hardware Connection

![Strain Gauge Module hardware.jpg](https://wiki.elecrow.com/images/thumb/7/7e/Strain_Gauge_Module_hardware.jpg/600px-Strain_Gauge_Module_hardware.jpg){ loading=lazy }

2.Copy the below code to you new skecth,then upload it.

```
int sensorPin = A0;    // select the input pin for the Strain Gauge
int sensorValue = 0;  // variable to store the value coming from the sensor

void setup() {
  // declare the ledPin as an OUTPUT:
   Serial.begin(9600);  
}

void loop() {
  // read the value from the sensor:
  sensorValue = analogRead(sensorPin);    
  delay(1000);          
  Serial.print("sensor = " );                       
  Serial.println(sensorValue);                   
}
```

3.Open the serial monitor, put the sensor on your desk horizontally, and then press it, you can see the output value was change.

![Strain Gauge Module reslut.jpg](https://wiki.elecrow.com/images/thumb/d/d2/Strain_Gauge_Module_reslut.jpg/400px-Strain_Gauge_Module_reslut.jpg){ loading=lazy }

## Resource
--------

- [Demo code](https://wiki.elecrow.com/images/f/f4/Strain_Gauge.zip)
- [Datasheet](../../files/Coding-System-of-Strain-Gauges-AGS-TECH-Version-pdf.md)