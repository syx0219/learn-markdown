---
title: Crowtail- Photo Electric Counter
---

## Description
-----------

This photo electric counter uses a groove IR Optocoupler to detect if there is anything between the IR emiter and IR receiver. With this method, this module can detect the number of obstruction in a given time thus to detect the speed of the rotation. When the photo electric sensor didn't covered , the D0 output logic LOW, the signal indicate LED light, when the opto sensor covered, the D0 output logic HIGH and the LED off, adjust the potentiometer can adjust the sensitivity of the sensor. And we add a Crowtail interface to it, so we can use with a Crowduino to make our work more easier and convenient.

**Model: [CT0062PEC](http://www.elecrow.com/crowtail-photo-electric-counter-p-1525.html)**

![Crowtail- Photo Electric Counter.jpg](https://wiki.elecrow.com/images/thumb/2/29/Crowtail-_Photo_Electric_Counter.jpg/600px-Crowtail-_Photo_Electric_Counter.jpg){ loading=lazy }

## Features
--------

- Wide power supply range DC3.3V to 5V
- High sensitive
- LM393 Comparator to make the output signal easy to read
- Nothing detected: Output low, LED on; Obstruction between the emitter and receiver: Output high, LED off.
- Dimensions(mm):20.0(L)x20.0(W)x20.0(H)

## Usage
-----

1\. Connect the Photo Electric Counter to the Digital port 2 of Crowtail -Nano Basic Shield using a Crowtail cable and connect an LED to Pin 4.

![Crowtail- Photo Electric Counter11.jpg](https://wiki.elecrow.com/images/thumb/6/67/Crowtail-_Photo_Electric_Counter11.jpg/500px-Crowtail-_Photo_Electric_Counter11.jpg){ loading=lazy }

2.Download [Crowtail- Photo Electric Counter library](https://wiki.elecrow.com/images/1/1b/Crowtail-_Photo_Electric_Counter.zip) the library; Unzip and put it in the libraries file : ..\\arduino-1.0\\libraries;

3.Open “Crowtail- Photo Electric Counter” example via the path: File --&gt; Examples --&gt;Crowtail- Photo Electric Counter

```
 
const int sensorPin = 2;   
const int ledPin =  4;      // the number of the LED pin

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

4.Upload it into your Crowduino-Nano board and keep out the groove ,observe the led.

![The result471.jpg](https://wiki.elecrow.com/images/thumb/6/63/The_result471.jpg/400px-The_result471.jpg){ loading=lazy }

## Resource
--------

- [Crowtail-\_Photo\_Electric Counter Program](https://wiki.elecrow.com/images/1/1b/Crowtail-_Photo_Electric_Counter.zip)
- [Crowtail- Photo Electric Counter eagle files](https://wiki.elecrow.com/images/c/c0/Crowtail-_Photo_Electric_Counter_eagle_files.zip)