---
title: Crowtail- Thumb Joystick
---

## Description
-----------

Crowtail- Thumb Joystick is a Crowtail compatible module which is very similar to the 'analog' joystick on PS2 (PlayStation 2) controllers. Two direction movements will output different analog signals as they are actually two potentiometers. The resistor is ~10k for each. The joystick also has a push button that is could be used for special applications. When the module is in working mode it will output two analog values representing two directions. The value is restricted in a little smaller range (e.g 200~700)compared to the normal joystick, while it is around 1023 when the button is pushed, so that the MCU can detect the action of pressing.

**Model: [CT0020TJ](http://www.elecrow.com/crowtail-thumb-joystick-p-1270.html)**

![Crowtail- Thumb Joystickh.JPG](https://wiki.elecrow.com/images/thumb/e/e4/Crowtail-_Thumb_Joystickh.JPG/600px-Crowtail-_Thumb_Joystickh.JPG){ loading=lazy }

## Features
--------

- 5V/3.3V Compatible
- Analog Output

## Application
-----------

- Robot remot
- Game Controller

## Specifications
--------------

Dimensions(mm):40.0(L)x27.0(W)x40.0(H)

| Item | Min | Typical | Max | Unit |
|:-:|:-:|:-:|:-:|:-:|
| Working Voltage | 4.75 | 5.0 | 5.25 | V |
| Output Analog Value （X coordinate） | 200 | 516 | 800 | / |
| Output Analog Value （Y coordinate） | 200 | 516 | 800 | / |

## Usage
-----

The Crowtial - Thumb Joystick is an analog device that outputs analog signal ranging from 0 to 1023. That requires us to use the analog port of Arduino to take the readings.

1\. Connect the module to the A5/A4 of Crowtail - Basic Shield using the 4-pin Crowtail cable.

2\. Plug the Crowtail - Basic Shield into Arduino or Crowduino.

3.Connect Arduino or Crowduino to PC by using a USB cable.

![Joystick.JPG](https://wiki.elecrow.com/images/thumb/1/18/Joystick.JPG/600px-Joystick.JPG){ loading=lazy }

4.Copy and paste code below to a new Arduino sketch, upload.

```
/*
 Thumb Joystick demo v1.0
 connect the module to A4&A5 for using;
*/

 void setup() {
 Serial.begin(9600);
}

void loop() {
 int sensorValue1 = analogRead(A5);
 int sensorValue2 = analogRead(A4);
 Serial.print("The X and Y coordinate is:");
 Serial.print(sensorValue1, DEC);
 Serial.print(",");
 Serial.println(sensorValue2, DEC);
 Serial.println(" ");
 delay(200);
}
```

5\. You can check the values of the output analog signals by opening the Serial Monitor.

![Joystick result.png](https://wiki.elecrow.com/images/1/1f/Joystick_result.png){ loading=lazy }

## Resource
--------

- [Thumb Joystick Program](./files/Joystick-zip.md)
- [Crowtail- Thumb Joystick eagle files](./files/Crowtail-Thumb-Joystick-eagle-files-zip.md)