---
title: Bluetooth Shield v1.0
---

## Description
-----------

The Bluetooth Shield integrates a Serial Bluetooth module. It can be easily used with Arduino /Crowduino for transparent wireless serial communication. You can choose two pins from Arduino D0 to D7 as Software Serial Ports to communicate with Bluetooth Shield (D0 and D1 is Hardware Serial Port). It also expand five analog IOs that you can use it to connect other devices.

**Model: [MCS01108S](http://www.elecrow.com/bluetooth-shield-masterslave-p-332.html)**

![Bluetooth Shield.jpg](https://wiki.elecrow.com/images/thumb/4/4d/Bluetooth_Shield.jpg/600px-Bluetooth_Shield.jpg){ loading=lazy }

## Features
--------

- Crowduino/Arduino compatible.
- Standard Shield designed that you can use it easily.
- Up to10m communication distance in house without obstacle
- UART interface (TTL) with programmable baud rate (SPP firmware installed)
- Default baud rate: 38400, data bits: 8, stop bit: 1, Parity: No parity
- Default PINCODE:”0000”
- A full set of configuration commands
- On board PCB antenna
- FCC ID certificated

## Application Idea
----------------

1\. Communicate with two Bluetooth Shield.   
2\. Use your Android phone to control the Arduino car.  
3\. Communicate with your computer.  

## Specification
-------------

| **Items** | **Min** | **Typical** | **Max** | **Unit** |
|:-:|:-:|:-:|:-:|:-:|
| Voltage | 2.8 | 3.3 | 3.5 | v |
| Current | 3 | / | 100 | mA |
| Communication Distance(in house) | / | / | 10 | m |
| Protocol | Bluetooth V2.0 with SPP firmware | / |
| Interface | Uart Serial Port(TTL) | / |
| Supported Baudrate | 9600, 19200, 38400, 57600, 115200, 230400, 460800 | bps |
| ESD contact discharge | ±4 | KV |
| ESD air discharge | ±8 | / |
| Dimensions | 47.3(L)x55.0(W)x23.5(H) | mm |
| Net Weight |  | g |

## Interface
---------

![Interface of bluetooth Shield.png](https://wiki.elecrow.com/images/thumb/9/93/Interface_of_bluetooth_Shield.png/600px-Interface_of_bluetooth_Shield.png){ loading=lazy }

## Usage
-----

### **Communicating between two Bluetooth Shield**

![Upload1.jpg](https://wiki.elecrow.com/images/thumb/f/f1/Upload1.jpg/600px-Upload1.jpg){ loading=lazy }
This demo will show you how to communicate between two Arduino/Crowduino through Bluetooth Shield.For the special applications, you may need to write the code by yourself.

- Download the [Arduino Library](http://www.elecrow.com/wiki/images/c/c9/Bluetooth_Demo_Code.zip) for the shield, and unzip it into the path of Arduino Libraries. This library includes two sketch, one for Master and the other for Slave. Make sure [Software Serial Library](http://www.elecrow.com/wiki/images/d/d3/SoftwareSerial.zip) is included as well.

![Upload2.jpg](https://wiki.elecrow.com/images/thumb/a/ab/Upload2.jpg/450px-Upload2.jpg){ loading=lazy }

- Upload the sketch Master.ino and Slave.ino to two separate Arduino/Crowduino.
- Open two [Serial Terminals](http://www.elecrow.com/wiki/images/b/b2/Sscom32E.zip) on your PC, with the setting of 38400, 8, 1, N. Open the two Com Port of Arduino/Crowduino.
- Plug the Bluetooth Shields to the Master board and the Slave Board, and reset the two boards.

Then you will see the red and green LED on the board are flashing in interval indicting they are inquiring for each other. After a while only the green led is flashing one time per second indicating that they are connected. There's also some information printed on the two terminal as following.

![Upload3.png](https://wiki.elecrow.com/images/7/7d/Upload3.png){ loading=lazy }

- The connection is successful now, and you can type any character on the Serial Terminal and send to each .

### **Connecting Bluetooth Shield to Android Phone**

![BtAndroid.jpg](https://wiki.elecrow.com/images/8/85/BtAndroid.jpg){ loading=lazy }

This demo will show you how to connect Bluetooth Shield to Android Phone. Here we test on HTC Legend with Android 2.2.For the special applications, you may need to write the code by yourself.

- Download the [Arduino Library](http://www.elecrow.com/wiki/images/c/c9/Bluetooth_Demo_Code.zip) for the shield, and unzip it into the path of Arduino Libraries. This library includes two sketch, one for Master and the other for Salve. Make sure [Serial Library](http://www.elecrow.com/wiki/images/d/d3/SoftwareSerial.zip) is included as well.
- Plug the Bluetooth Shield onto the Arduino/Crowduino, and upload the Slave.ino to the board.Open the Serial Terminal with setting of 9600, 8, 1, N.

![Sscom.png](https://wiki.elecrow.com/images/5/5c/Sscom.png){ loading=lazy }

- Download an Serial Terminal for Android to the phone. Install the apk(Bluetooth SPP).

- Enable the bluetooth function and scan for devices. You will find the CrowBTSlave device.

- Select and pair with the "CrowBTSlave", input the PIN code **0000**, choose OK.


![PutPIN.jpg](https://wiki.elecrow.com/images/thumb/0/07/PutPIN.jpg/300px-PutPIN.jpg){ loading=lazy }

- Now let's open the Bluetooth SPP on Android. It illustrates Press \[search\] key to find Bluetooth-enabled device.and there will be a list of devices found shown the phone.

- Select "CrowBTSlave", and press connect key, wait a second, the connection will be established. And you can receive and send any character through this terminal.

![send](https://wiki.elecrow.com/images/9/9a/Send2bt.png){ loading=lazy } 
![receive](https://wiki.elecrow.com/images/thumb/e/ec/Receive.jpg/250px-Receive.jpg){ loading=lazy }

- <font color="red">Notice:you can also send data to your phone.</font>

## Resource
--------

- [Schematic in PDF](http://www.elecrow.com/wiki/images/e/e7/ELE_BlueTooth_Shield_v1.02.pdf)
- [SoftwareSerial library](../../files/SoftwareSerial-zip.md)
- [Bluetooth - module Datasheet](http://www.elecrow.com/download/Bluetooth_module.pdf)
- [Bluetooth Software instruction](http://www.elecrow.com/download/Bluetooth_Software_Instruction.pdf)

## How to buy
----------

You can visit [here to purchase it](https://www.elecrow.com/bluetooth-shield-masterslave-p-332.html).