---
title: Crowtail- UV Sensor
---

## Description
-----------

The Crowtail- UV Sensor ML8511 is an easy to use ultraviolet light sensor. The MP8511 UV (ultraviolet) Sensor works by outputing an analog signal in relation to the amount of UV light that’s detected. This breakout can be very handy in creating devices that warn the user of sunburn or detect the UV index as it relates to weather conditions.

**Model: [CT0027UV](http://www.elecrow.com/crowtail-uv-sensor-p-1275.html)**

![Crowtail- Crowtail- UV Sensor.JPG](https://wiki.elecrow.com/images/thumb/d/df/Crowtail-_Crowtail-_UV_Sensor.JPG/600px-Crowtail-_Crowtail-_UV_Sensor.JPG){ loading=lazy }

## Specifications
--------------

Dimensions(mm):20.0(L)x20.0(W)x6.8(H)

## Usage
-----

The ML8511 sensor is very easy to use. It outputs a analog voltage that is linearly related to the measured UV intensity (mW/cm2). If your microcontroller can do an analog to voltage conversion, then you can detect the level of UV.

1.Hardware connection

The Crowtail- UV sensor connectde to the I port(A4 and A5) of Crowtail- based shiled.

![UVsenso.jpg](https://wiki.elecrow.com/images/thumb/c/c3/UVsenso.jpg/400px-UVsenso.jpg){ loading=lazy }

2.Grab the following example:

```
/* 
MP8511 UV Sensor Read Example
The MP8511 UV Sensor outputs an analog signal in relation to the amount of UV light it detects.
This sensor detects 280-390nm light most effectively. This is categorized as part of the UVB (burning rays)
spectrum and most of the UVA (tanning rays) spectrum.
There's lots of good UV radiation reading out there: 
*/
//Hardware pin definitions
int UVOUT = A5; //Output from the sensor
int REF_3V3 = A4; //3.3V power on the Arduino board
void setup()
{
 Serial.begin(9600);
 pinMode(UVOUT, INPUT);
 pinMode(REF_3V3, INPUT);
 Serial.println("MP8511 example");
}
void loop()
{
 int uvLevel = averageAnalogRead(UVOUT);
 int refLevel = averageAnalogRead(REF_3V3);
 //Use the 3.3V power pin as a reference to get a very accurate output value from sensor
 float outputVoltage = 3.3 / refLevel * uvLevel;  
 float uvIntensity = mapfloat(outputVoltage, 0.99, 2.9, 0.0, 15.0);
 Serial.print("MP8511 output: ");
 Serial.print(uvLevel);
 Serial.print(" MP8511 voltage: ");
 Serial.print(outputVoltage);
 Serial.print(" UV Intensity (mW/cm^2): ");
 Serial.print(uvIntensity);  
 Serial.println();  
 delay(100);
}
//Takes an average of readings on a given pin
//Returns the average
int averageAnalogRead(int pinToRead)
{
  byte numberOfReadings = 8;
  unsigned int runningValue = 0; 
  for(int x = 0 ; x < numberOfReadings ; x++)
    runningValue += analogRead(pinToRead);
  runningValue /= numberOfReadings;
  return(runningValue);  
}
//The Arduino Map function but for floats
float mapfloat(float x, float in_min, float in_max, float out_min, float out_max)
{
  return (x - in_min) * (out_max - out_min) / (in_max - in_min) + out_min;
}
```

3.Open the Serial Monitor to read the data.

![Result1.jpg](https://wiki.elecrow.com/images/d/d6/Result1.jpg){ loading=lazy }

## Resource
--------

- [UV Sensor Program](./files/MP8511-Read-Example-zip.md)
- [Crowtail- UV Sensor eagle files](./files/Crowtail-UV-Sensor-eagle-files-zip.md)