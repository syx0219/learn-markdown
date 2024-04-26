---
title: LCD Keypad Shield
---

## Description
-----------

The LCD Keypad Shield is arduino compactible boards,to provide a user-friendly interface that allows users to display what they want to and make selections etc. it consists of a 1602 white character blue backlight LCD. The keypad consists of 5 keys — select, up, right, down and left. To save the digital IO pins, the keypad interface uses only one ADC channel(AD0). The key value is read through a 5 stage voltage divider.

**Model: [MCS01602M](http://www.elecrow.com/lcd-keypad-shield-for-arduino-p-311.html)**

![LCD Keypad.jpg](https://wiki.elecrow.com/images/4/40/LCD_Keypad.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){loading=lazy}](https://www.elecrow.com/lcd-keypad-shield-for-arduino-p-311.html?wiki "Title text")

## Featrues
--------

- The keypad interface uses only one ADC channel.
- Can control the contrast of LCD through the potentiometer.
- Can shows the words as you like.
- Dimensions(mm):80.0(L)x56.6(W)x20.0(H)

## Pin Allocatior
--------------

| **PIN** | **FUNCTION** |
|:-:|:-:|
| Analog 0 | Button (select, up, right, down and left) |
| Digital 4 | DB4 |
| Digital 5 | DB5 |
| Digital 6 | DB6 |
| Digital 7 | DB7 |
| Digital 8 | RS (Data or Signal Display Selection) |
| Digital 9 | Enable |
| Digital 10 | Backlit Control |

## Usage
-----

- How to control the Keypad and make selects

The following sample code is to introduce how to use this model.it shows what key you pressed down and the system time.  
1.Hardware connection  
Plug it into the Arduino/Crowduino.  
![LCD Keypad Shield hardware connect.jpg](https://wiki.elecrow.com/images/thumb/0/05/LCD_Keypad_Shield_hardware_connect.jpg/500px-LCD_Keypad_Shield_hardware_connect.jpg){ loading=lazy }  
2.Download the File:[LiquidCrystal library](https://wiki.elecrow.com/images/c/c9/LiquidCrystal.zip).   
3.Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0\\libraries.  
4.Copy and paste code below to a new Arduino sketch.  

```
/*
 * Created by 
 * Ark Bramwell, July 2010
 * Modified by keen 
 * Date: 05/05/2017
 * Function: this program will test the LCD panel and the buttons
 */ 
//Sample using LiquidCrystal library
#include <LiquidCrystal.h>
 
// select the pins used on the LCD panel
LiquidCrystal lcd(8, 9, 4, 5, 6, 7);
 
// define some values used by the panel and buttons
int lcd_key     = 0;
int adc_key_in  = 0;
#define btnRIGHT  0
#define btnUP     1
#define btnDOWN   2
#define btnLEFT   3
#define btnSELECT 4
#define btnNONE   5
 
// read the buttons
int read_LCD_buttons()
{
 adc_key_in = analogRead(0);      // read the value from the sensor 
 // my buttons when read are centered at these valies: 0, 144, 329, 504, 741
 // we add approx 50 to those values and check to see if we are close
 if (adc_key_in > 1500) return btnNONE; // We make this the 1st option for speed reasons since it will be the most likely result
 if (adc_key_in < 50)   return btnRIGHT;  
 if (adc_key_in < 195)  return btnUP; 
 if (adc_key_in < 380)  return btnDOWN; 
 if (adc_key_in < 500)  return btnLEFT; 
 if (adc_key_in < 700)  return btnSELECT;   
 return btnNONE;  // when all others fail, return this...
}
 
void setup()
{
 lcd.begin(16, 2);              // start the library
 lcd.setCursor(0,0);
 lcd.print("Push the buttons"); // print a simple message
}
  
void loop()
{
 lcd.setCursor(9,1);            // move cursor to second line "1" and 9 spaces over
 lcd.print(millis()/1000);      // display seconds elapsed since power-up
 
 
 lcd.setCursor(0,1);            // move to the begining of the second line
 lcd_key = read_LCD_buttons();  // read the buttons
 
 switch (lcd_key)               // depending on which button was pushed, we perform an action
 {
   case btnRIGHT:
     {
     lcd.print("RIGHT ");
     break;
     }
   case btnLEFT:
     {
     lcd.print("LEFT   ");
     break;
     }
   case btnUP:
     {
     lcd.print("UP    ");
     break;
     }
   case btnDOWN:
     {
     lcd.print("DOWN  ");
     break;
     }
   case btnSELECT:
     {
     lcd.print("SELECT");
     break;
     }
     case btnNONE:
     {
     lcd.print("NONE  ");
     break;
     }
 }
 }
```

5.Upload the code,the LCD will display the button which you press.  
![LCD Keypad display.jpg](https://wiki.elecrow.com/images/thumb/9/93/LCD_Keypad_display.jpg/500px-LCD_Keypad_display.jpg){ loading=lazy } 
![LCD Keypad display1.jpg](https://wiki.elecrow.com/images/thumb/2/2a/LCD_Keypad_display1.jpg/500px-LCD_Keypad_display1.jpg){ loading=lazy } 
![LCD Keypad display2.jpg](https://wiki.elecrow.com/images/thumb/e/ea/LCD_Keypad_display2.jpg/500px-LCD_Keypad_display2.jpg){ loading=lazy }

## Resource
--------

- [Library files: LiquidCrystal](http://www.elecrow.com/wiki/images/c/c9/LiquidCrystal.zip)
- [LCD datesheet :LCD1602.PDF](http://www.elecrow.com/wiki/images/1/16/LCD1602.pdf)
- [Schematic of LCD keypad Shield](http://www.elecrow.com/wiki/images/5/56/LCDKeypad_Shield_V1.0_SCH.pdf)

## How to buy
----------

Click [here](https://www.elecrow.com/lcd-keypad-shield-for-arduino-p-311.html) to buy LCD Keypad Shield ,or other [products](http://www.elecrow.com) you like.