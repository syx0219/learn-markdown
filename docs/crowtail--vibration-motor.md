---
title: Crowtail- Vibration Motor
---

## Description
-----------

This is a mini vibration motor suitable as a non-audible indicator. When the input is HIGH, the motor will vibrate just like your cell phone on silent mode.

**Model: [CT0014VM](http://www.elecrow.com/crowtail-vibration-motor-p-1246.html)**

![Crowtail- Vibration Motor.JPG](https://wiki.elecrow.com/images/thumb/6/61/Crowtail-_Vibration_Motor.JPG/600px-Crowtail-_Vibration_Motor.JPG){ loading=lazy }

## Features
--------

- Crowtail compatible
- Low power consumption
- High reliability

## Specification
-------------

Dimensions(mm):40.0(L)x20.0(W)x6.9(H)

<table border="1" cellspacing="0" width="100%">
   <tbody>
      <tr>
         <th scope="col" align="center"> Item</th>
         <th scope="col" align="center"> Min</th>
         <th scope="col" align="center"> Typical</th>
         <th scope="col" align="center"> Max</th>
         <th scope="col" align="center"> Unit</th>
      </tr>
      <tr>
         <th scope="row">Voltage</th>
         <td align="center">3.0</td>
         <td align="center">5.0</td>
         <td align="center">5.5</td>
         <td align="center">V</td>
      </tr>
      <tr>
         <th scope="row"> Control Mode</th>
         <td align="center" colspan="3">Logic Level <p>(When Logic HIGH, the motor is ON. When LOW, the motor is OFF.)</p></td>
         <td align="center">-</td>
      </tr>
      <tr>
         <th scope="row"> Rated speed</th>
         <td align="center" colspan="3">9000</td>
         <td align="center">rpm</td>
      </tr>
      <tr class="mw-empty-elt"></tr>
   </tbody>
</table>

## Usage
-----

Here is an example showing how to turn on the vibration motor.

1\. Plug it onto the Digital port 5 of Crowtail - Base Shield using a Crowtail cable.

2.Plug the Crowtail - Base Shield onto Arduino.

3\. Connect Arduino to PC by using a USB cable.

![Vibration1.jpg](https://wiki.elecrow.com/images/thumb/9/93/Vibration1.jpg/400px-Vibration1.jpg){ loading=lazy }

4\. Copy and paste code below to a new Arduino sketch, and upload it to your Arduino.

```
int MoPin = 5;    // vibrator connected to digital pin 5
void setup()  { 
 pinMode( MoPin, OUTPUT );
}  
void loop()  {  
   digitalWrite(MoPin, HIGH);         
   delay(1000);                           
   digitalWrite(MoPin, LOW);         
   delay(1000); 
}
```

5.When you upload the code complete,you can see the vibrating motor vibrate at one second intervals.  
![Vibration Motor result2.jpg](https://wiki.elecrow.com/images/thumb/b/bb/Vibration_Motor_result2.jpg/400px-Vibration_Motor_result2.jpg){ loading=lazy }

## Resource
--------

- [Crowtail\_Vibration-Motor Program](./files/Vibration-sensor-zip.md)
- [Crowtail\_Vibration\_Motor \_eagle\_files](./files/Crowtail-Vibration-Motor-eagle-files-zip.md)