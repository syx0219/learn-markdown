---
title: Crowtail- Vibration Sensor
---

## Description
-----------

The Crowtail- Vibration Sensor is Used to trigger the effect of various vibration with Normally closed type vibration sensor SW - 420.It is widely used to reported the theft alarm, intelligent car, earthquake alarm, motorcycle alarm, etc.This module is compared with the normally open type vibration sensor module, vibration trigger for longer periods of time, can drive the relay module.

**Model: [CT010129V](http://www.elecrow.com/crowtail-vibration-sensor-p-1662.html)**

![Crowtail- Vibration Sensor.jpg](https://wiki.elecrow.com/images/thumb/4/4f/Crowtail-_Vibration_Sensor.jpg/600px-Crowtail-_Vibration_Sensor.jpg){ loading=lazy }

## Features
--------

- Working voltage: 3.3 V to 5 V
- Digital switch output(0 and 1)
- Crowtail interface
- The LM393 wide voltage comparator
- Dimensions(mm):40.0(L)x20.0(W)x7.5(H)

## Directions for use
------------------

1.The product is not vibration, vibration switch is closed on state, output output low level, the green light is lit;

2.When product vibration, the vibration switch instantaneous disconnection, output, output level green light is not bright;

3.The output can be attached directly to the single chip microcomputer, through single chip microcomputer to detect the high and low level, thus to detect if there is a vibration environment, report to the police

## Usage
-----

Here is an example showing how to turn on the vibration Sensor.

1\. Plug it onto the Digital port 2 of Crowtail - Base Shield using a Crowtail cable and the led to port 5.

2.Plug the Crowtail - Base Shield onto Arduino.

3\. Connect Arduino to PC by using a USB cable.


4\. Copy and paste code below to a new Arduino sketch, and upload it to your Arduino.

```
int Vibration=2;
int led = 5;
int VibrationState=0;           
void setup() {                
  pinMode(led, OUTPUT); 
  pinMode(Vibration, INPUT);
}
void loop() {
   VibrationState = digitalRead(Vibration);
   if ( VibrationState == HIGH) 
   {     
       // turn LED on:    
       digitalWrite(led, LOW);  
      } 
 
    else {
       // turn LED1 and LED off:
       digitalWrite(led, HIGH);
   }
}
```

5.When you upload the code complete,vibration the Vibration\_sensor (on a board green will brighten lights), the LED is flashing at the same time.

## Resource
--------

- [Crowtail\_Vibration\_Sensor \_eagle\_files](./files/Crowtail-Vibration-Sensor-eagle-files-zip.md)