---
title: Crowtail- 1.3 Inch OLED v1.0
---

## **Bold text** Description
------------------------

Crowtail- OLED is constructed from 128 x 64 dot matrix OLED module. The display offers high brightness, self-emission, high contrast ratio, slim/thin outline, wide viewing angle, wide temperature range and low power consumption.

**Model:** [CRT01112O](https://www.elecrow.com/crowtail-1-3-inch-oled.html)

![Crowtail- 1.3 Inch OLED v1.0.jpg](https://wiki.elecrow.com/images/thumb/d/d4/Crowtail-_1.3_Inch_OLED_v1.0.jpg/500px-Crowtail-_1.3_Inch_OLED_v1.0.jpg){ loading=lazy }

## Features
--------

Connection Mode:I(IIC)

Voltage: 5V

Display Color:Blue/Black

Resolution:128x64

Interface:I2C

Wide range of working temperature: -20°C~70°C

Dimensions(mm):50.0(L)x35.0(W)x6.8(H)

## Usage
-----

1.Hardware connection

Connect the Crowtail- 1.3 Inch OLED to I port.

2.Connect the board to PC using USB cable.

3.Download the library [OLED library](../../files/U8glib-zip.md);Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0.1\\libraries.

4.Open the code directly by the path:File -&gt; Example -&gt;U8glib-&gt;Ele\_0\_96\_12864.

```
#include "U8glib.h"
U8GLIB_SSD1306_128X64 u8g(U8G_I2C_OPT_NONE);	
void drawColorBox(void)
{
 u8g_uint_t w,h;
 u8g_uint_t r, g, b;
 w = u8g.getWidth()/32;
 h = u8g.getHeight()/8;
 for( b = 0; b < 4; b++ )
   for( g = 0; g < 8; g++ )
     for( r = 0; r < 8; r++ )
     {
       u8g.setColorIndex((r<<5) |  (g<<2) | b );
       u8g.drawBox(g*w + b*w*8, r*h, w, h);
     }
}
void drawLogo(uint8_t d)
{
 u8g.setFont(u8g_font_gdr25r);
 u8g.drawStr(8+d, 30+d, "E");
 u8g.setFont(u8g_font_gdr25r);
 u8g.drawStr(30+d,30+d,"l");
 u8g.setFont(u8g_font_gdr25r);
 u8g.drawStr(40+d,30+d,"e"); 
 u8g.setFont(u8g_font_gdr25r);
 u8g.drawStr(55+d,30+d,"c");
 u8g.setFont(u8g_font_gdr25r);
 u8g.drawStr(70+d,30+d,"r");
 u8g.setFont(u8g_font_gdr25r);
 u8g.drawStr(85+d,30+d,"o");
 u8g.setFont(u8g_font_gdr25r);
 u8g.drawStr(100+d,30+d,"w");
}

void drawURL(void)
{
 u8g.setFont(u8g_font_4x6);
 u8g.drawStr(35,54,"www.elecrow.com");

}
void draw(void) {
 if ( u8g.getMode() == U8G_MODE_R3G3B2 ) {
   drawColorBox();
 }
 u8g.setColorIndex(1);
 if ( U8G_MODE_GET_BITS_PER_PIXEL(u8g.getMode()) > 1 ) {
   drawLogo(2);
   u8g.setColorIndex(2);
   drawLogo(1);
   u8g.setColorIndex(3);
 }
 drawLogo(0);
 drawURL();
  
}

void setup(void) {
}

void loop(void) {
 // picture loop
 u8g.firstPage();  
 do {
   draw();
 u8g.setColorIndex(1);
 } while( u8g.nextPage() );  
 // rebuild the picture after some delay
 delay(200);  
}
```

5.Upload the Code,you shoule see the display of OLED.

![1.3 Inch OLED v1.0.jpeg](https://wiki.elecrow.com/images/thumb/7/73/1.3_Inch_OLED_v1.0.jpeg/600px-1.3_Inch_OLED_v1.0.jpeg){ loading=lazy }

## Resource
--------

- [OLED demo code](../../files/U8glib-zip.md)
- [Crowtail- OLED eagle files](../../files/Crowtail-OLED-eagle-files-zip.md)