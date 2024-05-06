---
title: Crowtail- 3-Axis Digital Accelerometer
---

## Description
-----------

This is a high resolution digital accelerometer providing you at max 3.9mg/LSB resolution and large ±16g measurement range. It's base on an advanced 3-axis IC ADXL345. Have no worry to implement it into your free-fall detection project, cause it's robust enough to survive up to 10,000g shock. Meanwhile, it's agile enough to detect single and double taps. It's ideal for motion detection, Gesture detection as well as robotics.


**Model: [CT0056ADA](https://www.elecrow.com/crowtail-3axis-digital-accelerometer-16g-p-1512.html)**

![Crowtail- 3-Axis Digital Accelerometer.JPG](https://wiki.elecrow.com/images/thumb/6/6f/Crowtail-_3-Axis_Digital_Accelerometer.JPG/400px-Crowtail-_3-Axis_Digital_Accelerometer.JPG){ loading=lazy }

## Specification
-------------

- Input Voltage: 3.3V, 5V
- 3 axis sensing
- Small, low-profile package: 14-Terminal LGA
- High sensitivity
- Low power 0.1 mA in standby mode at VS = 2.5 V (typical)
- 10,000 g shock survival
- RoHS/WEEE lead-free compliant
- Crowtail compatible interface
- Dimensions(mm):20.0(L)x20.0(W)x9.8(H)

## Usage
-----

Every accelerometer has been individually tested before shipping to you. But in rare cases, you might need to reset the zero-offset by yourself.

Here below we show you how to read the raw data and obtain data in the unit of g, AKA g-force, from this accelerometer.  
![Crowtail- 3-Axis Digital Accelerometer(±16g)](https://wiki.elecrow.com/images/thumb/c/cf/Crowtail-_3-Axis_Digital_Accelerometer%28%C2%B116g%291.jpg/495px-Crowtail-_3-Axis_Digital_Accelerometer%28%C2%B116g%291.jpg){ loading=lazy }

1\. Plug it onto the I2C port of your [Crowtail- Base Shield](http://www.elecrow.com/crowtail-base-shield-p-1264.html).

2\. Download the [Crowtail- 3-Axis Digital Accelerometer Program](https://wiki.elecrow.com/images/d/d6/DigitalAccelerometer_ADXL345.zip) and unpack it into arduino-1.0\\libraries in your Arduino installation folder.

3\. Open the demo code directly by the path:File -&gt; Example -&gt;DigitalAccelerometer\_ADXL345-&gt;ADXL345\_demo\_code.

4\. Upload the code and open the serial monitor.

5\. Open the serial monitor to check the result.
![1.jpg](https://wiki.elecrow.com/images/f/f3/1.jpg){ loading=lazy }
![177.jpg](https://wiki.elecrow.com/images/2/2c/177.jpg){ loading=lazy }

The outputs of this sensor consist of two parts: raw data and 3-axis acceleration info converted into the unit of gravity, "g".

## Resource
--------

- [Crowtail- 3-Axis Digital Accelerometer Program](https://wiki.elecrow.com/images/d/d6/DigitalAccelerometer_ADXL345.zip)
- [Crowtail- 3-Axis Digital Accelerometer eagle files](https://wiki.elecrow.com/images/f/fb/Crowtail-_3-Axis_Digital_Accelerometer.zip)