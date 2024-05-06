---
title: Crowtail- Hall Sensor
---

## Description
-----------

The Crowtail- Hall Sensor uses the Allegro™ A1101 Hall-effect switches are next generation replacements for the popular Allegro312x and 314x lines of unipolar switches.It measures the Hall Effect, which is a production of a voltage difference across an electrical conductor, transverse to an electric current in the conductor as well as a magnetic field perpendicular to the current. The output of the continuous-time switch Hall sensor switches low(turns on) when a magnetic field (south polarity) perpendicular to the Hall sensor exceeds the BOP threshold, and it switches high( turn off) when the magnetic field disappears.

**Model: [CT0024HS](http://www.elecrow.com/crowtail-hall-sensor-p-1261.html)**

![Crowtail- Hall Sensor.JPG](https://wiki.elecrow.com/images/thumb/b/bd/Crowtail-_Hall_Sensor.JPG/600px-Crowtail-_Hall_Sensor.JPG){ loading=lazy }

## Features
--------

- Crowtail Compatible Interface
- 400ns transition period for rise and fall.
- Continuous-time hall effect sensor
- Reverse battery protection

## Specification
-------------

Dimensions(mm):20.0(L)x20.0(W)x6.8(H)

| Item | Min | Typical | Max | Unit |
|:-:|:-:|:-:|:-:|:-:|
| Voltage | 3.8 | 5.0 | 24 | V |
| Current | 4.1 | - | 24 | mA |
| Operating Temperature | -40 | - | 85 | ºC |

## Usage
-----

1.Hardware Connection

Connect the Hall Sensor to Digital port 4 of the Crowtail - Basic Shield using a 3 pin cable and connect Crowtail-LED to Digital Port 5.Then connect Arduino to PC by using a USB cable.

![Hallcontrolled1.jpg](https://wiki.elecrow.com/images/thumb/6/69/Hallcontrolled1.jpg/600px-Hallcontrolled1.jpg){ loading=lazy }

2.Upload the following sample sketch:

```
const int hall= 4;//PIN 4
const int led= 5;//PIN 5
void setup()
{
 pinMode(hall,INPUT); 
 pinMode(led,OUTPUT);
}
void loop()
{
  if(digitalRead(hall)==LOW){
  digitalWrite(led,HIGH);
 }
 else{
 digitalWrite(led,LOW);
 }
 delay(500);
}
```

3.When the magnet near the hall sensor, the LED will light up.
![Hall Sensor result11.jpg](https://wiki.elecrow.com/images/thumb/d/d3/Hall_Sensor_result11.jpg/500px-Hall_Sensor_result11.jpg){ loading=lazy } 
![Hall Sensor result22.jpg](https://wiki.elecrow.com/images/thumb/2/27/Hall_Sensor_result22.jpg/500px-Hall_Sensor_result22.jpg){ loading=lazy }

## Resource
--------

- [Hall sensor Program](./files/Hall-sensor-zip.md)
- [Crowtail\_Hall\_Sensor\_eagle\_files](./files/Crowtail-Hall-Sensor-eagle-files-zip.md)