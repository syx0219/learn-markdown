---
title: Crowbits-EEPROM
---

## Description
-----------

If you need to do some data storage in Arduino but found that the EEPROM in ATmega chip too limited, then this Crowbits-EEPROM is your best choice. This module is based on the EEPROM chip AT24C256, which has 256k bit capacity. It communicates with Arduino with I2C bus, helps you do much more data storage easily.

![Crowbits-EEPROM-1.jpg](https://wiki.elecrow.com/images/thumb/b/b3/Crowbits-EEPROM-1.jpg/600px-Crowbits-EEPROM-1.jpg){ loading=lazy }

## Features
--------

- Onboard chip AT24C256 chip
- Data is not lost when power off

## Specification
-------------

- Interface Type: I2C
- Operating Voltage: 3.3V DC
- Dimensions: 56(L)\*31(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the I2C interface on the Crowbits-UNO board, as shown in the figure:

![Crowbits-EEPROM-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/0/0b/Crowbits-EEPROM-Wiki_1.JPG/600px-Crowbits-EEPROM-Wiki_1.JPG){ loading=lazy }

3\. Upload the following code to the Crowbits-UNO board.

```
#include <Wire.h>
#define EEPROM_ADDR 0x50           // I2C Buss address of 24LC256 256K EEPROM

void setup()
{
  Wire.begin();                        // join I2C bus (address optional for master)
  Serial.begin(9600);

  // TESTS FOR EACH FUNCTION BEGIN HERE
  Serial.println("Writing Test:");
  for (int i=0; i<20; i++){            // loop for first 20 slots
    i2c_eeprom_write_byte(EEPROM_ADDR,i,i+65);   // write address + 65 A or 97 a
    Serial.print(". ");
    delay(10);                         // NEED THIS DELAY!
  }
  Serial.println("");
  delay(500);

  Serial.println("Reading Test:");
  for (int i=0; i<20; i++){            // loop for first 20 slots
    Serial.write(i2c_eeprom_read_byte(EEPROM_ADDR, i));
    Serial.print(" ");
  }

  // setup for page tests . . .
  byte PageData[30];                   // array that will hold test data for a page
  byte PageRead[30];                   // array that will hold result of data for a page
  for (int i=0; i<30; i++){            // zero both arrays for next test
    PageData[i] = 0;
    PageRead[i] = 0;
  }
  Serial.println("");
  for (int i=0; i<30; i++) PageData[i] = i+33;  // fill up array for next test char 33 = !

  Serial.println("Writing Page Test:");
  i2c_eeprom_write_page(EEPROM_ADDR, 100, PageData, 28 ); // 28 bytes/page is max

  Serial.println("Reading Page Test:");
  i2c_eeprom_read_buffer( EEPROM_ADDR, 100, PageRead, 28);
  for (int i=0; i<28; i++){
    Serial.write(PageRead[i]);    // display the array read
    Serial.print(" ");
  }
}

void loop()
{
}

void i2c_eeprom_write_byte( int deviceaddress, unsigned int eeaddress, byte data )
{
  int rdata = data;
  Wire.beginTransmission(deviceaddress);
  Wire.write((int)(eeaddress >> 8));    // Address High Byte
  Wire.write((int)(eeaddress & 0xFF));  // Address Low Byte
  Wire.write(rdata);
  Wire.endTransmission();
}

// Address is a page address, 6-bit (63). More and end will wrap around
// But data can be maximum of 28 bytes, because the Wire library has a buffer of 32 bytes
void i2c_eeprom_write_page
( int deviceaddress, unsigned int eeaddresspage, byte* data, byte length )
{
  Wire.beginTransmission(deviceaddress);
  Wire.write((int)(eeaddresspage >> 8)); // Address High Byte
  Wire.write((int)(eeaddresspage & 0xFF)); // Address Low Byte
  byte c;
  for ( c = 0; c < length; c++)
    Wire.write(data[c]);
  Wire.endTransmission();
  delay(10);                           // need some delay
}

byte i2c_eeprom_read_byte( int deviceaddress, unsigned int eeaddress )
{
  byte rdata = 0xFF;
  Wire.beginTransmission(deviceaddress);
  Wire.write((int)(eeaddress >> 8));    // Address High Byte
  Wire.write((int)(eeaddress & 0xFF));  // Address Low Byte
  Wire.endTransmission();
  Wire.requestFrom(deviceaddress,1);
  if (Wire.available()) rdata = Wire.read();
  return rdata;
}

// should not read more than 28 bytes at a time!
void i2c_eeprom_read_buffer( int deviceaddress, unsigned int eeaddress, byte *buffer, int length )
{
  Wire.beginTransmission(deviceaddress);
  Wire.write((int)(eeaddress >> 8));    // Address High Byte
  Wire.write((int)(eeaddress & 0xFF));  // Address Low Byte
  Wire.endTransmission();
  Wire.requestFrom(deviceaddress,length);
  //int c = 0;
  for ( int c = 0; c < length; c++ )
    if (Wire.available()) buffer[c] = Wire.read();
}
```

4\. After the upload is successful, open the serial port monitor, the baud rate is set to 9600, you can see the following print information.

![Crowbits-EEPROM-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/9/96/Crowbits-EEPROM-Wiki_2.jpg/600px-Crowbits-EEPROM-Wiki_2.jpg){ loading=lazy }