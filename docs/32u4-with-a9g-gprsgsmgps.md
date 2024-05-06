---
title: 32u4 with A9G GPRS/GSM/GPS
---

## Introduction
------------

The 32U4 with A9 GPRS/GSM/GPS Board is based on Mega32U4 and A9 GPRS/GSM/GPS module. It can be used to make a call, send text messages and get GPS positioning. Also it has one analog interface, one IIC interface and two digital interface, which you can connect to other expansion modules. It is very easy for you to make a GPS Tracker by using this board. It is also very easy to use AT firmware and use several AT commands can be configured successfully.

**Model: [AMC01219U](https://www.elecrow.com/32u4-with-a9g-gprs-gsm-gps-board.html)**

![A9G 1.jpg](https://wiki.elecrow.com/images/thumb/4/49/A9G_1.jpg/600px-A9G_1.jpg){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/32u4-with-a9g-gprs-gsm-gps-board.html?wiki "Title text")

## Features
--------

- ATMEGA32U4+A9G.
- Work voltage: 3.3V to 5V.
- Operating temperature： -30 ℃ to + 80 ℃.
- Three kinds of interface.
- Equipped with 3.5mm headphone jack.
- 3.7V Battery power supply.
- Standby average current 3ma or less.
- Support the GSM / GPRS/ GPS Quad-band, including 850,900,1800,1900MHZ.
- Support China Mobile and China Unicom's 2G GSM network worldwide.
- GPRS Class 10.
- Sensitivity &lt; -105.
- Support GPS Positioning.
- Support for voice calls.
- Support for SMS text messaging.
- Support GPRS data business, the maximum data rate: download 85.6Kbps, upload 42.8Kbps.
- Supports standard GSM07.07, 07.05 AT commands and Ai-Thinker extended commands.
- Supports two serial ports, a serial port to download an AT command port.
- Support for Global Positioning System.
- Horizontal positioning accuracy of less than 2.5m.
- AT command supports the standard AT and TCP / IP command interface.
- Support digital audio and analog audio support for HR, FR, EFR, AMR speech coding.
- Support ROHS, FCC, CE, CTA certification.

## Pin Definitions
---------------

![A9g pin.jpg](https://wiki.elecrow.com/images/8/86/A9g_pin.jpg){ loading=lazy }

## Specifications
--------------

- The size of A9G: 19.2\*18.8\*3mm
- Quad-band: 850/900/1800/1900 MHz.
- GPRS multi-slot: 12, 1 to 12 can be configured.
- GPRS mobile station: Class B.
- Compatible with GSM Phase 2/2 +: Class 4 (2W @ 850/900 MHz) Class 1 (1W @ 1800 / 1900MHz).
- Current consumption: 1.3mA @ DRX = 5; 1.2mA @ DRX = 9.
- AT command control: Standard GSM07.07, 07.05 AT commands and Ai-Thinker extended commands.
- SIM Application Toolkit.
- GPRS Class 10: Up 85.6 kbps (upstream) &amp; 42.8Kbps (downlink).
- Dynamic Conditions Altitude &lt;18,000 meters (60,000 feet).
- Speed &lt;515 m / s (1000 nautical miles), acceleration &lt;4 g.
- PBCCH support.
- Coding scheme: CS 1, 2, 3, 4.
- Support CSD: Up 14.4 kbps.
- Support USSD.
- Stack: PPP / TCP / UDP / HTTP / FTP / SMTP / MUX

## Cautions
--------

- Make sure your SIM card is locked.
- This product is supplied as is, without an insulated housing. In high humidity weather, pay special attention to ESD precautions.
- It just supports baud rate 115200bps.

## Interface Function
------------------

<img loading="lazy" src="https://wiki.elecrow.com/images/thumb/d/d4/A9G_2.jpg/400px-A9G_2.jpg" alt="A9G 2.jpg" style="zoom:90%;"/>
<img loading="lazy" src="https://wiki.elecrow.com/images/thumb/a/aa/A9G_3.jpg/400px-A9G_3.jpg" alt="A9G 3.jpg" style="zoom:90%;"/>

## Usage
-----

### **1.Connect**

Let's start a simple test.

1\. Install the antenna.

Two miniature coaxial RF connector is present on the back of the 32U4 with A9G GPRS/GSM/GPS Board to connect with a GSM antenna or a GPS antenna . The connector present on the 32U4 with A9G GPRS/GSM/GPS is called a U.FL connector.The GSM Antenna supplied with the GPRS Shield has an SMA connector (and not an RP-SMA connector) on it.The connection topology is shown in the diagram below:

<img loading="lazy" src="https://wiki.elecrow.com/images/d/d0/A9G_4.jpg" alt="A9G 4.jpg" style="zoom:90%;"/>
<img loading="lazy" src="https://wiki.elecrow.com/images/b/b9/A9G_5.jpg" alt="A9G 5.jpg" style="zoom:90%;"/>

2\. Insert the Micro SIM card into the SIM card holder.

There is a SIM card holder on the back of the board. Both 1.8 volts and 3.0 volts SIM Cards are supported by this board, the SIM card voltage type is automatically detected.  
![A9G 5-1.jpg](https://wiki.elecrow.com/images/thumb/f/f6/A9G_5-1.jpg/400px-A9G_5-1.jpg){ loading=lazy }

3\. Connect the battery.

Because the PC USB port output current is not enough，so you should connedct an 3.7V lithium battery to the battery port.

![A9G 6.jpg](https://wiki.elecrow.com/images/thumb/8/8b/A9G_6.jpg/400px-A9G_6.jpg){ loading=lazy }

4\. Upload the code

Open your Arduino IDE, choose the file, choose the Arduino Leonardo Board.

You can refer to this test code and upload it to your board: **[32U4\_with\_A9\_test](./files/32U4-with-A9-test-zip.md)**

5.Then open the SSCOM32. Please configure it as follows:

![A9G 7.jpg](https://wiki.elecrow.com/images/thumb/a/ad/A9G_7.jpg/400px-A9G_7.jpg){ loading=lazy }

6.Now, you can use some AT commands to control the 32u4 with A9G GPRS/GSM/GPS.

## Resource
--------

[32U4 with A9 eagle file](./files/32U4-with-A9-eagle-files-zip.md)

[32u4\_with\_A9G\_GPS\_test\_step.pdf](./files/32u4-with-A9G-GPS-test-step-pdf.md)

**[32U4\_with\_A9\_test](./files/32U4-with-A9-test-zip.md)**

[serial port tool SSCOM](./files/Sscom1-zip.md)