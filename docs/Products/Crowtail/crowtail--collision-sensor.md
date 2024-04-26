---
title: Crowtail- Collision Sensor
---

## Description
-----------

Have you ever been bothered for detecting simple collisions with complex algorithm with an acceleration sensor? The collision sensor is here to simplify the process,. It's also omni directional, stable, and sensitive. Crowtail-collision Sensor can detect whether any collision movement or vibration happens. It will output a low pulse signal when vibration is detected. To make the output signal more reliable and neat, we added a necessary exterior circuit to reduce the noise impact. So, normal shaking will not cause any output. The sensor has a high sensitivity, then you can use it to apply to your project, such as automatic wake-up and power-down for battery management. Its working voltage is 5v which make it compatible with standard Arduino/Crowduino 5V system.

**Model: [CT0061CCS](http://www.elecrow.com/crowtail-collision-sensor-p-1524.html)**

![Crowtail- Collision Sensor.jpg](https://wiki.elecrow.com/images/thumb/8/8e/Crowtail-_Collision_Sensor.jpg/600px-Crowtail-_Collision_Sensor.jpg){ loading=lazy }

## Specification
-------------

- Wide power supply range DC3.3V to 5V
- High sensitive
- RoHS/WEEE lead-free compliant
- Clock frequency - 16MHz (may be reduced to low energy consumption by up to 1MHz)
- Dimensions(mm):28.0(L)x20.0(W)x6.8(H)

## Features
--------

- Long range
- Wide angle
- Low consumption
- DC 3.0-5.5V power supplier

## Usage
-----

1\. Connect the collision sensor to the Digital port 2 of Crowtail - Basic Shield using a Crowtail cable and connect an LED to Pin 5.

![Crowtail- Collision Sensor11.jpg](https://wiki.elecrow.com/images/thumb/a/a1/Crowtail-_Collision_Sensor11.jpg/500px-Crowtail-_Collision_Sensor11.jpg){ loading=lazy }

2.Download [Crowtail- Collision Sensor library](../../files/Crowtail-Collision-Sensor-zip.md) the library; Unzip and put it in the libraries file : ..\\arduino-1.0\\libraries;

3.Open “Crowtail- Collision Sensor” example via the path: File --&gt; Examples --&gt; Crowtail- Collision Sensor.

```
const int sensorPin = 2;   
const int ledPin =  5;      // the number of the LED pin

// variables will change:
int sensorState = 0;      

void setup() {
  // initialize the LED pin as an output:
  pinMode(ledPin, OUTPUT);      
  pinMode(sensorPin, INPUT);     
}

void loop(){
  // read the state of the pushbutton value:
  sensorState = digitalRead(sensorPin);
  if (sensorState == HIGH) {     
    // turn LED on:    
    digitalWrite(ledPin,LOW);  
  } 
  else {
    // turn LED off:
    digitalWrite(ledPin, HIGH); 
  }
}
```

4.Upload it into your Arduino board and press the sheetmetal ,observe the led.

![The result271.jpg](https://wiki.elecrow.com/images/thumb/b/b3/The_result271.jpg/400px-The_result271.jpg){ loading=lazy }

## Resource
--------

- [Crowtail- Collision Sensor Program](../../files/Crowtail-Collision-Sensor-zip.md)
- [Crowtail- Collision Sensor eagle files](../../files/Crowtail-Collision-Sensor-eagle-files-zip.md)