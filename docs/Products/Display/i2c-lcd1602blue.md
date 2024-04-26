---
title: I2C LCD1602(Blue)
---

## Introduction
------------

An LCD display that can display a max of 16x2 charactors. with the help of the I2C bus convertor and related libraries, you can easily use this module with just 2 wires.   
**Model: [DLC11602A](http://www.elecrow.com/i2c-2004-lcd-module-yellow-backlight-p-457.html)**

![I2C LCD1602(Blue)1.jpg](https://wiki.elecrow.com/images/thumb/4/45/I2C_LCD1602%28Blue%291.jpg/400px-I2C_LCD1602%28Blue%291.jpg){ loading=lazy }
![I2C LCD1602(Blue)3.jpg](https://wiki.elecrow.com/images/thumb/4/4e/I2C_LCD1602%28Blue%293.jpg/400px-I2C_LCD1602%28Blue%293.jpg){ loading=lazy }

## Specification
-------------

- LCD Display Mode: STN, Positive, Transflective
- Display Color: ?Blue
- Driving Method : 1/16 duty, 1/5 bias
- Control Method: I2C
- Viewing Angle: 6H

## Application
-----------

- Electronic equipment

Interface
---------

Connect the I2C LCD1602 to the I2C port of Arduino(SDA&lt;-&gt;A4 and SCL&lt;-&gt;A5) and power this module with 5V voltage as belows:  
![I2c lcd1602.png](https://wiki.elecrow.com/images/thumb/7/71/I2c_lcd1602.png/400px-I2c_lcd1602.png){ loading=lazy }

## Usage
-----

### **"Hellow world" with this module**

After connecting the hardware, [Download](#resource)the "Hello World" demo to your Arduino board. you can refer to [Here](../../how/how-to-install-the-librarys-and-upload-programs-to-arduino.md) to learn how to download the sketchs.

### **Display the customer chars**

You can also make the LCD to display your own chars or logos as you like, you need to constrat your own chars in your program, as the method in the "CustomChars" demo. also, it would be easy for you to make the LCD display what you input with the serial port, just as the "SerialDisplay" demo, you can sent what you want to display with the serial monitor in the Arduino IDE, please note that you should set the baudrate to 9600. for me, i want the I2C LCD 1602 to show "good day".  
![1602customerchars.jpg](https://wiki.elecrow.com/images/thumb/c/c8/1602customerchars.jpg/400px-1602customerchars.jpg){ loading=lazy }
![1602Serialdisplay.jpg](https://wiki.elecrow.com/images/thumb/a/ac/1602Serialdisplay.jpg/400px-1602Serialdisplay.jpg){ loading=lazy }

### **Backlight control and Contrast control**

The Backlight can be controlled by the firmware or the on-board jumper:  
**Firmware:**

```
 lcd.backlight();// light on the backlight;
 lcd.noBacklight();//light off the backligth;
```


**Hardware:**  
There is a jumper on the board, if you take away this jumper , the backlight will aways be off:  
![1602jumper.jpg](https://wiki.elecrow.com/images/thumb/6/60/1602jumper.jpg/600px-1602jumper.jpg){ loading=lazy }  
You can control the LCD contrast by adjust the on-board potentiometer :  
![1602Contrast.jpg](https://wiki.elecrow.com/images/thumb/9/9d/1602Contrast.jpg/600px-1602Contrast.jpg){ loading=lazy }

For the usagage of other functions, pleae refer to the "LiquidCrystal\_I2C.h" in the sourcecode of **[I2C LCD library](http://www.elecrow.com/wiki/images/0/05/I2C_LCD_Library.zip).**

Resource
--------

[File:I2C LCD Library.zip](http://www.elecrow.com/wiki/images/0/05/I2C_LCD_Library.zip "File:I2C LCD Library.zip")