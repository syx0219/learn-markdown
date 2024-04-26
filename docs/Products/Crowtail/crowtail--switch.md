---
title: Crowtail- Switch
---

## Description
-----------

The Crowtail- Switch is a Latching switch. When the first press the switch, the switch and keep the current adjustment and the button outputs a HIGH signal,namely the self-locking. When the second press the switch, the switch off and switch button to pop up at the same time, outputs a LOW signal.

**Model: [CT008833S](http://www.elecrow.com/crowtail-switch-p-1646.html)**

![Crowtail- Switch.jpg](https://wiki.elecrow.com/images/thumb/d/d2/Crowtail-_Switch.jpg/600px-Crowtail-_Switch.jpg){ loading=lazy }

## Features
--------

- Easy to use momentary ON/OFF Switch
- Uses Standard 4-pin Crowtail Cables to connect to the Crowtail - Base Shield
- Dimensions(mm):20.0(L)x20.0(W)x15.2(H)

## Usage
-----

Switch control LED

1.Hardware connection

![Switch11.jpg](https://wiki.elecrow.com/images/thumb/f/fb/Switch11.jpg/500px-Switch11.jpg){ loading=lazy }

2.Upload the following sample sketch to make the LED turn ON and OFF based on input from Crowtail- Switch:

```
int ledpin=5;
 int button = 2;
void setup()
{
  pinMode(ledpin,OUTPUT);
  pinMode(button,INPUT); 
}
void loop()
{
  if(digitalRead(button)){
  digitalWrite(ledpin,HIGH);
 }
 else{
 digitalWrite(ledpin,LOW);
 }
}
```

3.Press the Switch first time, you will see the LED lights up, press the Switch again,you will see the LED lights off.

## Resource
--------

- [Crowtail\_Switch\_eagle\_files](../../files/Crowtail-Switch-eagle-files-zip.md)