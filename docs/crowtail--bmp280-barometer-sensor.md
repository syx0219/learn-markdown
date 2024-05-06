---
title: Crowtail- BMP280 Barometer Sensor
---

## Introduction
------------

The Crowtail-BMP280 Barometer Sensor is a breakout board for Bosch BMP280 high-precision and low-power digital barometer.It can be used to measure temperature and atmospheric pressure accurately. It can be connected to a microcontroller with I2C. As the atmospheric pressure changes with altitude, it can also measure approximate altitude of a place. We have also provided highly abstracted library to make this product easier to use.

**Model**: [CRT00289B](https://www.elecrow.com/catalog/product/view/id/3032/)

![Crowtail- BMP280 Barometer Sensor.jpg](https://wiki.elecrow.com/images/thumb/2/27/Crowtail-_BMP280_Barometer_Sensor.jpg/500px-Crowtail-_BMP280_Barometer_Sensor.jpg){ loading=lazy }

## Featrue
-------

- Smaller footprint, lower power consumption, lower noise measurements, lower RMS noise
- Higher resolutions for pressure and temperature, higher measuring rate
- Easy-to-use Crowtail Compatible Interface
- Can be used as an altimeter with accuracy of ±1 meter

## Specification
-------------

- Supply Voltage: 5V or 3.3V
- Current Consumption: 0.6 mA
- Barometric Pressure Measure

```
 Range: 300 – 1100 hPa
 Accuracy: ±1.0 hPa
```

- Temperature Measurement

```
 Range: -40 to 85
 Accuracy: ±1
```

- Interface: I2C
- Crowtail Port: I2C
- Dimensions(mm):20.0(L)x20.0(W)x9.8(H)

## **Usage**
---------

1\. Plug it onto the IIC port of Crowtail - Base Shield using a Crowtail cable.

2.Plug the Crowtail - Base Shield onto Arduino.

3\. Connect Arduino to PC by using a USB cable.

![Exampleddddd1.jpg](https://wiki.elecrow.com/images/thumb/a/aa/Exampleddddd1.jpg/600px-Exampleddddd1.jpg){ loading=lazy }

4.You can find development library [here](./files/BMP280-zip.md)

5\. Copy and paste code below to a new Arduino sketch, and upload it to your Arduino

```


#include "BMP280.h"
#include <Wire.h>

BMP280 bmp280;

void setup()
{
  Serial.begin(9600);
  if(!bmp280.init()){
    Serial.println("Device error!");
  }
}

void loop()
{
  float pressure;
  
  //get and print temperatures
  Serial.print("Temp: ");
  Serial.print(bmp280.getTemperature());
  Serial.println("C"); // The unit for  Celsius because original arduino don't support speical symbols
  
  //get and print atmospheric pressure data
  Serial.print("Pressure: ");
  Serial.print(pressure = bmp280.getPressure());
  Serial.println("Pa");
  
  //get and print altitude data
  Serial.print("Altitude: ");
  Serial.print(bmp280.calcAltitude(pressure));
  Serial.println("m");
  
  Serial.println("\n");//add a line between output of different times.

  delay(1000);
}
```

5.When you upload the code complete,you can see the result via the serial port debug window

![Edsge.png](https://wiki.elecrow.com/images/a/a1/Edsge.png){ loading=lazy }