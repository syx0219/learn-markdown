---
title: Crowtail- Encoder
---

## Description
-----------

The rotary encoder can convert the angular displacement and linear Displacement to the electrical signal,and then convert the electrical signal to the electrical pluse .The numbers of the pluse can be converted to the value of the angular displacement. There are two output pins of this module including signal A and signal B.we can determine the position of the detent and the direction of the rotation by sense the value of the output pins.

**Model: [CT0004EN](http://www.elecrow.com/crowtail-encoder-p-1231.html)**

![Crowtail-Encoder.JPG](https://wiki.elecrow.com/images/thumb/1/17/Crowtail-Encoder.JPG/600px-Crowtail-Encoder.JPG){ loading=lazy }

## Features
--------

- Crowtail Interface.
- Incremental encoder
- 360 degree rotary

## Specification
-------------

Dimensions(mm):20.0(L)x20.0(W)x36.3(H)

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
      <td align="center">4.5</td>
      <td align="center">5.0</td>
      <td align="center">5.5</td>
      <td align="center">VDC</td>
    </tr>
    <tr>
      <th scope="row">Current</th>
      <td align="center">10</td>
      <td align="center">20</td>
      <td align="center">30</td>
      <td align="center">mA</td>
    </tr>
    <tr>
      <th scope="row"> Dimension</th>
      <td align="center" colspan="3">20 x 20</td>
      <td align="center">mm</td>
    </tr>
    <tr>
      <th scope="row"> Net Weight</th>
      <td align="center" colspan="3">7</td>
      <td align="center">g</td>
    </tr>
  </tbody>
</table>

## Usage
-----

This Crowtail-Encoder is very easy to use.

1.Hardware Connection

![Encoder11.jpg](https://wiki.elecrow.com/images/thumb/4/45/Encoder11.jpg/600px-Encoder11.jpg){ loading=lazy }

2.Connect the board to PC using USB cable.

3.Upload the following sample sketch:

```
#define ENCODER_A_PIN 2
#define ENCODER_B_PIN 3
long position;

void setup(){

 pinMode(ENCODER_A_PIN, INPUT);
 pinMode(ENCODER_B_PIN, INPUT);
 attachInterrupt(0, read_quadrature, CHANGE);
 Serial.begin(9600);
}

void loop(){
  Serial.print("Position: ");
  Serial.println(position, DEC);
  delay(1000);
}

void read_quadrature(){  
 
  if (digitalRead(ENCODER_A_PIN) == LOW){   
   //Check clockwise or counterclockwise
   if (digitalRead(ENCODER_B_PIN) == LOW)
     position++;
 }
  
 else{

   if (digitalRead(ENCODER_B_PIN) == LOW)
     position--;
  }
}
```

4.Open the serial monitor. You should see some data from Encoder.

![Encoderresult.jpg](https://wiki.elecrow.com/images/e/e4/Encoderresult.jpg){ loading=lazy }

## Resource
--------

- [Encoder Program](../../files/Encoder-zip.md)
- [Crowtail- Encoder eagle files](../../files/Crowtail-Encoder-zip.md)