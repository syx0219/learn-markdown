---
title: Crowtail- Analog Grayscale Sensor
---

## Description
-----------

Here comes Elecrow's new Analog Ambient Light Sensor. Brand new design and much more convenient to use.This module help you to detect the light density and reflect the analog voltage signal back to Arduino controller. You can set the threshold of voltage level to trigger motors, relays or other actuators.

**Model: [CT010448A](https://www.elecrow.com/crowtail-analog-grayscale-sensor-p-1675.html)**

![Crowtail- Analog Grayscale Sensor Servo.jpg](https://wiki.elecrow.com/images/thumb/b/b0/Crowtail-_Analog_Grayscale_Sensor_Servo.jpg/600px-Crowtail-_Analog_Grayscale_Sensor_Servo.jpg){ loading=lazy }

## Specification
-------------

- Supply Voltage: 3.3V to 5V
- Interface: Analog
- Dimensions(mm):20.0(L)x20.0(W)x6.8(H)

## Usage
-----

Here is an example showing how to turn on the Crowtail- Analog Grayscale Sensor.

1\. Plug it onto the Analog port 0 of Crowtail - Base Shield using a Crowtail cable.

2.Plug the Crowtail - Base Shield onto Arduino.

3\. Connect Arduino to PC by using a USB cable.

![Analog grayscale0011.jpg](https://wiki.elecrow.com/images/thumb/9/91/Analog_grayscale0011.jpg/600px-Analog_grayscale0011.jpg){ loading=lazy }

4\. Copy and paste code below to a new Arduino sketch, and upload it to your Arduino.

```
void setup()
{
  Serial.begin(9600); // open serial port, set the baud rate to 9600 bps
}
void loop()
{
      int val;
      val=analogRead(0);   //connect grayscale sensor to Analog 0
      Serial.println(val,DEC);//print the value to serial        
      delay(100);
}
```

5.When you upload the code complete,you can see the led light and you can measure the gray of different objects and see the result via the serial port debug window

![20160524184003.png](https://wiki.elecrow.com/images/thumb/3/30/20160524184003.png/300px-20160524184003.png){ loading=lazy }

## Resource
--------

- [Crowtail- Analog Grayscale Sensor eagle file](./files/Crowtail-Analog-Grayscale-Sensor-eagle-files-zip.md)