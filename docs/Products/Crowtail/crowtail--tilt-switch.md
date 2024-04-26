---
title: Crowtail- Tilt Switch
---

## Description
-----------

The Crowtail- Tilt Switch is the equivalent of a button, and is used as a digital input. Inside the tilt switch is a pair of balls that make contact with the pins when the case is upright. Tilt the case over and the balls don't touch, thus not making a connection.

**Model: [CT0023TS](http://www.elecrow.com/crowtail-tilt-switch-p-1274.html)**

![Crowtail-Tilt Switch.JPG](https://wiki.elecrow.com/images/thumb/3/30/Crowtail-Tilt_Switch.JPG/600px-Crowtail-Tilt_Switch.JPG){ loading=lazy }

## Festure
-------

- Crowtail Interface
- Easy to use

## Specification
-------------

Dimensions(mm):20.0(L)x20.0(W)x6.8(H)

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
      <td align="center">4.75</td>
      <td align="center">5.0</td>
      <td align="center">5.25</td>
      <td align="center">V</td>
    </tr>
    <tr>
      <th scope="row"> Connect angle</th>
      <td align="center" colspan="3">10° ~170°</td>
      <td align="center">-</td>
    </tr>
    <tr>
      <th scope="row"> Disconnect angle</th>
      <td align="center" colspan="3">190° ~350°</td>
      <td align="center">-</td>
    </tr>
    <tr>
      <th scope="row"> Electrical life</th>
      <td align="center" colspan="3"> 100000</td>
      <td align="center">cycles</td>
    </tr>
    <tr class="mw-empty-elt"></tr>
  </tbody>
</table>

## Usage
-----

1.Hardware connection

![Tiltswitch1.jpg](https://wiki.elecrow.com/images/thumb/3/36/Tiltswitch1.jpg/400px-Tiltswitch1.jpg){ loading=lazy }

2.Copy and paste code below to a new Arduino sketch.

```
void setup()
{
   pinMode(4, INPUT); //connect to Crowtail- Tilt Switch  
   pinMode(5, OUTPUT);//connect to Crowtail- LED
}

void loop()
{ 
 if (digitalRead(4)==HIGH)
 {
   digitalWrite(1, HIGH);
   delay(100);
   digitalWrite(5, HIGH);
 }
 else
{
   digitalWrite(5, LOW);
 } 
}
```

3.Test result:  
![Tilt Switch result11.jpg](https://wiki.elecrow.com/images/thumb/4/48/Tilt_Switch_result11.jpg/400px-Tilt_Switch_result11.jpg){ loading=lazy } 
![Tilt Switch result22.jpg](https://wiki.elecrow.com/images/thumb/e/ec/Tilt_Switch_result22.jpg/400px-Tilt_Switch_result22.jpg){ loading=lazy }

## Resource
--------

- [Tilt Switch Program](../../files/Tilt-Switch-zip.md)
- [Crowtail-Tilt\_Switch \_eagle\_files](../../files/Crowtail-Tilt-Switch-eagle-files-zip.md)