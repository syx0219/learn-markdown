---
title: Crowtail- Dual Channel Latching Module
---

## Description
-----------

This is a dual-channel latching relay, it does not need continuous power to keep the state, only a rising/falling pulse is needed to change the work state. so the power supply can be cut off without changing the operating state. This module is specifically designed for low power consumption circuit design.

Model: [CRT01665R](https://www.elecrow.com/crowtail-dual-coil-latching-relay-module.html)

![Crowtail-Dual Channel Latching Module.jpg](https://wiki.elecrow.com/images/thumb/7/73/Crowtail-Dual_Channel_Latching_Module.jpg/400px-Crowtail-Dual_Channel_Latching_Module.jpg){ loading=lazy }

## Features
--------

- Dual Switch
- Low power consumption
- High sensitivity 150mW
- High switching capacity 60W,125VA
- Epoxy sealed for automatic wave soldering and cleaning

## Specification
-------------

Dimensions(mm):50.0(L)x35.0(W)x14.3(H)

| Parameter | Description |
|:-:|:-:|
| Operating Voltage | 5V |
| Set/Reset Voltage(Max) | 4.0VDC |
| Switching Voltage(Max) | 35VAC/35VDC |
| Switching Current(Max) | 3A |
| Max Switching Current | 3A |
| Set Time(Latching) | 4.5(max)ms |
| Reset Time(Latching) | 3.5(max)ms |

## Usage
-----

1.Connect the segment according to the following figure. The com pin is connected to the pin5, NC connected to the GND, NO and connected to the VCC.

![DUAL CONNECT1.jpg](https://wiki.elecrow.com/images/thumb/5/55/DUAL_CONNECT1.jpg/500px-DUAL_CONNECT1.jpg){ loading=lazy }

2.Relay is connected to the D3, D2 and D4 is connected to the LED.

![DUAL CONNECT21.jpg](https://wiki.elecrow.com/images/thumb/e/e7/DUAL_CONNECT21.jpg/500px-DUAL_CONNECT21.jpg){ loading=lazy }

3.Connect to USB, copy the program and upload it to the board

![DUAL UPLOAD2.jpg](https://wiki.elecrow.com/images/thumb/3/36/DUAL_UPLOAD2.jpg/500px-DUAL_UPLOAD2.jpg){ loading=lazy }

```
int relay=3;
int led1=4;
int led2=2;
int relayin1=5;
void setup()
{
  pinMode(relay,OUTPUT);
  pinMode(led1,OUTPUT);
  pinMode(led2,OUTPUT);
  pinMode(relayin1,INPUT);
  // put your setup code here, to run once:

}

void loop()
{
  /* first lift */
   digitalWrite(relay,HIGH);

   
   /* simply relay  and wait relay response */
   delay(200);
   if(digitalRead(relayin1)==HIGH)
   {
     digitalWrite(led1,HIGH);
     digitalWrite(led2,LOW);
   }
   else
   {
     digitalWrite(led1,LOW);
     digitalWrite(led2,HIGH);
   } 
   delay(5000);

   /* second lift */
   digitalWrite(relay,LOW);
   
   /* simply relay  and wait relay response */
   delay(200);
   if(digitalRead(relayin1)==HIGH)
   {
     digitalWrite(led1,HIGH);
     digitalWrite(led2,LOW);
   }
   else
   {
     digitalWrite(led1,LOW);
     digitalWrite(led2,HIGH);
   }    
   delay(5000);
  // put your main code here, to run repeatedly:

}
```

4.You can use external power supply or USB power supply.

![DUAL GREED2.jpg](https://wiki.elecrow.com/images/thumb/9/9d/DUAL_GREED2.jpg/500px-DUAL_GREED2.jpg){ loading=lazy }

5\. Observe RELAY module NO lights flashing, and green light, proved NO work! Green light; RELAY module on the NC module, NC lights flashing, and red, proved NC end work.

![DUAL RED1.jpg](https://wiki.elecrow.com/images/thumb/d/d0/DUAL_RED1.jpg/500px-DUAL_RED1.jpg){ loading=lazy }

## Resource
--------

- [Dual Channel code](https://wiki.elecrow.com/images/3/35/Dual_Channel_code.zip)
- [Dual Channel schematic](https://wiki.elecrow.com/images/5/50/Dual_Channel_schematic.zip)