---
title: CAN-BUS Shield
---

## Introduction
------------

CAN-BUS is a common industrial bus because of its long travel distance, medium communication speed and high reliability. It is widely used as the automotive diagnostic bus, and also commonly used on modern machine tools. This CAN-Bus shield gives the Arduino CAN-Bus capability, It uses the Microchip MCP2515 CAN controller with MCP2551 CAN transceiver, the CAN connection is via a standard 9-way sub-D for use with OBD-II cable, ideal for automotive CAN application. The shield also has a Micro SD card holder, which helps you store the diagnostic information in the SD card directly, making this shield ideal for data logging application.

**Model: [AS54887CAN](https://www.elecrow.com/canbus-shield-p-1133.html)**   
![CAN-BUS Shield1.jpg](https://wiki.elecrow.com/images/thumb/a/ac/CAN-BUS_Shield1.jpg/400px-CAN-BUS_Shield1.jpg){ loading=lazy }

## Features
--------

- Arduino Mega and Leonardo compatible
- Implements CAN V2.0B at up to 1 Mb/s
- SPI Interface up to 10 MHz
- Standard (11 bit) and extended (29 bit) data and remote frames
- Two receive buffers with prioritized message storage
- Industrial standard 9 pin sub-D connector
- Two LED indicators
- SD card holder for information storage
- Dimensions(mm):74.3(L)x53.6(W)x23.5(H)

## Usage
-----

### **Hardware Installation**

Plug the CAN-BUS Shield onto the Arduino. And then connect the Crowduino to PC with USB cable.  
![CAN-BUS Shield .jpg](https://wiki.elecrow.com/images/thumb/3/36/CAN-BUS_Shield_connect.jpg/400px-CAN-BUS_Shield_connect.jpg){ loading=lazy }

### **Upload the program**

1\. Download the [CAN-BUS Source code file for Arduino 1.0](./files/CAN-BUS-Shield-master-zip.md) and release it in the libraries file in the Arduino-1.0 program.: ..\\arduino-1.0\\libraries.

If the folder name include "-master", just remove it.

2\. Open the Arduino-1.0, and you will find 8 examples: receive\_check ,send and receive\_interrupt and so on. Here we'll use send and receive\_check, open it then you should get two programming windows now.

![Open CAN BUS examples send.jpg](https://wiki.elecrow.com/images/thumb/3/37/Open_CAN_BUS_examples_send.jpg/400px-Open_CAN_BUS_examples_send.jpg){ loading=lazy }
![Open CAN BUS examples receive.jpg](https://wiki.elecrow.com/images/thumb/a/aa/Open_CAN_BUS_examples_receive.jpg/400px-Open_CAN_BUS_examples_receive.jpg){ loading=lazy }  
2.1 Send data:

```
// demo: CAN-BUS Shield, send data
#include <mcp_can.h>
#include <SPI.h>

// the cs pin of the version after v1.1 is default to D9
// v0.9b and v1.0 is default D10
const int SPI_CS_PIN = 9;

MCP_CAN CAN(SPI_CS_PIN);                                    // Set CS pin

void setup()
{
    Serial.begin(115200);

START_INIT:

    if(CAN_OK == CAN.begin(CAN_500KBPS))                   // init can bus : baudrate = 500k
    {
        Serial.println("CAN BUS Shield init ok!");
    }
    else
    {
        Serial.println("CAN BUS Shield init fail");
        Serial.println("Init CAN BUS Shield again");
        delay(100);
        goto START_INIT;
    }
}

unsigned char stmp[8] = {0, 1, 2, 3, 4, 5, 6, 7};
void loop()
{
    // send data:  id = 0x00, standrad frame, data len = 8, stmp: data buf
    CAN.sendMsgBuf(0x00, 0, 8, stmp);
    delay(100);                       // send data per 100ms
}
```

2.2 Receive data

```
// demo: CAN-BUS Shield, receive data with check mode
// send data coming to fast, such as less than 10ms, you can use this way


#include <SPI.h>
#include "mcp_can.h"


// the cs pin of the version after v1.1 is default to D9
// v0.9b and v1.0 is default D10
const int SPI_CS_PIN = 9;

MCP_CAN CAN(SPI_CS_PIN);                                    // Set CS pin

void setup()
{
    Serial.begin(115200);

START_INIT:

    if(CAN_OK == CAN.begin(CAN_500KBPS))                   // init can bus : baudrate = 500k
    {
        Serial.println("CAN BUS Shield init ok!");
    }
    else
    {
        Serial.println("CAN BUS Shield init fail");
        Serial.println("Init CAN BUS Shield again");
        delay(100);
        goto START_INIT;
    }
}


void loop()
{
    unsigned char len = 0;
    unsigned char buf[8];

    if(CAN_MSGAVAIL == CAN.checkReceive())            // check if data coming
    {
        CAN.readMsgBuf(&len, buf);    // read data,  len: data length, buf: data buf

        unsigned char canId = CAN.getCanId();
        
        Serial.println("-----------------------------");
        Serial.println("get data from ID: ");
        Serial.println(canId);

        for(int i = 0; i<len; i++)    // print the data
        {
            Serial.print(buf[i]);
            Serial.print("\t");
        }
        Serial.println();
    }
}
```

3\. Upload two examples to two boards separately. Choose the board via the path: Tools --&gt;Serial Port--&gt;COMX. Note down which board is assigned as a "send" node and which board is assigned as a "receive" node.

4\. Open the "Serial Monitor" on the "receive" COM, you will get message sent from the "send" node. Here we have the preset message "0 1 2 3 4 5 6 7" showing in the following picture.

![CAN BUS message1.jpg](https://wiki.elecrow.com/images/thumb/8/82/CAN_BUS_message1.jpg/400px-CAN_BUS_message1.jpg){ loading=lazy }

## Reference
---------

### 1. Set the BaudRate

This function is used to initialize the baudrate of the CAN Bus system.

The available baudrates are listed as follws:

CAN\_5KBPS, CAN\_10KBPS, CAN\_20KBPS, CAN\_40KBPS, CAN\_50KBPS, CAN\_80KBPS, CAN\_100KBPS, CAN\_125KBPS, CAN\_200KBPS, CAN\_250KBPS, CAN\_500KBPS and CAN\_1000KBPS

### 2. Set Receive Mask and Filter

There are 2 receive mask registers and 5 filter registers on the controller chip that guarantee you get data from the target device. They are useful especially in a large network consisting of numerous nodes.

We provide two functions for you to utilize these mask and filter registers. They are:

*init\_Mask(unsigned char num, unsigned char ext, unsigned char ulData);* &amp; *init\_Filt(unsigned char num, unsigned char ext, unsigned char ulData);*

*"num"* represents which register to use. You can fill 0 or 1 for mask and 0 to 5 for filter.

*"ext"* represents the status of the frame. 0 means it's a mask or filter for a standard frame. 1 means it's for a extended frame.

*"ulData"* represents the content of the mask of filter.

### 3. Check Receive

The MCP2515 can operate in either a polled mode, where the software checks for a received frame, or using additional pins to signal that a frame has been received or transmit completed. Use the following function to poll for received frames.

*INT8U MCP\_CAN::checkReceive(void);*

The function will return 1 if a frame arrives, and 0 if nothing arrives.

### 4. Get CAN ID

When some data arrive, you can use the following function to get the CAN ID of the "send" node.

*INT32U MCP\_CAN::getCanId(void)*

### 5. Send Data

*CAN.sendMsgBuf(INT8U id, INT8U ext, INT8U len, data\_buf);*

is a function to send data onto the bus. In which:

*"id"* represents where the data come from.

*"ext"* represents the status of the frame. '0' means standard frame. '1' means extended frame.

*"len"* represents the length of this frame.

*"data\_buf"* is the content of this message.

For example, In the 'send' example, we have:

```
  
unsigned char stmp[8] = {0, 1, 2, 3, 4, 5, 6, 7};

CAN.sendMsgBuf(0x00, 0, 8, stmp); //send out the message 'stmp' to the bus and tell other devices this is a standard frame from 0x00.
```

### 6. Receive Data

The following function is used to receive data on the 'receive' node:

*CAN.readMsgBuf(unsigned char len, unsigned char buf);*

In conditions that masks and filters have been set. This function can only get frames that meet the requirements of masks and filters.

*"len"* represents the data length.

*"buf"* is where you store the data.

## Resources
---------

- [CAN-BUS Source code file for Arduino 1.0](./files/CAN-BUS-Shield-master-zip.md)
- [MCP2551 datasheet](./files/Mcp2551en-pdf.md)
- [MCP2515 datasheet](./files/MCP2515-pdf.md)