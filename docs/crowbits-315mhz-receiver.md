---
title: Crowbits-315Mhz Receiver
---

## Description
-----------

It uses 315Mhz simplex wireless communication. This module is small, affordable and easy to carry, suitable for indoor and outdoor wireless communication systems, and anti-theft systems, household appliances.

![Crowbits-315Mhz-RF-Receiver-1.jpg](https://wiki.elecrow.com/images/thumb/4/44/Crowbits-315Mhz-RF-Receiver-1.jpg/600px-Crowbits-315Mhz-RF-Receiver-1.jpg){ loading=lazy }

## Features
--------

- Remote controller system
- Easy to use

## Specification
-------------

- Operating Voltage: 3.3V DC
- Dimensions: 31.5(L)\*24.5(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1\. You need to prepare two Crowbits motherboards, such as Crowbits-UNO board. And a Crowbits-315Mhz Emitter board. Two output modules, such as Crowbits-LED.

2\. Connect the Crowbits-315Mhz Receiver board to the D2 interface of the Crowbits-UNO board and Crowbits-LED to the D11 interface.

3\. Connect the Crowbits-315Mhz Emitter board to the D9 interface of another Crowbits-UNO board and Crowbits-LED to the D5 interface.

4\. Download the “transmitter” program to the motherboard with the Crowbits-315Mhz Emitter module.

```
// transmitter.pde
//
// Simple example of how to use VirtualWire to transmit messages
// Implements a simplex (one-way) transmitter with an TX-C1 module
//
// See VirtualWire.h for detailed API docs
// Author: Mike McCauley (mikem@open.com.au)
// Copyright (C) 2008 Mike McCauley
// $Id: transmitter.pde,v 1.3 2009/03/30 00:07:24 mikem Exp $

#include <VirtualWire.h>
#undef int
#undef abs
#undef double
#undef float
#undef round

//TX-PIN 9
//LED-PIN 4
#define LedPin 5

void setup()
{
    pinMode(LedPin,OUTPUT);
    Serial.begin(9600);	  // Debugging only
    Serial.println("setup");

    // Initialise the IO and ISR
    vw_set_ptt_inverted(true); // Required for DR3100
    vw_setup(2000);	 // Bits per sec
}

void loop()
{
    const char *msg = "hello";

    digitalWrite(LedPin, true); // Flash a light to show transmitting
    vw_send((uint8_t *)msg, strlen(msg));
    vw_wait_tx(); // Wait until the whole message is gone
    Serial.print("Send: ");
    Serial.println(msg);
    digitalWrite(LedPin, false);
    delay(1000);
}
```

5\. Download the “receiver” program to the motherboard with the Crowbits-315Mhz Receiver module.

```
// receiver.pde
//
// Simple example of how to use VirtualWire to receive messages
// Implements a simplex (one-way) receiver with an Rx-B1 module
//
// See VirtualWire.h for detailed API docs
// Author: Mike McCauley (mikem@open.com.au)
// Copyright (C) 2008 Mike McCauley
// $Id: receiver.pde,v 1.3 2009/03/30 00:07:24 mikem Exp $

#include <VirtualWire.h>
#undef int
#undef abs
#undef double
#undef float
#undef round

//RX-PIN  2
//LED-PIN 11

#define LedPin 11

void setup()
{
  pinMode(LedPin, OUTPUT);
  Serial.begin(9600);	// Debugging only
  Serial.println("setup");

  // Initialise the IO and ISR
  vw_set_ptt_inverted(true); // Required for DR3100
  vw_setup(2000);	 // Bits per sec

  vw_rx_start();       // Start the receiver PLL running
}

void loop()
{
  char buf[VW_MAX_MESSAGE_LEN];
  char buflen = VW_MAX_MESSAGE_LEN;

  if (vw_get_message(buf, &buflen)) // Non-blocking
  {
    int i;

    digitalWrite(LedPin, true); // Flash a light to show received good message
    // Message with a good checksum received, dump it.
    Serial.print("Got: ");

    for (i = 0; i < buflen; i++)
    {
      Serial.print(buf[i]);
    }
    Serial.println("");
    digitalWrite(LedPin, false);
  }
}
```

6\. After the download procedure is completed, if the Crowbits-315Mhz Receiver module receives the information, the LED light connected to the D11 port will be on.

![Crowbits-315Mhz-Reciver-1.JPG](https://wiki.elecrow.com/images/thumb/4/41/Crowbits-315Mhz-Reciver-1.JPG/600px-Crowbits-315Mhz-Reciver-1.JPG){ loading=lazy }