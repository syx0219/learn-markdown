---
title: Crowtail-LED Matrix
---

## Introduction
------------

A 8\*8 LED matrix has lots of applications when we DIY some electronic kit. So we invite it to join our crowtail, this Crowtail- 8\*8 LED Matrix use the HT16K33 which is a neat little chip that has the ability to drive a multiplexed 8x8 matrix (that's 64 individual LEDs).

The I2C communication protocol uses only 2 pins, and you can have up to 8 selectable I2C addresses so thats a total of 8 matrices, each one controlling 8x8 LEDs for 64 total LEDs. We offer three LED matrix to you-red ,blue and green. You need to pay attention to that the driver can turn LEDs on and off but does not have the ability to individually PWM dim them. This chip is rock solid, has Arduino &amp; Pi example code written for it and is easy to use.

**Model: [CRT15121M](https://www.elecrow.com/crowtail-led-matrix.html)**

![Crowtail- 8x8 LED Matrix.jpg](https://wiki.elecrow.com/images/thumb/a/a9/Crowtail-_8x8_LED_Matrix.jpg/500px-Crowtail-_8x8_LED_Matrix.jpg){ loading=lazy }

## **Features**
------------

Crowtail interface 8\*8 LED matrix DC 5V working voltage Size: 40mm(L)\*20mm(W)

## Usage
-----

1\. Connect the LED Matrix 2.0 board to Base Shield's I2C pin with 4pin Crowtail Cable.

2\. Plug it onto the Arduino/Crowduino. Connect the board to PC using USB cable.

3\. Download the library “ledlab”; Unzip it into the libraries file of Arduino IDE by the path: .. \\ Arduino\\libraries.

4\. Copy the demo code to your sketch, then upload to Arduino or Crowduino board.

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
    for (int8_t x=0; x>=-36; x--) {
    matrix.clear();
    matrix.setCursor(x,0);
    matrix.print("world");
    matrix.writeDisplay();
    delay(100);
  }
  matrix.setRotation(3);
  //for (int8_t x=7; x>=-36; x--) 
  for (int8_t x=0; x>=-36; x--)
  {
    matrix.clear();
    matrix.setCursor(x,0);
    matrix.print("hello");
    matrix.writeDisplay();
    delay(100);
  }
    for (int8_t x=0; x>=-36; x--)
  {
    matrix.clear();
    matrix.setCursor(x,0);
    matrix.print("elecrow");
    matrix.writeDisplay();
    delay(100);
  }
  matrix.setRotation(0);
}

```

5\. Then you can see the pattern of 8\*8 LED matrix, as shown in the figure below:

![Crowtail-led matrix 1.jpg](https://wiki.elecrow.com/images/thumb/6/69/Crowtail-led_matrix_1.jpg/500px-Crowtail-led_matrix_1.jpg){ loading=lazy }

![Crowtail-led matrix 3.jpg](https://wiki.elecrow.com/images/thumb/7/79/Crowtail-led_matrix_3.jpg/500px-Crowtail-led_matrix_3.jpg){ loading=lazy }

![Crowtail-led matrix 4.jpg](https://wiki.elecrow.com/images/thumb/7/76/Crowtail-led_matrix_4.jpg/500px-Crowtail-led_matrix_4.jpg){ loading=lazy }