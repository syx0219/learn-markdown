---
title: Crowtail- Linear Potentiometer
---

## Description
-----------

The Crowtail- Linear Potentiometer module uses a linear variable resistor with a maximum resistance of 10KΩ. When you move the slider from one side to the other, its output voltage will range from 0 V to the Vcc you applied. The panel mount design makes this module easy to be installed in projects.

**Model: [CT0022LP](http://www.elecrow.com/crowtail-linear-potentiometer-p-1272.html)**

![Crowtail- Linear Potentiometer.JPG](https://wiki.elecrow.com/images/thumb/2/20/Crowtail-_Linear_Potentiometer.JPG/600px-Crowtail-_Linear_Potentiometer.JPG){ loading=lazy }

## Feature
-------

- 30 mm long slide length
- Linear resistance taper
- Connection Mode:A(Analog)

## Specification
-------------

Dimensions(mm):60.0(L)x20.0(W)x18.0(H)

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
      <td align="center">3.5</td>
      <td align="center">5.0</td>
      <td align="center">30</td>
      <td align="center">V</td>
    </tr>
    <tr>
      <th scope="row">Current</th>
      <td align="center">-</td>
      <td align="center">-</td>
      <td align="center">30</td>
      <td align="center">mA</td>
    </tr>
    <tr>
      <th scope="row"> Dimension</th>
      <td align="center" colspan="3">20 x 60</td>
      <td align="center">mm</td>
    </tr>
    <tr>
      <th scope="row"> Net Weight</th>
      <td align="center" colspan="3">8.3</td>
      <td align="center">g</td>
    </tr>
    <tr>
      <th scope="row"> Rotational life</th>
      <td align="center" colspan="3"> &gt;15000</td>
      <td align="center">cycles</td>
    </tr>
    <tr>
      <th scope="row"> Total resistance</th>
      <td align="center" colspan="3"> 10</td>
      <td align="center">KΩ</td>
    </tr>
    <tr>
      <th scope="row"> Stroke length</th>
      <td align="center" colspan="3"> 30</td>
      <td align="center">mm</td>
    </tr>
    <tr>
      <th scope="row"> Total resistance tolerance</th>
      <td align="center" colspan="3"> +/- 20%</td>
      <td align="center">/</td>
    </tr>
  </tbody>
</table>

## Usage
-----

### **With Arduino**

Follow these simple steps to make the Linear potentiometer module function as a voltage divider:

1.When using the module in conjunction with an Arduino or a Crowduino, use the Crowtail - Base Shield and connect the Crowtail - Linear Potentiometer module to the shield using a designated Crowtail Interface (e.g., Analog Port 0 as shown below):

![Linear Pottentiomerter1.jpg](https://wiki.elecrow.com/images/thumb/e/e2/Linear_Pottentiomerter1.jpg/400px-Linear_Pottentiomerter1.jpg){ loading=lazy }

2.Connect the board to PC using USB cable.

3.Upload the following sample sketch:

```
int sensorpin=A0;
int sensorValue=0;
void setup() 
{
   Serial.begin(9600);
}
void loop()
{
  sensorValue = analogRead(sensorpin);
  Serial.print("sensorValue ");
  Serial.println(sensorValue);
}
```

4.Open the serial monitor. You should see some data from ADC.

![Result.png](https://wiki.elecrow.com/images/thumb/3/3c/Result.png/400px-Result.png){ loading=lazy }

## Resource
--------

- [Linear\_Potentiometer Program](../../files/Linear-Potentiometer-zip.md)
- [Crowtail-Linear\_Potentiometer eagle files](../../files/Crowtail-Linear-Potentiometer-eagle-files-zip.md)