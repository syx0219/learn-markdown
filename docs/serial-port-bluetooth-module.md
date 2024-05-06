---
title: Serial Port Bluetooth Module
---

## Introduction
------------

This module is an easy to use Bluetooth SPP (Serial Port Protocol) module, designed for transparent wireless serial connections.

The Serial port Bluetooth module is fully qualified Bluetooth V2.0+EDR (Enhanced Data Rate) 3Mbps Modulation with complete 2.4GHz radio transceiver and baseband. It uses CSR Bluecore 04-External single chip Bluetooth system with CMOS technology and with AFH(Adaptive Frequency Hopping Feature). It has a footprint as small as 12.7mmx27mm. Hopefully it will simplify your overall design/development cycle.

**Model: [WBT20101B](http://www.elecrow.com/wireless-c-78/misc-c-78_123/serial-port-bluetooth-module-masterslave-p-375.html)**  
![Serial Port Bluetooth Module2.jpg](https://wiki.elecrow.com/images/thumb/4/49/Serial_Port_Bluetooth_Module2.jpg/400px-Serial_Port_Bluetooth_Module2.jpg){ loading=lazy }

## Features
--------

### **Hardware features**

- Typical -80dBm sensitivity
- Up to +4dBm RF transmit power
- Low Power 1.8V Operation ,1.8 to 3.6V I/O
- PIO control
- UART interface with programmable baud rate
- Integrated antenna
- Edge connector

### **Software features**

- Default Baud rate: 38400, Data bits:8, Stop bit:1,Parity:No parity, Data control: yes. Supported baud rate:

9600,19200,38400,57600,115200,230400,460800.

- Use CTS and RTS to control data stream.
- Given a rising pulse in PIO0, device will be disconnected.
- Status instruction port PIO1: low-disconnected, high-connected;
- PIO10 and PIO11 can be connected to red and blue LED separately. When master and slave are paired, red

and blue led blinks 1time/2s in interval. While disconnected only blue led blinks 2times/s.

- Auto-connects to the last device on power as default.
- Permits pairing device to connect as default.
- Auto-pairing PINCODE:”0000” as default
- Auto-reconnect in 30 min when disconnected as a result of beyond the range of connection.

## Application Ideas
-----------------

- Remote controller
- Wireless communication

## Cautions
--------

- <font color="red">While using with Crowduino/ Arduino, set the operation voltage to 5V. Else use a proper logic level converter.</font>
- <font color="red">While using with USBSerial Adapter, set the operation voltage to 5V</font>
- <font color="red">Command to change baud rate is persistent even after reset. Hence remember the baud rate for next use.</font>

## Specification
-------------

| Pin | \# | Pad Type | Description |
|---|---|---|---|
| PIO11 | 34 | Bi-Direction | Programmable input/output line |
| PIO10 | 33 | Bi-Direction | Programmable input/output line |
| PIO9 | 32 | Bi-Direction | Programmable input/output line |
| PIO8 | 31 | Bi-Direction | Programmable input/output line |
| PIO7 | 30 | Bi-Direction | Programmable input/output line |
| PIO6 | 29 | Bi-Direction | Programmable input/output line |
| PIO5 | 28 | Bi-Direction | Programmable input/output line |
| PIO4 | 27 | Bi-Direction | Programmable input/output line |
| PIO3 | 26 | Bi-Direction | Programmable input/output line |
| PIO32 | 25 | Bi-Direction | Programmable input/output line |
| PIO1 | 24 | Bi-Direction TX EN | Programmable input/output line, control output for PA(if fitted) |
| PIO0 | 23 | Bi-Direction RX EN | Programmable input/output line, control output for LNA(if fitted) |
| GND | 13,21,22 | VSS | Ground pot |
| USB± | 15,20 | Bi-Directional |  |
| SPI\_CLK | 19 | CMOS input with weak internal pull-down | Serial peripheral interface clock |
| SPI\_MISO | 18 | CMOS input with weak internal pull-down | Serial peripheral interface data Output |
| SPI\_MOSI | 17 | CMOS input with weak internal pull-down | Serial peripheral interface data input |
| SPI\_CSB | 16 | CMOS input with weak internal pull-up | Chip select for serial peripheral interface,active low |
| NC | 14 |  |  |
| 3.3VCC | 12 | 3.3V | Integrated 3.3V(+)supply with on-chip linear regulator output within 3.15-3.3V |
| RESETB | 11 | CMOS input with weak internal pull-up | Reset if low. input debouncde so must be low for&gt;5MS to cause a reset |
| AIO1 | 10 | Bi-Direction | Programmable input/output line |
| AIO0 | 9 | Bi-Direction | Programmable input/output line |
| PCM\_SYNC | 8 | Bi-Direction | Synchronous PCM data strobe |
| PCM\_IN | 7 | CMOS Input | Synchronous PCM data input |
| PCM\_OUT | 6 | CMOS output | Synchronous PCM data output |
| PCM\_CLK | 5 | Bi-Direction | Synchronous PCM data clock |
| UART\_RTS | 4 | CMOS output tri-stable with weak internal pull-up | UART request to send, active low |
| UART\_CTS | 3 | CMOS input with weak internal pull-down | UART Data input |
| UART\_RX | 2 | CMOS output,tri-stable with weak internal pull-down | UART Data input |
| UART\_TX | 1 | CMOS output,tri-stable with weak internal pull-up | UART Data output |

## Software Instruction
--------------------

#### **Working Sketch Map**


#### **Flowchat**


#### **Commands to change default configuration**

**1. Set working MODE**

| \\r\\n+STWMOD=0\\r\\n | Set device working mode as client (slave). Save and Rest. |
|---|---|
| \\r\\n+STWMOD=1\\r\\n | Set device working mode as server (master). Save and Rest. |

**Note:** **\\r\\n** is necessary for operation and the value of are **0x0D 0x0A** in Hex. **\\r** and **\\n** represent **carriage-return** and **line-feed**(or next line),

**2.Set BAUDRATE**

| \\r\\n+STBD=115200\\r\\n | Set baudrate 115200. Save and Rest. |
|---|---|
| Supported baudrate: 9600, 19200,38400,57600,115200,230400,460800. |

**3. Set Device NAME**

<table>
    <tbody>
        <tr>
            <td width="200px">\r\n+STNA=abcdefg</td>
            <td width="400px">Set device name as “abcdefg”. Save and Rest.</td>
        </tr>
    </tbody>
</table>

**4. Auto-connect the last paired device on power**

| \\r\\n+STAUTO=0\\r\\n | Auto-connect forbidden. Save and Rest. |
|---|---|
| \\r\\n+STAUTO=1\\r\\n | Permit Auto-connect. Save and Rest. |

**5. Permit Paired device to connect me**

| \\r\\n+STOAUT=0\\r\\n | Forbidden. Save and Rest. |
|---|---|
| \\r\\n+STOAUT=1\\r\\n | Permit. Save and Rest. |

**6. Set PINCODE**

<table>
    <tbody>
        <tr>
            <td width="200px">\r\n +STPIN=2222\r\n</td>
            <td width="400px">Set pincode “2222”, Save and Rest.</td>
        </tr>
    </tbody>
</table>

**7. Delete PINCODE(input PINCODE by MCU)**

<table>
    <tbody>
        <tr>
            <td width="200px">\r\n+DLPIN\r\n</td>
            <td width="400px">Delete pincode. Save and Rest.</td>
        </tr>
    </tbody>
</table>

**8. Read local ADDRESS CODE**

<table>
    <tbody>
        <tr>
            <td width="200px">\r\n+RTADDR\r\n</td>
            <td width="400px">Return address of the device.</td>
        </tr>
    </tbody>
</table>

**9. Auto-reconnecting when master device is beyond the valid range (slave device will auto-reconnect in 30 min when it is beyond the valid range)**

| \\r\\n+LOSSRECONN=0\\r\\n | Forbid auto-reconnecting. |
|---|---|
| \\r\\n+LOSSRECONN=1\\r\\n | Permit auto-reconnecting. |

#### **Commands for Normal Operation:**

**1. Inquire**

| **a) Master** |
|---|
| \\r\\n+INQ=0\\r\\n | Stop Inquiring |
| \\r\\n+INQ=1\\r\\n | Begin/Restart Inquiring |
| **b) Slave** |
| \\r\\n+INQ=0\\r\\n | Disable been inquired |
| \\r\\n+INQ=1\\r\\n | Enable been inquired |

