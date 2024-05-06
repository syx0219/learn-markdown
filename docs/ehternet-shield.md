---
title: Ehternet Shield
---

## Description
-----------

The Ethernet Shield connects your Arduino device to the internet in mere minutes. Just plug this module onto your Arduino board, connect it to your network with an RJ45 cable (not included) and follow a few simple instructions to start controlling your world through the internet.

The Ethernet controller of this Ethernet Shield is W5200. it is twice the buffer size of W5100 and support for up to eight simultaneous TCP/UDP connections. There is an onboard micro-SD card slot, which can be used to store files for serving over the network. Thanks to a lowered RJ45 pot, you can flexibly add most shields on top of this Ethernet Shield.

**Model: [ACS52001S](http://www.elecrow.com/w5200-ethernet-shield-p-367.html)**

![Ethernet Shield.JPG](https://wiki.elecrow.com/images/thumb/d/dc/Ethernet_Shield.JPG/400px-Ethernet_Shield.JPG){ loading=lazy }

## Features
--------

- Standard Shield that Arduino, Mega, Crowduino Compatible
- High speed Ethernet controller W5200 with internal 32K buffer
- With Micro SD card for storing large amounts of data.
- Connection with Arduino on SPI port
- Support up to eight simultaneous TCP/UDP connections
- Lowered RJ45 Ethernet jack
- long wire-wrap headers extend through the shield

## Specification
-------------

<table border="1" cellspacing="0" width="100%">
    <tbody>
        <tr>
            <th scope="col" align="center"> Item</th>
            <th scope="col" align="center"> Min</th>
            <th scope="col" align="center"> Typical</th>
            <th scope="col" align="center"> Max</th>
            <th scope="col" align="center"> Unit</th>
        </tr>
        <tr>
            <th scope="row">Voltage</th>
            <td align="center">3.5</td>
            <td align="center">5.0</td>
            <td align="center">5.5</td>
            <td align="center">VDC</td>
        </tr>
        <tr>
            <th scope="row">Current</th>
            <td align="center">120</td>
            <td align="center">210</td>
            <td align="center">350</td>
            <td align="center">mA</td>
        </tr>
        <tr>
            <th scope="row"> Supported SD</th>
            <td align="center" colspan="3">Micro SD card(More than 2G is not guaranteed)</td>
            <td align="center">/</td>
        </tr>
        <tr>
            <th scope="row"> Supported Connection</th>
            <td align="center" colspan="3">TCP/UDP</td>
            <td align="center">/</td>
        </tr>
        <tr>
            <th scope="row"> Dimension</th>
            <td align="center" colspan="3"> 53.4X68.7</td>
            <td align="center">mm</td>
        </tr>
        <tr>
            <th scope="row"> Weight</th>
            <td align="center" colspan="3"> 22.3</td>
            <td align="center">g</td>
        </tr>
    </tbody>
</table>

## Interface
---------

![Interface of Ethernet Shield.jpg](https://wiki.elecrow.com/images/thumb/e/ec/Interface_of_Ethernet_Shield.jpg/800px-Interface_of_Ethernet_Shield.jpg){ loading=lazy }

**Hardware Configuration**

RJ45: Ethernet Port;

IC HX1198: 10/100BASE-T signal port;

IC W5200: a hardwired TCP/IP Ethernet Controller;

U3: IC CJ117, low dropout linear regulator;

U6: IC 74VHC125PW, quad buffer;

Reset KEY: Reset Ethernet shield and Arduino when pressed;

SD card: support Micro SD card in FAT16 or FAT32; maximum storage is 2GB.

**Pins usage on Arduino**

D4: SD card chip select

D10: W5200 Chip Select

D11: SPI MOSI

D12: SPI MISO

D13: SPI SCK

*Notice:*

Both W5200 and SD card communicate with Arduino via SPI bus. Pin 10 and pin 4 are chip select pins for W5200 and SD slot. They cannot be used as general I/O.   
Connect the PWDN pin to GND or VCC to control it be in Power Down Mode.  
If you can't run the the Ethernet. please connect thw PWDN pin to GND and have a try again.

## Usage
-----

We are going to build a simple web server that answer request from a client and store the readings from A0 through A5 to SD card.

**Step 1: Hookup**

1\. Mount Ethernet Shield v1.0 to your Arduino;

2\. Connect the shield to your computer or a network hub or a router using a standard Ethernet cable;

3\. Connect Arduino to PC via USB cable;

4\. Insert a SD card to the SD card slot.


**Step 2: Upload the program**

1\. Download the library：[Ethernet\_Shield\_W5200 Library](https://wiki.elecrow.com/images/7/77/Ethernet_Shield_W5200.zip).

2\. Unzip and put it in the libraries file of Arduino IDE by the path: ..\\arduino-1.0.1\\libraries.

3\. Restart the Arduino IDE.

4\. Open the example "WebServerWithSD" via the path: File --&gt; Examples --&gt; EthernetV1\_0 --&gt; WebServerWithSD. This example shows you how to build up a simple web server that displays the readings of anolog A0 through A5 when requested. After that, store those readings into SD card.

*Note**:*

This new library covers all functions included in the buildin Ethernet library of Arduino IDE. You can use other examples in the same way as that in the preceding Ethernet library.

5\. Upload the program to Arduino. If you do no how to upload code, please click [here](./index.md).


![Example.jpg](https://wiki.elecrow.com/images/a/a9/Example.jpg){ loading=lazy }

In this code ,we have defined pin 4 as SD card chip select port and pin 10 as W5200 chip select port.

Firstly it will send a link to this client if there has a client request access this server.Then send the value of each analog input pin to the network.

Finally you can view each analog pin by open SD Card file.

**Step 3: Results**

Open a web browser and enter the IP address of your controller. It's dependent on your local network but used to be 192.168.168.178. Then you should find the readings of A0 through A5 popping up as shown below.

![Ethernet Score.jpg](https://wiki.elecrow.com/images/7/7f/Ethernet_Score.jpg){ loading=lazy }

To check what's going on to the SD card, open the serial monitor. You can use the built-in serial monitor of Arduino IDE or a serial monitor tool as us. After opening a serial monitor, you can read the content of file "test.txt" which we created to store the readings of analog pins.

![WebServerWithSD Result.jpg](https://wiki.elecrow.com/images/2/25/WebServerWithSD_Result.jpg){ loading=lazy }

Notice:  
1） Make sure the Ethernet Shield and your computer are in the same local network.  
2） Once the code has been successfully uploaded, it's fine to disconnect the board from your computer and apply independent power to it, leaving it run alone.

## Resource
--------

- [Ethernet\_Shield\_W5200 Library](https://wiki.elecrow.com/images/7/77/Ethernet_Shield_W5200.zip)

- [SD Library](https://wiki.elecrow.com/images/8/88/SD.zip)

- [W5200 Datasheet.pdf](https://wiki.elecrow.com/images/a/ae/IEthernet_W5200_datasheet_v1.2.5_en.pdf)

- [Ethernet Shield v1.0 Schematic.pdf](https://wiki.elecrow.com/images/c/c8/Ethernet_Shield_v1.1.pdf)

- [Ethernet Shield v1.1 eagle file.zip](https://wiki.elecrow.com/images/b/b4/ELE_Ethernet_Shield_eagle_files.zip)

- [Ethernet shield 1.2 eagle file.zip](https://wiki.elecrow.com/images/1/10/Ethernet_shield_1.2_eagle_file.zip)