---
title: Crowbits-Adjustable Infrared Sensor
---

## Description
-----------

This infrared distance switch features a high-sensitivity photo reflector to perform distance detection function, ranging from 3cm to 80cm. When the infrared light emitted by the emitter gets reflected on a surface that blocked it, the phototransistor can pick up the signal for distance calculation. Also a potentiometer for adjustment is arranged for easy and clear use. It is small, easy to use/assemble, and inexpensive. Useful for robotics, interactive media, industrial assembly line, etc.

![Crowbits-Adjustable Infrared Sensor 1.jpg](https://wiki.elecrow.com/images/thumb/d/d6/Crowbits-Adjustable_Infrared_Sensor_1.jpg/600px-Crowbits-Adjustable_Infrared_Sensor_1.jpg){ loading=lazy }

## Features
--------

- Easy to use/assemble
- High-sensitivity

## Specification
-------------

- Power supply: 3.3V
- Current: 100mA
- Range: 3-80cm adjustable
- Wire length: 20cm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1.You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2.Connect the module to the D2 interface of the Crowbits-UNO board, as shown in the figure:

![Crowbits-Adjustable Infrared Sensor-Wiki 1.jpg](https://wiki.elecrow.com/images/thumb/7/7e/Crowbits-Adjustable_Infrared_Sensor-Wiki_1.jpg/600px-Crowbits-Adjustable_Infrared_Sensor-Wiki_1.jpg){ loading=lazy }

3.Upload the following code to the Crowbits-UNO board.

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

4.After the upload is successful, open the serial port monitor, the baud rate is set to 9600. When an object is detected, the serial port will print “object detected.”

![Crowbits-Adjustable Infrared Sensor-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/4/44/Crowbits-Adjustable_Infrared_Sensor-Wiki_2.jpg/600px-Crowbits-Adjustable_Infrared_Sensor-Wiki_2.jpg){ loading=lazy }