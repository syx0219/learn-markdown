---
title: Crowtail- Buzzer
---

## Description
-----------

The buzzer module is for making sound in your project. It sounds when activated by a logic HIGH signal. Connect the buzzer to any of the D(digital) ports of Crowtail- Base Shiled, you can easily make it sounds with setting the related ports to logic HIHG. The buzzer module can be also connected to an analog pluse-width modulation(PWM) output to generate various of tones.

**Model: [CT0003BU](http://www.elecrow.com/crowtail-buzzer-p-1223.html)**

![Crowtail-Buzzer.JPG](https://wiki.elecrow.com/images/thumb/7/75/Crowtail-Buzzer.JPG/600px-Crowtail-Buzzer.JPG){ loading=lazy }

## Features
--------

- Easy to use piezoelectric buzzer
- Standard 3-pin Crowtail Cables

## Specifications
--------------

- Operating Voltage: 5V
- Sound Output: ≥85dB
- Resonant Frequency: 2300±300Hz
- Dimensions(mm):20.0(L)x20.0(W)x9.8(H)

## Usage
-----

Follow these simple steps to build a Crowtail circuit using the buzzer:

1.Hardware connection Use the Crowtail - Base Shield and connect the Crowtail - Buzzer module to the shield using a designated Crowtail Interface as shown below:

![Buzzercontro.jpg](https://wiki.elecrow.com/images/thumb/b/b4/Buzzercontro.jpg/400px-Buzzercontro.jpg){ loading=lazy }

2.Upload the following sample sketch to make the Buzzer make a beeping noise:

```
#define buzzer 5 //connect Buzzer to digital pin5
void setup() {                
 // initialize the digital pin5 as an output.
 pinMode(buzzer, OUTPUT);     
}

void loop() {
 digitalWrite(buzzer, HIGH);   // set the Buzzer on
 delay(500);                  // for 500ms
 digitalWrite(buzzer, LOW);   // set the Buzzer off
 delay(500);
}
```

## Resource
--------

- [Buzzer Program](../../files/Buzzer-zip.md)
- [Crowtail\_Buzzer\_eagle\_files](../../files/Crowtail-Buzzer-files-zip.md)