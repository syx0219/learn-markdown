---
title: Crowbits-Non-Contact Liquid Level Sensor
---

## Description
-----------

Intelligent non-contact liquid level sensor (here in after referred to as the liquid level sensor) adopted the advanced signal processing technology and high-speed signal processing chip, broke through the vessel wall thickness, the influence of realized in an airtight container level of real non-contact detection. Liquid level sensor (probe) installed on the outer wall of the container to be tested on the lower part (level of high and low), non-metallic containers without the hole, easy to install, do not affect production. Can realize various toxic substances of high pressure airtight container, strong acid, strong alkali and all kinds of liquid level detection. The material of liquid level sensor for liquid medium and container no special requirements, can be widely used.

![Crowbits-Non-Contact Liquid Level Sensor1.jpg](https://wiki.elecrow.com/images/thumb/1/18/Crowbits-Non-Contact_Liquid_Level_Sensor1.jpg/600px-Crowbits-Non-Contact_Liquid_Level_Sensor1.jpg){ loading=lazy }

## Features
--------

- No direct contact with liquid
- Working Voltage: 3.3V
- Induction distance can reach more than 12 mm
- Easy to use

## Specification
-------------

- The thickness of the induction (sensitivity) 0 ～ 20 mm
- humidity 5% ～ 100%
- The material ABS.
- Waterproof properties IP67
- Sensor dimensions(mm):28.3(L)x28.3(W)x17.0(H)
- Cable length:58.5cm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1.You need to prepare a Crowbits motherboard, such as Crowbits-UNO board. And an output module, such as Crowbits-LED.

2.Connect the Crowbits-Non-Contact Liquid Level Sensor to the D2 interface of the Crowbits-UNO board, and Crowbits-LED to the D9 Interface.


3.Upload the following code to the Crowbits-UNO board.

```
int liquid_level=2;
int buzzer=9;
int liquid_state=0;

void setup()
{
   pinMode( liquid_level,INPUT);
   pinMode(buzzer,OUTPUT);
}

void loop()
{
 liquid_state=digitalRead(liquid_level);
 if(liquid_state==HIGH)
 {
 digitalWrite(buzzer,HIGH);
 }
 else
 {
  digitalWrite(buzzer,LOW);
 }
}
```

4\. After the upload is successful, open the serial port monitor, the baud rate is set to 9600. Then send a command to call.