---
title: WiFi Shield
---

## Description
-----------

This Wifi Shield utilizes a RN171 wifi module to provide your Arduino/Crowduino with serial Ethernet's function and adds storage to your arduino project . It features an independent antenna which can cover a wider range and transmit stronger signals. With supports for common TCP, UDP and FTP communication protocols, this Wifi Shield can meet needs of most wireless network projects, like smart home networks, robot controls or personal weather stations, etc. We prepared an easy and convenient command set for this shield so that you can use neat and concise code to run the function. If you use the wifi function, it takes two pins to hook your device up to 802.11b/g wireless networks. If you use the storage, it takes SPI and a select pin to access to the SD.

**Model：[ACS17101S](https://www.elecrow.com/wifi-shield-p-428.html)**

![WiFi Shield.jpg](https://wiki.elecrow.com/images/thumb/c/cb/WiFi_Shield.jpg/600px-WiFi_Shield.jpg){ loading=lazy }

## Features
--------

- Arduino, Crowduino, Seeeduino, Arduino Mega and Crowduino Mega compatible
- Host Data Rate up to 1 Mbps for UART, 2 Mbps over SPI slave
- UART serial port of RN171 on the Shield can be connected to Arduino by jumpers
- SPI pin of RN171 is just breakout
- Support SD card 2GB and 4GB.
- Secure WiFi authentication WEP-128, WPA-PSK (TKIP), WPA2-PSK (AES)
- Built-in networking applications: DHCP client, DNS client, ARP, ICMP ping, FTP, TELNET, HTTP, UDP, TC
- Dimensions(mm):68.6(L)x55.0(W)x23.5(H)

## Specification
-------------

<table cellspacing="0" cellpadding="5" border="1">
  <tbody>
    <tr>
      <td style="background: #F99D30; color: white" align="center" width="150"><b>Items</b></td>
      <td style="background: #F99D30; color: white" align="center" width="80"><b>Min</b></td>
      <td style="background: #F99D30; color: white" align="center" width="80"><b>Typical</b></td>
      <td style="background: #F99D30; color: white" align="center" width="80"><b>Max</b></td>
      <td style="background: #F99D30; color: white" align="center" width="80"><b>Unit</b></td>
    </tr>
    <tr style="font-size: 90%">
      <td align="center">Voltage</td>
      <td align="center">3.3</td>
      <td align="center">5</td>
      <td align="center">5.5</td>
      <td align="center">v</td>
    </tr>
    <tr style="font-size: 90%">
      <td align="center">Current</td>
      <td align="center">25</td>
      <td align="center">80</td>
      <td align="center">500</td>
      <td align="center">mA</td>
    </tr>
    <tr style="font-size: 90%">
    <td align="center">Transmit power</td>
    <td align="center" colspan="3" rowspan="1">0-10</td>
    <td align="center">dBm</td>
    </tr>
    <tr style="font-size: 90%">
    <td align="center">Frequency</td>
    <td align="center" colspan="3" rowspan="1">2402~2480</td>
    <td align="center">MHz</td>
    </tr>
    <tr style="font-size: 90%">
      <td align="center">Network rate</td>
      <td align="center" colspan="4" rowspan="1">1-11 Mbps for 802.11b/6-54Mbps for 802.11g</td>
    </tr>
    <tr style="font-size: 90%">
      <td align="center">Supported Card Type</td>
      <td align="center" colspan="4" rowspan="1">SD card(&lt;=2G); Micro SD card(&lt;=2G);</td>
    </tr>
  </tbody>
</table>

## Interface
---------

![Wifi shield interface.png](https://wiki.elecrow.com/images/thumb/6/6a/Wifi_shield_interface.png/600px-Wifi_shield_interface.png){ loading=lazy }

## Usage
-----

- **hardware Installation**

Assemble these parts together like the picture below. and mount the shield onto your Arduino/Crowduino.
![Assemble wifi.jpg](https://wiki.elecrow.com/images/thumb/0/01/Assemble_wifi.jpg/600px-Assemble_wifi.jpg){ loading=lazy }

- **Software Programming**

First you have to make sure that Arduino1.0 has already been installed on your computer.

![Tb2.jpg](https://wiki.elecrow.com/images/5/57/Tb2.jpg){ loading=lazy } 
Download the wifishield library here [Wifi Shield.zip](http://www.elecrow.com/wiki/images/b/b8/WifiShield.zip) and unzip it into the libraries file of Arduino via this path: ..\\arduino-1.0\\libraries  
Open a new sketch in Arduino-1.0, then copy the following code to your sketch.

```
#include "Wifly.h"
#include <SoftwareSerial.h>
WiflyClass Wifly(2,3);
void setup()
{
  Serial.begin(9600);//use the hardware serial to communicate with the PC
  Wifly.init();//Initialize the wifishield
  Wifly.setConfig("SSID","PASSWORD");//here to set the ssid and password of the Router
  Wifly.join("SSID");
  Wifly.checkAssociated();
  while(!Wifly.connect("192.168.1.164","90"));//connect the remote service
  Wifly.writeToSocket("Connected!");
}
void loop()
{
  if(Wifly.canReadFromSocket())
  {
    Serial.print(Wifly.readFromSocket());
  }
  if(Serial.available())
  {
    Wifly.print((char)Serial.read());
  }
}

```


You need to do some modifications on this sketch according to your specific configuration.

## Debug through computer
----------------------

## Resource
--------

[Design files](https://wiki.elecrow.com/images/4/42/ELE_Wifi_Shield_V1.0.zip) 
[wifiShield library](http://www.elecrow.com/wiki/images/b/b8/WifiShield.zip) 
[RN171 Datasheet](https://wiki.elecrow.com/images/9/92/WiFly-RN-171-DS.pdf)
If some function isn't included in the library, This [User Manul](https://wiki.elecrow.com/images/b/be/WiFly-RN-UM.pdf) may help.