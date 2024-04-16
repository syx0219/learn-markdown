---
title: Adjustable Infrared Sensor Switch
---

## Introduction
------------

This infrared distance switch features a high-sensitivity photoreflector to perform distance detection function,ranging from 3cm to 80cm. When the infrared light emitted by the emitter gets reflected on a surface that blocked it, the phototransistor can pick up the signal for distance calculation. Also a potentiometer for adjustment is arranged for easy and clear use. It is small, easy to use/assemble, and inexpensive. Useful for robotics, interactive media, industrial assembly line, etc.  
**Model: [SOD00380S](http://www.elecrow.com/sensor-c-111/object-dectect-c-111_113/adjustable-infrared-sensor-switch-3-80cm-p-318.html)**  

![Adjustable Infrared Sensor Switch 3 - 80cm2.jpg](https://wiki.elecrow.com/images/thumb/0/0c/Adjustable_Infrared_Sensor_Switch_3_-_80cm2.jpg/400px-Adjustable_Infrared_Sensor_Switch_3_-_80cm2.jpg){ loading=lazy }

## Features
--------

- Power supply: 5V
- Current: 100mA
- Range: 3-80cm adjustable
- Red: +5V
- Yellow: Signal
- Black: GND
- Wire length: 20cm

## Usage
-----

### **Hardware**

Connect this sensor to your Arduino/Crowduino digital pins( D2 for example). When there is an object behind this sensor, the output would be low.
![Adjustable infrared sensor1 hardware1.jpg](https://wiki.elecrow.com/images/thumb/0/04/Adjustable_infrared_sensor1_hardware1.jpg/500px-Adjustable_infrared_sensor1_hardware1.jpg){ loading=lazy }

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
![Infrared Sensor Switch test result.jpg](https://wiki.elecrow.com/images/thumb/f/f2/Infrared_Sensor_Switch_test_result.jpg/500px-Infrared_Sensor_Switch_test_result.jpg){ loading=lazy } ![Infrared Sensor Switch test result1.jpg](https://wiki.elecrow.com/images/thumb/d/d5/Infrared_Sensor_Switch_test_result1.jpg/500px-Infrared_Sensor_Switch_test_result1.jpg){ loading=lazy }