---
title: Crowtail- SPDT Relay
---

## Description
-----------

The SPDT relay module is a high performance single pole double throw relay and can operate with 30A current. When the relay does not work, COM and NC have continuity, when the relay work, COM and NO have continuity. Can be it usually be used as power switches, electric heaters, fans, air conditioners, and a variety of common household switch appliances. If you want to control the high current, it will give you a lot of convenience.

model: [CRT03349R](https://www.elecrow.com/crowtail-spdt-relay.html)

![Crowtail-SPDT Relay v0.9.jpg](https://wiki.elecrow.com/images/thumb/0/0a/Crowtail-SPDT_Relay_v0.9.jpg/400px-Crowtail-SPDT_Relay_v0.9.jpg){ loading=lazy }

## Features
--------

- SPDT Switch
- 30A, 250VAC, 30VDC
- High current

## Specification
-------------

Dimensions(mm):50.0(L)x35.0(W)x22.6(H)

| Parameter | Description |
|:-:|:-:|
| Operating Voltage | 5V |
| Operating Current | 185mA |
| Pull-in Votage(Max) | 3.75VDC |

## Usage
-----

1.Connect the Crowtail LED(red) to D3 port of base shield,connect Crowtail SPDT Relay to D2 port.and then connect COM of the SPDT Relay to PIN4 of base shield,connect NO to GND,connect NC to VCC,flowing the picture:

![SPDT CONNECT1.jpg](https://wiki.elecrow.com/images/thumb/5/55/SPDT_CONNECT1.jpg/500px-SPDT_CONNECT1.jpg){ loading=lazy }

2.Copy the demo code to your sketch, then upload to Arduino or Crowduino board.

```
int led=3;
int relay=2;
int relayin=4;
void setup() 
{
  pinMode(relay,OUTPUT);
  pinMode(led,OUTPUT);
  pinMode(relayin,INPUT);
  // put your setup code here, to run once:

}

void loop() 
{
  digitalWrite(relay,HIGH);
  delay(250);
  if(digitalRead(relayin)==HIGH)
  {
     digitalWrite(led,HIGH); 
   }
   else
   {
      digitalWrite(led,LOW);   
   }
  delay(2000);
  digitalWrite(relay,LOW);
  delay(250);
  if(digitalRead(relayin)==HIGH)
  {
     digitalWrite(led,HIGH); 
   }
   else
   {
      digitalWrite(led,LOW);   
   }
  delay(2000);
  // put your main code here, to run repeatedly:

}
```

3.If the D2 light on the relay board is bright and the LED of connected to the D3 lights out, it indicates that the relay COM is connected to the NO.Test passed. Following picture:

![SPDT RED1.jpg](https://wiki.elecrow.com/images/thumb/d/d3/SPDT_RED1.jpg/500px-SPDT_RED1.jpg){ loading=lazy }

4.If the D2 on the relay board is turned off, the LED light of connected with the D3 is switched on and the relay COM is connected to the NC.Test passed. Following picture:

![SPDT green1.jpg](https://wiki.elecrow.com/images/thumb/b/be/SPDT_green1.jpg/500px-SPDT_green1.jpg){ loading=lazy }

## Resource
--------

- [SPDT code](../../files/SPDT-code-zip.md)
- [SPDT schematic diagram](../../files/SPDT-schematic-diagram-zip.md)