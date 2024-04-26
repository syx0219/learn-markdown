---
title: Crowtail- NFC
---

## **Introduction**
----------------

The Crowtail-NFC module (Near Field Communications) uses a highly integrated transceiver module PN532 which handles contactless communication at 13.56MHz. You can read and write a 13.56MHz tag with this module or implement point to point data exchange with two NFC Shields. It is designed to use IIC (default) communication protocols. In addition, you can also use UART communication protocols via change the connection between the welded plates.

Model: [CRT01015N](https://www.elecrow.com/crowtail-nfc.html)

![Crowtail- NFC.jpg](https://wiki.elecrow.com/images/thumb/b/b1/Crowtail-_NFC.jpg/500px-Crowtail-_NFC.jpg){ loading=lazy }

## **Features**
------------

- Use as a RFID reader with Mifare One tags and cards (13.56MHZ).

- Support host interface : UART ,IIC(default).

- Independent PCB antenna(13.56MHZ).

- Max operating distance for detecting NFC tags is 28mm depending on current antenna size.

- Support P2P communication.

## **Specification**
-----------------

- Working Voltage:3.3V.

- Support ISO14443 type A and Type B protocols.

- Antenna size : 18 x 28 x0.8 mm, IPX port.

- Antenna wire impedance : 50omh.

- Dimensions(mm):40.0(L)x20.0(W)x9.8(H)

## **Application**
---------------

- Build visiting card sharing system.

- Build attendance systems.

- Design authentication systems.

- Read Smart Posters.

- Securely exchange small data with other NFC devices

- And other endless possibility

## **Interface**
-------------

![Dsg14.jpg](https://wiki.elecrow.com/images/thumb/2/29/Dsg14.jpg/600px-Dsg14.jpg){ loading=lazy }

## **Usage**
---------

This demo is going to show you how to read NFC information via use this Crowtail-NFC module.

### **IIC mode：**

**1.Hardware Installation**

The Crowtail-NFC is connecting to IIC port of Crowtail - Base Shield and then plug in the antenna.

![NFC1131.jpg](https://wiki.elecrow.com/images/thumb/a/a5/NFC1131.jpg/600px-NFC1131.jpg){ loading=lazy }

2.Download ["NFC Lib"](../../files/LD-NFClib-zip.md) for arduino boards, unzip and put it in the libraries of Arduino IDE by the path : ..\\arduino-1.x.x\\libraries;

3.Open "ReadTag" example via the path: File--&gt;Examples--&gt;ND EF--&gt;ReadTag.

![NFC114.jpg](https://wiki.elecrow.com/images/thumb/6/66/NFC114.jpg/500px-NFC114.jpg){ loading=lazy }


4.Upload it into your arduino board and open the serial monitor, move NFC card close to the NFC atntenna and then observe the NFC information.

![NFC116.jpg](https://wiki.elecrow.com/images/thumb/c/c4/NFC116.jpg/300px-NFC116.jpg){ loading=lazy }

### **UART mode:**

1.First, if you want to use UART communication protocols,you need to disconnect the left welding disks and connect the right welding disks of the P1 via a soldering iron.

![NFC1162.jpg](https://wiki.elecrow.com/images/thumb/8/87/NFC1162.jpg/500px-NFC1162.jpg){ loading=lazy }

The connect Crowtail NFC J2 port to the arduino MEGE2560 via the jumper ,as follow:

![NFC117.jpg](https://wiki.elecrow.com/images/thumb/c/c5/NFC117.jpg/500px-NFC117.jpg){ loading=lazy }

VCC ------ VCC

GND ------- GND

RX ------- TX1

TX ------- RX1

2.Download “LD\_NFClib” for arduino boards, unzip and put it in the libraries of Arduino IDE by the path : ..\\arduino-1.x.x\\libraries;

3\. open ” ReadTag” example via the path: File--&gt;Examples--&gt; LD\_NFClib --&gt;example --&gt;testNFC.

4\. Upload it into your arduino board and open the serial monitor, move NFC card close to the NFC atntenna and then observe the NFC information.

## **Resource**
------------

- [LD\_NFClib Library](../../files/LD-NFClib-zip.md)
- [NFC](../../files/NFC-zip.md)