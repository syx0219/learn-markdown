---
title: Barometer Sensor
---

## Description
-----------

This Barometer Sensor has a Bosch BMP085 which is a high-accuracy chip to detect barometric pressure and temperature. It can widely measure pressure ranging from 300hPa to 1100hPa, AKA +9000m to -500m above sea level, with a super high accuracy of 0.03hPa(0.25m) in ultra-high resolution mode. This Barometer sensor compatible with 3.3V and 5V, so it can be used in Arduinos without moditdfication.

**Model:[STH01002S](http://www.elecrow.com/barometer-sensor-p-399.html)**

![Bmp085 Sensor.jpg](https://wiki.elecrow.com/images/thumb/6/61/Bmp085_Sensor.jpg/400px-Bmp085_Sensor.jpg){ loading=lazy }

## Features
--------

- Wide pressure range
- Arduino/Crowduino compatible interface (3.3V or 5V)
- I2C interface
- Fully calibrated
- Low power consumption: 5μA at 1 sample/sec. in standard mode
- Low noise:

```
   0.06hPa(0.5m) in ultra-low power mode
   0.03hPa(0.25m) in ultra-high resolution mode
```

- Possibility to lower to 0.1m(rms noise)

## Usage
-----

Barometric condition is one of the criteria used to predict coming change in weather and deduce altitude above sea level. Here is a demo to show you how to read the barometric data from this Barometer Sensor.

1.Hardware connection


![Bmp085 Sensor hardware.jpg](https://wiki.elecrow.com/images/thumb/5/59/Bmp085_Sensor_hardware.jpg/600px-Bmp085_Sensor_hardware.jpg){ loading=lazy }

2.Download [the library](../../files/Barometer-zip.md)  
3.Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0.1\\libraries.  
4.Create a new Arduino sketch and paste the codes below to it or open the code directly by the path:File -&gt; Examples -&gt;Barometer-&gt;Barometer\_Sensor.

```
/* Barometer demo V1.0
* Get pressure, altitude, and temperature from the BMP085.
* Serial.print it out at 9600 baud to serial monitor.
*
*/
#include "Barometer.h"
#include <Wire.h>
float temperature;
float pressure;
float atm;
float altitude;
Barometer myBarometer;
void setup(){
  Serial.begin(9600);
  myBarometer.init();
  
}

void loop()
{
   temperature = myBarometer.bmp085GetTemperature(myBarometer.bmp085ReadUT()); //Get the temperature, bmp085ReadUT MUST be called first
   pressure = myBarometer.bmp085GetPressure(myBarometer.bmp085ReadUP());//Get the temperature
   altitude = myBarometer.calcAltitude(pressure); //Uncompensated caculation - in Meters 
   atm = pressure / 101325; 
  
  Serial.print("Temperature: ");
  Serial.print(temperature, 2); //display 2 decimal places
  Serial.println("deg C");

  Serial.print("Pressure: ");
  Serial.print(pressure, 0); //whole number only.
  Serial.println(" Pa");

  Serial.print("Ralated Atmosphere: ");
  Serial.println(atm, 4); //display 4 decimal places

  Serial.print("Altitude: ");
  Serial.print(altitude, 2); //display 2 decimal places
  Serial.println(" m");

  Serial.println();

  delay(1000); //wait a second and get values again.
}

```

5.Open the serial monitor.You should see the data from BMP085.

![Bmp085result.jpg](https://wiki.elecrow.com/images/thumb/f/f6/Bmp085result.jpg/400px-Bmp085result.jpg){ loading=lazy }

## Resource
--------

- [Barometer Program](../../files/Barometer-zip.md)