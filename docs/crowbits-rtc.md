---
title: Crowbits-RTC
---

## Description
-----------

If you want to make your own electronic watch, an RTC module is needed to generate you the right timer, with low power consumption. Crowbits-RTC module is based on the clock chip DS1307 which communicate with microcontrollers with I2C protocol. The clock/calendar provides seconds, minutes, hours, day, date, month, and year information. The end of the month date is automatically adjusted for months with fewer than 31 days, including corrections for leap year.

![Crowbits-RTC-1.jpg](https://wiki.elecrow.com/images/thumb/5/56/Crowbits-RTC-1.jpg/600px-Crowbits-RTC-1.jpg){ loading=lazy }

## Features
--------

- Low power consumption

## Specification
-------------

- Interface Type: I2C
- Operating Voltage: 3.3V DC
- Dimensions: 56(L)\*56(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the I2C interface on the Crowbits-UNO board, as shown in the figure:

![Crowbits-RTC-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/8/8c/Crowbits-RTC-Wiki_1.JPG/600px-Crowbits-RTC-Wiki_1.JPG){ loading=lazy }

3\. Download the library “RTC”. Unzip and put it in the libraries file of the Arduino IDE, for example: C:\\Program Files (x86)\\Arduino\\libraries.

4\. Upload the following code to the Crowbits-UNO board.

```
#include <Wire.h>
#include "RTClib.h"
RTC_DS1307 RTC;

void setup () {
    Serial.begin(9600);
    Wire.begin();
    RTC.begin();
  if (! RTC.isrunning()) {
    Serial.println("RTC is NOT running!");
    // following line sets the RTC to the date & time this sketch was compiled
    RTC.adjust(DateTime(__DATE__, __TIME__));
  }
}
void loop () {
    DateTime now = RTC.now(); 
    Serial.print(now.year(), DEC);
    Serial.print('/');
    Serial.print(now.month(), DEC);
    Serial.print('/');
    Serial.print(now.day(), DEC);
    Serial.print(' ');
    Serial.print(now.hour(), DEC);
    Serial.print(':');
    Serial.print(now.minute(), DEC);
    Serial.print(':');
    Serial.print(now.second(), DEC);
    Serial.println(); 
    delay(1000);
}
```

5\. After the upload is successful, open the serial port monitor, the baud rate is set to 9600. You can see the time when the serial port is printed out.

![Crowbits-RTC-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/6/6c/Crowbits-RTC-Wiki_2.jpg/600px-Crowbits-RTC-Wiki_2.jpg){ loading=lazy }