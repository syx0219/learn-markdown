---
title: Crowbits-Ultrasonic Ranging Sensor
---

## Description
-----------

This HC-SR04 Ultrasonic Ranging Sensor is a non-contact distance measurement module with stable performance and high ranging accuracy, with the inexpensive price. The measurement range can be up to 5M, which would be helpful for your project such as robotic Obstacle Avoidance and so on.

![Crowbits-Ultrasonic-Ranging-Sensor-1.jpg](https://wiki.elecrow.com/images/thumb/d/de/Crowbits-Ultrasonic-Ranging-Sensor-1.jpg/600px-Crowbits-Ultrasonic-Ranging-Sensor-1.jpg){ loading=lazy }

## Features
--------

- High precision
- Stable

## Specification
-------------

- Ranging distance: 2cm to 500 cm
- Operating Voltage: 3.3V DC
- Dimensions: 31.5(L)\*24.5(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of digital display.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the D4 and D5 interface of the Crowbits-UNO board, as shown in the figure:

![Crowbits-Ultrasonic Ranging Sensor-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/6/64/Crowbits-Ultrasonic_Ranging_Sensor-Wiki_1.JPG/600px-Crowbits-Ultrasonic_Ranging_Sensor-Wiki_1.JPG){ loading=lazy }

3\. Download the library “Ultrasonic”. Unzip and put it in the libraries file, for example: C:\\Program Files (x86)\\Arduino\\libraries.

4\. Upload the following code to the Crowbits-UNO board.

```
#include <Ultrasonic.h>
Ultrasonic ultrasonic(4,5);//Init an Ultrasonic object
int Distance;
void setup() {
Serial.begin(9600);
}

void loop()
{
 Distance=ultrasonic.Ranging(CM);//get the current result;
 delay(100);
 Serial.print("the distance is ");
 Serial.println(Distance);
 delay(1000);
}
```

5\. After the upload is successful, open the serial port monitor, the baud rate is set to 9600. Put an object in front of the sensor, the serial port will print the corresponding distance, as shown in the figure:

![Crowbits-Ultrasonic Ranging Sensor-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/d/d7/Crowbits-Ultrasonic_Ranging_Sensor-Wiki_2.jpg/600px-Crowbits-Ultrasonic_Ranging_Sensor-Wiki_2.jpg){ loading=lazy }