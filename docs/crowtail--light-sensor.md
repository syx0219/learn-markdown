---
title: Crowtail- Light Sensor
---

## Description
-----------

The Crowtail- Light Sensor module incorporates a light dependent resistor (LDR), is a commonly used sensor in a wide variety of applications from DIY projects to industrial automation. Typically, the resistance of the LDR or Photoresistor will decrease when the ambient light intensity increases. This means that the output signal from this module will be HIGH in bright light, and LOW in the dark.

**Model: [CT0013LS](http://www.elecrow.com/crowtail-light-sensor-p-1244.html)**

![Crowtail- Light Sensor.JPG](https://wiki.elecrow.com/images/thumb/1/16/Crowtail-_Light_Sensor.JPG/600px-Crowtail-_Light_Sensor.JPG){ loading=lazy }

## Features
--------

- Easy to use light sensor module
- Resistance decreases as luminance increases

## Specifications
--------------

- Voltage:5V
- Supply Current: 0.5-3mA
- Light resistance: 20KΩ
- Dark resistance: 1MΩ
- Response time: 20-30 secs
- Peak Wavelength: 540 nm
- Ambient temperature: -30~70℃
- Dimensions(mm):20.0(L)x20.0(W)x6.8(H)

## Usage
-----

Follow these simple steps to build a Crowtail circuit using the light sensor:

1.Hardware Connection

![Lightcontrol1.jpg](https://wiki.elecrow.com/images/thumb/7/78/Lightcontrol1.jpg/600px-Lightcontrol1.jpg){ loading=lazy }

2.Upload the following sample sketch to make the LED turn ON and OFF based on input from the light sensor:

```
const int light=A0;
const int ledPin=5;
int sensorValue = 0;
const int thresholdvalue=100; //The threshold for which the LED should turn on. 
void setup()
{
 pinMode(ledPin,OUTPUT);  //Set the LED on Digital 5 as an OUTPUT
 Serial.begin(9600);     //Start the Serial connection
}
void loop()
{
  sensorValue = analogRead(light);
  if(sensorValue<thresholdvalue)
 {
   digitalWrite(ledPin,HIGH);
 }
 else
 {
 digitalWrite(ledPin,LOW);
 }
  Serial.print("light sensor = " );
 Serial.println(sensorValue); 
 delay(500);
}
```

3.When the light value lower than 100,the LED will lights up:  
![Light Sensor result11.jpg](https://wiki.elecrow.com/images/thumb/a/a8/Light_Sensor_result11.jpg/600px-Light_Sensor_result11.jpg){ loading=lazy } 
![Light Sensor result22.jpg](https://wiki.elecrow.com/images/thumb/c/ca/Light_Sensor_result22.jpg/600px-Light_Sensor_result22.jpg){ loading=lazy }

## Resource
--------

- [Light Sensor Program](./files/Light-sensor-zip.md)
- [Crowtail- Light Sensor eagle files](./files/Crowtail-Light-Sensor-eagle-files-zip.md)