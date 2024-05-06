---
title: Crowtail- Protoboard
---

## Description
-----------

This Crowtail allows you to add your own circuitry or components to your Crowtail system prototypes. It gives you access to all four lines from the crowtail connector cable – S0, S1, VCC and GND. There is also a reserved space for a normally-open button. Standard 2.54mm spacing makes it easy to install normal DIP-format ICs and other components onto the board.

**Model: [CT008726P](http://www.elecrow.com/crowtail-protoboard-p-1645.html)**

![Crowtail- Protoboard.jpg](https://wiki.elecrow.com/images/thumb/6/6c/Crowtail-_Protoboard.jpg/600px-Crowtail-_Protoboard.jpg){ loading=lazy }

## Features
--------

- Standardised Grove Interface
- Breadboard style
- Standard spacings
- Silk screen labels
- Reserved space for normally-open button
- Dimensions(mm):40.0(L)x20.0(W)x9.8(H)

## Usage
-----

VCC and GND of the Grove interface are routed out as two buses as shown above. You can find soldering pads of Sig0 and Sig1 between two power buses. They are marked out by white lines. The square area on the right is for a ubiquitous temporary button, you can easily snap one into it as shown below.

![20160524114014.png](https://wiki.elecrow.com/images/thumb/3/3f/20160524114014.png/400px-20160524114014.png){ loading=lazy }

Also the protoshield is shipped with two 20-pin male headers. You can break them into smaller pieces and solder them onto protoshield when you need extension on other breadboard or protoboard. They work well with normal breadboard jumpers.

![20160524114037.png](https://wiki.elecrow.com/images/thumb/c/c8/20160524114037.png/400px-20160524114037.png){ loading=lazy }

### **Demo: Light LED**

1\. Insert the longer pin of LED into the VCC interface and the shorter pin into Sig0 interface.

2\. Solder LED on the Protoshield and let it connect to sig0.

![20160524114050.png](https://wiki.elecrow.com/images/thumb/1/1d/20160524114050.png/400px-20160524114050.png){ loading=lazy }

3\. Connect the module to the U3 port of Crowtail- Basic Shield using the 4-pin Crowtail cable.

4\. Plug the Crowtail- Basic Shield into Arduino and connect Arduino to PC by using a USB cable.

5\. Copy and paste code below to a new Arduino sketch.

```
int led = 7;// Sig0 connect the digital pin 7.

// the setup routine runs once when you press reset:
void setup() {                
  // initialize the digital pin as an output.
  pinMode(led, OUTPUT);     
}

// the loop routine runs over and over again forever:
void loop() {
  digitalWrite(led, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);               // wait for a second
  digitalWrite(led, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);               // wait for a second
}
```

## Resource
--------

- [Crowtail- Protoboard eagle files v1.0](./files/Crowtail-Protoboard-v1.0-eagle-file-zip.md)