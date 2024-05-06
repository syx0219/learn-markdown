---
title: Crowtail- 4-Digit Display
---

## Description
-----------

Usually 4 digit display module is a 12 pin module. But in our Crowtail gadget, we utilize a TM1637 to scale down the controlling pins into 2 Crowtail pins. It only takes 2 digital pins of Arduino or Crowduino to control the content, even the luminance of this display. For projects that require of alpha-numeric display, this can be a nice choice.

**Model: [CT0060FDD](https://www.elecrow.com/crowtail-4-digit-display.html)**

![Crowtail- 4-Digit Display1.JPG](https://wiki.elecrow.com/images/thumb/e/e1/Crowtail-_4-Digit_Display1.JPG/400px-Crowtail-_4-Digit_Display1.JPG){ loading=lazy }

## Features
--------

- Compatible with Crowtail interface
- 4 digit red alpha-numeric display
- 8 adjustable luminance levels
- Dimensions(mm):40.0(L)x20.0(W)x12.8(H)

## Application Ideas
-----------------

- Time display
- Stopwatch
- Sensors' input display

## Usage
-----

The following sketch demonstrates a simple application of digital display.

1.Hardware Connection.  
Connect to I2C connetor on the base shield for Arduino.  
![Crowtail- 4-Digit Display Hardware Connection12.JPG](https://wiki.elecrow.com/images/thumb/2/22/Crowtail-_4-Digit_Display_Hardware_Connection12.JPG/400px-Crowtail-_4-Digit_Display_Hardware_Connection12.JPG){ loading=lazy }

2.Download the library [Crowtail- 4-Digit Display library](https://wiki.elecrow.com/images/4/43/Crowtail-_4-Digit_Display.zip); Unzip and put it in the libraries file : ..\\arduino-1.0\\libraries;

3.Open “\_4Digital7\_SegmentLED ” example via the path: File --&gt; TM1650 --&gt; Examples --&gt; \_4Digital7\_SegmentLED.

```
/*
	Demo code of P21 - 4 Digital 7-Segment LED with Time Separator
	by maker studio
*/
#include "TM1650.h"
#include <inttypes.h>
static uint8_t TubeTab[] = {
						   0x3F,0x06,0x5B,0x4F,
						   0x66,0x6D,0x7D,0x07,
						   0x7F,0x6F,0x77,0x7C,
						   0x39,0x5E,0x79,0x71,   
						   };//0~9,A,B,C,D,E,F  
static uint8_t TubeTabwithPoit[] = {
						   0xBF,0x86,0xDB,0xCF,
						   0xE6,0xED,0xFD,0x87,
						   0xFF,0xEF   
						   };//0~9  
TM1650 DigitalLED(A5,A4);
int8_t number[] = {0,0,0,0};
void setup()
{
	//Serial.begin(9600);
}

void loop()
{
    DigitalLED.clearDisplay();
     delay(1000);
     DigitalLED.display(0,TubeTab[1]);
     DigitalLED.display(1,TubeTab[2]);
     DigitalLED.display(2,TubeTab[3]);
     DigitalLED.display(3,TubeTab[4]);
     delay(1000);
     DigitalLED.clearDisplay();
     delay(100);
     DigitalLED.display(0,TubeTabwithPoit[5]);
     DigitalLED.display(1,TubeTabwithPoit[6]);
     DigitalLED.display(2,TubeTabwithPoit[7]);
     DigitalLED.display(3,TubeTabwithPoit[8]);
     delay(1000);
}
```

4.Upload it into your Crowduino board and observe the Digit-Display.

![The result372.jpg](https://wiki.elecrow.com/images/thumb/7/79/The_result372.jpg/400px-The_result372.jpg){ loading=lazy }

## Resource
--------

- [Crowtail- 4-Digit Display Program](https://wiki.elecrow.com/images/4/43/Crowtail-_4-Digit_Display.zip)
- [Crowtail- 4-Digit Display eagle files](https://wiki.elecrow.com/images/3/3c/Crowtail-_4-Digit_Display_eagle_files.zip)