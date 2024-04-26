---
title: Crowtail- 4G SIM-A7670E
---

## Description
-----------

This Crowtail series 4G module is a high-performance LTE Cat1 wireless module. It uses the SIM A7670E communication module from Simcom and communicates through a UART interface, which enables 4G data transmission and voice communication. The module supports multiple LTE bands, including B1/B3/B5/B7/B8/B20, as well as WCDMA and GSM networks. In addition, it supports various protocols such as TCP/IP, FTP, HTTP, and multiple satellite navigation systems such as GPS, GLONASS, and BDS.

The module comes with a charging interface and can be powered by a 3.7V lithium battery or a 5V type-C interface. It also has a 3.5mm headphone jack, and by connecting a headphone with a microphone, it can be used for making and receiving phone calls. Its compact size makes it easy to integrate into various IoT devices and meet various application requirements. Furthermore, its low power consumption and reliable performance are also the reasons why it is widely used in IoT, smart home, automotive, and industrial control fields.

When paired with our expansion board (Crowtail base shield for Raspberry Pi or Crowtail base shield for Arduino), it can quickly build 4G-related projects with Arduino or Raspberry Pi boards.

**Model: [CRT01260S](https://www.elecrow.com/crowtail-sim-a7670e-4g-module-gps-breakout-board-support-gps-glonass-bds.html)**

![Crowtail 4G SIM-A7670E main.png](https://wiki.elecrow.com/images/thumb/5/5e/Crowtail_4G_SIM-A7670E_main.png/600px-Crowtail_4G_SIM-A7670E_main.png){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png)](https://www.elecrow.com/crowtail-sim-a7670e-4g-module-gps-breakout-board-support-gps-glonass-bds.html?wiki "Title text")

## Features
--------

- Integrate the A7670E communication module, enabling 4G data transmission and voice communication with low power consumption and high reliability
- Supports multiple LTE bands, including B1/B3/B5/B7/B8/B20, as well as WCDMA and GSM networks
- Supports various protocols such as TCP/IP, FTP, HTTP, and multiple satellite navigation systems such as GPS, GLONASS, and BDS
- Comes with a charging interface and a headphone jack, which can be used for making and receiving phone calls by connecting a headphone with a microphone
- Small but powerful, compact size makes it easy to integrate into various IoT devices.

## Technical Specifications
------------------------

- Mainchip: SIM A7670E
- LTE-FDD: B1/B3/B5/B7/B8/B20
- GSM: 900/1800MHz
- GSM/GPRS power class:

EGSM900: 4 (33dBm±2dB)
DCS1800: 1 (30dBm±2dB)

- EDGE power class:

EGSM900: E2 (27dBm±3dB)
DCS1800 : E1 (26dBm+3dB/-4dB)

- LTE power class: 3 (23dBm±7dB)
- Supply Voltage: 4V~ 4.2V
- Power: 3.8V
- LTE(Mbps): 10(DL)/5(UL)
- GPRS/EDGE(Kbps): 236.8(DL)/236.8(UL)
- Protocol: TCP/IP/IPV4/IPV6/Multi-PDP/FTP/FTPS /HTTP/HTTPS/DNS
- Communication interface: USB / UART
- Firmware Upgrade: USB/FOTA
- Support phonebook types: SM/FD/ON/AP/SDN
- Interface: 1x Power button, 1x BAT, 1x UART, 1X Type-C, 1x SIM Card slot
- Size:35\*50mm
- Net Weight: 19.5g

## Interface Function
------------------

![Lora RA-08H Node PCB 1.png](https://wiki.elecrow.com/images/thumb/9/9d/Lora_RA-08H_Node_PCB_1.png/484px-Lora_RA-08H_Node_PCB_1.png){ loading=lazy }
![Lora RA-08H Node PCB 2.png](https://wiki.elecrow.com/images/thumb/1/11/Lora_RA-08H_Node_PCB_2.png/484px-Lora_RA-08H_Node_PCB_2.png){ loading=lazy }

| **Name** | **Interface/Function Definition** |
|:-:|:-:|
| USB-C | USB-C interface, used for the power supply of the development board and the communication interface between the PC and the development board. |
| UART | None |
| BAT | Battery charging interface |
| POWER | Power button. It needs to be pressed for 1 second to let the development board enter the working state. |
| SIM Card Slot | None |
| 4G ANT | None |
| GNSS ANT | None |

## Usage
-----

### **Crowtail\_4G SIM-A7670E driver installation**

1\. Connect Crowtail 4G SIM-A7670E to the computer, and press and hold the onboard power button for 1 second. After the network indicator lights up, open the device manager and check whether the driver of Crowtail\_4G SIM-A7670E is installed.  
![Crowtail 4G SIM-A7670E 2 1.png](https://wiki.elecrow.com/images/thumb/9/9b/Crowtail_4G_SIM-A7670E_2_1.png/440px-Crowtail_4G_SIM-A7670E_2_1.png){ loading=lazy }

2\. If the driver is successfully installed, three ports with different port numbers will be displayed respectively.  
![Crowtail 4G SIM-A7670E 3.png](https://wiki.elecrow.com/images/e/eb/Crowtail_4G_SIM-A7670E_3.png){ loading=lazy }

3\. If the driver is not installed, it will be displayed in the "Other Devices" column. Here you need to update the driver for each device. For the driver, see "...\\Crowtail \_4G SIM-A7670E-Windows-Driver-USB\\Windows\\..." (need to install the corresponding driver according to the computer version).  
![Crowtail 4G SIM-A7670E 4.png](https://wiki.elecrow.com/images/3/38/Crowtail_4G_SIM-A7670E_4.png){ loading=lazy }

### **Connect to the Mobile Network**

1\. Insert the SIM card into the SIM card slot according to the silk screen instructions on the Crowtail\_4G SIM-A7670E.

2\. Wait for 5 seconds, if the network indicator starts to flash at a frequency of 0.5 seconds/time, it means that it is connected to the mobile network, otherwise you need to check whether the SIM card is correctly inserted or connected.  
![Crowtail 4G SIM-A7670E 6 1.png](https://wiki.elecrow.com/images/4/4b/Crowtail_4G_SIM-A7670E_6_1.png){ loading=lazy }

### **Answer/Make Calls Test**

1\. Find the *sscom5.13.1.exe* software and double-click to open it.  
![Crowtail 4G SIM-A7670E 7.png](https://wiki.elecrow.com/images/e/e1/Crowtail_4G_SIM-A7670E_7.png){ loading=lazy }

2\. Select the port number. If you are not sure whether the port number is correct, you can enter the "AT" command in the sending area and send it. If the serial port returns OK, it means that the currently selected port number is correct; set the baud rate to 115200.  
![Crowtail 4G SIM-A7670E 8.png](https://wiki.elecrow.com/images/thumb/8/81/Crowtail_4G_SIM-A7670E_8.png/600px-Crowtail_4G_SIM-A7670E_8.png){ loading=lazy }

3\. Enter ATD+receiver's mobile phone number+";" (for example, ATD13660643260;) and send it to make a call; connect the headset and answer it, and check whether the call sound is clear. If there is no noise or intermittent sound, it means the function is normal.  
![Crowtail 4G SIM-A7670E 9.png](https://wiki.elecrow.com/images/thumb/e/e0/Crowtail_4G_SIM-A7670E_9.png/600px-Crowtail_4G_SIM-A7670E_9.png){ loading=lazy }

4\. When the mobile phone calls the Crowtail\_4G module, enter the "ATA" command and send it to answer the call.  
![Crowtail 4G SIM-A7670E 10.png](https://wiki.elecrow.com/images/thumb/2/2d/Crowtail_4G_SIM-A7670E_10.png/600px-Crowtail_4G_SIM-A7670E_10.png){ loading=lazy }

5\. If you find that the sound quality of the call is poor, or the call is intermittent, you need to check whether the 4G copper tube antenna is properly buckled in place.

### **Receive/Send Message Test**

1\. Click "Multiple Strings" on the toolbar to display the interface for sending multiple strings, and enter the following text information one by one in the string (double-click comment) column:

- AT+CMGF=1
- AT+CSCS="UCS2"
- AT+CSMP=17,167,0,8
- AT+CMGS="00310033003600350031003400340033003300370038"
- 4F60597D

![Crowtail 4G SIM-A7670E 11.png](https://wiki.elecrow.com/images/thumb/5/54/Crowtail_4G_SIM-A7670E_11.png/600px-Crowtail_4G_SIM-A7670E_11.png){ loading=lazy }

What needs special attention is that the content to be sent and the mobile phone number used to receive the information need to be converted into Unicode codes with a Unicode tool. Here we use the Unicode.exe software.  
![Crowtail 4G SIM-A7670E 12.png](https://wiki.elecrow.com/images/thumb/2/27/Crowtail_4G_SIM-A7670E_12.png/400px-Crowtail_4G_SIM-A7670E_12.png){ loading=lazy }

2\. Enter 1A and check the box in front of it, then check the "add carriage return and line feed" at the bottom, and click the "send" button on the right to send instructions one by one to complete the message sending.  
![Crowtail 4G SIM-A7670E 13.png](https://wiki.elecrow.com/images/thumb/d/dd/Crowtail_4G_SIM-A7670E_13.png/600px-Crowtail_4G_SIM-A7670E_13.png){ loading=lazy }

3\. The operation method of receiving information is also the same, input AT+CMGF=1, AT+CSCS="GSM", "AT+CNMI=2,1" and AT+CMGR=21.  
![Crowtail 4G SIM-A7670E 14.png](https://wiki.elecrow.com/images/thumb/a/aa/Crowtail_4G_SIM-A7670E_14.png/600px-Crowtail_4G_SIM-A7670E_14.png){ loading=lazy }

It is important to note that when the Crowtail\_4G module receives information, it will display "data" in the software window area. Here you need to change the number in AT+CMGR=21 to the number of the received information.  
![Crowtail 4G SIM-A7670E 15.png](https://wiki.elecrow.com/images/thumb/0/0d/Crowtail_4G_SIM-A7670E_15.png/400px-Crowtail_4G_SIM-A7670E_15.png){ loading=lazy }

4\. Send instructions in sequence to complete the information reading; if the window area can normally display the data composed of Unicode codes, it means that the information reading is successful.  
![Crowtail 4G SIM-A7670E 16.png](https://wiki.elecrow.com/images/thumb/f/fc/Crowtail_4G_SIM-A7670E_16.png/600px-Crowtail_4G_SIM-A7670E_16.png){ loading=lazy }

### **GPS Test**

1\. Find the SIMCom GPS DEMO V1.07.exe software and double-click to open it.  
![Crowtail 4G SIM-A7670E 17.png](https://wiki.elecrow.com/images/thumb/8/87/Crowtail_4G_SIM-A7670E_17.png/800px-Crowtail_4G_SIM-A7670E_17.png){ loading=lazy }


2\. After connecting the Crowtail\_4G module to the computer and pressing the power button to make the module work, open the device manager to see which ports are listed in the port column, and remember the port number of the ***SimTech HS-USB AT Port 9011*** port and the *'**SimTech HS-USB NMEA 9011***' port.


3\. Click the third icon "Setting Comport" below the toolbar to open the setting window; you can also click *"Module" &gt; "Properties..."* on the toolbar to open the setting window.    
![Crowtail 4G SIM-A7670E 20 1.png](https://wiki.elecrow.com/images/6/63/Crowtail_4G_SIM-A7670E_20_1.png){ loading=lazy }  
![Crowtail 4G SIM-A7670E 20 2.png](https://wiki.elecrow.com/images/7/7d/Crowtail_4G_SIM-A7670E_20_2.png){ loading=lazy }


4\. In the ComPort column, select SimTech HS-USB AT Port 9011 for NMEA COM; select 115200 for BaudRate, and finally click OK to complete the setting.  
![Crowtail 4G SIM-A7670E 21.png](https://wiki.elecrow.com/images/5/52/Crowtail_4G_SIM-A7670E_21.png){ loading=lazy }


5\. Enter the command "AT+CGNSSPWR=1" in the text box in the lower right corner of the software and click send to enable the GNSS function; enter the command "AT+CGNSSTST=1" and click send to receive location information. When Command send success is displayed below the text box, it means that the command is sent successfully.  
![Crowtail 4G SIM-A7670E 22 1.png](https://wiki.elecrow.com/images/e/e0/Crowtail_4G_SIM-A7670E_22_1.png){ loading=lazy }
![Crowtail 4G SIM-A7670E 22 2.png](https://wiki.elecrow.com/images/2/21/Crowtail_4G_SIM-A7670E_22_2.png){ loading=lazy }


6\. Open the setting window again, change the NMEA COM option to SimTech HS-USB NMEA 9011 port, and click OK to complete the setting.    
![Crowtail 4G SIM-A7670E 23.png](https://wiki.elecrow.com/images/4/41/Crowtail_4G_SIM-A7670E_23.png){ loading=lazy }


7\. Click the first icon *"Run Comport"* at the bottom of the toolbar to start receiving location information; at this time, move the Crowtail\_4G SIM-A7670E module and the computer to an open place or indoors with a satellite adapter.   
(If you use a desktop computer, try to choose a place as close to the outside as possible for testing)  
![Crowtail 4G SIM-A7670E 24.png](https://wiki.elecrow.com/images/8/85/Crowtail_4G_SIM-A7670E_24.png){ loading=lazy }


8\. If the satellite information received is as shown in the figure below, it means that the GPS function is qualified.    
![Crowtail 4G SIM-A7670E 25.png](https://wiki.elecrow.com/images/thumb/8/8c/Crowtail_4G_SIM-A7670E_25.png/800px-Crowtail_4G_SIM-A7670E_25.png){ loading=lazy }

### **Battery Charging Test**

As shown in the figure below, connect the lithium battery to the BAT port of the Crowtail\_4G module, and at the same time plug the USB end into a 5V power supply, and observe whether the charging indicator light is red. If the red light is normally on, it means that it is charging. Check whether the battery is correctly inserted into the BAT socket; the red light will turn off automatically after charging is completed.  
![Crowtail 4G SIM-A7670E 26 1.png](https://wiki.elecrow.com/images/thumb/6/61/Crowtail_4G_SIM-A7670E_26_1.png/300px-Crowtail_4G_SIM-A7670E_26_1.png){ loading=lazy }
![Crowtail 4G SIM-A7670E 26 2.png](https://wiki.elecrow.com/images/thumb/e/ea/Crowtail_4G_SIM-A7670E_26_2.png/300px-Crowtail_4G_SIM-A7670E_26_2.png){ loading=lazy }

## Resources
---------

- [Crowtail- 4G\_SIM-A7670E\_Arduino\_Code](https://wiki.elecrow.com/images/7/73/Arduino_Code_%284G%29.zip)
- [Crowtail\_4G\_SIM-A7670C\_V1.0-eagle\_file](https://wiki.elecrow.com/images/0/07/Crowtail_4G_SIM-A7670C_V1.0-eagle_file.zip)
- [A7600\_Series\_AT\_Command\_Manual\_V1.01.pdf](https://wiki.elecrow.com/images/d/dd/A7600_Series_AT_Command_Manual_V1.01.pdf)
- [Crowtail \_4G SIM-A7670C-Windows-Driver-USB](https://github.com/Elecrow-RD/Crowtail-_4G-SIM-A7670C)

## Support
-------

If you have any problem about how to use it, you can connect to us at [the bottom-right of bazzer](http://www.elecrow.com/) or contact to **techsupport@elecrow.com** to get technology support.