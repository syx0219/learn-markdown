---
title: Crowtail- I2C LCD
---

## Description
-----------

A new crowtail for LCD1602, it contains LCD1602 and MCP23008 module. Unique interface for crowtail. Provide convenience to work with a LCD.

**Model: [CT0046LCD](http://www.elecrow.com/crowtail-i2c-lcd-p-1494.html)**

![CT0046LCD-02.JPG](https://wiki.elecrow.com/images/thumb/9/98/CT0046LCD-02.JPG/400px-CT0046LCD-02.JPG){ loading=lazy }

## Features
--------

- Easy to use
- Voltage:3v-5v
- Crowtail compatible interface
- Dimensions(mm):80.0(L)x36.0(W)x17.8(H)

## Usage
-----

1.Hardware connection

Connect the Crowtail- I2C LCD to I port.

2.Connect the board to PC using USB cable.

3.Download the [library](../../files/Crowtail-I2C-1602LCD-zip.md);Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0.1\\libraries.

4.Open the code directly by the path:File -&gt; Example -&gt;Liquid Crystal-&gt;HelloWorld.

```
 #include <Wire.h>
 #include "LiquidCrystal.h"

// Connect via i2c, default address #0 (A0-A2 not jumpered)
LiquidCrystal lcd(0);

void setup() {
  // set up the LCD's number of rows and columns: 
  lcd.begin(16, 2);
  // Print a message to the LCD.
  lcd.print("hello, world!");
}

void loop() {
  // set the cursor to column 0, line 1
  // (note: line 1 is the second row, since counting begins with 0):
  lcd.setCursor(0, 1);
  // print the number of seconds since reset:
  lcd.print(millis()/1000);

  lcd.setBacklight(HIGH);
  delay(1000);
  lcd.setBacklight(LOW);
  delay(1000);
}
```

5.Upload the Code,you shoule see the display of LCD1602.


![CT0046LCD-051.JPG](https://wiki.elecrow.com/images/thumb/1/10/CT0046LCD-051.JPG/600px-CT0046LCD-051.JPG){ loading=lazy }

## Resource
--------

- [LiquidCrystal](../../files/LiquidCrystal-zip.md)
- [Crowtail- I2C LCD v1.0](../../files/Crowtail-I2C-LCD-v1.0.zip.md)