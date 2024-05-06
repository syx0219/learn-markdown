---
title: Crowtail- One Wire Waterproof Temperature Sensor
---

## Introduction
------------

A NEW member of our “Crowtail family”, maybe we can use it more easier. This is a waterproofed version of the DS18B20 Temperature sensor. Handy for when you need to measure something far away, or in wet conditions. While the sensor is good up to 125 degree, the cable is jacketed in PVC so we suggest keeping it under 100 degree. Because they are digital, you don't get any signal degradation even over long distances! The DS18B20 provides 9 to 12-bit (configurable) temperature readings over a 1-Wire interface, so that only one wire (and ground) needs to be connected from a central microprocessor.Usable with 3.0-5.5V systems. Because each DS18B20 contains a unique silicon serial number, multiple DS18B20s can exist on the same 1-Wire bus. This allows for placing temperature sensors in many different places. Applications where this feature is useful include HVAC environmental controls, sensing temperatures inside buildings,equipment or machinery, and process monitoring and control..

Because each DS18B20 contains a unique silicon serial number, multiple DS18B20s can exist on the same 1-Wire bus. This allows for placing temperature sensors in many different places. Applications where this feature is useful include HVAC environmental controls, sensing temperatures inside buildings,equipment or machinery, and process monitoring and control.

**Model: [CT0049OTS](http://www.elecrow.com/crowtail-one-wire-waterproof-temperature-sensor-p-1508.html)**

![CT0049OTS-101.jpg](https://wiki.elecrow.com/images/thumb/e/e6/CT0049OTS-101.jpg/400px-CT0049OTS-101.jpg){ loading=lazy }

## Features
--------

- 9 to 12 bit selectable resolution.
- one digital pin for communication.
- Multiple sensors can share one pin.
- Query time is less than 750ms.
- Crowtail compatible interface.

## Specification
-------------

- 3.0V to 5.5V input.
- Temperature range: -55 to 125°C (-67°F to +257°F).
- ±0.5°C Accuracy from -10°C to +85°C.
- Stainless steel tube 6mm diameter by 30mm long.
- Cable length: 90cm.

## Usage
-----

Here, we will show how to use the waterproof temperature sensor (DS18B20) with your Arduino. This sensor uses the one wire protocol to talk with the microcontroller. So, it requires only one digital port to communicate.

### **Hardware**

Connect the Crowtail- One Wire Waterproof Temperature Sensor to D10 port.
![DS18B2050 Hardware1.jpg](https://wiki.elecrow.com/images/thumb/a/ac/DS18B2050_Hardware1.jpg/600px-DS18B2050_Hardware1.jpg){ loading=lazy }

### **Programming**

First download the [DS18B20 Library for Arduino](./files/DS18B20-zip.md) to your computer. please refer to [here](./how-to-install-the-librarys-and-upload-programs-to-arduino.md) to learn how to install the library and upload the programs.

The demo code is:

```
#include <OneWire.h>
OneWire  ds(10);  // on pin 10

void setup(void) {
  Serial.begin(9600);
}

void loop(void) {
  byte i;
  byte present = 0;
  byte type_s;
  byte data[12];
  byte addr[8];
  float celsius, fahrenheit;
  
  if ( !ds.search(addr)) {
    Serial.println("No more addresses.");
    Serial.println();
    ds.reset_search();
    delay(250);
    return;
  }
  
  Serial.print("ROM =");
  for( i = 0; i < 8; i++) {
    Serial.write(' ');
    Serial.print(addr[i], HEX);
  }

  if (OneWire::crc8(addr, 7) != addr[7]) {
      Serial.println("CRC is not valid!");
      return;
  }
  Serial.println();
 
  // the first ROM byte indicates which chip
  switch (addr[0]) {
    case 0x10:
      Serial.println("  Chip = DS18S20");  // or old DS1820
      type_s = 1;
      break;
    case 0x28:
      Serial.println("  Chip = DS18B20");
      type_s = 0;
      break;
    case 0x22:
      Serial.println("  Chip = DS1822");
      type_s = 0;
      break;
    default:
      Serial.println("Device is not a DS18x20 family device.");
      return;
  } 

  ds.reset();
  ds.select(addr);
  ds.write(0x44,1);         // start conversion, with parasite power on at the end
  
  delay(1000);     // maybe 750ms is enough, maybe not
  // we might do a ds.depower() here, but the reset will take care of it.
  
  present = ds.reset();
  ds.select(addr);    
  ds.write(0xBE);         // Read Scratchpad

  Serial.print("  Data = ");
  Serial.print(present,HEX);
  Serial.print(" ");
  for ( i = 0; i < 9; i++) {           // we need 9 bytes
    data[i] = ds.read();
    Serial.print(data[i], HEX);
    Serial.print(" ");
  }
  Serial.print(" CRC=");
  Serial.print(OneWire::crc8(data, 8), HEX);
  Serial.println();

  // convert the data to actual temperature

  unsigned int raw = (data[1] << 8) | data[0];
  if (type_s) {
    raw = raw << 3; // 9 bit resolution default
    if (data[7] == 0x10) {
      // count remain gives full 12 bit resolution
      raw = (raw & 0xFFF0) + 12 - data[6];
    }
  } else {
    byte cfg = (data[4] & 0x60);
    if (cfg == 0x00) raw = raw << 3;  // 9 bit resolution, 93.75 ms
    else if (cfg == 0x20) raw = raw << 2; // 10 bit res, 187.5 ms
    else if (cfg == 0x40) raw = raw << 1; // 11 bit res, 375 ms
    // default is 12 bit resolution, 750 ms conversion time
  }
  celsius = (float)raw / 16.0;
  fahrenheit = celsius * 1.8 + 32.0;
  Serial.print("  Temperature = ");
  Serial.print(celsius);
  Serial.print(" Celsius, ");
  Serial.print(fahrenheit);
  Serial.println(" Fahrenheit");
}
```

Open the Sscom32 terminal or the Serial moniter , and set the baudrate to 9600, you will see calculated temperature on the moniter. 
![Ds18B20 output.jpg](https://wiki.elecrow.com/images/7/7f/Ds18B20_output.jpg){ loading=lazy }

## Resource
--------

[DS18B20 DataSheet](http://dlnmh9ip6v2uc.cloudfront.net/datasheets/Sensors/Temp/DS18B20.pdf)  
[DS18B20 Lib Get Start](http://bildr.org/2011/07/ds18b20-arduino/)  
[1-Wire Protocol Explanation ](http://playground.arduino.cc/Learning/OneWire) 