When **+INQ=1** command is successful, the <font color="red">red</font>  and <font color="green">green</font> LEDS blink alternatively.

**2. Bluetooth module returns inquiring result**

<table>
    <tbody>
        <tr>
            <td width="200px">\r\n+RTINQ=aa,bb,cc,dd,ee,ff;name\r\n</td>
            <td width="400px">Serial Bluetooth device with the address “aa,bb,cc,dd,ee,ff” and the name “name” is inquired</td>
        </tr>
    </tbody>
</table>

**3. Connect device**

<table>
    <tbody>
        <tr>
            <td width="200px">\r\n+CONN=aa,bb,cc,dd,ee,ff\r\n</td>
            <td width="400px">Connect to a device with address of "aa,bb,cc,dd,ee,ff”</td>
        </tr>
    </tbody>
</table>

**4. Bluetooth module requests inputting PINCODE**

\\r\\n+INPIN\\r\\n

**5. Input PINCODE**

| \\r\\n+RTPIN=code\\r\\n |
|---|
| Example: RTPIN=0000 | Input PINCODE which is four zero |

**6. Disconnect device** Pulling PIO0 high will disconnect current working Bluetooth device.

**7. Return status** \\r\\n+BTSTA:**xx**\\r\\n 
 **xx** status:

- 0 - Initializing
- 1 - Ready
- 2 - Inquiring
- 3 - Connecting
- 4 - Connected

(**Note:** This is not a command, but the information returned from the module after every command)

## Reference
---------

[How to Connect to Mac Laptop](http://elasticsheep.com/2011/05/serial-bluetooth-module-slave-test/)
File:User Guide step by step.pdf
File:Demo Code for Master&amp;Slave.zip