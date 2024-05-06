---
title: Lora Basic Gateway Module
---

## Description
-----------

The Lora Basic Gateway Module is a single-channel Lora gateway module that combines the ESP32 WROOM 32UE with the RA-01H module. It uses a TYPE C USB interface for power supply and is equipped with a LAN8720A-10/100Mbps RMII interface Ethernet chip. In addition to being able to connect to the network via ESP32 WIFI, it can also be connected to a wired network through an RJ45 network interface. The WIFI and LORA antenna interfaces use a built-in SMA interface antenna, which supports long-distance LORA communication. The module also features a 1.8-inch touch display screen that can display gateway networking information, IP addresses, etc. The Gateway Module can be used with LORA node modules and LORA development boards to build LORA WAN IoT networks, and can be applied in fields such as smart homes, industrial and agricultural control, and more.

**Model: [CRT01262M](https://www.elecrow.com/lorawan-gateway-module-ased-on-eso32-with-1-8-lcd-1-channel-for-long-range-communication.html)**   
![ELECROW-LoRa-Basic-Gateway 01.jpg](https://wiki.elecrow.com/images/thumb/5/53/ELECROW-LoRa-Basic-Gateway_01.jpg/600px-ELECROW-LoRa-Basic-Gateway_01.jpg){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png){loading=lazy}](https://www.elecrow.com/lorawan-gateway-module-ased-on-eso32-with-1-8-lcd-1-channel-for-long-range-communication.html?wiki "Title text")

## Feature
-------

- Integrated ESP32 WROOM UE and RA-01H modules
- Main control ESP32-DOWD-V3/ESP32-DOWDR2-V3, with built-in 520KB SRAM and 4MB Flash
- Xtensa dual-core 32-bit LX6 microprocessor @ 240MHz
- ESP32 WROOM UE supports 802.11b/g/n Wifi protocol
- RA-01H module supports FSK, GFSK, MSK, LoRa and other modulation methods
- RA-01H module supports frequency band: 803MHZ-930MHZ
- Supports 10/100Mbps RJ45 interface Ethernet connection
- Compatible with Arduino/Micropython programming platform
- Supports 5V-USB power supply
- External SMA 2.4G wifi antenna, 868MHZ/915MHZ LoRa antenna

## Technical Specification
-----------------------

- TYPE C USB input voltage: DC-5V
- Operating temperature range: -10°C ~ 65°C
- Size: 65mm (L) x 58mm (W)

## Interface Function
------------------

![Lora gateway 2.png](https://wiki.elecrow.com/images/thumb/1/11/Lora_gateway_2.png/490px-Lora_gateway_2.png){ loading=lazy }
![Lora gateway 3.png](https://wiki.elecrow.com/images/thumb/5/5e/Lora_gateway_3.png/490px-Lora_gateway_3.png){ loading=lazy }

| **Name** | **Interface/Function Definition** |
|:-:|:-:|
| PWR | Red power indicator light, always on when powered on, and off when power is off. |
| DATA | Blue data indicator light, flashes during data transmission and is off by default. |
| RESET | Reset button. Press this button to reset the system. |
| BOOT | Download button. Pressing and holding the Boot button and then pressing the RESET button can start the firmware download mode. Users can download firmware through the USB interface. |
| USB-C | USB-C interface, which is used as a power supply for the gateway module and a communication interface between the PC and ESP32. |
| WIFI | ESP32 2.4G WIFI antenna SMA interface. |
| LORA | 868MHZ/915MHZ LoRa antenna SMA interface. |
| Ethernet | 100Mbps Ethernet RJ45 interface. |

The corresponding IO ports are as shown in the figure:
![Lora gateway 3-1.png](https://wiki.elecrow.com/images/2/29/Lora_gateway_3-1.png){ loading=lazy }

## Usage
-----

### **Development Environment Construction**

1\. Directly visit the Arduino official website and download the Arduino development tools supported by the device. The link is as follows: *[https://www.arduino.cc/en/software](https://www.arduino.cc/en/software)*.   
![Lora RA-08H 1 1.png](https://wiki.elecrow.com/images/2/23/Lora_RA-08H_1_1.png){ loading=lazy }

2\. Click the downloaded Arduino development tool to install the software. After the software installation is complete, open it directly, as shown in the figure below:   
![Lora RA-08H 2 1 2 1.png](https://wiki.elecrow.com/images/thumb/c/c6/Lora_RA-08H_2_1_2_1.png/490px-Lora_RA-08H_2_1_2_1.png){ loading=lazy }

3\. Click *"File" -&gt; "Preferences"* on the menu bar to pop up the preference setting interface.   
![Lora RA-08H 1 3.png](https://wiki.elecrow.com/images/thumb/8/87/Lora_RA-08H_1_3.png/490px-Lora_RA-08H_1_3.png){ loading=lazy }

4\. Click the icon on the far right of the Additional Boards Manager URLs column, enter ***[https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package\_esp32\_index.json](https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json)*** and ***[https://github.com/earlephilhower/arduino-pico/releases/download/global/package\_rp2040\_index.json](https://github.com/earlephilhower/arduino-pico/releases/download/global/package_rp2040_index.json)*** in the pop-up window.(The two URLs need to be separated by line breaks)   
![Lora gateway 4.png](https://wiki.elecrow.com/images/thumb/0/05/Lora_gateway_4.png/490px-Lora_gateway_4.png){ loading=lazy }

5\. Click *"Tools" -&gt; "Board:..." -&gt; "Boards Manager..."* in the menu bar to enter the Boards Manager interface.   
![Lora gateway 5.png](https://wiki.elecrow.com/images/thumb/1/17/Lora_gateway_5.png/490px-Lora_gateway_5.png){ loading=lazy }

6\. Enter "ESP32" in the search box, select "ESP32" and install the development environment.   
 **It should be noted here that when selecting the development environment version, do not choose the latest one. It is recommended to choose version 2.0.3.**

![Lora gateway 5.png](https://wiki.elecrow.com/images/thumb/1/17/Lora_gateway_5.png/490px-Lora_gateway_5.png){ loading=lazy }

7\. After the environment is successfully installed, if you find "ESP32 Arduino" in the Arduino IDE development board management, it means that the environment is successfully built.   
![Lora gateway 6.png](https://wiki.elecrow.com/images/thumb/c/c7/Lora_gateway_6.png/490px-Lora_gateway_6.png){ loading=lazy }

### **Software Settings**

1\. For the first use, you need to set up and select the correct development board. Click *"Tools" -&gt; "Board:..." -&gt; "ESP32 Arduino" -&gt; "ESP32 Dev Module"* in the menu bar, as shown in the figure below:    
![Lora gateway 7.png](https://wiki.elecrow.com/images/thumb/4/4f/Lora_gateway_7.png/490px-Lora_gateway_7.png){ loading=lazy }

2\. After connecting the Lora Basic Gateway Module to the computer via a TYPE-C USB cable, the computer will automatically recognize the USB COM port (if the USB is not recognized successfully, please check if the CH340 driver has been installed on the computer).    
![Lora gateway 8.png](https://wiki.elecrow.com/images/thumb/4/43/Lora_gateway_8.png/490px-Lora_gateway_8.png){ loading=lazy }

3.After the USB COM port is successfully recognized, open the Arduino IDE and burn an example code as shown in the figure below:File-&gt;Examples-&gt;Basics-&gt;Blink    
![Lora RA-08H 2 3 1.png](https://wiki.elecrow.com/images/thumb/4/45/Lora_RA-08H_2_3_1.png/490px-Lora_RA-08H_2_3_1.png){ loading=lazy }

The code that is opened is as follows: modify "LED\_BUILTIN" to "5".    
![Lora gateway 9.png](https://wiki.elecrow.com/images/c/cc/Lora_gateway_9.png){ loading=lazy }

Select the recognized "COMxx port" in the Arduino IDE.    
![Lora gateway 10.png](https://wiki.elecrow.com/images/thumb/e/ea/Lora_gateway_10.png/490px-Lora_gateway_10.png){ loading=lazy }

Press and hold the "BOOT" button on the Lora Basic Gateway Module, then press the "RESET" button, release the "RESET" button first, and finally release the "BOOT" button. Click "Download" to successfully burn the code into the ESP32!

### **Sample Program**

**Example: The Lora RA-08H Node Board (915MHz) uploads data to TTN server via Lora Basic Gateway Module.**    
![Lora gateway 11.png](https://wiki.elecrow.com/images/thumb/4/41/Lora_gateway_11.png/490px-Lora_gateway_11.png){ loading=lazy }

(Lora RA-08H Node Board(915MHZ)Node module)

1 Burn the example program to the Lora Basic Gateway Module via Arduino IDE.    
1.1 First, copy the library files in the "libraries" folder of the "Code" folder to the Arduino IDE library management folder, as shown in the following picture..    
![Lora gateway 12.png](https://wiki.elecrow.com/images/thumb/5/5e/Lora_gateway_12.png/600px-Lora_gateway_12.png){ loading=lazy }

1.2Open the "ESP-sc-gway-end.ino" file in the "ESP-Lora\_Factory\_program" folder.   
![LORAGATWAY-ESP-SC-GWAY-END.png](https://wiki.elecrow.com/images/thumb/0/0e/LORAGATWAY-ESP-SC-GWAY-END.png/600px-LORAGATWAY-ESP-SC-GWAY-END.png){ loading=lazy }

1.3 Burn the "ESP-sc-gway-end.ino" example program to the Lora Basic Gateway Module. Select the board model and COM port.   
![600px-Lora gateway 14-1.png](https://wiki.elecrow.com/images/b/bf/600px-Lora_gateway_14-1.png){ loading=lazy }

```
Click to start burning the program and wait for the program to be burned!
```

![Lora gateway 15-1.png](https://wiki.elecrow.com/images/c/cb/Lora_gateway_15-1.png){ loading=lazy }

After the burning process is complete, press the RESET button to reset the module. After resetting, the LCD screen on the back of the gateway module will display the gateway configuration information, as shown in the following figure:    
![Lora gateway 16-1.png](https://wiki.elecrow.com/images/thumb/e/e7/Lora_gateway_16-1.png/300px-Lora_gateway_16-1.png){ loading=lazy }

2 Lora Basic Gateway Module network configuration   
2.1 Use a mobile phone or laptop to connect to the gateway module's WiFi "ELECROW-GW1C" with the password "12345678".   
![Lora gateway 17.png](https://wiki.elecrow.com/images/2/26/Lora_gateway_17.png){ loading=lazy }

2.2 Enter the webpage by typing 192.168.4.1 in the browser; configure the gateway network connection mode as WIFI (must enter the correct WIFI account password) or NET (directly connect to the router using an RJ45 cable, no WIFI information is required under NET); press Gateway Default to obtain the default gateway ID or enter a 16-digit ID of your own; enter the server address port; REGION sets the gateway working frequency band (EU868 and US915); set the gateway channel (CHANNEL) and spreading factor (SF); as shown in the figure below:    
![Lora gateway 18.png](https://wiki.elecrow.com/images/thumb/1/1d/Lora_gateway_18.png/400px-Lora_gateway_18.png){ loading=lazy }
![Lora gateway 19.png](https://wiki.elecrow.com/images/thumb/7/79/Lora_gateway_19.png/400px-Lora_gateway_19.png){ loading=lazy }


(1)NET MODE: WIFI/NET optional   
(2)WIFI SSID: Fill in the name of the WiFi to be connected (no need to fill in any information under NET mode)   
(3)WIFI PASS: Fill in the password of the WiFi to be connected (no need to fill in any information under NET mode)  
(4)Gateway ID: Press Gateway Default to obtain the default gateway ID or enter a 16-digit ID of your own   
(5)SERVER ADDR: eu1.cloud.thethings.network  
(6)SERVER PORT: Default 1700  
(7)REGION: The gateway working frequency band setting can choose EU868/US915   
(8)CHANNEL: Default 0   
(9)SF: Default 7 (Choose 7 for EU868MHz band and 10 for US915 band)   
2.3After confirming that there are no errors, click Submit to submit the configuration information. The gateway will load the corresponding configuration after completion, as shown in the figure below:   
![Lora gateway 20-1.png](https://wiki.elecrow.com/images/thumb/8/8b/Lora_gateway_20-1.png/300px-Lora_gateway_20-1.png){ loading=lazy }

3 Create a gateway in the TTN (thethings.network) server      
3.1 Enter eu1.cloud.thethings.network/oauth/login in the browser to enter the following web page, and click "Login with the things ID".    
![Lora gateway 21.png](https://wiki.elecrow.com/images/thumb/3/39/Lora_gateway_21.png/600px-Lora_gateway_21.png){ loading=lazy }

3.2 Click "Switch account" to create an account and log in (only an email account is required to register, follow the prompts to complete the registration, which will not be repeated here).    
![Lora gateway 22.png](https://wiki.elecrow.com/images/thumb/a/a3/Lora_gateway_22.png/600px-Lora_gateway_22.png){ loading=lazy }

3.3 After logging in to the account, enter the following interface, and click Go to the Console.   
![.jpgLora gateway 23.png](https://wiki.elecrow.com/images/thumb/b/b9/.jpgLora_gateway_23.png/600px-.jpgLora_gateway_23.png){ loading=lazy }

3.4 Create a gateway in the TTN server backend by clicking Gateway-&gt;Register Gateway. Enter the following interface, and enter 16-bit ID: 0000000000009151 in the Gateway Eui (you can set the ID yourself. If the creation fails, it may be because the entered ID has been registered, so please modify the ID address).    
![Lora gateway 24.png](https://wiki.elecrow.com/images/thumb/d/d2/Lora_gateway_24.png/600px-Lora_gateway_24.png){ loading=lazy }


Important Note: Select the frequency band "Europe 863-870MHz (SF12 for RX2)" (choose this for LoRa nodes using 868MHz band) or "United States 902-928MHz FSB1" (choose this for testing LoRa nodes using 915MHz band).    
After setting the gateway information, click "Register Gateway" to register the gateway!

After setting as shown in the figure above, register the gateway! (Make sure that the gateway ID is consistent, otherwise the connection will fail.) Click Gateway to refresh and you can see that the gateway has connected to the TTN server backend. After the gateway is established, power off and reset the gateway module, and then log in to the TTN server again to see that the gateway has connected to the TTN server (may require multiple repetitions).     
![Lora gateway 25.png](https://wiki.elecrow.com/images/thumb/b/b9/Lora_gateway_25.png/600px-Lora_gateway_25.png){ loading=lazy }


4 Add the node application of the Lora RA-08H Node Board (915MHz) to the TTN server   
4.1 Click Applications-&gt;Create Applications and enter the Applications ID and Applications name in the pop-up interface. After entering, click "Create Applications".    
![Lora gateway 26.png](https://wiki.elecrow.com/images/thumb/4/49/Lora_gateway_26.png/600px-Lora_gateway_26.png){ loading=lazy }
![Lora gateway 27.png](https://wiki.elecrow.com/images/thumb/b/b4/Lora_gateway_27.png/600px-Lora_gateway_27.png){ loading=lazy }

Click Register end device to register the node.      
![Lora gateway 28.png](https://wiki.elecrow.com/images/thumb/0/0f/Lora_gateway_28.png/600px-Lora_gateway_28.png){ loading=lazy }

Enter the following interface, and set it as shown in the figure below (Frequency plan is optional):    
![Lora gateway 29.png](https://wiki.elecrow.com/images/thumb/e/e9/Lora_gateway_29.png/600px-Lora_gateway_29.png){ loading=lazy }
![Lora gateway 30.png](https://wiki.elecrow.com/images/1/10/Lora_gateway_30.png){ loading=lazy }

If you are using a 868MHz gateway, select "Europe 863-870MHz (SF12 for RX2)"   
If you are using a 915MHz gateway, select "United States 902-928MHz FSB1"

4.2 Configure the DevEui, AppEui, and AppKey information of the RA-08H node module as shown in the figure below:   
![Lora gateway 31.png](https://wiki.elecrow.com/images/b/b2/Lora_gateway_31.png){ loading=lazy }

Click Register end device to register the device. After successful registration, enter the following interface:    
![Lora gateway 32.png](https://wiki.elecrow.com/images/thumb/8/82/Lora_gateway_32.png/600px-Lora_gateway_32.png){ loading=lazy }

5\. The Lora RA-08H Node Board (915MHz) node module connects to the TTN gateway server and uploads data by configuring AT commands.    
5.1. First, burn the serial application program to the Lora RA-08H Node Board (915MHz) node module. In the Code folder, open the "RA-08\_H.ino" program using the Arduino IDE.     
![Lora gateway 33.png](https://wiki.elecrow.com/images/9/92/Lora_gateway_33.png){ loading=lazy }

Select the board type, COM port, and burn it!    
![Lora gateway 34.png](https://wiki.elecrow.com/images/thumb/7/79/Lora_gateway_34.png/600px-Lora_gateway_34.png){ loading=lazy }


5.2. After the program is successfully burned, use the serial assistant tool in the TOOL folder to send AT commands to configure the Lora RA-08H Node Board (915MHz) node module as shown below:    
(1) Serial port settings   

```
1. Baud rate: 9600<br></br>
2. Open the serial port with carriage return and line feed<br></br>
```

(2) Node access to single channel gateway configuration steps (Send AT commands)

```
1. Set the node access method to OTAA: AT+CJOINMODE=0
2. Set the node group frequency mask: AT+CFREQBANDMASK=0001 (Set channels 0-7)
3. Set the node type: AT+CLASS=0 (Class A node)
4. Set the node DevEui: AT+CDEVEUI=70B3D57ED005D380 (The red part corresponds to the TTN server)
5. Set the node AppEui: AT+CAPPEUI=0000000000000022 (The red part corresponds to the TTN server)
6. Set the node AppKey: AT+CAPPKEY=7FAFC241494DDD85E77840E60748E49C (The red part corresponds to the TTN server)
7. Set the node to turn off adaptive spreading factor: AT+CADR=0
8. Set the uplink communication rate after the node successfully joins: AT+CDATARATE=5 (Values 0-5, depending on the gateway configuration for 868 and 915, different frequency bands have different settings. See the protocol macro definition below. AT+CDATARATE=5 corresponds to 868, and AT+CDATARATE=0 corresponds to 915.)
9. Set the receive window delay: AT+CRX1DELAY=1 (Default=1 for 1 second, increase the time based on distance and network status to improve the success rate of join, generally no need to change)
10. Set the port for the node to receive TTN downlink data: AT+CAPPPORT=2 (The red part corresponds to the TTN server)
11. Set the node uplink and downlink on the same frequency: AT+CULDLMODE=1 (1 for same frequency, 2 for different frequency)
12. Set the node to join the network: AT+CJOIN=1,0,8,8 (Appear +CJOIN:OK for success)
13. Set the node to send data to the TTN server: AT+DTRX=0,10,2,0109 (Can be sent after successful joining, data format must be even)
```

Click on EXT and enter the following AT commands in the serial tool's extension column, making sure to enter the DevEui, AppEui, and AppKey corresponding to the node in TTN.       
![Lora gateway 35.png](https://wiki.elecrow.com/images/thumb/9/98/Lora_gateway_35.png/600px-Lora_gateway_35.png){ loading=lazy }
![Lora gateway 36.png](https://wiki.elecrow.com/images/thumb/5/52/Lora_gateway_36.png/600px-Lora_gateway_36.png){ loading=lazy }

Send the command "AT+CJOIN=1,0,8,8" and wait until the serial port prints "Successfully joined!" to confirm successful joining.    
![Lora gateway 37.png](https://wiki.elecrow.com/images/thumb/2/26/Lora_gateway_37.png/600px-Lora_gateway_37.png){ loading=lazy }

Send the command "AT+DTRX=0,10,2,0109" and then send the data "0109". The Lora RA-08H Node Board (915MHz) node module will successfully upload the data "0109" to the TTN server!    
![Lora gateway 38.png](https://wiki.elecrow.com/images/thumb/8/85/Lora_gateway_38.png/600px-Lora_gateway_38.png){ loading=lazy }
![Lora gateway 39.png](https://wiki.elecrow.com/images/thumb/c/ce/Lora_gateway_39.png/600px-Lora_gateway_39.png){ loading=lazy }

## Resource
--------

- [Lora\_Gateway\_Module ](https://drive.google.com/drive/folders/1pdnOdEx0FmTOJj_3wIaKNj99Ayka7nOC?usp=sharing)
- [Lora\_GateWay\_Datasheet](https://wiki.elecrow.com/images/6/6c/Lora_GateWay_Datasheet.zip)
- [Lora\_GateWay\_Eagle\_File](https://wiki.elecrow.com/images/4/4f/Lora_GateWay_Eagle_File.zip)
- [Lora\_GateWay\_Tool](https://wiki.elecrow.com/images/0/05/Lora_GateWay_Tool.zip)
- [Lora\_gateway\_Libraries.rar](https://www.elecrow.com/download/product/CRT01262M/Lora_gateway_Libraries.rar)
- [ESP-Lora\_Factory\_program.rar](https://www.elecrow.com/download/product/CRT01262M/ESP-Lora_Factory_program.rar)