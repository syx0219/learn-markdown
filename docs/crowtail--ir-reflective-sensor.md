---
title: Crowtail- IR Reflective Sensor
---

## Description
-----------

This module emits the infrared and estimates if there is a echo or not,then it generates logic HIGH or logic LOW to Arduino according to the result.it Can be used for detecting distance ,for example you can make a project to detect if the tank is full or not.

This IR reflective sensor utilizes a RPR-220 to detect distance. The RPR-220 is a reflective photosensor.The emitter is GaAs infrared light emitting diode and the detector is a high-sensitivity,silicon planar phototransistor. There is also an on-board potentiometer to adjust the sensitivity.

**Model: [CT0005IR](http://www.elecrow.com/crowtail-ir-reflective-sensor-p-1233.html)**

![Crowtail-IR Reflective Sensor.JPG](https://wiki.elecrow.com/images/thumb/9/9b/Crowtail-IR_Reflective_Sensor.JPG/600px-Crowtail-IR_Reflective_Sensor.JPG){ loading=lazy }

## Specification
-------------

- Voltage:5V
- Current：14.69 - 15.35 mA
- Effective Distance ：4-15 mm
- Dimensions(mm):20.0(L)x20.0(W)x16.6(H)

## Usage
-----

This sensor can be used to help a robot car follow a black line on white background or vice versa.

1.Hardware Connetion

The Crowtail- IR Reflective Sensor connected the D5 of Arduino.

![IR Reflective11.jpg](https://wiki.elecrow.com/images/thumb/4/41/IR_Reflective11.jpg/600px-IR_Reflective11.jpg){ loading=lazy }

2.Connect the board to PC using USB cable.

3.Upload the following sample sketch:

```
void setup()  
{
 Serial.begin(9600);
 pinMode(5,INPUT);
}
void loop() 
{
   delay(500);
   if(digitalRead(5)==LOW)  {
     Serial.println("Somebody is here.");
   }
   else  {
     Serial.println("nobody.");
   }
}
```

4.Open the serial monitor. Hold the sensor 12mm or other height you need above the background. After that,keep the distance and move the sensor horizontally above the black line.You can see the test result. When it on the black line,the serial print "nobody".

![IR Reflectiveresult.jpg](https://wiki.elecrow.com/images/b/bd/IR_Reflectiveresult.jpg){ loading=lazy }

## Resource
--------

- [IR\_reflective\_sensor Program](./files/IR-reflective-sensor-zip.md)
- [Crowtail- IR Reflective Sensor eagle files](./files/Crowtail-IR-Reflective-Sensor-zip.md)