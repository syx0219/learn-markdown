---
title: Crowtail- Flame Sensor
---

## Description
-----------

The flame sensor can be used to detect fire and the other light sources which's wavelength at 760nm~1100nm ,it's based on the YG1006 sensor which is a fast response and high photo senstivity NPN silicon phototransistor. Due to its black epoxy, the sensor is sensitive to infrared radiation. In fire fighting robot game, The sensor plays a very important role, it can be used as a robot eyes to find the fire source.

**Model: [CT0052CFS](https://www.elecrow.com/crowtail-flame-sensor.html)**

![CT0052CFS-07.jpg](https://wiki.elecrow.com/images/thumb/6/64/CT0052CFS-07.jpg/600px-CT0052CFS-07.jpg){ loading=lazy }

## Features
--------

- Work Voltage: 3.3V ~ 5V
- Crowduino interface
- Easy to use
- Sensitivity can adjustable
- Dimensions(mm):32.0(L)x20.0(W)x9.8(H)

## Usage
-----

This demo is going to show you how to detect fire.

1.Hardware Connection
The flame sensor is connecting to digital port D2 of Crowtail - Base Shield. Crowtail-LED is connecting to D5.

![Crowtail flame Sensor271.jpg](https://wiki.elecrow.com/images/thumb/9/9f/Crowtail_flame_Sensor271.jpg/600px-Crowtail_flame_Sensor271.jpg){ loading=lazy }

2.Download [Flame\_sensor library](../../files/Flame%20sensor-zip.md) for Crowduino boards with 16MHz XTAL; Unzip and put it in the libraries file of Arduino IDE by the path: ..\\arduino-1.0\\libraries;

3.Open “Flame\_Sensor” example via the path: File --&gt; Examples --&gt; Flame\_Sensor

```
 const int ledpin=5;
const int  Flame_Sensor = 2;
void setup()
{
  pinMode(ledpin,OUTPUT);
  pinMode(Flame_Sensor,INPUT); 
}
void loop()
{
  if(digitalRead( Flame_Sensor)){
  digitalWrite(ledpin,LOW);
 }
 else{
 digitalWrite(ledpin,HIGH);
 }
}
 
```

4.Upload it into your Crowduino board and adjust your silp resisitance. Pay attentiong to the Crowtail-LED and LED light on the module when you put the fire far away from sensor about 10cm.

![Crowtail-flame-sensor11.jpg](https://wiki.elecrow.com/images/thumb/5/54/Crowtail-flame-sensor11.jpg/400px-Crowtail-flame-sensor11.jpg){ loading=lazy }

## Resource
--------

- [Flame\_sensor Program](../../files/Flame%20sensor-zip.md)
- [Crowtail- Flame Sensor v1.0](../../files/Crowtail-Flame-Sensor-zip.md)