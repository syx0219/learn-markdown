---
title: Crowbits-Digital Display
---

## Description
-----------

The nixie tube is composed of four 7-segment nixie tubes. Each 7-segment nixie tube can display a number. It can display all the parameters that can be represented by numbers, such as time, date, and temperature. The module has an LED driver chip TM1650, which can communicate through the I2C interface. When the module receives data, it is encoded by TM1650 and sent to the digital display.

![Crowbits-Digital-Display-1.jpg](https://wiki.elecrow.com/images/thumb/b/b0/Crowbits-Digital-Display-1.jpg/700px-Crowbits-Digital-Display-1.jpg){ loading=lazy }

## Features
--------

- 4-digit red alpha-numeric display

## Specification
-------------

- Interface Type：I2C
- Operating Voltage: 3.3V DC
- Dimensions: 56(L)\*31(W)\*13(H)mm

## Application Ideas
-----------------

- Time display
- Stopwatch

## Usage
-----

The following sketch demonstrates a simple application of digital display.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the I2C interface on the Crowbits-UNO board, as shown in the figure:

![Crowbits-Digital Display-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/6/63/Crowbits-Digital_Display-Wiki_1.JPG/700px-Crowbits-Digital_Display-Wiki_1.JPG){ loading=lazy }

3\. Download the library Crowbits-Digital Display library. Unzip and put it in the libraries file, for example: C:\\Program Files (x86)\\Arduino\\libraries.

4\. Upload the following code to the Crowbits-UNO board.

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

5\. After the code is uploaded successfully, you will see the following display on the digital tube.

![Crowbits-Digital-Display Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/1/16/Crowbits-Digital-Display_Wiki_2.jpg/700px-Crowbits-Digital-Display_Wiki_2.jpg){ loading=lazy }

![Crowbits-Digital Display-Wiki3.JPG](https://wiki.elecrow.com/images/thumb/4/44/Crowbits-Digital_Display-Wiki3.JPG/700px-Crowbits-Digital_Display-Wiki3.JPG){ loading=lazy }