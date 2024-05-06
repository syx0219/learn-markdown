---
title: Crowtail- Laser Pointer
---

## Description
-----------

A change of Laser Pointer is that we make it compatible with Crowtail base board, you can use it more easier than before. This laser pointer or laser pen is a small handheld device with a laser diode emitting a very narrow coherent low-powered laser beam of visible light, it is frequently used in lecture halls and demonstrations to point at topics of interest on a presentation board. In a school setting, they have become ubiquitous, and they are very useful teaching aids. Please note that DO NOT Point this module to eyes directly, It may cause some blindness, glare and afterimages.

**Model: [CT0048CLP](http://www.elecrow.com/crowtail-laser-pointer-p-1507.html)**
![CT0048CLP-07.jpg](https://wiki.elecrow.com/images/thumb/3/3b/CT0048CLP-07.jpg/600px-CT0048CLP-07.jpg){ loading=lazy }

## Features
--------

- Supply voltage:5V
- Power:5mW
- Wavelength :650nm
- Dimensions(mm):26.4(L)x20.0(W)x7.9(H)

## Usage
-----

1.Hardware Connection
Plug the Crowtail- Laser Pointer onto the D5 port on Crowtail - Base Shield, and then plug the base shield onto Crowduino;

![Crowtail- Laser Pointer11.jpg](https://wiki.elecrow.com/images/thumb/c/c0/Crowtail-_Laser_Pointer11.jpg/600px-Crowtail-_Laser_Pointer11.jpg){ loading=lazy }

2.Download the library from here Crowtail- Laser Pointer \[[Crowtail- Laser Pointer Program](https://wiki.elecrow.com/images/1/14/Crowtail-_Laser_Pointer.zip)\]

3.Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0.1\\libraries.

4.Create an Arduino sketch and paste the following codes to it or open the code directly by the path:File -&gt; Example -&gt; Crowtail- Laser Pointer.

```
int Laser_Pointer = 5;


void setup() {                

  pinMode(Laser_Pointer, OUTPUT);     
}


void loop() {
  digitalWrite(Laser_Pointer, HIGH);   
  delay(2000);            
  digitalWrite(Laser_Pointer, LOW);  
  delay(1000); 
}
```

4.Upload it into your Crowduino board and observe the change of the Laser Pointer's light.

## Resource
--------

- [Crowtail- Laser Pointer Program](https://wiki.elecrow.com/images/1/14/Crowtail-_Laser_Pointer.zip)
- [Crowtail- Laser Pointer eagle files](https://wiki.elecrow.com/images/9/9d/Crowtail-_Laser_Pointer_v1.0.zip)