---
title: Crowbits-RGB Matrix
---

## Description
-----------

The RGB Matrix module is an 8 \* 8 matrix display module composed of 64 rgb led lamp beads. It can respond to changes in input signals in monochrome, full-color, gradual, and horse racing modes, and can also display simple graphics.

![Crowbits-RGB-Matrix-1.jpg](https://wiki.elecrow.com/images/8/80/Crowbits-RGB-Matrix-1.jpg){ loading=lazy }

## Features
--------

- Low power consumption
- Easy to use

## Specification
-------------

- Operating Voltage: 3.3V DC
- Dimensions: 56(L)\*56(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the D11 interface of the Crowbits-UNO board, as shown in the figure:

![Crowbits-RGB Matrix-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/7/75/Crowbits-RGB_Matrix-Wiki_1.JPG/600px-Crowbits-RGB_Matrix-Wiki_1.JPG){ loading=lazy }

3\. Download the library FastLED-3.2.10. Unzip and put it in the libraries file, for example: C:\\Program Files (x86)\\Arduino\\libraries.

4\. Upload the following code to the Crowbits-UNO board.

```
#include <FastLED.h>
#define NUM_LEDS 64

CRGBArray<NUM_LEDS> leds;

void setup() { FastLED.addLeds<WS2812B,11,GRB>(leds, NUM_LEDS); }

void loop(){ 
  static uint8_t hue;
  for(int i = 0; i < NUM_LEDS/2; i++) {   
    // fade everything out
    leds.fadeToBlackBy(40);

    // let's set an led value
    leds[i] = CHSV(hue++,255,255);

    // now, let's first 20 leds to the top 20 leds, 
    leds(NUM_LEDS/2,NUM_LEDS-1) = leds(NUM_LEDS/2 - 1 ,0);
    FastLED.delay(33);
  }
}
```

5\. After the upload is successful, you can see the phenomenon that the RGB lights alternate from red, green and blue.

![Crowbits-RGB Matrix-Wiki 2.JPG](https://wiki.elecrow.com/images/thumb/a/ad/Crowbits-RGB_Matrix-Wiki_2.JPG/600px-Crowbits-RGB_Matrix-Wiki_2.JPG){ loading=lazy }


![Crowbits-RGB Matrix-Wiki 3.JPG](https://wiki.elecrow.com/images/thumb/d/d0/Crowbits-RGB_Matrix-Wiki_3.JPG/600px-Crowbits-RGB_Matrix-Wiki_3.JPG){ loading=lazy }