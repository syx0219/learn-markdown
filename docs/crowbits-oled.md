---
title: Crowbits-OLED
---

## Description
-----------

Crowbits- OLED is constructed from 128 x 64 dot matrix OLED module. The display offers high brightness, self-emission, high contrast ratio, slim/thin outline, wide viewing angle, wide temperature range and low power consumption.

![Crowbits-OLED-1.jpg](https://wiki.elecrow.com/images/thumb/9/91/Crowbits-OLED-1.jpg/600px-Crowbits-OLED-1.jpg){ loading=lazy }

## Features
--------

- Low power consumption

## Specification
-------------

- Display Color: Blue
- Resolution: 128x64
- Interface Type: I2C
- Operating Voltage: 3.3V DC
- Dimensions: 56(L)\*31(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the I2C interface on the Crowbits-UNO board, as shown in the figure:

![Crowbits-OLED-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/e/e4/Crowbits-OLED-Wiki_2.jpg/600px-Crowbits-OLED-Wiki_2.jpg){ loading=lazy }

3\. The following sketch demonstrates a simple application of the module.

4.Connect the module to the I2C interface on the Crowbits-UNO board, as shown in the figure:

```
#include "U8glib.h"
U8GLIB_SSD1306_128X64 u8g(U8G_I2C_OPT_NONE);  

void drawURL(void)
{
   u8g.setFont(u8g_font_9x18);
   u8g.drawStr(25,10,"Elecrow");
   u8g.setFont(u8g_font_7x14);
   u8g.drawStr(5,35,"www.elecrow.com");

}
void setup(void) {
}

void loop(void) {
  // picture loop
  u8g.firstPage();  
  do {
    drawURL();
  u8g.setColorIndex(1);
  } while( u8g.nextPage() );  
  // rebuild the picture after some delay
  delay(200);  
}
```

5\. After the code is uploaded successfully, you will see the following words displayed on the OLED screen.

![Crowbits-OLED-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/1/13/Crowbits-OLED-Wiki_1.JPG/600px-Crowbits-OLED-Wiki_1.JPG){ loading=lazy }