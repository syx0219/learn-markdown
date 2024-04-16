---
title: Crowbits-LED Matrix
---

## Description
-----------

The I2C communication protocol uses only 2 pins, and you can have up to 8 selectable I2C addresses so thats a total of 8 matrices, each one controlling 8x8 LEDs for 64 total LEDs. We offer three LED matrix to you-red ,blue and green. You need to pay attention to that the driver can turn LEDs on and off but does not have the ability to individually PWM dim them. This chip is rock solid, has Arduino &amp; Pi example code written for it and is easy to use.

![Crowbits-LED-Matrix-1.jpg](https://wiki.elecrow.com/images/3/33/Crowbits-LED-Matrix-1.jpg){ loading=lazy }

## Features
--------

- 8\*8 LED matrix

## Specification
-------------

- Interface Type: I2C
- Operating Voltage: 3.3V DC
- Dimensions: 56(L)\*56(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the I2C interface of the Crowbits-UNO board, as shown in the figure:

![Crowbits-LED Matrix-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/2/24/Crowbits-LED_Matrix-Wiki_1.JPG/600px-Crowbits-LED_Matrix-Wiki_1.JPG){ loading=lazy }

3\. Download the library “Adafruit\_GFX” and “Adafruit\_LEDBackpack”. Unzip and put it in the libraries file, for example: C:\\Program Files (x86)\\Arduino\\libraries.

4\. Upload the following code to the Crowbits-UNO board.

```
/*************************************************** 
  This is a library for our I2C LED Backpacks

  Designed specifically to work with the Adafruit LED Matrix backpacks 
  ----> http://www.adafruit.com/products/872
  ----> http://www.adafruit.com/products/871
  ----> http://www.adafruit.com/products/870

  These displays use I2C to communicate, 2 pins are required to 
  interface. There are multiple selectable I2C addresses. For backpacks
  with 2 Address Select pins: 0x70, 0x71, 0x72 or 0x73. For backpacks
  with 3 Address Select pins: 0x70 thru 0x77

  Adafruit invests time and resources providing this open source code, 
  please support Adafruit and open-source hardware by purchasing 
  products from Adafruit!

  Written by Limor Fried/Ladyada for Adafruit Industries.  
  BSD license, all text above must be included in any redistribution
 ****************************************************/

#include <Wire.h>
#include <Adafruit_GFX.h>
#include "Adafruit_LEDBackpack.h"

Adafruit_8x8matrix matrix = Adafruit_8x8matrix();

void setup() {
  Serial.begin(9600);
  Serial.println("8x8 LED Matrix Test");
  
  matrix.begin(0x70);  // pass in the address
}

static const uint8_t PROGMEM
  smile_bmp[] =
  { B00111100,
    B01000010,
    B10100101,
    B10000001,
    B10100101,
    B10011001,
    B01000010,
    B00111100 },
  neutral_bmp[] =
  { B00111100,
    B01000010,
    B10100101,
    B10000001,
    B10111101,
    B10000001,
    B01000010,
    B00111100 },
  frown_bmp[] =
  { B00111100,
    B01000010,
    B10100101,
    B10000001,
    B10011001,
    B10100101,
    B01000010,
    B00111100 };

void loop() {
  matrix.clear();
  matrix.drawBitmap(0, 0, smile_bmp, 8, 8, LED_ON);
  matrix.writeDisplay();
  delay(500);

  matrix.clear();
  matrix.drawBitmap(0, 0, neutral_bmp, 8, 8, LED_ON);
  matrix.writeDisplay();
  delay(500);

  matrix.clear();
  matrix.drawBitmap(0, 0, frown_bmp, 8, 8, LED_ON);
  matrix.writeDisplay();
  delay(500);

  matrix.clear();      // clear display
  matrix.drawPixel(0, 0, LED_ON);  
  matrix.writeDisplay();  // write the changes we just made to the display
  delay(500);

  matrix.clear();
  matrix.drawLine(0,0, 7,7, LED_ON);
  matrix.writeDisplay();  // write the changes we just made to the display
  delay(500);

  matrix.clear();
  matrix.drawRect(0,0, 8,8, LED_ON);
  matrix.fillRect(2,2, 4,4, LED_ON);
  matrix.writeDisplay();  // write the changes we just made to the display
  delay(500);

  matrix.clear();
  matrix.drawCircle(3,3, 3, LED_ON);
  matrix.writeDisplay();  // write the changes we just made to the display
  delay(500);

  matrix.setTextSize(1);
  matrix.setTextWrap(false);  // we dont want text to wrap so it scrolls nicely
  matrix.setTextColor(LED_ON);
  for (int8_t x=0; x>=-36; x--) {
    matrix.clear();
    matrix.setCursor(x,0);
    matrix.print("Hello");
    matrix.writeDisplay();
    delay(100);
  }
  matrix.setRotation(3);
  for (int8_t x=7; x>=-36; x--) {
    matrix.clear();
    matrix.setCursor(x,0);
    matrix.print("World");
    matrix.writeDisplay();
    delay(100);
  }
  matrix.setRotation(0);
}
```

5\. After the code is uploaded successfully, you can see the patterns and words displayed on the 8 \* 8 dot matrix.

![Crowbits-LED Matrix-Wiki 1 2.jpg](https://wiki.elecrow.com/images/thumb/5/5d/Crowbits-LED_Matrix-Wiki_1_2.jpg/600px-Crowbits-LED_Matrix-Wiki_1_2.jpg){ loading=lazy }

![Crowbits-LED Matrix-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/6/68/Crowbits-LED_Matrix-Wiki_2.jpg/600px-Crowbits-LED_Matrix-Wiki_2.jpg){ loading=lazy }