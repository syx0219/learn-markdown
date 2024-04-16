---
title: 433MHz RF Transceiver CC1101 Module
---

## Introduction
------------

The CC1101 is a low-cost sub- 1 GHz transceiver designed for very low-power wireless applications. The circuit is mainly intended for the ISM (Industrial, Scientific and Medical) and SRD (Short Range Device) frequency bands at 315, 433, 868, and 915 MHz, but can easily be programmed for operation at otherfrequencies in the 300-348 MHz, 387-464 MHz and 779-928 MHz bands.

**Model: [WRF11010R](https://www.elecrow.com/433mhz-rf-transceiver-cc1101-module-p-374.html)**  
![433MHz RF Transceiver CC1101 Module3.jpg](https://wiki.elecrow.com/images/thumb/f/fb/433MHz_RF_Transceiver_CC1101_Module3.jpg/400px-433MHz_RF_Transceiver_CC1101_Module3.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/433mhz-rf-transceiver-cc1101-module-p-374.html?wiki "Title text")

## Features:
---------

- Input voltage :3.3V
- Maximum operating speed: 500kbps, support 2-FSK, GFSK and MSK modulation
- Can be modify the baud rate, power, frequency and other related parameters by software
- High sensitivity (&lt;1.2kbps -110dDm, 0.1% packet error rate)
- CRC error detection and built-in hardware address multipoint communication control
- Lower current consumption (RX, 15.6mA; 2.4kbps, 433MHz)
- Programmable control of output power, maximum output power of +10dBm
- Standard 2.0mm DIP pitch interfaces for embedded applications
- Separate 64-byte RX and TX data FIFO
- Transmission distance: 300 - 500 meters (Depending on the specific situation of the environment and communication baud rate, etc.)

## Usage
-----

1.Hardware connection  
![433MHz RF Transceiver CC1101 Module hardware connection.jpg](https://wiki.elecrow.com/images/thumb/5/5f/433MHz_RF_Transceiver_CC1101_Module_hardware_connection.jpg/400px-433MHz_RF_Transceiver_CC1101_Module_hardware_connection.jpg){ loading=lazy } ![433MHz RF Transceiver CC1101 Module hardware connection1.jpg](https://wiki.elecrow.com/images/thumb/4/48/433MHz_RF_Transceiver_CC1101_Module_hardware_connection1.jpg/400px-433MHz_RF_Transceiver_CC1101_Module_hardware_connection1.jpg){ loading=lazy }  
2.Download the code below into the TX Arduino (transmit) — This code will drive the 433MHz RF Transceiver CC1101 module to send out data form 0 to 10.

```
#include <ELECHOUSE_CC1101.h>

#define size 11

byte TX_buffer[size]={0};
byte i;

void setup()
{
  Serial.begin(9600);
  ELECHOUSE_cc1101.Init();
  for(i=0;i<size;i++)
  {
     TX_buffer[i]=i;
  }
}

void loop()
{
  ELECHOUSE_cc1101.SendData(TX_buffer,size);
  delay(1);
}
```

3.Download the code below into the RX Arduino (receive) – This code will drive the 433MHz RF Transceiver CC1101 module to receive the data that transmit form the TX module and print it to serial port.

```
 #include <ELECHOUSE_CC1101.h>
 
 void setup()
{
  Serial.begin(9600);
  ELECHOUSE_cc1101.Init();
  ELECHOUSE_cc1101.SetReceive();
}

byte RX_buffer[11]={0};
byte size,i,flag;

void loop()
{
  if(ELECHOUSE_cc1101.CheckReceiveFlag())
  {
    size=ELECHOUSE_cc1101.ReceiveData(RX_buffer);
    for(i=0;i<size;i++)
    {
      Serial.print(RX_buffer[i],DEC);
      Serial.print("  ");
    }
    Serial.println("");
    ELECHOUSE_cc1101.SetReceive();
  }
}
```

4.Now power on both Arduino , and connect the RX one to PC via USB. Open the IDE serial port monitor , change the baud rate to 9600 bps , and you can see the data that received.
![433MHz RF Transceiver CC1101 Module result.jpg](https://wiki.elecrow.com/images/a/ab/433MHz_RF_Transceiver_CC1101_Module_result.jpg){ loading=lazy }

## Resource
--------

- [CC101 module demo code for Arduino](../../files/CC1101-zip.md)
- [CC101 module demo code for Arduino of panstamp](../../files/Panstamp-zip.md)

## Related links
-------------

Click [here](http://www.elecrow.com/wireless-c-78/rf-c-78_122/433mhz-rf-transceiver-cc1101-module-p-374.html) to buy [433MHz RF Transceiver CC1101 Module](http://www.elecrow.com/wireless-c-78/rf-c-78_122/433mhz-rf-transceiver-cc1101-module-p-374.html)