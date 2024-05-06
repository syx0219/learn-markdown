---
title: Crowtail- Electromagnet
---

## Description
-----------

An electromagnet is a type of magnet in which the magnetic field is produced by electric current. An electric current flowing in a wire creates a magnetic field around the wire, due to Ampere's law(see drawing below). To concentrate the magnetic field, in an electromagnet the wire is wound into a coil with many turns of wire lying side by side. The magnetic field of all the turns of wire passes through the center of the coil, creating a strong magnetic field there. Crowtail- Electromagnet can shuck 1KG weight and hold on. it easy to use, to learn electromagnet principle..

**Model: [CT008617E](http://www.elecrow.com/crowtail-electromagnet-p-1644.html)**

![Crowtail- Electromagnet.jpg](https://wiki.elecrow.com/images/thumb/5/5e/Crowtail-_Electromagnet.jpg/600px-Crowtail-_Electromagnet.jpg){ loading=lazy }

## Features
--------

- Easy to use
- Crowtail base module
- 1KG peak suction
- Low standby current

## Specifications
--------------

- Working Voltage ：DC 5V
- Working Current ： 400mA
- Standby current ： 200uA
- Load Weight： 1KG
- Dimensions(mm):40.0(L)x20.0(W)x20.8(H)

## Usage
-----

### **With Arduino**

1.Hardware Connection
The Crowtail- Electromagnetr is connecting to analog port D2 of Crowtail - Base Shield. A Button is connecting to D5.
![6155026001.jpg](https://wiki.elecrow.com/images/thumb/7/7d/6155026001.jpg/600px-6155026001.jpg){ loading=lazy }

2.Copy the demo code to your sketch, then upload to Arduino or Crowduino board.

```
int Electromagnet = 2;
int button = 5;
int buttonstate;

void setup() {                
  pinMode(Electromagnet, OUTPUT); 
  pinMode(button, INPUT);   
}
void loop() {
   buttonstate=digitalRead(button); 
   if(buttonstate==HIGH)
   {
  digitalWrite(Electromagnet, HIGH);
  delay(200); 
  
}
else
{
digitalWrite(Electromagnet, LOW);
 delay(200); 
}
}

```

3\. Press the Button, you will find that the magnet is magnetic, and it can adsorption something (1 kg), loosen the Button, magnetic disappeared..

## Resource
--------

- [ZYE1-P20-15](./files/ZYE1-P20-15-pdf.md)
- [Crowtail- Electromagnet eagle file](./files/Crowtail-Electromagnet-eagle-file-zip.md)