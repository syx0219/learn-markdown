---
title: Crowbits-Color Sensor
---

## Description
-----------

This module is based on the color sensor TCS3414CS with digital output I2C. Based on the 8\*2 array of filtered photodiodes and 16-bits analog-to-digital converters, you can gain the color chromaticity of ambient light or the color of objects. Of the 16 photodiodes, 4 have red filters, 4 have green filters, 4 have blue filters and 4 have no filter(clear). With the synchronization input pin, an external pulsed light source can provide precise synchronous conversion control.

![Crowbits-Color-Sensor-1.jpg](https://wiki.elecrow.com/images/thumb/7/7e/Crowbits-Color-Sensor-1.jpg/600px-Crowbits-Color-Sensor-1.jpg){ loading=lazy }

## Features
--------

- SYNC Input Synchronizes Integration Cycle to Modulated Light Sources

## Specification
-------------

- Interface Type: I2C
- Operating Voltage: 3.3V DC
- Dimensions: 56(L)\*56(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1.You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2.Connect the module to the I2C interface on the Crowbits-UNO board, as shown in the figure:

![Crowbits-Color Sensor-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/2/27/Crowbits-Color_Sensor-Wiki_1.JPG/600px-Crowbits-Color_Sensor-Wiki_1.JPG){ loading=lazy }

3.Download the library “Adafruit\_TCS34725-master”. Unzip and put it in the libraries file of the Arduino IDE, for example: C:\\Program Files (x86)\\Arduino\\libraries.

4.Upload the following code to the Crowbits-UNO board.

```
#include <Wire.h>
#include "Adafruit_TCS34725.h"

// Pick analog outputs, for the UNO these three work well
// use ~560  ohm resistor between Red & Blue, ~1K for green (its brighter)
#define redpin 2
#define greenpin 4
#define bluepin 6
// for a common anode LED, connect the common pin to +5V
// for common cathode, connect the common to ground

// set to false if using a common cathode LED
#define commonAnode true

// our RGB -> eye-recognized gamma color
byte gammatable[256];


Adafruit_TCS34725 tcs = Adafruit_TCS34725(TCS34725_INTEGRATIONTIME_50MS, TCS34725_GAIN_4X);

void setup() {
  Serial.begin(9600);
  Serial.println("Color View Test!");

  if (tcs.begin()) {
    Serial.println("Found sensor");
  } else {
    Serial.println("No TCS34725 found ... check your connections");
    while (1); // halt!
  }
  
  // use these three pins to drive an LED
  pinMode(redpin, OUTPUT);
  pinMode(greenpin, OUTPUT);
  pinMode(bluepin, OUTPUT);
  
  // thanks PhilB for this gamma table!
  // it helps convert RGB colors to what humans see
  for (int i=0; i<256; i++) {
    float x = i;
    x /= 255;
    x = pow(x, 2.5);
    x *= 255;
      
    if (commonAnode) {
      gammatable[i] = 255 - x;
    } else {
      gammatable[i] = x;      
    }
    //Serial.println(gammatable[i]);
  }
}


void loop() {
  uint16_t clear, red, green, blue;

  tcs.setInterrupt(false);      // turn on LED

  delay(60);  // takes 50ms to read 
  
  tcs.getRawData(&red, &green, &blue, &clear);

  tcs.setInterrupt(true);  // turn off LED
  
  Serial.print("C:\t"); Serial.print(clear);
  delay(1000);
  Serial.print("\tR:\t"); Serial.print(red);
  delay(1000);
  Serial.print("\tG:\t"); Serial.print(green);
  delay(1000);
  Serial.print("\tB:\t"); Serial.print(blue);
  delay(1000);

  // Figure out some basic hex code for visualization
  uint32_t sum = clear;
  float r, g, b;
  r = red; r /= sum;
  g = green; g /= sum;
  b = blue; b /= sum;
  r *= 256; g *= 256; b *= 256;
  Serial.print("\t");
  Serial.print((int)r, HEX); Serial.print((int)g, HEX); Serial.print((int)b, HEX);
  Serial.println();

  //Serial.print((int)r ); Serial.print(" "); Serial.print((int)g);Serial.print(" ");  Serial.println((int)b );

  analogWrite(redpin, gammatable[(int)r]);
  analogWrite(greenpin, gammatable[(int)g]);
  analogWrite(bluepin, gammatable[(int)b]);
}
```

5\. After the upload is successful, open the serial port monitor, the baud rate is set to 9600. Pointing the sensor at different colors will output different values. When facing different colors, the value of CRBG changes significantly.

![Crowbits-Color Sensor-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/9/9b/Crowbits-Color_Sensor-Wiki_2.jpg/600px-Crowbits-Color_Sensor-Wiki_2.jpg){ loading=lazy }