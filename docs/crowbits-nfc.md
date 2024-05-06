---
title: Crowbits-NFC
---

## Description
-----------

The Crowbits-NFC module (Near Field Communications) uses a highly integrated transceiver module PN532 which handles contactless communication at 13.56MHz. It is designed to use IIC (default) communication protocols. You can read and write a 13.56MHz tag with this module or implement point to point data exchange with two NFC Shields.

![Crowbits-NFC-1.jpg](https://wiki.elecrow.com/images/thumb/b/b4/Crowbits-NFC-1.jpg/600px-Crowbits-NFC-1.jpg){ loading=lazy }

## Features
--------

- Uses as a PFID reader with Mifare one tags and cards(13.56 MHz).

## Specification
-------------

- Interface Type: I2C
- Operating Voltage: 3.3V DC
- Dimensions: 31.5(L)\*24.5(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the I2C interface on the Crowbits-UNO board, as shown in the figure:

![Crowbits-NFC-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/8/82/Crowbits-NFC-Wiki_1.JPG/600px-Crowbits-NFC-Wiki_1.JPG){ loading=lazy }

3\. Download the library “Crowbits-NFC”. Unzip it and copy the folder inside to the libraries file of the Arduino IDE, for example: C:\\Program Files (x86)\\Arduino\\libraries.

4\. Upload the following code to the Crowbits-UNO board.

```
#if 0
#include <SPI.h>
#include <PN532_SPI.h>
#include <PN532.h>
#include <NfcAdapter.h>

PN532_SPI pn532spi(SPI, 10);
NfcAdapter nfc = NfcAdapter(pn532spi);
#else

#include <Wire.h>
#include <PN532_I2C.h>
#include <PN532.h>
#include <NfcAdapter.h>

PN532_I2C pn532_i2c(Wire);
NfcAdapter nfc = NfcAdapter(pn532_i2c);
#endif

void setup(void) {
    Serial.begin(9600);
    Serial.println("NDEF Reader");
    nfc.begin();
}

void loop(void) {
    Serial.println("\nScan a NFC tag\n");
    if (nfc.tagPresent())
    {
        NfcTag tag = nfc.read();
        tag.print();
    }
    delay(5000);
}
```

5\. After the upload is successful, open the serial port monitor, the baud rate is set to 9600. Put the NFC card in the detection area, the serial port will print out the corresponding information.

![Crowbits-NFC-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/9/9c/Crowbits-NFC-Wiki_2.jpg/600px-Crowbits-NFC-Wiki_2.jpg){ loading=lazy }