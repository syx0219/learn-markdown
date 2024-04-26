---
title: Crowtail- I2C Color Sensor
---

## Description
-----------

This module is based on the color sensor TCS3414CS with digital output I2C. Based on the 8\*2 array of filtered photodiodes and 16-bits analog-to-digital converters, you can gain the color chromaticity of ambient light or the color of objects. Of the 16 photodiodes, 4 have red filters, 4 have green filters, 4 have blue filters and 4 have no filter(clear). With the synchronization input pin, external pulsed light source can provides precise synchronous conversion control.

**Model: [CT0067ICS](http://www.elecrow.com/crowtail-i2c-color-sensor-p-1523.html)**

![Crowtail- I2C Color Sensor2.JPG](https://wiki.elecrow.com/images/thumb/4/4a/Crowtail-_I2C_Color_Sensor2.JPG/400px-Crowtail-_I2C_Color_Sensor2.JPG){ loading=lazy }

## Specification
-------------

- Crowtail compatible interface
- 16-Bit digital output with I 2C at 400 kHz
- SYNC Input Synchronizes Integration Cycle to Modulated Light Sources
- Operating temperature range -40°C to 85°C
- Programmable interrupt function with User-Defined Upper and lower threshold settings
- Dimensions(mm):20.0(L)x20.0(W)x13.6(H)

## Usage
-----

![Crowtail- I2C Color Sensor1.jpg](https://wiki.elecrow.com/images/thumb/b/b1/Crowtail-_I2C_Color_Sensor1.jpg/600px-Crowtail-_I2C_Color_Sensor1.jpg){ loading=lazy }

1.Download [Crowtail- I2C Color Sensor library](../../files/I2C-Color-Sensor1-zip.md); Unzip and put it in the libraries file : ..\\arduino-1.0\\libraries;

2.Open "colorview" example via the path: File --&gt; Examples --&gt; Adafruit TCS34725 --&gt;colorview.

```
#include <Wire.h>
//#include <math.h>
#include <IICColorSensor.h>

void setup()
{
	Serial.begin(9600);
	Wire.begin();
}

void loop()
{
	int red, green, blue;
	IICColorSensor colorSensor;
	colorSensor.ledStatus = 1;							// When turn on the color sensor LED, ledStatus = 1; When turn off the color sensor LED, ledStatus = 0.
	while(1)
	{
		colorSensor.readRGB(&red, &green, &blue);		//Read RGB values to variables.
		delay(300);
		Serial.print("The RGB value are: RGB( ");
		Serial.print(red,DEC);
		Serial.print(", ");
		Serial.print(green,DEC);
		Serial.print(", ");
		Serial.print(blue,DEC);
	    Serial.println(" )");
		colorSensor.clearInterrupt();
	}
}
```

3.Upload it into your Arduino board and have a test.

## Resource
--------

- [Crowtail- I2C Color Sensor Program](../../files/I2C-Color-Sensor1-zip.md)
- [Crowtail- I2C Color Sensor eagle files](../../files/Crowtail-I2C-Color-Sensor-eagle-files-zip.md)