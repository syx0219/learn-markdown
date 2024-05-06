---
title: Crowtail- RTC
---

## Description
-----------

If you want to make your own electronic watch,a RTC module is needed to generatet you the right timer, with low power consumption.That is what this tiny RTC can do for you. This tiny RTC module is based on the clock chip DS1307 which communicate with microcontrollers with I2C protocol. The clock/calendar provides seconds, minutes, hours, day, date,month, and year information. The end of the month date is automatically adjusted for months with fewer than 31 days, including corrections for leap year. besies, it is really low power consumption, it can serves you more than a month with a CR1220 battery.

**Model: [CT0009RT](https://www.elecrow.com/crowtail-rtc-p-1267.html)**

![Crowtail-RTC.JPG](https://wiki.elecrow.com/images/thumb/6/68/Crowtail-RTC.JPG/600px-Crowtail-RTC.JPG){ loading=lazy }

## Features
--------

- VCC：5V
- IO Structure: SCL,SDA,VCC,GND
- Battery Voltage：2.0~3.5 V
- Dimensions(mm):20.0(L)x20.0(W)x10.0(H)

## Usage
-----

The following sketch demonstrates a simple application of setting the time and reading it out.

1.Connect the module to the I2C Interface of Crowtail- Base Shield.

2.Plug Crowtail- Base Shield into Arduino.

3.Connect Arduino to PC via a USB cable.

![Rtchardware11.jpg](https://wiki.elecrow.com/images/thumb/1/17/Rtchardware11.jpg/600px-Rtchardware11.jpg){ loading=lazy }

4.Download the library File:[RTC Library](https://wiki.elecrow.com/images/2/21/RTC.zip)

5.Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0\\libraries.

6.Open the code directly by the path:File -&gt; Example -&gt;RTC.

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

7.Upload the code,then open the serial monitor to see the result.

![Rtcresult.jpg](https://wiki.elecrow.com/images/thumb/7/7a/Rtcresult.jpg/400px-Rtcresult.jpg){ loading=lazy }

## Resource
--------

- [RTC Program](https://wiki.elecrow.com/images/2/21/RTC.zip)
- [Crowtail- RTC eagle files](https://wiki.elecrow.com/images/c/c4/Crowtail-RTC.zip)