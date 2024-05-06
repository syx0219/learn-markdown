---
title: ESP8266 IOT Board(Arduino IDE or NodeMCU Lua Programming)
---

## Introduction
------------

This is a ESP8266 IOT board- our take on an 'all-in-one' ESP8266 WiFi development board with built in USB and battery charging. It’s an ESP8266 WiFi module with all the extras you need, The most important part is an ESP8266 WiFi microcontroller clocked at 80 MHz and at 3.3V logic. This microcontroller contains a Tensilica chip core as well as a full WiFi stack. You can program the microcontroller using the Arduino IDE for an easy-to-run Internet of Things core. We wired up a USB-Serial chip that can upload code. It also has auto-reset so no noodling with pins and reset button pressings. To make it easy to use for portable projects, we added a connector for 3.7V Lithium polymer batteries and built in battery charging. You don't need a battery, it will run just fine straight from the micro USB connector. But, if you do have a battery, you can take it on the go, then plug in the USB to recharge. The board will automatically switch over to USB power when its available. Comes fully assembled and tested, with a USB interface that lets you quickly use it with the Arduino IDE or NodeMCU Lua. (It comes preprogrammed with the Lua interpretter) We also toss in some header so you can solder it in and plug into a solderless breadboard. Lipoly battery and USB cable not included (but we do have lots of options in the shop if you'd like!)

