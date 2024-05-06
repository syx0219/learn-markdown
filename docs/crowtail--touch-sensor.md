---
title: Crowtail- Touch Sensor
---

## Description
-----------

The Crowtail- Touch Sensor can help us use our body current to control the electronic device. It is connected to digital I/O port, it can generate a high voltage when we touch the touch pad.

**Model: [CT0012TS](http://www.elecrow.com/crowtail-touch-sensor-p-1230.html)**

![Crowtail- Touch Sensor.JPG](https://wiki.elecrow.com/images/thumb/4/4d/Crowtail-_Touch_Sensor.JPG/600px-Crowtail-_Touch_Sensor.JPG){ loading=lazy }

## Specifications
--------------

- Operating Voltage: 2.0 - 5.5V
- Output Response Time: 60 - 220mS
- Used Chipset:TTB223-BA6
- Dimensions(mm):20.0(L)x20.0(W)x6.8(H)

## Usage
-----

1.Hardware connection

![Touc.jpg](https://wiki.elecrow.com/images/thumb/d/d7/Touc.jpg/400px-Touc.jpg){ loading=lazy }

2.Copy the demo code to your sketch, then upload to Arduino or Crowduino board.

```
const int TouchPin=4;
const int ledPin=5;
void setup() {
pinMode(TouchPin, INPUT);
pinMode(ledPin,OUTPUT);
} 
  
void loop() {
int sensorValue = digitalRead(TouchPin);
if(sensorValue==1)
{
    digitalWrite(ledPin,HIGH);
}
else
{
  digitalWrite(ledPin,LOW);
 }
}
```

3.Touch the touch sensor,you will see the LED lights up.
![Touch Sensor result11.jpg](https://wiki.elecrow.com/images/thumb/6/69/Touch_Sensor_result11.jpg/400px-Touch_Sensor_result11.jpg){ loading=lazy } 
![Touch Sensor result22.jpg](https://wiki.elecrow.com/images/thumb/7/7b/Touch_Sensor_result22.jpg/400px-Touch_Sensor_result22.jpg){ loading=lazy }

## Resource
--------

- [Touch\_Sensor\_Program](./files/Touch-sersor-zip.md)
- [Touch\_Sensor\_eagle\_files](./files/Crowtail-Touch-Sensor-zip.md)