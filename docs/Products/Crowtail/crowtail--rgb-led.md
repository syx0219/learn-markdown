---
title: Crowtail- RGB-LED
---

## Description
-----------

The Crowtail- RGB-LED module with 4 pcs of WS2812B which is a Chainable &amp; Addressable LED. Users can control all the LED with only one microcontroller pin! Besides, the LED bar can be also chainable, that is, you can connect more than one LED bar together to make your project more dreamful. In this module , you can control every LED whit different color at the same time.

**Model: [CT0028RL](http://www.elecrow.com/crowtail-rgbled-p-1301.html)**

![Crowtail-RGB-LED.JPG](https://wiki.elecrow.com/images/thumb/8/85/Crowtail-RGB-LED.JPG/600px-Crowtail-RGB-LED.JPG){ loading=lazy }

## Features
--------

- Connection Mode:D(digital)
- Voltage: 5V
- One high speed serial port
- Dimensions(mm):60.0(L)x20.0(W)x11.5(H)

## Usage
-----

1.Hardware connection

Connect the Crowtail- RGB-LED to D5.

![RGB-LEDhware1.jpg](https://wiki.elecrow.com/images/thumb/2/22/RGB-LEDhware1.jpg/600px-RGB-LEDhware1.jpg){ loading=lazy }

2.Connect the board to PC using USB cable.

3.Download the library [RGB-LED library](https://wiki.elecrow.com/images/6/60/Adafruit_NeoPixel.zip);Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0.1\\libraries.

4.Open the code directly by the path:File -&gt; Example -&gt;Adafruit\_NeoPixel-&gt;strandtest.

```
#include <Adafruit_NeoPixel.h>
#define PIN 5
 
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

5.Upload the Code,then you shoule see the colourful RGB-LED display.


![Crowtail- RGB-LED display11.jpg](https://wiki.elecrow.com/images/thumb/4/44/Crowtail-_RGB-LED_display11.jpg/400px-Crowtail-_RGB-LED_display11.jpg){ loading=lazy } 
![Crowtail- RGB-LED display22.jpg](https://wiki.elecrow.com/images/thumb/5/56/Crowtail-_RGB-LED_display22.jpg/400px-Crowtail-_RGB-LED_display22.jpg){ loading=lazy } 
![Crowtail- RGB-LED display33.jpg](https://wiki.elecrow.com/images/thumb/4/4a/Crowtail-_RGB-LED_display33.jpg/400px-Crowtail-_RGB-LED_display33.jpg){ loading=lazy }

## Resource
--------

- [RGB-LED Program](https://wiki.elecrow.com/images/6/60/Adafruit_NeoPixel.zip)
- [Crowtail- RGB-LED eagle files](https://wiki.elecrow.com/images/a/ab/Crowtail-RGB-LED_eagle_files.zip)