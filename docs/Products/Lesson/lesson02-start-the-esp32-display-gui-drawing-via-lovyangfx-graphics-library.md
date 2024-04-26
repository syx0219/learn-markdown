---
title: Lesson02 Start the ESP32 DISPLAY GUI drawing via LovyanGFX Graphics Library
---

## **Project Introduction:**
-------

Using Arduino programming and the graphics library functions, draw different patterns and combine them into a complete clock work.

## **Introduction to Knowledge Points:**
--------

**[LovyanGFX Library](https://drive.google.com/file/d/1w3Xt00C6rwhlHV74DnlwxJFm1X7UMR0W/view?usp=sharing):**   
LovyanGFX is a high-performance graphics library based on the Adafruit-GFX-Library that can run on many hardware platforms such as ESP32, ESP8266, STM32, etc. LovyanGFX aims to provide fast, flexible, and easy-to-use tools for drawing high-quality graphics in graphical user interfaces and graphics applications. It supports pixel-level operations, 68 billion colors, multiple fonts, image loading, and many other features. It also includes a powerful graphics engine that can provide efficient performance in a variety of situations. Therefore, LovyanGFX can help users quickly create high-quality graphics applications and user interfaces while maintaining good performance and compatibility.   
**Basic Functions of LovyanGFX Library:**

| **Basic Function** | **Overview**                                                 | **Prototype**                                                | **Parameter Descripition**                                   |
| ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **createSprite()** | The createSprite() function is used in the LovyanGFX library to create graphic sprites. Before drawing patterns, the screen size needs to be configured. | LGFX_Sprite createSprite(int16_t w, int16_t h);              | **w**: the width of the sprite. **h**: the height of the sprite. **Return value**: an object of type LGFX_Sprite, representing the created graphic sprite. |
| **fillRect()**     | The fillRect() function is used in the LovyanGFX library to draw rectangles. | void fillRect(int32_t x, int32_t y, int32_t w, int32_t h, uint32_t color); | **x, y**: the coordinates of the upper-left corner of the rectangle. **w, h**: the width and height of the rectangle. **color**: the fill color. It can be an RGB888 format color value or an RGB565 format color value. |
| **drawLine()**     | The drawLine() function is used in the LovyanGFX library to draw straight lines. | void drawLine(int32_t x0, int32_t y0, int32_t x1, int32_t y1, uint32_t color); | **x0, y0**: the starting coordinates of the line. **x1, y1**: the ending coordinates of the line. **color**: the color of the line. It can be an RGB888 format color value or an RGB565 format color value. |
| **drawCircle()**   | The drawCircle() function is used in the LovyanGFX library to draw circles. | void drawCircle(int32_t x, int32_t y, int32_t r, uint32_t color); | **x, y**: the coordinates of the center of the circle. **r**: the radius of the circle. **color**: the color of the circle. It can be an RGB888 format color value or an RGB565 format color value. |
| **loadFont()**     | The loadFont() function is used in the LovyanGFX library to load small fonts. | void loadFont(small);                                        | **small**: the type of small font to be loaded.              |
| **setTextColor()** | The setTextColor() function is used in the LovyanGFX library to set the text and background colors. | void setTextColor(uint32_t color1, uint32_t color2);         | **Color1**: the color of the text. It can be an RGB888 format color value or an RGB565 format color value. **Color2**: the color of the background. It can be an RGB888 format color value or an RGB565 format color value. |
| **drawString()**   | The drawString() function is used in the LovyanGFX library to draw strings. | void drawString(const char* str, int32_t x, int32_t y);      | **str**: the string to be drawn. **x, y**: the coordinates of the lower-left corner of the string. |
| **pushSprite()**   | The pushSprite() function is used in the LovyanGFX library to draw graphic sprites on the screen. After drawing the pattern, this function needs to be called. | void pushSprite(int32_t x, int32_t y);                       | **x**: the horizontal coordinate of the sprite on the screen. **y**: the vertical coordinate of the sprite on the screen. |

**Usage:**
Call the **begin()** function in the **setup()** function to initialize the screen and LovyanGFX library.

In the **loop()** function, first call the **createSprite()** function to create a graphic sprite, then use functions such as **fillRect(), drawLine(), drawCircle(), loadFont(), setTextColor()**, and **drawString()** to draw patterns and text, and finally use the **pushSprite()** function to draw the graphic sprite on the screen. The specific implementation needs to be written based on the specific clock design.

## **[Sample program](https://wiki.elecrow.com/images/4/46/ESP-Display-lesson2.zip):**
---------

According to the usage of the library functions introduced above, we write a program to display related patterns:
Take the esp32 3.5inch rgb terminal screen as an example.<be>

**Please download [lesson02-1.zip](https://wiki.elecrow.com/images/b/be/ESP-Display-lesson02-1.zip)**

```
//Contains LovyanGFX library and related font library

#include "rgbdisplay.h"
#include "Latin_Hiragana_24.h"
#include "NotoSansBold15.h"
#include "NotoSansMonoSCB20.h"
//define font
#define latin Latin_Hiragana_24
#define small NotoSansBold15
#define digits NotoSansMonoSCB20

//define color
#define c1 0xE73C //white
#define c2 0x18C3  //gray
#define c3 0x9986 //red
#define c4 0x2CAB  //green
#define c5 0xBDEF //gold
#define c6 0xFFFAFA //snow

//Settings for initializing the program
void setup() {
  pinMode(LCD_CS, OUTPUT);//sets the pin mode for the LCD chip select (CS) pin to output mode. This pin is likely used to enable communication with the display.<br>
  pinMode(LCD_BLK, OUTPUT);//sets the pin mode for the LCD backlight (BLK) pin to output mode. This pin is likely used to control the display's backlight.<br>
  digitalWrite(LCD_CS, LOW);//sets the CS pin to low, likely to enable communication with the display.<br>
  digitalWrite(LCD_BLK, HIGH);//sets the BLK pin to high, likely to turn on the display's backlight.<br>
  lcd.init();//initializes the display library.<br>
  lcd.setRotation(1);//sets the display rotation to 1, likely to rotate the display 90 degrees.<br>
  lcd.fillScreen(TFT_WHITE);//fills the display screen with white color.<br>
    sprite.createSprite(480,320);//creates a sprite object with a width of 480 pixels and a height of 320 pixels. This sprite is likely used to draw graphics or images on the display.<br>
}

void loop()
{
  //draw graphics
  sprite.fillRect(80,61,310,50,0x9986);//draw a rectangle
  sprite.drawLine(80,164,80,240,0x2CAB);//draw a line
  sprite.loadFont(small);
  sprite.setTextColor(c4,c3);
  sprite.drawString("Hello elecrow!",190,230);//write a paragraph
  sprite.drawCircle(240, 160, 30, c5);//draw a circle
  sprite.pushSprite(0,0);
}
```

**program effect:**   
![2-1.png](https://wiki.elecrow.com/images/thumb/9/96/2-1.png/681px-2-1.png){ loading=lazy }

## **Expansion:**

According to the functions learned earlier, draw a graph, here draw a small house.

**Please download [lesson02-2.zip](https://wiki.elecrow.com/images/0/0c/ESP-Display-lesson02-2.zip)**

```
#include "rgbdisplay.h"
#include "Latin_Hiragana_24.h"
#include "NotoSansBold15.h"
#include "NotoSansMonoSCB20.h"

#define latin Latin_Hiragana_24
#define small NotoSansBold15
#define digits NotoSansMonoSCB20

#define c1 0xE73C //white
#define c2 0x18C3  //gray
#define c3 0x9986 //red
#define c4 0x2CAB  //green
#define c5 0xBDEF //gold
#define c6 0xFFFAFA //snow

void setup() {

  pinMode(LCD_CS, OUTPUT);
  pinMode(LCD_BLK, OUTPUT);

  digitalWrite(LCD_CS, LOW);
  digitalWrite(LCD_BLK, HIGH);

  lcd.init();
  lcd.setRotation(1);
  lcd.fillScreen(TFT_WHITE);
  
  sprite.createSprite(480,320);
}

void loop()
{
  sprite.fillRect(80,120,320,160,0x9986);
  sprite.fillRect(250,200,40,50,c2);
  sprite.drawLine(80,120,240,20,0x2CAB);
  sprite.drawLine(240,20,400,120,0x2CAB);
  sprite.drawCircle(160, 170, 30, c5);
  sprite.pushSprite(0,0);
}
```

**Show results:**   
![2-2.png](https://wiki.elecrow.com/images/thumb/1/19/2-2.png/744px-2-2.png){ loading=lazy }

## **HMI Display Tutorial Contents**
-------

- [Lesson01 Introducing the ESP32 Display series and environment configuration](./lesson01-introducing-the-esp32-display-series-and-environment-configuration.md)
- Lesson02 Start the ESP32 DISPLAY GUI drawing via LovyanGFX Graphics Library
- [Lesson03 How to Display Pictures on ESP32 Boards](./lesson03-how-to-display-pictures-on-esp32-boards.md)
- [Lesson04 LVGL Basics: How to install LVGL for ESP32 Displays](./lesson04-lvgl-basics-how-to-install-lvgl-for-esp32-displays.md)
- [Lesson05 Introduction to the 5 categories of LVGL GUI library Widgets](./lesson06-use-squareline-studio-to-start-your-1st-human-machine-interface-project.md)
- [Lesson06 Use Squareline Studio to start your 1st human machine interface project](./lesson06-use-squareline-studio-to-start-your-1st-human-machine-interface-project.md)
- [Lesson07 How to implement text information input with Squareline Studio](./lesson07-how-to-implement-text-information-input-with-squareline-studio.md)
- [Lesson08 How to make the menu and a progress bar with Squareline Studio](./lesson08-how-to-make-the-menu-and-a-progress-bar-with-squareline-studio.md)
- [Lesson09 How to make an analysis report on ESP32 Display](./lesson09-how-to-make-an-analysis-report-on-esp32-display.md)
- [Lesson10 Create a 3D Printer UI Project on ESP32 Display](./lesson10-create-a-3d-printer-ui-project-on-esp32-display.md)
- [Lesson11 How to Make a Mixer Interface on ESP32 Display](./lesson11-how-to-make-a-mixer-interface-on-esp32-display.md)
- [Lesson12 Make Your ESP32 Display the Lantern Control terminal](./lesson12-make-your-esp32-display-the-lantern-control-terminal.md)
- [Lesson13 DIY Electronic Control Terminal on ESP32 Display with Squareline Studio](./lesson13-diy-electronic-control-terminal-on-esp32-display-with-squareline-studio.md)
- [Lesson14 Create Car Control Screen on ESP32 Display: A Step-by-Step Guide](./lesson14-create-car-control-screen-on-esp32-display-a-step-by-step-guide.md)
- [Lesson15 Smart Agriculture Monitoring: IoT-Based Real-Time ESP32 Display Project](./lesson15-smart-agriculture-monitoring-lot-based-real-time-esp32-display-project.md)
- [Lesson16 ESP32 Display for Smart Home Central Control: A Home Automation Solution](./lesson16-esp32-display-for-smart-home-central-control-a-home-automation-solution.md)

## **[Back to Main Content](../../Tutorials/lvgl-esp32-display-tutorial-a-step-by-step-guide-to-lvgl-gui-development.md)** 

## Resources
-----

[ESP_Terminal_Libraries](https://drive.google.com/drive/folders/1Ot7eu2HhlgfzXu_Fgvm5NCnJcG4a0Cx2?usp=sharing)   
[LovyanGFX Library](https://drive.google.com/file/d/1w3Xt00C6rwhlHV74DnlwxJFm1X7UMR0W/view?usp=sharing)   
[lesson2.zip](https://wiki.elecrow.com/images/4/46/ESP-Display-lesson2.zip)