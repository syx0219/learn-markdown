---
title: TEXT
---

## Interface Function
------------------

- Onboard Ports and Functions

| **Basic Function** | **Overview** | **Prototype** | **Parameter Descripition** |
|:-:|:-:|:-:|:-:|
| **createSprite()** | The createSprite() function is used in the LovyanGFX library to create graphic sprites. Before drawing patterns, the screen size needs to be configured. | LGFX\_Sprite createSprite(int16\_t w, int16\_t h); | **w**: the width of the sprite. **h**: the height of the sprite. **Return value**: an object of type LGFX\_Sprite, representing the created graphic sprite. |
| **fillRect()** | The fillRect() function is used in the LovyanGFX library to draw rectangles. | void fillRect(int32\_t x, int32\_t y, int32\_t w, int32\_t h, uint32\_t color); | **x, y**: the coordinates of the upper-left corner of the rectangle. **w, h**: the width and height of the rectangle. **color**: the fill color. It can be an RGB888 format color value or an RGB565 format color value. |
| **drawLine()** | The drawLine() function is used in the LovyanGFX library to draw straight lines. | void drawLine(int32\_t x0, int32\_t y0, int32\_t x1, int32\_t y1, uint32\_t color); | **x0, y0**: the starting coordinates of the line. **x1, y1**: the ending coordinates of the line. **color**: the color of the line. It can be an RGB888 format color value or an RGB565 format color value. |
| **drawCircle()** | The drawCircle() function is used in the LovyanGFX library to draw circles. | void drawCircle(int32\_t x, int32\_t y, int32\_t r, uint32\_t color); | **x, y**: the coordinates of the center of the circle. **r**: the radius of the circle. **color**: the color of the circle. It can be an RGB888 format color value or an RGB565 format color value. |
| **loadFont()** | The loadFont() function is used in the LovyanGFX library to load small fonts. | void loadFont(small); | **small**: the type of small font to be loaded. |
| **setTextColor()** | The setTextColor() function is used in the LovyanGFX library to set the text and background colors. | void setTextColor(uint32\_t color1, uint32\_t color2); | **Color1**: the color of the text. It can be an RGB888 format color value or an RGB565 format color value. **Color2**: the color of the background. It can be an RGB888 format color value or an RGB565 format color value. |
| **drawString()** | The drawString() function is used in the LovyanGFX library to draw strings. | void drawString(const char\* str, int32\_t x, int32\_t y); | **str**: the string to be drawn. **x, y**: the coordinates of the lower-left corner of the string. |
| **pushSprite()** | The pushSprite() function is used in the LovyanGFX library to draw graphic sprites on the screen. After drawing the pattern, this function needs to be called. | void pushSprite(int32\_t x, int32\_t y); | **x**: the horizontal coordinate of the sprite on the screen. **y**: the vertical coordinate of the sprite on the screen. |