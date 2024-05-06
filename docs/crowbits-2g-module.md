---
title: Crowbits-2G Module
---

## Description
-----------

Crowbits- OLED is constructed from 128 x 64 dot matrix OLED module. The display offers high brightness, self-emission, high contrast ratio, slim/thin outline, wide viewing angle, wide temperature range and low power consumption.

![Crowbits-2G-Module-1.jpg](https://wiki.elecrow.com/images/thumb/b/b1/Crowbits-2G-Module-1.jpg/600px-Crowbits-2G-Module-1.jpg){ loading=lazy }

## Features
--------

- GSM
- Easy to use

## Specification
-------------

- Interface Type: UART
- Operating Voltage: 3.3V DC
- Dimensions: 56(L)\*31(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board. And Crowbits-Key Board module.

2\. Connect the module to the D4 and D5 interface of the Crowbits-UNO board, and Crowbits-Key Board connect the MIC interface of the Crowbits-2G Module. As shown in the figure:

![Crowbits-2G Module-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/f/f8/Crowbits-2G_Module-Wiki_1.JPG/600px-Crowbits-2G_Module-Wiki_1.JPG){ loading=lazy }

3\. Upload the following code to the Crowbits-UNO board.

```
#include <SoftwareSerial.h>
 
SoftwareSerial mySerial(4, 5); // RX, TX
 
void setup() {
  // Open serial communications and wait for port to open:
  Serial.begin(9600);
  while (!Serial) {
    ; // wait for serial port to connect. Needed for native USB port only
  }
 
 
  Serial.println("test uart!");
 
  // set the data rate for the SoftwareSerial port
  mySerial.begin(9600);
}
 
void loop() { // run over and over
  if (mySerial.available()) {
    Serial.write(mySerial.read());
  }
  if (Serial.available()) {
    mySerial.write(Serial.read());
  }
}
```

4\. After the upload is successful, open the serial port monitor, the baud rate is set to 9600. Then send a command to call.

- AT return OK // The serial port connection is normal
- AT+CREG? Return +CREG: 0,1 // Indicates successful network registration
- AT+CSQ //Test signal strength
- ATD10086; //Call
- ATH // hang up the phone
- ATA // answer the phone

![Crowbits-2G Module-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/c/c4/Crowbits-2G_Module-Wiki_2.jpg/600px-Crowbits-2G_Module-Wiki_2.jpg){ loading=lazy }