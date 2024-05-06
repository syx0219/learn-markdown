---
title: PIR Motion Sensor
---

## Introduction
------------

This is a highly integrated module popularly used for human-being entry detection, it can simplely and easily to adopt in system. There are two adjustable potentiometer on the module, you can use them to change the trigger sensitivity and the duration of the trigger signal.Besides,The module can also be set as retriggerable or un- retriggerable. When the switch is in the H position, the module is retriggerable and is unretrigerred when the switch is in L position.  
**Model: [SOD00101S](http://www.elecrow.com/sensor-c-111/object-dectect-c-111_113/pir-motion-sensor-module-p-315.html)**

![PIR Motion Sensor1.jpg](https://wiki.elecrow.com/images/thumb/e/e5/PIR_Motion_Sensor1.jpg/400px-PIR_Motion_Sensor1.jpg){ loading=lazy }
![PIR3.jpg](https://wiki.elecrow.com/images/thumb/a/a7/PIR3.jpg/400px-PIR3.jpg){ loading=lazy }

## Specification
-------------

- Input Voltage: DC 4.5-20V
- Static current: 50uA
- Output signal: 0,3V or 5V (Output high when motion detected)
- Sentry Angle: 110 degree
- Sentry Distance: max 7 m
- Shunt for setting overide trigger: H - Yes, L - No

## Interface
---------

![Pir hardware.jpg](https://wiki.elecrow.com/images/0/05/Pir_hardware.jpg){ loading=lazy }

## Usage
-----

### **Hardware**

Connect this sensor to your Arduino/Crowduino digital pins( D2 for example). Adjust the RT&amp;CDS to change trigger sensitivity and duration of the trigger signal.Set the module as retriggerable or un- retriggerable with the switch, when the H position, the module is retriggerable and is unretrigerred when the switch is in L position.  
![Pir hardware connect.jpg](https://wiki.elecrow.com/images/thumb/e/e1/Pir_hardware_connect.jpg/500px-Pir_hardware_connect.jpg){ loading=lazy }

### **Programming**

1.Copy and paste code below to a new Arduino sketch.

```
 const int PIRPin = 2;// the number of the PIR Motion sensor pin
 const int ledPin=13;//The led to indicate the motion
 int PIRState = 0; // variable for reading the PIR Motion sensor status
 void setup(){
     pinMode(PIRPin, INPUT);//Use pin 2 to receive the signal outputted by the module 
     pinMode(ledPin, OUTPUT);
 }
 void loop() {
      PIRState=digitalRead(PIRPin);
     if(PIRState==HIGH)
     {
           digitalWrite(ledPin,HIGH);
     }
     else
     {
           digitalWrite(ledPin,LOW);
     }
 }
```

2.Upload the code,When someone moves before the sensor, the led on the arduino board light.  
![PIR Motion Sensor display.jpg](https://wiki.elecrow.com/images/thumb/b/b7/PIR_Motion_Sensor_display.jpg/500px-PIR_Motion_Sensor_display.jpg){ loading=lazy }