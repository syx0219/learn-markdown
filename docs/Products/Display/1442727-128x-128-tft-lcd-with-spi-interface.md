---
title: 1.44'' 128x 128 TFT LCD with SPI Interface
---

##  Introduction
------------

This Color TFT LCD display has 128 x 128 resolution and 262 color, it uses SPI interface to communicate with controller such Arduino, it is the best upgrading of the Nokia5110.  
**Model: [DL144128TF](http://www.elecrow.com/144-128x-128-tft-lcd-with-spi-interface-p-855.html)**  

![128x 128 TFT LCD with SPI Interface.jpg](https://wiki.elecrow.com/images/thumb/c/c1/128x_128_TFT_LCD_with_SPI_Interface.jpg/400px-128x_128_TFT_LCD_with_SPI_Interface.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/144-128x-128-tft-lcd-with-spi-interface-p-855.html?wiki "Title text")

## Features
--------

- Size: 1.44 inch
- Interface:SPI
- Resolution: 128\*128
- Visual area: 1:1 square
- TFT color screen, the effect is far better than other small CSTN screen
- Drive IC: ILI9163
- Fully compatible and alternative 5110 interface
- Onboard LDO, support 5V/3.3V input voltage, the LED backlight, 3.3V input

## Usage
-----

1.Hardware connection


 ![128x 128 TFT LCD with SPI Interface hardware.jpg](https://wiki.elecrow.com/images/thumb/e/ec/128x_128_TFT_LCD_with_SPI_Interface_hardware.jpg/500px-128x_128_TFT_LCD_with_SPI_Interface_hardware.jpg){ loading=lazy } ![128x 128 TFT LCD with SPI Interface hardware1.jpg](https://wiki.elecrow.com/images/thumb/5/57/128x_128_TFT_LCD_with_SPI_Interface_hardware1.jpg/500px-128x_128_TFT_LCD_with_SPI_Interface_hardware1.jpg){ loading=lazy }

2.Connect the board to PC using USB cable.

3.Download the library [TFT\_ILI9163C library](../../files/TFT-ILI9163C-library-zip.md);Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0.1\\libraries.

4.Open the code directly by the path:File -&gt; Example -&gt;TFT\_ILI9163C-&gt;test.

```
#include <SPI.h>
#include <Adafruit_GFX.h>
#include <TFT_ILI9163C.h>

// All wiring required, only 3 defines for hardware SPI on 328P
#define __DC 9
#define __CS 10
// MOSI --> (SDA) --> D11
#define __RST 12
// SCLK --> (SCK) --> D13

// Color definitions
#define	BLACK   0x0000
#define	BLUE    0x001F
#define	RED     0xF800
#define	GREEN   0x07E0
#define CYAN    0x07FF
#define MAGENTA 0xF81F
#define YELLOW  0xFFE0  
#define WHITE   0xFFFF

TFT_ILI9163C tft = TFT_ILI9163C(__CS, __DC, __RST);

void setup() {
  tft.begin();
}

void loop(){
  testLines(random(0x00ff,0xffff));
  delay(100);
  testText();
  delay(500);
}


unsigned long testText() {
  tft.fillScreen();
  unsigned long start = micros();
  tft.setCursor(0, 0);
  tft.setTextColor(WHITE);  
  tft.setTextSize(1);
  tft.println("Hello World!");
  tft.setTextColor(YELLOW); 
  tft.setTextSize(2);
  tft.println(1234.56);
  tft.setTextColor(RED);    
  tft.setTextSize(3);
  tft.println(0xDEAD, HEX);
  tft.println();
  tft.setTextColor(GREEN);
  tft.setTextSize(4);
  tft.println("Hello");
  return micros() - start;
}

unsigned long testLines(uint16_t color) {
  tft.fillScreen();
  unsigned long start, t;
  int           x1, y1, x2, y2,
  w = tft.width(),
  h = tft.height();
  tft.fillScreen();
  x1 = y1 = 0;
  y2    = h - 1;
  start = micros();
  for(x2=0; x2<w; x2+=6) tft.drawLine(x1, y1, x2, y2, color);
  x2    = w - 1;
  for(y2=0; y2<h; y2+=6) tft.drawLine(x1, y1, x2, y2, color);
  t     = micros() - start; // fillScreen doesn't count against timing
  tft.fillScreen();
  x1    = w - 1;
  y1    = 0;
  y2    = h - 1;
  start = micros();
  for(x2=0; x2<w; x2+=6) tft.drawLine(x1, y1, x2, y2, color);
  x2    = 0;
  for(y2=0; y2<h; y2+=6) tft.drawLine(x1, y1, x2, y2, color);
  t    += micros() - start;
  tft.fillScreen();
  x1    = 0;
  y1    = h - 1;
  y2    = 0;
  start = micros();
  for(x2=0; x2<w; x2+=6) tft.drawLine(x1, y1, x2, y2, color);
  x2    = w - 1;
  for(y2=0; y2<h; y2+=6) tft.drawLine(x1, y1, x2, y2, color);
  t    += micros() - start;
  tft.fillScreen();
  x1    = w - 1;
  y1    = h - 1;
  y2    = 0;
  start = micros();
  for(x2=0; x2<w; x2+=6) tft.drawLine(x1, y1, x2, y2, color);
  x2    = 0;
  for(y2=0; y2<h; y2+=6) tft.drawLine(x1, y1, x2, y2, color);
  return micros() - start;
}
```

5.Upload the Code,you shoule see the display of LCD.


![128x 128 TFT LCD with SPI Interfaceshow.jpg](https://wiki.elecrow.com/images/thumb/2/25/128x_128_TFT_LCD_with_SPI_Interfaceshow.jpg/400px-128x_128_TFT_LCD_with_SPI_Interfaceshow.jpg){ loading=lazy }

## Resource
--------

- [TFT\_ILI9163C library](../../files/TFT-ILI9163C-library-zip.md)