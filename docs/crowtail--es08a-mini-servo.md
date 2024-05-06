---
title: Crowtail- ES08A Mini Servo
---

## Description
-----------

A NEW Crowtail product! we add a crowtail port for pluging into crowtail base board. so it can simple use for our Crowduino. This EMAX servo is an entry level servo for beginners who like to enjoy servo controlling fun. This product includes a full set of common shafts as shown in the pictures, great for small mechatronic projects.

**Model: [CT0037EMS](http://www.elecrow.com/crowtail-emax-9g-es08a-mini-servo-p-1482.html)**

![Crowtail- ES08A Mini Servo11.jpg](https://wiki.elecrow.com/images/thumb/1/11/Crowtail-_ES08A_Mini_Servo11.jpg/400px-Crowtail-_ES08A_Mini_Servo11.jpg){ loading=lazy }

## Specification
-------------

- Compatible with Crowtail interface
- Operating Voltage: 4.8 ~ 6.0V
- Operating Speed(4.8V): 0.12 Sec/60° at no load
- Temperature range: 0°C - 55°C
- Stall Torque(4.8V): 1.5Kgf.cm(22.2 oz.in)
- Brand name: EMax
- location of each pin: red (+), brown (-), yellow (signal).
- 3 pole ferrite, all nylon gear. Top ball bearing
- Dimensions(mm):32.2(L)x11.7(W)x27.5(H)

## Usage
-----

1\. Connect the Crowtail- EMAX 9g ES08A Mini Servo to the Digital port 9 of Crowtail - Basic Shield using a Crowtail cable

![Crowtail- ES08A Mini Servo011.jpg](https://wiki.elecrow.com/images/thumb/9/92/Crowtail-_ES08A_Mini_Servo011.jpg/600px-Crowtail-_ES08A_Mini_Servo011.jpg){ loading=lazy }

2.Download [Crowtail- ES08A Mini Servo library](./files/Crowtail-ES08A-MiniServo-zip.md) the library; Unzip and put it in the libraries file : ..\\arduino-1.0\\libraries;

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

4.Upload it into your Crowduino board and observe what will happen.

## Resource
--------

- [Crowtail- ES08A Mini Servo Program](./files/Crowtail-9G-Servo-zip.md)