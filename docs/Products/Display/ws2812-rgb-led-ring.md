---
title: WS2812 RGB LED Ring
---

## Description
-----------

This is a RGB LED ring with 16 pcs of WS2812 Chainable&amp; Addressable LED. Users can control all the LED with only one microcontroller pin! Besides, the LED Ring can be also chainable, that is, you can connect more the one ring together to make your project more dreamful.

**Model:[DLC2812RLR](http://www.elecrow.com/ws2812-rgb-led-ring-p-1158.html)**

![WS2812 RGB LED Ring.jpg](https://wiki.elecrow.com/images/thumb/f/fc/WS2812_RGB_LED_Ring.jpg/400px-WS2812_RGB_LED_Ring.jpg){ loading=lazy }

## Features
--------

- Qty of LED: 16
- Current for each LED: 18mA
- Working Voltage: 5V DC
- Out Diameter: 61 mm

## Usage
-----

1.Hardware connection

![WS2812 RGB LED Ring hardware.jpg](https://wiki.elecrow.com/images/thumb/d/d2/WS2812_RGB_LED_Ring_hardware.jpg/600px-WS2812_RGB_LED_Ring_hardware.jpg){ loading=lazy }

2.Connect the board to PC using USB cable.

3.Download the library [WS2812 RGB LED Ring library](https://wiki.elecrow.com/images/6/60/Adafruit_NeoPixel.zip);Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0.1\\libraries.

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


![WS2812 RGB LED Ring display1.jpg](https://wiki.elecrow.com/images/thumb/7/71/WS2812_RGB_LED_Ring_display1.jpg/400px-WS2812_RGB_LED_Ring_display1.jpg){ loading=lazy } 
![WS2812 RGB LED Ring display2.jpg](https://wiki.elecrow.com/images/thumb/2/2b/WS2812_RGB_LED_Ring_display2.jpg/400px-WS2812_RGB_LED_Ring_display2.jpg){ loading=lazy } 
![WS2812 RGB LED Ring display3.jpg](https://wiki.elecrow.com/images/thumb/6/6d/WS2812_RGB_LED_Ring_display3.jpg/400px-WS2812_RGB_LED_Ring_display3.jpg){ loading=lazy } 
![WS2812 RGB LED Ring display4.jpg](https://wiki.elecrow.com/images/thumb/5/59/WS2812_RGB_LED_Ring_display4.jpg/400px-WS2812_RGB_LED_Ring_display4.jpg){ loading=lazy }

## Resource
--------

- [WS2812 RGB LED Program](https://wiki.elecrow.com/images/6/60/Adafruit_NeoPixel.zip)