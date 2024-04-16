---
title: Crowbits-RGB LED
---

## Description
-----------

It is composed of two RGB lamp beads and can display various colors. Respond to changes in input signals in monochrome, full-color, and gradual manner. Users can control all the LED with only one microcontroller pin! Besides, the LED bar can be also chainable, that is, you can connect more than one LED bar together to make your project more dreamful. In this module , you can control every LED whit different color at the same time.

![Crowbits-RGB-LED-1.jpg](https://wiki.elecrow.com/images/thumb/b/b1/Crowbits-RGB-LED-1.jpg/600px-Crowbits-RGB-LED-1.jpg){ loading=lazy }

## Features
--------

- Can achieve 256-level brightness display

## Specification
-------------

- Interface Type：GPIO
- Operating Voltage: 3.3V DC
- imensions: 31.5(L)\*24.5(W)\*13(H)mm

## Application Ideas
-----------------

- Display test information

## Usage
-----

The following sketch demonstrates a simple application.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the D4 interface on the Crowbits-UNO board, as shown in the figure:

![Crowbits-RGB LED-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/4/48/Crowbits-RGB_LED-Wiki_1.JPG/600px-Crowbits-RGB_LED-Wiki_1.JPG){ loading=lazy }

3\. Download the library Crowbits-RGB LED library. Unzip and put it in the libraries file, for example: C:\\Program Files (x86)\\Arduino\\libraries.

4\. Open the code directly by the path: File-&gt; Example-&gt; Adafruit\_NeoPixel-&gt; strandtest.Upload the following code to the Crowbits-UNO board.

```
#include <Adafruit_NeoPixel.h>

#define PIN 4

// Parameter 1 = number of pixels in strip
// Parameter 2 = pin number (most are valid)
// Parameter 3 = pixel type flags, add together as needed:
//   NEO_KHZ800  800 KHz bitstream (most NeoPixel products w/WS2812 LEDs)
//   NEO_KHZ400  400 KHz (classic 'v1' (not v2) FLORA pixels, WS2811 drivers)
//   NEO_GRB     Pixels are wired for GRB bitstream (most NeoPixel products)
//   NEO_RGB     Pixels are wired for RGB bitstream (v1 FLORA pixels, not v2)
Adafruit_NeoPixel strip = Adafruit_NeoPixel(60, PIN, NEO_GRB + NEO_KHZ800);

void setup() {
  strip.begin();
  strip.show(); // Initialize all pixels to 'off'
}

void loop() {
  // Some example procedures showing how to display to the pixels:
  colorWipe(strip.Color(255, 0, 0), 50); // Red
  colorWipe(strip.Color(0, 255, 0), 50); // Green
  colorWipe(strip.Color(0, 0, 255), 50); // Blue
  // Send a theater pixel chase in...
  theaterChase(strip.Color(127, 127, 127), 50); // White
  theaterChase(strip.Color(127,   0,   0), 50); // Red
  theaterChase(strip.Color(  0,   0, 127), 50); // Blue

  rainbow(20);
  rainbowCycle(20);
  theaterChaseRainbow(50);
}

// Fill the dots one after the other with a color
void colorWipe(uint32_t c, uint8_t wait) {
  for(uint16_t i=0; i<strip.numPixels(); i++) {
      strip.setPixelColor(i, c);
      strip.show();
      delay(wait);
  }
}

void rainbow(uint8_t wait) {
  uint16_t i, j;

  for(j=0; j<256; j++) {
    for(i=0; i<strip.numPixels(); i++) {
      strip.setPixelColor(i, Wheel((i+j) & 255));
    }
    strip.show();
    delay(wait);
  }
}

// Slightly different, this makes the rainbow equally distributed throughout
void rainbowCycle(uint8_t wait) {
  uint16_t i, j;

  for(j=0; j<256*5; j++) { // 5 cycles of all colors on wheel
    for(i=0; i< strip.numPixels(); i++) {
      strip.setPixelColor(i, Wheel(((i * 256 / strip.numPixels()) + j) & 255));
    }
    strip.show();
    delay(wait);
  }
}

//Theatre-style crawling lights.
void theaterChase(uint32_t c, uint8_t wait) {
  for (int j=0; j<10; j++) {  //do 10 cycles of chasing
    for (int q=0; q < 3; q++) {
      for (int i=0; i < strip.numPixels(); i=i+3) {
        strip.setPixelColor(i+q, c);    //turn every third pixel on
      }
      strip.show();
     
      delay(wait);
     
      for (int i=0; i < strip.numPixels(); i=i+3) {
        strip.setPixelColor(i+q, 0);        //turn every third pixel off
      }
    }
  }
}

//Theatre-style crawling lights with rainbow effect
void theaterChaseRainbow(uint8_t wait) {
  for (int j=0; j < 256; j++) {     // cycle all 256 colors in the wheel
    for (int q=0; q < 3; q++) {
        for (int i=0; i < strip.numPixels(); i=i+3) {
          strip.setPixelColor(i+q, Wheel( (i+j) % 255));    //turn every third pixel on
        }
        strip.show();
       
        delay(wait);
       
        for (int i=0; i < strip.numPixels(); i=i+3) {
          strip.setPixelColor(i+q, 0);        //turn every third pixel off
        }
    }
  }
}

// Input a value 0 to 255 to get a color value.
// The colours are a transition r - g - b - back to r.
uint32_t Wheel(byte WheelPos) {
  if(WheelPos < 85) {
   return strip.Color(WheelPos * 3, 255 - WheelPos * 3, 0);
  } else if(WheelPos < 170) {
   WheelPos -= 85;
   return strip.Color(255 - WheelPos * 3, 0, WheelPos * 3);
  } else {
   WheelPos -= 170;
   return strip.Color(0, WheelPos * 3, 255 - WheelPos * 3);
  }
}
```

5\. After successfully uploading the code, you will see the color of the light change.

![Crowbits-RGB LED Wiki 2.JPG](https://wiki.elecrow.com/images/thumb/7/74/Crowbits-RGB_LED_Wiki_2.JPG/600px-Crowbits-RGB_LED_Wiki_2.JPG){ loading=lazy }

![Crowbits-RGB LED Wiki 4.jpg](https://wiki.elecrow.com/images/thumb/a/ac/Crowbits-RGB_LED_Wiki_4.jpg/600px-Crowbits-RGB_LED_Wiki_4.jpg){ loading=lazy }