**Model: [DPO82666E](http://www.elecrow.com/esp8266-iot-board-p-1591.html)**  
![ESP8266 IOT Board.jpg](https://wiki.elecrow.com/images/thumb/8/8e/ESP8266_IOT_Board.jpg/600px-ESP8266_IOT_Board.jpg){ loading=lazy }

## Features
--------

- Dimensions(mm): 50.0(L)x35.0(W)x7.3(H)
- Light weight
- ESP8266 @ 80MHz with 3.3V logic/power
- 4MB of FLASH (32 MBit)
- Built in WiFi 802.11 b/g/n
- 3.3V regulator with 500mA peak current output
- CP2012 USB-Serial converter onboard with 921600 max baudrate for uploading
- Auto-reset support for getting into bootload mode before firmware upload
- 9 x GPIO pins - can also be used as I2C and SPI
- 1 x analog inputs 1.0V max
- Built in 100mA LiPoly charger with charging status indicator LED, can also cut a trace to disable the charger
- Pin #0 red LED for general purpose blinking. Pin #2 blue LED for bootloading debug &amp; general purpose blinking
- Power/enable pin
- 4 mounting holes
- Reset button

## Interface Function
------------------

![Esp8266iot.jpg](https://wiki.elecrow.com/images/thumb/6/68/Esp8266iot.jpg/800px-Esp8266iot.jpg){ loading=lazy }
![177110.jpg](https://wiki.elecrow.com/images/c/cd/177110.jpg){ loading=lazy }


**Micro USB port** - it use for upload the program and update firmware,you can also charge the battery  
**Battery interface** - you can power this board with a lipo battery by this port  
**Reset button** - to have a reset  
**Flash button** - it use for update the firmware  

## Usage
-----

### **Hardware installation**

#### **1.Power Management**

It's easy to power it both when connected to a computer as well as lipo battery  
![Iot1.jpg](https://wiki.elecrow.com/images/thumb/2/25/Iot1.jpg/500px-Iot1.jpg){ loading=lazy } 
![Iot2.jpg](https://wiki.elecrow.com/images/thumb/a/a6/Iot2.jpg/500px-Iot2.jpg){ loading=lazy }

#### **2.Using NodeMCU Lua**

### **Prepareation**

ESP8266 IOT board comes pre-programmed with NodeMCU's lua interpretter. The Lua interpretter runs on the ESP8266 and you can type in commands and read out the results over serial. In order to upload code to the ESP8266 and use the serial console, connect any data-capable micro USB cable to the IOT board and the other side to your computer's USB port.Maybe you need to install the cp2102 USB driver,you can download driver [hear.](https://www.silabs.com/products/mcu/Pages/USBtoUARTBridgeVCPDrivers.aspx)

### **Load the firmware**

If you want to burning the firmware,please refer the following steps. Our ESP8266 IOT Board had comes preprogrammed with the Lua interpretter.You can direct use it.   
1.Download the tool nodemcu-flasher-master,unzip it and choose the right loading software according to your computer system(32 bit or 64 bit) ,open it you can see as bellow:  
![Nodemcu001.jpg](https://wiki.elecrow.com/images/thumb/6/6f/Nodemcu001.jpg/500px-Nodemcu001.jpg){ loading=lazy }

Note:The COM Port you should choose what are you using.
2.Download the firmware and click the config button,then load the firmware.

![Nomemcu004.jpg](https://wiki.elecrow.com/images/thumb/3/32/Nomemcu004.jpg/500px-Nomemcu004.jpg){ loading=lazy }

3.Then click the "Flash" button to load the firmware,as bellow:

![Nomemcu003.jpg](https://wiki.elecrow.com/images/thumb/a/ae/Nomemcu003.jpg/500px-Nomemcu003.jpg){ loading=lazy }

when the firmware is flashing the blue led in the ESP8266 IOT Board will continuous flashing .

### **Open up serial console**

Next up, we need to choose a development tool such as LuaLoader/ NodeMCUStudioIDE/ Decoda. Now do a demonstration with the LuaLoader.
First, disconnected the usb cable and run the LuaLoader;  
![IOT1.png](https://wiki.elecrow.com/images/thumb/a/af/IOT1.png/600px-IOT1.png){ loading=lazy }  
Click the menu "Setting", choose the"Comm Port Settings", and it'll popup a "Serial Advanced Setting", you could set the port there.  
![IESP001.jpg](https://wiki.elecrow.com/images/thumb/2/25/IESP001.jpg/600px-IESP001.jpg){ loading=lazy }  
Then connect the USB cable with it, and click the "Connect" button on the top of menu.  

![ESP002.jpg](https://wiki.elecrow.com/images/thumb/8/88/ESP002.jpg/600px-ESP002.jpg){ loading=lazy }  
Input command statement into the below edit box.  
![ESP003.jpg](https://wiki.elecrow.com/images/thumb/2/2b/ESP003.jpg/600px-ESP003.jpg){ loading=lazy }  
and it will output that:  
![ESP004.jpg](https://wiki.elecrow.com/images/thumb/f/fa/ESP004.jpg/600px-ESP004.jpg){ loading=lazy }

Also you use some of the function of the display on the right of the NodeMCU Lua.
1.GPIO Function

![ESP005.jpg](https://wiki.elecrow.com/images/thumb/5/5f/ESP005.jpg/600px-ESP005.jpg){ loading=lazy }

2.you can check the information about the chip and restart NodeMcu.like as bellow:

![ESP006.jpg](https://wiki.elecrow.com/images/thumb/7/7e/ESP006.jpg/600px-ESP006.jpg){ loading=lazy }

3.Connect the wireless networks around you

![ESP007.jpg](https://wiki.elecrow.com/images/thumb/7/7a/ESP007.jpg/600px-ESP007.jpg){ loading=lazy }

4.Download the program

In its bottom right corner you will see something about download program function button.

![ESP008.jpg](https://wiki.elecrow.com/images/thumb/5/50/ESP008.jpg/600px-ESP008.jpg){ loading=lazy }

#### **3.Using Arduino IDE**

1.Install the Arduino IDE 1.6.4 or greater Download [Arduino IDE](https://www.arduino.cc/en/Main/OldSoftwareReleases#previous) from Arduino.cc (1.6.4 or greater) - don't use 1.6.2! You can use your existing IDE if you have already installed it.（We're seeing some difficulties with IDE 1.6.6 so please try 1.6.5 or skip 1.6.6!） You can also try downloading the ready-to-go package from the ESP8266-Arduino project, if the proxy is giving you problems

2.Install the COM/Serial port driver for USB. In order to upload code to the ESP8266 and use the serial console, connect any data-capable micro USB cable to ESP8266 IOT Board and the other side to your computer's USB port.

3.Install the ESP8266 Board Package  
 Open Arduino v1.6.4 preferences  

Enter the below URL into Additional Board Manager URLs field

```
http://arduino.esp8266.com/stable/package_esp8266com_index.json 
```

![Esp82660112.jpg](https://wiki.elecrow.com/images/thumb/3/33/Esp82660112.jpg/500px-Esp82660112.jpg){ loading=lazy }

Next, use the Board manager to install the ESP8266 package

![Esp82660113.jpg](https://wiki.elecrow.com/images/thumb/a/a9/Esp82660113.jpg/500px-Esp82660113.jpg){ loading=lazy } 
![Esp8266114.jpg](https://wiki.elecrow.com/images/thumb/b/bb/Esp8266114.jpg/500px-Esp8266114.jpg){ loading=lazy }


Note: you should close the Arduino v1.6.4 and restart it again.

4.Setup ESP8266 Support  
When you've restarted, select Generic ESP8266 Module from the Tools-&gt;Board dropdown  
![IOT177.png](https://wiki.elecrow.com/images/thumb/f/f4/IOT177.png/600px-IOT177.png){ loading=lazy }


80 MHz as the CPU frequency  
![IOT178.png](https://wiki.elecrow.com/images/thumb/5/5e/IOT178.png/600px-IOT178.png){ loading=lazy }  
15200 baud upload speed (You can also try faster baud rates, we were able to upload at a blistering 921600 baud but sometimes it fails &amp; you have to retry)  
![IOT179.png](https://wiki.elecrow.com/images/thumb/2/27/IOT179.png/600px-IOT179.png){ loading=lazy }  
The matching COM port for your FTDI or USB-Serial cable  
![IOT180.png](https://wiki.elecrow.com/images/a/a6/IOT180.png){ loading=lazy }


and nodemcu as the reset method  
![IOT181.png](https://wiki.elecrow.com/images/f/f6/IOT181.png){ loading=lazy }  
Check also that you have

- Flash Mode "QIO"
- Flash Frequency "40MHz"
- Upload Using "Serial"
- CPU Frequency "80 MHz"
- Flash Size "4M"
- Reset Method "nodemcu"

#### **4.Using Luaeditor**

We use this Luaeditor to edit the program,as follow shows   
![IOT10.jpg](https://wiki.elecrow.com/images/thumb/0/0f/IOT10.jpg/600px-IOT10.jpg){ loading=lazy }

When you finish your editing, please save as a lua file.

![IOT6.jpg](https://wiki.elecrow.com/images/thumb/7/79/IOT6.jpg/600px-IOT6.jpg){ loading=lazy }

#### **5.Upload the program**

1：Click the "Upload file" then open the file we save on last step.  
![IOT11.jpg](https://wiki.elecrow.com/images/thumb/1/16/IOT11.jpg/600px-IOT11.jpg){ loading=lazy }  
2: After uploading, you just need to click the "do file" and observe the oled.  
![IOT12.jpg](https://wiki.elecrow.com/images/thumb/4/45/IOT12.jpg/600px-IOT12.jpg){ loading=lazy }
![IOT13.jpg](https://wiki.elecrow.com/images/thumb/3/30/IOT13.jpg/600px-IOT13.jpg){ loading=lazy }

## FAQ
---

You can list you question here or contact with **techsupport@elecrow.com** for technology support.

## How to buy
----------

You can click [here](http://www.elecrow.com/esp8266-iot-board-p-1591.html) to buy **[ESP8266 IOT Board(Arduino IDE or NodeMCU Lua Programming)](http://www.elecrow.com/esp8266-iot-board-p-1591.html)**.

## Resources
---------

- [Elecrow ESP8266 IOT Board Design files V1.0](https://wiki.elecrow.com/images/5/5b/ESP826_IOT_Board_v1.0.zip)
- [Crowtail-\_ESP8266\_Node\_MCU\_v2.0.zip](https://wiki.elecrow.com/images/1/1d/Crowtail-_ESP8266_Node_MCU_v2.0.zip)
- [Elecrow Tools and firmware](https://wiki.elecrow.com/images/a/ab/Tools_and_firmware.zip)