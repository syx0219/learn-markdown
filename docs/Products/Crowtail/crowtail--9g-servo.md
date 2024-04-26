---
title: Crowtail- 9G Servo
---

## Description
-----------

Tower Pro SG90 is a high quality, low-cost servo for all your mechatronic needs. It comes with a 3-pin power and control cable, mounting hardware. For good use with Crowtail series products, we decide to add it to our Crowtail family. Hope you can make your work more easier by using it.

**Model: [CT0064NGS](http://www.elecrow.com/crowtail-9g-servo-p-1516.html)**

![Crowtail- Crowtail- 9G Servo1.jpg](https://wiki.elecrow.com/images/thumb/9/96/Crowtail-_Crowtail-_9G_Servo1.jpg/400px-Crowtail-_Crowtail-_9G_Servo1.jpg){ loading=lazy }

## Specification
-------------

- Compatible with Crowtail
- Operating Voltage: 4.8 ~ 6.0V
- Operating Speed: 0.12sec/60 degree(4.8V)~0.1sec/60 degree(6.0V)
- Torque: 1.6kg/cm(4.8V)
- Dead Band Width: 5usec
- Temperature Range: -30℃~+60℃
- Cable Length: 22.5cm
- Servo dimensions(mm):32.2(L)x12.6(W)x31.2(H)
- Brand name: Tower Pro
- location of each pin: red (+), brown (-), yellow (signal).

## Usage
-----

1\. Connect the Crowtail- 9G Servo to the Digital port 9 of Crowtail - Basic Shield using a Crowtail cable

![Crowtail- 9G Servo21.jpg](https://wiki.elecrow.com/images/thumb/4/49/Crowtail-_9G_Servo21.jpg/500px-Crowtail-_9G_Servo21.jpg){ loading=lazy }

2.Download [Crowtail- 9G Servo library](../../files/Crowtail-9G-Servo-zip.md) the library; Unzip and put it in the libraries file : ..\\arduino-1.0\\libraries;

3.Open “sweep” example via the path: File --&gt; Examples --&gt; Servo --&gt;sweep.

```
// Sweep
// by BARRAGAN <http://barraganstudio.com> 
// This example code is in the public domain.


#include <Servo.h> 
 
Servo myservo;  // create servo object to control a servo 
                // a maximum of eight servo objects can be created 
 
int pos = 0;    // variable to store the servo position 
 
void setup() 
{ 
  myservo.attach(9);  // attaches the servo on pin 9 to the servo object 
} 
 
 
void loop() 
{ 
  for(pos = 0; pos < 180; pos += 1)  // goes from 0 degrees to 180 degrees 
  {                                  // in steps of 1 degree 
    myservo.write(pos);              // tell servo to go to position in variable 'pos' 
    delay(15);                       // waits 15ms for the servo to reach the position 
  } 
  for(pos = 180; pos>=1; pos-=1)     // goes from 180 degrees to 0 degrees 
  {                                
    myservo.write(pos);              // tell servo to go to position in variable 'pos' 
    delay(15);                       // waits 15ms for the servo to reach the position 
  } 
} 
```

4.Upload it into your Crowduino board and see what will happen.

## Resource
--------

- [Crowtail- 9G Servo Program](../../files/Crowtail-9G-Servo-zip.md)