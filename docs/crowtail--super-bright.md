---
title: Crowtail- Super Bright
---

## Description
-----------

Crowtail- Super Bright is a high brightness and large angle LED. Then it low thermal resistancea it can be applied to indoor lighting, commercial lighting, you can provide a strong light source for your project, lighting, lighting or so on.

Model:[CRT00536L](https://www.elecrow.com/crowtail-bright-led.html)


![Crowtail-Super Bright.jpg](https://wiki.elecrow.com/images/thumb/e/ed/Crowtail-Super_Bright.jpg/600px-Crowtail-Super_Bright.jpg){ loading=lazy }

## Features
--------

- Operating Voltage: 5VDC
- Opearting Current: 20mA (Max)

## Specification
-------------

Dimensions(mm):20.0(L)x20.0(W)x9.8(H)

| Item | Description |
|:-:|:-:|
| LED Control Mode | Digital Pin of Arduino |
| Working Voltage | 5V |
| Supply Mode | Crowtail Interface |

## Usage
-----

1\. Connect the LED to Base Shield's digital D12 with 4pin Crowtail Cable and micro USB cable to micro USB port.

![Bright connect1.jpg](https://wiki.elecrow.com/images/thumb/d/d6/Bright_connect1.jpg/500px-Bright_connect1.jpg){ loading=lazy }

2.Copy the demo code to your sketch, then upload to Arduino or Crowduino board.

```
const int ledpin=12;   
void setup()
{
  pinMode(ledpin,OUTPUT); 
}
void loop()
{
  digitalWrite(ledpin,HIGH); 
  delay(1000);
  digitalWrite(ledpin,LOW); 
  delay(1000);
}
```

3.You will see the LED blink every second.

![Bright off1.jpg](https://wiki.elecrow.com/images/thumb/4/4e/Bright_off1.jpg/500px-Bright_off1.jpg){ loading=lazy }

## Resource
--------

- [LED schematic](./files/Super-bright-schematic-zip.md)
- [LED Code](./files/Super-bright-code-zip.md)