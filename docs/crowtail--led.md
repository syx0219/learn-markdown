---
title: Crowtail- LED
---

## Description
-----------

The Crowtail-LED is designed for the beginners of Arduino. It is the best way to step into the Aduino from it’s I/O pins. The LED is the best choice to help you learn I/O pins.

**Model: [CT0006LD](http://www.elecrow.com/crowtail-led-p-1224.html)**

![Crowtail-LED1.JPG](https://wiki.elecrow.com/images/thumb/4/4f/Crowtail-LED1.JPG/600px-Crowtail-LED1.JPG){ loading=lazy }

## Features
--------

- Crowtail compatible interface
- 3.3V/5V Compatible
- 8mm LED

## Specification
-------------

- Dimensions(mm):20.0(L)x20.0(W)x13.0(H)

| Item | Description |
|:-:|:-:|
| LED Control Mode | Digital Pin of Arduino |
| Working Voltage | 5V |
| Supply Mode | Crowtail Interface |

## Usage
-----

1\. Connect the LED to Base Shield's digital port 5 with 3pin Crowtail Cable.

2\. Plug it onto the Arduino/Crowduino. Connect the board to PC using USB cable.

![Ledcontro.jpg](https://wiki.elecrow.com/images/thumb/c/c1/Ledcontro.jpg/400px-Ledcontro.jpg){ loading=lazy }

3.Copy the demo code to your sketch, then upload to Arduino or Crowduino board.You will see the LED blink every second.

```
#define LED 5 //connect LED to digital pin5
void setup() {                
 // initialize the digital pin5 as an output.
 pinMode(LED, OUTPUT);     
}

void loop() {
 digitalWrite(LED, HIGH);   // set the LED on
 delay(500);               // for 500ms
 digitalWrite(LED, LOW);   // set the LED off
 delay(500);
}
```

4.Test result:  
![LED result11.jpg](https://wiki.elecrow.com/images/thumb/d/da/LED_result11.jpg/400px-LED_result11.jpg){ loading=lazy } 
![LED result22.jpg](https://wiki.elecrow.com/images/thumb/d/d9/LED_result22.jpg/400px-LED_result22.jpg){ loading=lazy }

## Resource
--------

- [LED Program](./files/LED-zip.md)
- [Crowtail\_LED\_eagle\_files](./files/Crowtail-LED-v1.1-zip.md)