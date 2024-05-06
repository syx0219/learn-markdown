---
title: Relay Shield
---

## Introduction
------------

The Relay Shield is an Arduino compatible smart module with 4 mechanical relays providing an easy way to control high voltage. The max switching power is 35VDC 70W for each channel. It can be directly controlled by Arduino/Crowduino through digital IOs with an external 6.5~12V DC supply. With the onboard 4 control keys,you can also control the high voltage without programming.

**Note**: Take care the pins on the Shield should not touched the USB connector of Arduino UNO when they connected .

**Model: [MCS01584R](http://www.elecrow.com/relay-shield-v11-p-732.html)**

![Relay Shield.jpg](https://wiki.elecrow.com/images/thumb/2/24/Relay_Shield.jpg/600px-Relay_Shield.jpg){ loading=lazy }

## Features
--------

- Arduino,Crowduino,Seeeduino,Arduino Mega compatible
- Automatic control and manual control
- 4 mechanical relays with photo-coupled circuit
- Equipped with screw holes for easy installation
- Light weight
- Small form factor
- Native Arduino/Seeeduino compatibility
- Extendible

## Specification
-------------

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
      <th scope="row">Voltage</th>
      <td align="center">7</td>
      <td align="center">9</td>
      <td align="center">12</td>
      <td align="center">VDC</td>
    </tr>
    <tr>
      <th scope="row">Current</th>
      <td align="center">8</td>
      <td align="center">/</td>
      <td align="center">250</td>
      <td align="center">mA</td>
    </tr>
    <tr>
      <th scope="row">Switching Voltage</th>
      <td align="center">/</td>
      <td align="center">/</td>
      <td align="center">35</td>
      <td align="center">VDC</td>
    </tr>
    <tr>
      <th scope="row">Switching Current</th>
      <td align="center">/</td>
      <td align="center">/</td>
      <td align="center">2</td>
      <td align="center">A</td>
    </tr>
    <tr>
      <th scope="row">Frequency Response</th>
      <td align="center">-1</td>
      <td align="center">/</td>
      <td align="center">1</td>
      <td align="center">dB</td>
    </tr>
    <tr>
        <th scope="row">Switching Power</th>
         <td align="center">/</td>
        <td align="center">/</td>
        <td align="center">70</td>
        <td align="center">W</td>
    </tr>
    <tr>
        <th scope="row">Relay Life</th>
        <td align="center">100,000</td>
        <td align="center">/</td>
        <td align="center">/</td>
        <td align="center">Cycle</td>
    </tr>
    <tr>
        <th scope="row">ESD contact discharge</th>
        <td align="center" colspan="3">±4</td>
        <td align="center">KV</td>
    </tr>
    <tr>
        <th scope="row">ESD air discharge</th>
        <td align="center" colspan="3">±8</td>
        <td align="center">/</td>
    </tr>
    <tr>
      <th scope="row">Dimension</th>
      <td align="center" colspan="3">75.0(L)x56.8(W)x23.5(H)</td>
      <td align="center">mm</td>
    </tr>
    <tr>
      <th scope="row">Net Weight</th>
      <td align="center" colspan="3"> </td>
      <td align="center">g</td>
    </tr>
  </tbody>
</table>

## Cautions
--------

- <font color="red">**Place 2 layers of electrical tape on the top of the Arduino's usb connector. This will prevent the relay shield from making contact.**
- **Do not operate voltage more than 35V DC.**
- **Please be cautious while operating high voltage circuits! You may get hurt or hurt your appliances if used improperly.**</font> 

## Interface Function
------------------

![Shield schematic.jpg](https://wiki.elecrow.com/images/5/56/Shield_schematic.jpg){ loading=lazy }

**4 groups of channels for High voltage connection**  
Terminal 1:  
COM1- Common pin  
NC1- Normally Closed, in which case NC1 is connected with COM1 when D0 is set low and disconnected when D0 is high;  
NO1- Normally Open, in which case NO1 is disconnected with COM1 when D0 is set low and connected when D0 is high.  
Terminal 2-4 are similar to terminal 1, except that the control ports are D1-D3.  

**9V DC power supply connection**  
The function of the Terminal and the Jack is the same since they are internally connected, and you can choose either of them in needs.

**IO controlling 4 on-board relays**  
C0-C3 4pins could be connected directly with Arduino pin number of 7-4, so that four relays could be easily controlled by the Arduino.  
K1-K4 4keys could control the four relays without programming.


## Usage
------

**With Arduino/Crowduino**  
Relay Shield could be directly controlled by Arduino or [Crowduino](https://www.elecrow.com/crowduino-with-atmega-328-v11-p-338.html).

![RelaywithCrowduino.jpg](https://wiki.elecrow.com/images/thumb/9/95/RelaywithCrowduino.jpg/600px-RelaywithCrowduino.jpg){ loading=lazy }

Step1. Plug Relay Shield onto Arduino Duemilanove (or compatible) board;  
Step2. Supply 9v DC power to Arduino;  
Step3. Download the [example code](http://www.elecrow.com/wiki/images/9/92/Relay_control_code.zip) and run in [Arduino IDE](http://arduino.cc/en/Main/Software).  
If using Arduino via its USB connection for power, you must also provide 9v DC power to the Relay Shield or the relays won't switch.  
Relays 1-4 can be activated by setting Arduino ports 4-7 to output, and doing a digitalWrite(portNumber,HIGH).  
Use COMx and either NCx (normally closed) or NOx (normally opened) connections to switch power through to the controlled device.   
**example code**

```
void setup()
{
pinMode(4,OUTPUT);
pinMode(5,OUTPUT);
pinMode(6,OUTPUT);
pinMode(7,OUTPUT);
}
void loop()
{
digitalWrite(4,HIGH);
digitalWrite(5,HIGH);
digitalWrite(6,HIGH);
digitalWrite(7,HIGH);
delay(1500);
digitalWrite(4,LOW);
digitalWrite(5,LOW);
digitalWrite(6,LOW);
digitalWrite(7,LOW);
delay(1500);
}
```

After downloanding the above code to your Arduino, the relays, with the relative LED on relay shield ,will be switch on and off with a period of 3 seconds. you will hear some noice "bang …bang..” when the relay works.

You can also control the relays with the on-board keys, just have a try...

## Support
-------

You can contact with **techsupport@elecrow.com**.

## How to buy
----------

You can click [here](http://www.elecrow.com/relay-shield-v11-p-732.html) to buy Relay Shield.

## Resources
---------

- [Relay Shield v1.0 Schematic](http://www.elecrow.com/wiki/images/e/ee/Relay_shield_v1.01.pdf)
- [Relay Shield demo code for Arduino](https://wiki.elecrow.com/images/9/92/Relay_control_code.zip)