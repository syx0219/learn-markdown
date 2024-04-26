---
title: Crowtail- LoRa RA-08H
---

## Description
-----------

Crowtail - LoRa RA-08H uses the Ra-08H (ASR6601) module, which has ultra long distance spread spectrum communication. Its chip ASR6601 is a general-purpose LPWAN wireless communication SoC integrated with RF transceiver, modem and a 32-bit RISC MCU. The Ra-08H module supports LoRa modulation and traditional (G) FSK modulation under the LPWAN use case; The transmitter also supports BPSK modulation and (G) MSK modulation.
The Ra-08H module provides ultra long range and ultra-low power consumption communication for LPWAN applications, and can be widely used in intelligent instruments, supply chain and logistics, home building automation, security systems, remote irrigation systems and other scenarios.

**Model: [CRT01158H](https://www.elecrow.com/crowtail-lora-ra-08h-for-long-range-application-803-930mhz.html)**  
![Crt01158h-crowtail-lora-ra-08h-05.jpg](https://wiki.elecrow.com/images/thumb/f/f1/Crt01158h-crowtail-lora-ra-08h-05.jpg/500px-Crt01158h-crowtail-lora-ra-08h-05.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png)](https://www.elecrow.com/crowtail-lora-ra-08h-for-long-range-application-803-930mhz.html?wiki "Title text")

## Specifications
--------------

- Voltage: 3.3~5V
- Theoretical maximum transmission power+22dBm
- Supported frequency band: 803~930MHZ
- High sensitivity: -138dBm@125KzSF12
- Support spread spectrum factor: SF5/SF6/SF7/SF8/SF9/SF10/SF11/SF12
- Embedded memory: 128KB FLASH, 16KB SRAM
- Support LoRa/(G) FSK/BPSK/(G) MSK modulation
- Maximum transmission distance 1KM (ideal value for open space)
- With download and communication switching functions, users can customize programming
- Equiped with the first generation IPEX seat
- Dimension (mm): 40 (L) \* 20 (W) \* 7.5 (H)

## Schematic
---------

![RA-08H.png](https://wiki.elecrow.com/images/2/24/RA-08H.png){ loading=lazy }

## Usage
-----

### Hardware Connection

STEP1 Prepare the below stuffs:  

| **Crowduino Uno**                                            | **Base Shield**                                              | **Crowtail- LoRa RA-08H**                                    |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| [![Crowduino 2.jpg](https://wiki.elecrow.com/images/thumb/d/d4/Crowduino_2.jpg/300px-Crowduino_2.jpg)](https://wiki.elecrow.com/index.php?title=File:Crowduino_2.jpg) | [![Crowtail-base shield 2.jpg](https://wiki.elecrow.com/images/thumb/c/cb/Crowtail-base_shield_2.jpg/200px-Crowtail-base_shield_2.jpg)](https://wiki.elecrow.com/index.php?title=File:Crowtail-base_shield_2.jpg) | [![Crt01158h-crowtail-lora-ra-08h-05.jpg](https://wiki.elecrow.com/images/thumb/f/f1/Crt01158h-crowtail-lora-ra-08h-05.jpg/300px-Crt01158h-crowtail-lora-ra-08h-05.jpg)](https://wiki.elecrow.com/index.php?title=File:Crt01158h-crowtail-lora-ra-08h-05.jpg) |
| [**Get one now**](https://www.elecrow.com/crowduino-unosd-v15-p-840.html) | [**Get one now**](https://www.elecrow.com/crowtail-base-shield-p-1264.html) | [**Get one now**](https://www.elecrow.com/crowtail-lora-ra-08h-for-long-range-application-803-930mhz.html) |

STEP2 Plug Crowtail-Base Shield into Crowduino Uno;  
STEP3 Plug Crowtail-LoRa RA-08H to D2 D3 slot of Crowtail-Base Shield via 4 pin Crowtail Cable;  
STEP4 Connect Crowduino Uno to PC via a Mini USB cable.  
![RA-08H-connection.png](https://wiki.elecrow.com/images/thumb/e/e2/RA-08H-connection.png/500px-RA-08H-connection.png){ loading=lazy }  

| ==**NOTE**== |  
|---|  
| ==If we don't have Crowtail Base Shield, We also can directly connect this module to Crowduino Uno as below.== |

| **Crowduino Uno** | **Crowtail- LoRa RA-08H** |
|:-:|:-:|
| D2 | TX |
| D3 | RX |
| 3.3V | VCC |
| GND | GND |

### Software

STEP1 Configure controller board&amp;communication port  
On top of the Arduino IDE, click “Tools&gt;Board&gt;” and select “Arduino Uno” from the available options  
![SELECT BOARD.png](https://wiki.elecrow.com/images/thumb/c/c5/SELECT_BOARD.png/700px-SELECT_BOARD.png){ loading=lazy }  
STEP2 Select the COM port that indicates Arduino Uno. Please note that the actual numbers after the “COM” word will vary from computer to computer, so they could be different from the ones shown in the figure.  
![S 2 2.png](https://wiki.elecrow.com/images/thumb/d/d5/S_2_2.png/600px-S_2_2.png){ loading=lazy }  
STEP3 Open the program in the Arduino IDE  
```
#include <SoftwareSerial.h> 
// Pin2接LORA的TXD
// Pin3接LORA的RXD
SoftwareSerial LORA(2, 3); 
char val;
 
void setup() {
  Serial.begin(9600); 
  Serial.println("LORA is ready!");
  LORA.begin(9600);
}
 
void loop() {
  if (Serial.available()) {
    val = Serial.read();
    LORA.print(val);
    delay(10);
  }
 
  if (LORA.available()) {
    val = LORA.read();
    Serial.print(val);
    delay(10);
  }
}
```

STEP4 Click the ![Upload.png](../../assets/images/30px-Upload.png){ loading=lazy } to upload the code to the Crowduino board  
STEP5 Open the AT command description of Ra-08H, find the relevant command, open the serial port monitor, and input the command into the serial port monitor, for example, enter \[AT+CGSN?\] Command, click Send, and the reply code will be received:+CGSN=1E612A8482213201  
OK  
![RA-08H-1.png](https://wiki.elecrow.com/images/2/20/RA-08H-1.png){ loading=lazy }  
![RA-08H-2.png](https://wiki.elecrow.com/images/a/a1/RA-08H-2.png){ loading=lazy }  

**Update firmware**

 **Hardware preparation**  
 1. Prepare the serial port board and connect it to the computer through USB  
 ![RA08H firmwareupdate1.png](https://wiki.elecrow.com/images/thumb/3/3f/RA08H_firmwareupdate1.png/400px-RA08H_firmwareupdate1.png){ loading=lazy }  
 2. Switch RA-08H module to BOOT end:  
 ![RA08H firmwareupdate2.png](https://wiki.elecrow.com/images/thumb/5/54/RA08H_firmwareupdate2.png/300px-RA08H_firmwareupdate2.png){ loading=lazy }     
 ![RA08H firmwareupdate3.png](https://wiki.elecrow.com/images/thumb/d/d8/RA08H_firmwareupdate3.png/200px-RA08H_firmwareupdate3.png){ loading=lazy }    
 3. Press and hold the BOOT button, insert the HY2.0-4P male connector, and power on to enter the burning mode  
 ![RA08H firmwareupdate4.png](https://wiki.elecrow.com/images/thumb/b/be/RA08H_firmwareupdate4.png/400px-RA08H_firmwareupdate4.png){ loading=lazy }

 **Firmware upgrade**  
 1. Open "TremoProgrammer\_v0.8" in "firmware\_update\_tool" folder.  
 ![RA08H firmwareupdate5.png](https://wiki.elecrow.com/images/b/b4/RA08H_firmwareupdate5.png){ loading=lazy }  
 2. Select the corresponding serial port number, and use the default 921600 baud rate.  
 ![RA08H firmwareupdate7.png](https://wiki.elecrow.com/images/8/8f/RA08H_firmwareupdate7.png){ loading=lazy }  
 3. Select the firmware file to be upgraded.
 ![RA08H firmwareupdate12.png](https://wiki.elecrow.com/images/9/95/RA08H_firmwareupdate12.png){ loading=lazy }  
 4. After selecting the firmware, click the start button to start the upgrade  
 ![RA08H firmwareupdate10.png](https://wiki.elecrow.com/images/b/b5/RA08H_firmwareupdate10.png){ loading=lazy }  
 5. Upgrade completed  
 ![RA08H firmwareupdate11.png](https://wiki.elecrow.com/images/0/02/RA08H_firmwareupdate11.png){ loading=lazy }  

## FAQS
----

You can post your questions on our [forum](https://forum.elecrow.com/) or contact with techsupport@elecrow.com for technology support.

## Resources
---------

[Crowtail-\_LoRa\_RA-08H-V1.2-eagle\_file.zip ](https://wiki.elecrow.com/images/1/1b/Crowtail-_LoRa_RA-08H-V1.2-eagle_file.zip)  
[Lora\_code.zip](https://wiki.elecrow.com/images/1/16/Lora.zip)  
[Ra-08h\_v1.1.0\_specification.pdf](https://wiki.elecrow.com/images/1/1b/Ra-08h_v1.1.0_specification.pdf)  
[RA-08\_AT\_Instruction.pdf](https://wiki.elecrow.com/images/e/e1/RA-08_AT_Instruction.pdf)  
[firmware](https://wiki.elecrow.com/images/2/23/Lorawan-at-eu868-v1.3.4.zip)  