---
title: ENC28J60 Ethernet Module
---

## Description
-----------

The ENC28J60 Ethernet Module utilizes the new Microchip ENC28J60 Stand-Alone Ethernet Controller IC featuring a host of features to handle most of the network protocol requirements. The board connects directly to most microcontrollers with a standard SPI interface with a transfer speed of up to 20MHz.  
**Model:[SIN16080E](http://www.elecrow.com/enc28j60-ethernet-module-p-587.html)**

![ENC28J60 Ethernet Module.jpg](https://wiki.elecrow.com/images/thumb/a/ad/ENC28J60_Ethernet_Module.jpg/400px-ENC28J60_Ethernet_Module.jpg){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png)](https://www.elecrow.com/enc28j60-ethernet-module-p-587.html?wiki "Title text")

## Specification
-------------

- ENC28J60 Ethernet chips, SOP28 package
- SPI Interface
- 2X5 connector, can be easily mounted with the MCU
- Power indicator
- Single Supply: +3.3 V
- PCB size: 55x36 mm

## Usage
-----

1.Hardware Installation

![ENC-table.jpg](https://wiki.elecrow.com/images/d/d7/ENC-table.jpg){ loading=lazy }
![ENC28J60 Ethernet Module hardware.jpg](https://wiki.elecrow.com/images/thumb/d/dc/ENC28J60_Ethernet_Module_hardware.jpg/500px-ENC28J60_Ethernet_Module_hardware.jpg){ loading=lazy }

2.Download the library File:[ENC28J60 Library](https://wiki.elecrow.com/images/a/aa/Arduino_library_for_ENC28J60.zip)  
3.Unzip it into the libraries file of Arduino IDE by the path: ..\\arduino-1.0\\libraries.  
4.Open Arduino IDE Files -&gt; Examples -&gt; ENC\_28J60 -&gt; Helloworld.  
The IP address in the example code need to be changed for the address assigned to ENC28J60 module.

```
// A simple web server that always just says "Hello World"

#include "etherShield.h"
#include "ETHER_28J60.h"

static uint8_t mac[6] = {0x54, 0x55, 0x58, 0x10, 0x00, 0x24};   // this just needs to be unique for your network, 
                                                                // so unless you have more than one of these boards
                                                                // connected, you should be fine with this value.
                                                           
static uint8_t ip[4] = {192, 168, 1, 15};                       // the IP address for your board. Check your home hub
                                                                // to find an IP address not in use and pick that
                                                                // this or 10.0.0.15 are likely formats for an address
                                                                // that will work.

static uint16_t port = 80;                                      // Use port 80 - the standard for HTTP

ETHER_28J60 ethernet;

void setup()
{ 
  ethernet.setup(mac, ip, port);
}

void loop()
{
  if (ethernet.serviceRequest())
  {
    ethernet.print("<H1>Hello World</H1>");
    ethernet.respond();
  }
  delay(100);
}
```

5.Upload the code,then enter your Ethernet shield IP address into the URL bar.
![px](https://wiki.elecrow.com/images/4/4b/ENC28J60_Ethernet_Module_test_result.jpg){ loading=lazy }

## Resources
---------

- [[ENC28J60 Library](https://wiki.elecrow.com/images/a/aa/Arduino_library_for_ENC28J60.zip)