---
title: 315/433Mhz RF Link Kit
---

## Introduction
------------

The 315/433MHz RF link kit is consisted of transmitter and receiver, popular used for remote control. It will be easy to use this kit to transmit data via RF With the suggest[Arduino VirtualWire library](#resource).  
**Model: [WRF43301R](http://www.elecrow.com/communication-c-78/rfism-c-78_122/433mhz-rf-transmitting-module-p-372.html) [WRF31501R](http://www.elecrow.com/communication-c-78/rfism-c-78_122/315mhz-rf-transmitting-module-p-371.html)**  

![3154331.jpg](https://wiki.elecrow.com/images/thumb/5/56/3154331.jpg/400px-3154331.jpg){ loading=lazy }

## Specification
-------------

- Frequency: 315/433Mhz
- Modulation: ASK
- Receiver Data Output: High - 1/2 Vcc, Low - 0.7v
- Transmitor Input Voltage: 3-12V (high voltage = more transmitting power)

## Usage
-----

### **Hardware**

There are one transmitter and one receiver in this kit, you will needs 2 arduino main board in your application. one for coding and senting the message, with the RF transmitter, the other one for receiving message and decoding. the whole system working as belows: 
![315433hard.png](https://wiki.elecrow.com/images/e/e5/315433hard.png){ loading=lazy }

### **Programming**

with the [virtualwire arduino library](#resource),please refer to [how to install library and upload program](../../how/how-to-install-the-librarys-and-upload-programs-to-arduino.md), it would be easy to transmit data or message from the transmitter to receiver.
on the transmitter, After connecting the transmitter data pin to arduino D2 and installing the virtualwire library, program the arduino as below:

```
#include <VirtualWire.h>
int RF_TX_PIN = 2;
void setup()
{
  vw_set_tx_pin(RF_TX_PIN); // Setup transmit pin
  vw_setup(2000); // Transmission speed in bits per second.
}
 
void loop()
{
  const char *msg = "hi,RFlink";
  vw_send((uint8_t *)msg, strlen(msg));  // Send 'hello' every 400ms.
  delay(400);
}
```

on the receiver, After connecting the receiver data pin to arduino D2 and installing the virtualwire library, program the arduino as below:

```
#include <VirtualWire.h> 
int RF_RX_PIN = 2;
void setup()
{
  Serial.begin(9600);//init the UART between arduino and PC
  Serial.println("setup");
  vw_set_rx_pin(RF_RX_PIN); 
  vw_setup(2000); // Transmission speed in bits per second.
  vw_rx_start(); // Start the PLL receiver.
}
 
void loop()
{
  uint8_t buf[VW_MAX_MESSAGE_LEN];
  uint8_t buflen = VW_MAX_MESSAGE_LEN;
  if(vw_get_message(buf, &buflen)) // non-blocking I/O
  {
    int i;
    // Message with a good checksum received, dump HEX
    Serial.print("Got: ");
    for(i = 0; i < buflen; ++i)
    {
	// Serial.write(buf[i]);//print the received message to the serial
    }
    Serial.println("");
  }
}
```

## Resource
--------

[File:Virtualwire.zip](../../files/Virtualwire-zip.md "File:Virtualwire.zip")  
[Virtualwire Introduction](http://www.elecrow.com/wiki/images/2/2f/Virtualwire_introduction.pdf)