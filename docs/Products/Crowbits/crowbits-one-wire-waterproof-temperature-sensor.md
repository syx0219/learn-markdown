---
title: Crowbits-One Wire Waterproof Temperature Sensor
---

## Description
-----------

This is a waterproofed version of the DS18B20 Temperature sensor. Handy for when you need to measure something far away, or in wet conditions. While the sensor is good up to 125 degree, the cable is jacketed in PVC so we suggest keeping it under 100 degree. Because they are digital, you don't get any signal degradation even over long distances! The DS18B20 provides 9 to 12-bit (configurable) temperature readings over a 1-Wire interface, so that only one wire (and ground) needs to be connected from a central microprocessor. It Usable with 3.0-5.5V systems. Because each DS18B20 contains a unique silicon serial number, multiple DS18B20s can exist on the same 1-Wire bus. This allows for placing temperature sensors in many different places. Applications where this feature is useful include HVAC environmental controls, sensing temperatures inside buildings, equipment or machinery, and process monitoring and control.  
![Crowbits-One Wire Waterproof Temperature Sensor 1.jpg](https://wiki.elecrow.com/images/7/7a/Crowbits-One_Wire_Waterproof_Temperature_Sensor_1.jpg){ loading=lazy }

## Features
--------

- 9 to 12bit selectable resolution
- one digital pin for communication
- Multiple sensors can share one pin
- Query time is less than 750ms

## Specification
-------------

- 3.0V to 5.5V input
- Temperature range: -55 to +125 degree
- 0.5degree Accuracy from -10 to +85 degree
- Stainless steel tube 6mm diameter by 30mm long
- Cable length: 90cm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1.You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2.Connect the module to the D2 interface of the Crowbits-UNO board, as shown in the figure:

![Crowbits-One Wire Waterproof Temperature Sensor-Wiki 1.jpg](https://wiki.elecrow.com/images/thumb/0/0a/Crowbits-One_Wire_Waterproof_Temperature_Sensor-Wiki_1.jpg/600px-Crowbits-One_Wire_Waterproof_Temperature_Sensor-Wiki_1.jpg){ loading=lazy }

3.Download the library “DS18B20”. Unzip and put it in the libraries file of the Arduino IDE, for example: C:\\Program Files (x86)\\Arduino\\libraries.

4.Upload the following code to the Crowbits-UNO board.

```
#include <OneWire.h>
OneWire  ds(2);  // on pin 10

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

5.After the upload is successful, open the serial port monitor, the baud rate is set to 9600. You can see the temperature value printed out.

![Crowbits-One Wire Waterproof Temperature Sensor-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/6/6b/Crowbits-One_Wire_Waterproof_Temperature_Sensor-Wiki_2.jpg/600px-Crowbits-One_Wire_Waterproof_Temperature_Sensor-Wiki_2.jpg){ loading=lazy }