---
title: Crowtail- Water Sensor
---

## Description
-----------

This sensor works by having a series of exposed traces connected to ground and interlaced between the grounded traces are the sens traces. The sensor traces have a weak pull-up resistor of 1 MΩ. The resistor will pull the sensor trace value high until a drop of water shorts the sensor trace to the grounded trace. Believe it or not this circuit will work with the digital I/O pins of your Arduino or you can use it with the analog pins to detect the amount of water induced contact between the grounded and sensor traces.

**Model: [CT0042CWS](http://www.elecrow.com/crowtail-water-sensor-p-1490.html)**

![Crowtail-Water Sensor2.JPG](https://wiki.elecrow.com/images/thumb/6/66/Crowtail-Water_Sensor2.JPG/400px-Crowtail-Water_Sensor2.JPG){ loading=lazy }

## Specification
-------------

- Crowtail compatible interface
- Low power consumption
- High sensitivity
- Working voltage:4.75v - 5.25v
- Working temperature:10℃ - 30℃
- Dimensions(mm):40.0(L)x20.0(W)x6.8(H)

## Applications Ideas
------------------

- Rainfall detecting
- Liquid leakage
- Tank overflow detector

## Usage
-----

This demo simplely for using the Water sensor to control the LED.
1.Hardware Connection
Connect the module to the Basic board using digital pin 2. LED using digital pin 5.


2.Download [Crowtail- Water\_sensor](https://wiki.elecrow.com/images/b/be/Crowtail-Water_sensor.zip) for Arduino boards with 16MHz XTAL; Unzip and put it in the libraries file of Arduino IDE by the path: ..\\arduino-1.0\\libraries;

3.Open “Crowtail\_Water\_Sensor” example via the path: File --&gt; Examples --&gt; Crowtail\_Water\_Sensor

```
const int ledpin=5;
const int sensor = 2;
void setup()
{
  pinMode(ledpin,OUTPUT);
  pinMode(sensor,INPUT); 
}
void loop()
{
  if(！digitalRead(sensor)){
  digitalWrite(ledpin,HIGH);
 }
 else{
 digitalWrite(ledpin,LOW);
 }
}
```

4.Upload it into your Crowduino board and drop water on the surface of sensor. The LED light up when the sensor is damp. Have a try!

![CT0042CWS-051.jpg](https://wiki.elecrow.com/images/thumb/f/f5/CT0042CWS-051.jpg/400px-CT0042CWS-051.jpg){ loading=lazy }
![CT0042CWS-061.jpg](https://wiki.elecrow.com/images/thumb/7/75/CT0042CWS-061.jpg/400px-CT0042CWS-061.jpg){ loading=lazy }

## Resource
--------

- [Crowtail-Water sensor Program](https://wiki.elecrow.com/images/b/be/Crowtail-Water_sensor.zip)
- [Crowtail-Water Sensor v1.0 eagle files](https://wiki.elecrow.com/images/1/1a/Crowtail-Water_Sensor_v1.0.zip)