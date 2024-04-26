---
title: Lipower Shield v1.1
---

## Introduction
------------

You may need this item if you want to power your Arduino with a 3.7V LiPo battery to make it become a portable device. It made up of a “power cell” and “fuel gauge”, it allows you to connect a 3.7V single cell Lithium polymer battery which it will boost up to 5V and connect to the Arduino board’s 5V pin. The on-board MAX17043G+U IC is connected to the I2C lines (A4 and A5) so that your project can monitor it’s own power supply. The configurable alert interrupt pin on the MAX17043G+U IC is broken out to D2 which will activate when the LiPo gets to 32% or lower. The charging circuit is configured to charge the LiPo at 500mA and there is a mini-USB port on the shield which allows you to charge the battery from a USB power source.

**Model: [ACS33721L](https://www.elecrow.com/lipower-shield.html)**
![LiPower Shield.jpg](https://wiki.elecrow.com/images/thumb/c/c8/LiPower_Shield.jpg/600px-LiPower_Shield.jpg){ loading=lazy }

## Features
--------

- Power monitoring
- Compatible with 3.7V LiPo battery

## Specifications
--------------

<table border="1" cellspacing="0" width="100%">
  <tbody>
    <tr>
      <th scope="col" align="center">Item</th>
      <th scope="col" align="center">Min</th>
      <th scope="col" align="center">Typical</th>
      <th scope="col" align="center">Max</th>
      <th scope="col" align="center">Unit</th>
    </tr>
    <tr>
      <th scope="row">Output Voltage</th>
      <td align="center">4.8</td>
      <td align="center">5.0</td>
      <td align="center">5.2</td>
      <td align="center">VDC</td>
    </tr>
    <tr>
      <th scope="row">Current</th>
      <td align="center">2</td>
      <td align="center">-</td>
      <td align="center">800</td>
      <td align="center">mA</td>
    </tr>
    <tr>
      <th scope="row">Dimensions(with antenna)</th>
      <td align="center" colspan="3">77.0(L)x55.0(W)x23.5(H)</td>
      <td align="center">mm</td>
    </tr>
    <tr>
      <th scope="row">Net Weight</th>
      <td align="center" colspan="3">20±2</td>
      <td align="center">g</td>
    </tr>
  </tbody>
</table>

## Interface Function
------------------

![LiPower Shield1.jpg](https://wiki.elecrow.com/images/thumb/8/8b/LiPower_Shield1.jpg/600px-LiPower_Shield1.jpg){ loading=lazy }  
**Mini USB port** - Supply power for battery charge circuit. 
**Battery charge port** - you can connect the 3.7v lipower battery to it  
**Switch** - Switch to control battery charging and discharging  
**5v out put** - power out put  

## Usage
-----

**Charge battery:**  
you need a mini usb cable, connect it to 5V power，and switch pull to “CHG"，the red led will be light up and shows that it chageing battery now.  
![LiPower Shield4.jpg](https://wiki.elecrow.com/images/thumb/d/dc/LiPower_Shield4.jpg/600px-LiPower_Shield4.jpg){ loading=lazy }

**Supply power for Arduino**  
Switch pull to "ON" and put the lipower shield onto the Arduino, it will work independently.  
![LiPower Shield3.jpg](https://wiki.elecrow.com/images/thumb/d/d5/LiPower_Shield3.jpg/600px-LiPower_Shield3.jpg){ loading=lazy }

### **Monitor the battery power with Arduino**

The on-board MAX17043G+U IC is connected to the I2C lines (A4 and A5) so that your project can monitor it’s own power supply. The configurable alert interrupt pin on the MAX17043G+U IC is broken out to D2 which will activate when the LiPo gets to 32% or lower.   
First you need to connect the Arduino to computer and upload the power detecting demo to it, and then pull the switch into the "ON" side.  
![LiPower Shield5.jpg](https://wiki.elecrow.com/images/thumb/4/4e/LiPower_Shield5.jpg/600px-LiPower_Shield5.jpg){ loading=lazy }

Then open your serial monitor and set the baud rate at 9600, observe the output.

![LiPower Shield6.png](https://wiki.elecrow.com/images/b/b0/LiPower_Shield6.png){ loading=lazy }

## How to buy
----------

You can click [here](https://www.elecrow.com/lipower-shield.html) to buy LiPower Shield.

## Resources
---------

- [Power detection program](https://wiki.elecrow.com/images/9/9c/Lipower_shield.zip)
- [Eagle files](https://wiki.elecrow.com/images/4/44/LiPower_Shield_v1.0.zip)
- [MAX17043G+U](https://wiki.elecrow.com/images/b/b7/MAX17043-MAX17044.pdf)
- [MCP738312](https://wiki.elecrow.com/images/0/02/MCP738312.pdf)