---
title: Tiny Adjustable Infrared Sensor Switch
---

## Introduction
------------

This is a new version of infrared distance switch. It has small size and higher ranging, it is able to detect ranging from 3cm to 100cm. It is tiny, easy to use/assemble, and inexpensive. Useful for robotics, interactive media, industrial assembly line, etc.  
**Model: [SOD00300S](http://www.elecrow.com/sensor-c-111/object-dectect-c-111_113/tiny-adjustable-infrared-sensor-switch-3-100cm-p-319.html)**

![Infrared Sensor Switch 3 - 100cm1 011.jpg](https://wiki.elecrow.com/images/thumb/f/f1/Infrared_Sensor_Switch_3_-_100cm1_011.jpg/400px-Infrared_Sensor_Switch_3_-_100cm1_011.jpg){ loading=lazy }

## Features
--------

- Power supply: 5V
- Current: 100mA
- Range: 3-100cm adjustable

## Usage
-----

### **Hardware**

Connect this sensor to your Arduino/Crowduino digital pins( D2 for example). When there is an object behind this sensor, the output would be low.  
![Tiny Adjustable Infrared Sensor Switch.jpg](https://wiki.elecrow.com/images/thumb/f/fa/Tiny_Adjustable_Infrared_Sensor_Switch.jpg/500px-Tiny_Adjustable_Infrared_Sensor_Switch.jpg){ loading=lazy }

### **Programming**

1.Copy the following program to Arduino IDE and upload to your Arduino/Crowduino:

```
 void setup()  {
  Serial.begin(9600);
  pinMode(2,INPUT);
 }
 void loop()  {
  while(1)  {
    delay(500);
    if(digitalRead(2)==LOW)  {
      Serial.println("object detected.");
    }
    else  {
      Serial.println("no object detected.");
    }
  }
 }
```

2.Open the Serial moniter, and set the baudrate to 9600, you will see the output change with the object behind this sensor or not.  
![Tiny Adjustable Infrared Sensor Switch test1.jpg](https://wiki.elecrow.com/images/thumb/f/fb/Tiny_Adjustable_Infrared_Sensor_Switch_test1.jpg/600px-Tiny_Adjustable_Infrared_Sensor_Switch_test1.jpg){ loading=lazy } 
![Tiny Adjustable Infrared Sensor Switch test2.jpg](https://wiki.elecrow.com/images/thumb/9/93/Tiny_Adjustable_Infrared_Sensor_Switch_test2.jpg/600px-Tiny_Adjustable_Infrared_Sensor_Switch_test2.jpg){ loading=lazy }