---
title: Crowtail- PIR Motion Sensor
---

## Description
-----------

This is a simple to use PIR motion（Passive Infrared Detection） sensor with Crowtail compatible interface. Simply connect it to Crowtail base shield and program it, when anyone moves in its detecting range, the sensor outputs HIGH on its SIG pin. The detecting range can be adjusted by a potentiometer soldered on its circuit board, The max detecting range of it up to 6 meters. This version has a large lens which can support long range and wide angle. 2.54mm standard connector is easy to fix it anywhere.

**Model: [CT0057PIR](http://www.elecrow.com/crowtail-pir-motion-sensor-p-1518.html)**

![Crowtail- PIR Motion Sensor.JPG](https://wiki.elecrow.com/images/thumb/1/1c/Crowtail-_PIR_Motion_Sensor.JPG/600px-Crowtail-_PIR_Motion_Sensor.JPG){ loading=lazy }

## Specification
-------------

- Input Voltage: DC3.0-5.5V
- Current: 100uA(max)
- Detecting distance: 6m(max)
- Output signal: 0,VCC (Output high when motion detected)
- Sentry Angle: 120°
- Connector:3Pin 2.54mm pitch
- Dimensions(mm):40.0(L)x20.0(W)x13.0(H)

## Features
--------

- Long range
- Wide angle
- Low consumption
- DC 3.0-5.5V power supplier

## Usage
-----

The following sketch demonstrates a simple application of sensing montion. When someone moves in its detecting range, it will output High through its SIG pin and the LED will light. Otherwise, it will output LOW. Then you can use it to detect the motion of people.
 ![Crowtail- PIR Motion Sensor11.jpg](https://wiki.elecrow.com/images/thumb/d/d7/Crowtail-_PIR_Motion_Sensor11.jpg/600px-Crowtail-_PIR_Motion_Sensor11.jpg){ loading=lazy }

2.Download [Crowtail- PIR\_Motion\_Sensor library](../../files/Crowtail-PIR-Motion-Sensor-zip.md) the library; Unzip and put it in the libraries file : ..\\arduino-1.0\\libraries;

3.Open “PIR\_Sensor ” example via the path: File --&gt; Examples --&gt; PIR\_Sensor.

```
 #define PIR_MOTION_SENSOR 2//Use pin 2 to receive the signal from the module 
 #define LED	5//the Crowtail - LED is connected to D5 of Arduino
 
 
void setup()
{
	pinsInit();
}
 
void loop() 
{
	if(isPeopleDetected())//if it detects the moving people?
		turnOnLED();
	else
		turnOffLED();
}
 
 
void pinsInit()
{
	pinMode(PIR_MOTION_SENSOR, INPUT);
	pinMode(LED,OUTPUT);
}
void turnOnLED()
{
	digitalWrite(LED,HIGH);
}
void turnOffLED()
{
	digitalWrite(LED,LOW);
}
/***************************************************************/
/*Function: Detect whether anyone moves in it's detecting range*/
/*Return:-boolean, true is someone detected.*/
boolean isPeopleDetected()
{
	int sensorValue = digitalRead(PIR_MOTION_SENSOR);
	if(sensorValue == HIGH)//if the sensor value is HIGH?
	{
		return true;//yes,return true
	}
	else
	{
		return false;//no,return false
	}
}
```

4.Upload it into your Arduino board and open the serial monitor to observe the led.

![The result1.jpg](https://wiki.elecrow.com/images/thumb/f/f5/The_result1.jpg/400px-The_result1.jpg){ loading=lazy }

## Resource
--------

- [Crowtail- PIR Motion Sensor Program](../../files/Crowtail-PIR-Motion-Sensor-zip.md)
- [Crowtail- PIR Motion Sensor eagle files](../../files/Crowtail-PIR-Motion-Sensor-eagle-files-zip.md)