---
title: Crowbits-HTU21D Humiture Sensor
---

## Description
-----------

Our Crowbits add a new sensor about environmental monitoring that called Crowbits-HTU21D Humiture Sensor, which is a low-cost, easy to use, highly accurate, digital humidity and temperature sensor. The sensor outputs the calibrated digital signal in standard I2C format. HTU21D series module designed for low-power/small-volume application design, with good quality, fast response speed, anti-interference ability, cost-effective advantages, very low power consumption. It’s ideal for environmental sensing and data logging and perfect for a weather stations or humidor control systems.

![Crowbits-HTU21D-Humiture-Sensor--1.jpg](https://wiki.elecrow.com/images/thumb/6/67/Crowbits-HTU21D-Humiture-Sensor--1.jpg/600px-Crowbits-HTU21D-Humiture-Sensor--1.jpg){ loading=lazy }

## Features
--------

- Low-cost
- High precision

## Specification
-------------

- Interface Type: I2C
- Operating Voltage: 3.3V DC
- Dimensions: 56(L)\*56(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1.You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2.Connect the module to the I2C interface of the Crowbits-UNO board, as shown in the figure:

![Crowbits-HTU21D Humiture Sensor-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/b/b6/Crowbits-HTU21D_Humiture_Sensor-Wiki_1.JPG/600px-Crowbits-HTU21D_Humiture_Sensor-Wiki_1.JPG){ loading=lazy }

3.Download the library SparkFunHTU21D. Unzip and put it in the libraries file, for example: C:\\Program Files (x86)\\Arduino\\libraries.

4.Upload the following code to the Crowbits-UNO board.

```
/* 
 HTU21D Humidity Sensor Example Code
 By: Nathan Seidle
 SparkFun Electronics
 Date: September 15th, 2013
 License: This code is public domain but you buy me a beer if you use this and we meet someday (Beerware license).
 
 Uses the HTU21D library to display the current humidity and temperature
 
 Open serial monitor at 9600 baud to see readings. Errors 998 if not sensor is detected. Error 999 if CRC is bad.
  
 Hardware Connections (Breakoutboard to Arduino):
 -VCC = 3.3V
 -GND = GND
 -SDA = A4 (use inline 330 ohm resistor if your board is 5V)
 -SCL = A5 (use inline 330 ohm resistor if your board is 5V)

 */

#include <Wire.h>
#include "SparkFunHTU21D.h"

//Create an instance of the object
HTU21D myHumidity;

void setup()
{
  Serial.begin(9600);
  Serial.println("HTU21D Example!");

  myHumidity.begin();
}

void loop()
{
  float humd = myHumidity.readHumidity();
  float temp = myHumidity.readTemperature();

  Serial.print("Time:");
  Serial.print(millis());
  Serial.print(" Temperature:");
  Serial.print(temp, 1);
  Serial.print("C");
  Serial.print(" Humidity:");
  Serial.print(humd, 1);
  Serial.print("%");

  Serial.println();
  delay(1000);
}
```

5\. After the upload is successful, open the serial port monitor, the baud rate is set to 9600. The serial port will print out the current temperature and humidity values.

![Crowbits-HTU21D Humiture Sensor-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/7/76/Crowbits-HTU21D_Humiture_Sensor-Wiki_2.jpg/600px-Crowbits-HTU21D_Humiture_Sensor-Wiki_2.jpg){ loading=lazy }