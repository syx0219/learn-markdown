---
title: Crowbits-Digital Light Sensor
---

## Description
-----------

This module is based on the I2C light-to-digital converter TSL2561 to transform light intensity to a digital signal. Different from traditional analog light sensor, this digital module features a selectable light spectrum range due to its dual light sensitive diodes: infrared and full spectrum.

![Crowbits-Digital-Light-Sensor-1.jpg](https://wiki.elecrow.com/images/thumb/9/9c/Crowbits-Digital-Light-Sensor-1.jpg/600px-Crowbits-Digital-Light-Sensor-1.jpg){ loading=lazy }

## Features
--------

- Programmable interrupt function with User-Defined Upper and lower threshold settings
- Easy to use

## Specification
-------------

- Interface Type: I2C
- Operating Voltage: 3.3V DC
- Dimensions: 31.5(L)\*24.5(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the I2C interface on the Crowbits-UNO board, as shown in the figure:

![Crowbits-Digital Light Sensor-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/2/27/Crowbits-Digital_Light_Sensor-Wiki_1.JPG/600px-Crowbits-Digital_Light_Sensor-Wiki_1.JPG){ loading=lazy }

3\. Download the library “Digital\_Light\_Sensor”. Unzip and put it in the libraries file, for example: C:\\Program Files (x86)\\Arduino\\libraries.

4\. Upload the following code to the Crowbits-UNO board.

```
/*
 * Digital_Light_Sensor.ino
 * A library for TSL2561
 * Permission is hereby granted, free of charge, to any person obtaining a copy
 * of this software and associated documentation files (the "Software"), to deal
 * in the Software without restriction, including without limitation the rights
 * to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
 * copies of the Software, and to permit persons to whom the Software is
 * furnished to do so, subject to the following conditions:
 *
 * The above copyright notice and this permission notice shall be included in
 * all copies or substantial portions of the Software.
 *
 * THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
 * IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
 * FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
 * AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
 * LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
 * OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
 * THE SOFTWARE.
 */

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

5\. After the upload is successful, open the serial port monitor, the baud rate is set to 9600. The stronger the light, the greater the output value, as shown in the figure:

![Crowbits-Digital Light Sensor-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/d/d7/Crowbits-Digital_Light_Sensor-Wiki_2.jpg/600px-Crowbits-Digital_Light_Sensor-Wiki_2.jpg){ loading=lazy }