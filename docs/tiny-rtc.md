---
title: Tiny RTC
---

## Introduction
------------

This tiny RTC module is based on the clock chip DS1307 which supports the I2C protocol. It uses a Lithium cell battery (CR1225). The clock/calendar provides seconds, minutes, hours, day, date,month, and year information. The end of the month date is automatically adjusted for months with fewer than 31 days, including corrections for leap year. The clock operates in either the 24-hour or 12-hour format with AM/PM indicator.  
**Model: [SMI00101S](http://www.elecrow.com/tiny-rtc-for-arduino-p-323.html)**

![RTC1.jpg](https://wiki.elecrow.com/images/thumb/1/1d/RTC1.jpg/200px-RTC1.jpg){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png){loading=lazy}](https://www.elecrow.com/tiny-rtc-for-arduino-p-323.html?wiki "Title text")

## Features
--------

- 5V DC supply
- Programmable Square-Wave output signal
- Automatic Power-Fail detect and switch circuitry
- Consumes less than 500nA in Battery-Backup Mode with Oscillator Running
- 56-Byte, Battery-Backed, Nonvolatile (NV)RAM for data storage

## Usage
-----

### **Hardware**

The RTC module use the I2C bus to communicate with Arduino&amp;Crowduinom. Arduino has one I2C port with A4 and A5, connect the RTC module to Arduino as below:  
![TinyRTC hardware.jpg](https://wiki.elecrow.com/images/thumb/2/23/TinyRTC_hardware.jpg/500px-TinyRTC_hardware.jpg){ loading=lazy } 
![TinyRTC hardware1.jpg](https://wiki.elecrow.com/images/thumb/d/d2/TinyRTC_hardware1.jpg/500px-TinyRTC_hardware1.jpg){ loading=lazy }

### **Programming**

1.Download the library File:[RTC Library](https://wiki.elecrow.com/images/2/21/RTC.zip)

2.Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0\\libraries.

3.Open the code directly by the path:File -&gt; Example -&gt;RTC.

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

4.Upload the code,then open the serial monitor to see the current time.


## Resource
--------

- [RTC Program](https://wiki.elecrow.com/images/2/21/RTC.zip)
- Click [Tiny RTC For Arduino](http://www.elecrow.com/tiny-rtc-for-arduino-p-323.html) to buy.