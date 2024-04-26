---
title: Crowtail- Adjustable Infrared Sensor
---

## Introduction
------------

This infrared distance switch features a high-sensitivity photoreflector to perform distance detection function,ranging from 3cm to 50cm. When the infrared light emitted by the emitter gets reflected on a surface that blocked it, the phototransistor can pick up the signal for distance calculation. Also a potentiometer for adjustment is arranged for easy and clear use. It is small, easy to use/assemble, and inexpensive. Useful for robotics, interactive media, industrial assembly line, etc.  
**Model: [CT0036AIS](http://www.elecrow.com/crowtail-adjustable-infrared-sensor-350cm-p-1481.html)**

![Crowtail- Adjustable Infrared Sensor11.jpg](https://wiki.elecrow.com/images/thumb/a/aa/Crowtail-_Adjustable_Infrared_Sensor11.jpg/400px-Crowtail-_Adjustable_Infrared_Sensor11.jpg){ loading=lazy }

## Features
--------

- Power supply: 5V
- Current: 100mA
- Range: 3-50cm adjustable
    
    - Red: +5V
    - Yellow: Signal
    - Black: GND
- Wire length: 20cm
- Dimensions(mm):45.0(L)x23.4(W)x23.4(H)

## Usage
-----

### **Hardware**

Connect this sensor to your Arduino/Crowduino digital pins( D2 for example). When there is an object behind this sensor, the output would be low.  
![Crowtail- Adjustable Infrared Sensor12.jpg](https://wiki.elecrow.com/images/thumb/7/7f/Crowtail-_Adjustable_Infrared_Sensor12.jpg/400px-Crowtail-_Adjustable_Infrared_Sensor12.jpg){ loading=lazy }

### **Programming**

1.Download the following program to Arduino, Please refer to [here](../../how/how-to-install-the-librarys-and-upload-programs-to-arduino.md)

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

2.open the serial monitor , and set the baudrate to 9600, you will see the output changes with the object behind this sensor or not.

if no object:  
![Crowtail- Adjustable Infrared Sensor01.jpg](https://wiki.elecrow.com/images/thumb/f/f5/Crowtail-_Adjustable_Infrared_Sensor01.jpg/300px-Crowtail-_Adjustable_Infrared_Sensor01.jpg){ loading=lazy }  
have object:  
![Crowtail- Adjustable Infrared Sensor21.jpg](https://wiki.elecrow.com/images/thumb/1/18/Crowtail-_Adjustable_Infrared_Sensor21.jpg/300px-Crowtail-_Adjustable_Infrared_Sensor21.jpg){ loading=lazy } 
![Crowtail- Adjustable Infrared Sensor3.png](https://wiki.elecrow.com/images/thumb/c/c9/Crowtail-_Adjustable_Infrared_Sensor3.png/300px-Crowtail-_Adjustable_Infrared_Sensor3.png){ loading=lazy }