---
title: Crowtail- Infrared Temperature Sensor
---

## Description
-----------

This module is based on the I2C light-to-digital converter TSL2561 to transform light intensity to a digital signal. Different from traditional analog light sensor, as Crowtail - Light Sensor, this digital module features a selectable light spectrum range due to its dual light sensitive diodes: infrared and full spectrum. You can switch among three detection modes to take your readings. They are infrared mode, full spectrum and human visible mode. When running under the human visible mode, this sensor will give you readings just close to your eye feelings.  
**Model: [CT0040DLS](http://www.elecrow.com/crowtail-digital-light-sensor-p-1488.html)**

![Crowtail- Digital Light Sensor1.JPG](https://wiki.elecrow.com/images/thumb/e/e2/Crowtail-_Digital_Light_Sensor1.JPG/600px-Crowtail-_Digital_Light_Sensor1.JPG){ loading=lazy }

## Features
--------

- Selectable detection modes
- Measuring Range:High resolution 16-Bit digital output at 400 kHz I2C Fast-Mode
- Wide dynamic range: 0.1 - 40,000 LUX
- Wide operating temperature range: -40°C to 85°C
- Programmable interrupt function with User-Defined Upper and lower threshold settings
- Dimensions(mm):20.0(L)x20.0(W)x9.7(H)

## Usage
-----

1.Hardware Connection
Plug the Crowtail - Digital Light Sensor onto the I2C port on Crowtail - Base Shield, and then plug the base shield onto Crowduino;

![CT0040DLS-0411.jpg](https://wiki.elecrow.com/images/thumb/c/c0/CT0040DLS-0411.jpg/600px-CT0040DLS-0411.jpg){ loading=lazy }

2.Download the library from here Digital Light Sensor Library \[[Digital Light Sensor Program](../../files/Digital-Light-Sensor-zip.md)\]

3.Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0.1\\libraries.

4.Create an Arduino sketch and paste the following codes to it or open the code directly by the path:File -&gt; Example -&gt;Digital\_Light\_Sensor-&gt;Digital\_Light\_Sensor.

```
#include <Wire.h>
#include <Digital_Light_TSL2561.h>
void setup()
{
  Wire.begin();
  Serial.begin(9600);
  TSL2561.init();
}

void loop()
{
  Serial.print("The Light value is: ");
  Serial.println(TSL2561.readVisibleLux());
  delay(1000);
}
```

5.Upload it into your Crowduino board and open the serial monitor to see the result.try to keep out light, observe the value change.

![CT0040DLS-05.png](https://wiki.elecrow.com/images/0/0b/CT0040DLS-05.png){ loading=lazy }

## Resource
--------

- [Digital Light Sensor Program](../../files/Digital-Light-Sensor-zip.md)
- [Crowtail- Digital Light Sensor eagle files](../../files/Crowtail-Digital-Light-Sensor-v1.0-zip.md)