---
title: ESP32S WIFI BLE Board
---

## Description
-----------

ESP-WROOM-32 is a powerful, generic Wi-Fi+BT+BLE MCU module that targets a wide variety of applications, ranging from low-power sensor networks to the most demanding tasks, such as voice encoding, music streaming and MP3 decoding. The development board breaks out all the module’s pins to 0.1″ headers and provides a CP2102 USB-TTL serial adapter, programming and reset buttons, and a power regulator to supply the ESP32 with a stable 3.3 V. Espressif doubled-down on the CPU resources for the ESP32 with a dual core, running at 160MHz and tons more pins and peripherals. The integration of Bluetooth, Bluetooth LE and Wi-Fi ensures that a wide range of applications can be targeted, and that the module is future proof: using Wi-Fi allows a large physical range and direct connection to the internet through a Wi-Fi router, while using Bluetooth allows the user to conveniently connect to the phone or broadcast low energy beacons for its detection. The sleep current of the ESP32 chip is less than 5 µA, making it suitable for battery powered and wearable electronics applications. ESP-WROOM-32 supports data rates of up to 150 Mbps, and 22 dBm output power at the PA to ensure the widest physical range. As such the chip does offer industry-leading specifications and the best performance for electronic integration, range, power consumption, and connectivity.

**Model: [ARS01119B](https://www.elecrow.com/esp32-wifi-ble-board.html)**

![Esp32s wifi ble board v1.0.jpg](https://wiki.elecrow.com/images/thumb/6/69/Esp32s_wifi_ble_board_v1.0.jpg/500px-Esp32s_wifi_ble_board_v1.0.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png)](https://www.elecrow.com/esp32-wifi-ble-board.html?wiki "Title text")

## Features
--------

- Support SD card, UART, SPI, SDIO, I2C, LED PWM, Motor PWM,I2S, I2C, IRUSB-UART
- Integrated 802.11 BGN WiFi transceiver and dual-mode Bluetooth (classic and BLE)
- Hardware accelerated encryption (AES, SHA2, ECC, RSA-4096)
- Integrated LiPo Battery Charger.
- 10-electrode capacitive touch support
- Up to 240MHz clock frequency and 520kB internal SRAM
- Support Station/SoftAP/SoftAP+Station/P2P
- Support WPA/WPA2/WPA2-Enterprise/WPS
- include bridge, reset- and boot-mode buttons, LDO regulator and a micro-USB connector.
- Support AES/RSA/ECC/SHA

## Specifications
--------------

| **Item** | **Value** |
|---|---|
|  | FCC/CE/IC/TELEC/KCC/SRRC/NCC |
| Wi-Fi | 802.11 b/g/n/e/i (802.11n up to 150 Mbps) |
|  | A- MPDU and A-MSDU aggregation and 0.4 \_s guard interval support |
| Frequency range | 2.4 ~ 2.5 GHz |
| Bluetooth | v4.2 BR/EDR and BLE specification |
| Radio | NZIF receiver with -98 dBm sensitivity, Class-1, class-2 and class-3 transmitter |
| Audio | CVSD and SBC |
| On-board clock | 40 MHz crystal |
| Operating voltage | 2.2 ~ 3.6V |
| Operating current | Average: 80 mA |
| Operating temperature range | -40°C ~ 85°C |

## Interface
---------

![600px-Esp321.jpg](https://wiki.elecrow.com/images/d/d2/600px-Esp321.jpg){ loading=lazy }

## Platforms Supported
-------------------

| **Arduino** |
|:-:|
| ![Arduino.png](https://wiki.elecrow.com/images/6/63/Arduino.png){ loading=lazy } |

Usage
-----

### Hardware

STEP1 Prepare the below stuffs:  

| **ESP32 WIFI BLE Board**                                     |
| :------------------------------------------------------------: |
| ![Esp32s wifi ble board v1.0.jpg](https://wiki.elecrow.com/images/thumb/6/69/Esp32s_wifi_ble_board_v1.0.jpg/400px-Esp32s_wifi_ble_board_v1.0.jpg){ loading=lazy } |
| [**Get one now**](https://www.elecrow.com/esp32-wifi-ble-board.html) |

STEP2 Connect WIFI BLE Board to PC via a Mini USB cable.

### **Software**

- 1.Build arduino Programming Environment (Windows)

STEP1 Put the espressif folder in the C:/Program Files (x86)/Arduino/ Hardware path (depending on which disk your Arduino is installed on, Arduino is installed on disk D as shown below)  
![Esp32ss1.png](https://wiki.elecrow.com/images/0/00/Esp32ss1.png){ loading=lazy }  
STEP2 Double click open the get.exe(arduino-1.6.5\\hardware\\espressif\\esp32\\tools)  
![Esp32ss2.png](https://wiki.elecrow.com/images/7/70/Esp32ss2.png){ loading=lazy }  
Loading board data, wait a moment. Automatically closes after downloading  
![Esp32ss3.png](https://wiki.elecrow.com/images/0/0c/Esp32ss3.png){ loading=lazy }  
STEP3 After downloading, you can see that there are two additional folders "dist" and "Xtensa-esp32-elf" in the folder. The programming environment has been built.  
![Esp32ss4.png](https://wiki.elecrow.com/images/5/50/Esp32ss4.png){ loading=lazy }  

- 2.Wifi test

STEP1 Open the Arduino IDE, click "Tools", select the board type "ESP32 Dev Module", set baud rate 115200, and select the correct port.  
![Esp32ss5.png](https://wiki.elecrow.com/images/4/4f/Esp32ss5.png){ loading=lazy }  
STEP2 Load the code "wifitest. Ino". Modify according to your own Settings
![Wifiset.png](https://wiki.elecrow.com/images/thumb/3/30/Wifiset.png/600px-Wifiset.png){ loading=lazy }  

```
// Copyright 2015-2016 Espressif Systems (Shanghai) PTE LTD
//
// Licensed under the Apache License, Version 2.0 (the "License");
// you may not use this file except in compliance with the License.
// You may obtain a copy of the License at

//     http://www.apache.org/licenses/LICENSE-2.0
//
// Unless required by applicable law or agreed to in writing, software
// distributed under the License is distributed on an "AS IS" BASIS,
// WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
// See the License for the specific language governing permissions and
// limitations under the License.

// Sketch shows how to switch between WiFi and BlueTooth or use both
// Button is attached between GPIO 0 and GND and modes are switched with each press

#include "WiFi.h"
#define STA_SSID "Elecrow"
#define STA_PASS "elecrow2014"
#define AP_SSID  "esp32"

enum { STEP_STA, STEP_AP,  STEP_END };

void onButton(){
  static uint32_t step = STEP_STA;
  switch(step){
  /*  case STEP_BTON://BT Only
      Serial.println("** Starting BT");
      btStart();
    break;
    case STEP_BTOFF://All Off
      Serial.println("** Stopping BT");
      btStop();
    break;*/
    case STEP_STA://STA Only
      Serial.println("** Starting STA");
      WiFi.begin(STA_SSID, STA_PASS);
    break;
    case STEP_AP://AP Only
      Serial.println("** Stopping STA");
      WiFi.mode(WIFI_AP);
      Serial.println("** Starting AP");
      WiFi.softAP(AP_SSID);
    break;
  /* case STEP_AP_STA://AP+STA
      Serial.println("** Starting STA");
      WiFi.begin(STA_SSID, STA_PASS);
    break;
    case STEP_OFF://All Off
      Serial.println("** Stopping WiFi");
      WiFi.mode(WIFI_OFF);
    break;
    case STEP_BT_STA://BT+STA
      Serial.println("** Starting STA+BT");
      WiFi.begin(STA_SSID, STA_PASS);
      btStart();
    break;
    case STEP_END://All Off
      Serial.println("** Stopping WiFi+BT");
      WiFi.mode(WIFI_OFF);
      btStop();
    break;*/
    default:
    break;
  }
  if(step == STEP_END){
    step = STEP_STA;
  } else {
    step++;
  }
  //little debounce
  delay(100);
}

void WiFiEvent(WiFiEvent_t event){
    switch(event) {
        case SYSTEM_EVENT_AP_START:
            Serial.println("AP Started");
            WiFi.softAPsetHostname(AP_SSID);
            break;
        case SYSTEM_EVENT_AP_STOP:
            Serial.println("AP Stopped");
            break;
        case SYSTEM_EVENT_STA_START:
            Serial.println("STA Started");
            WiFi.setHostname(AP_SSID);
            break;
        case SYSTEM_EVENT_STA_CONNECTED:
            Serial.println("STA Connected");
            WiFi.enableIpV6();
            break;
        case SYSTEM_EVENT_AP_STA_GOT_IP6:
            Serial.print("STA IPv6: ");
            Serial.println(WiFi.localIPv6());
            break;
        case SYSTEM_EVENT_STA_GOT_IP:
            Serial.print("STA IPv4: ");
            Serial.println(WiFi.localIP());
            break;
        case SYSTEM_EVENT_STA_DISCONNECTED:
            Serial.println("STA Disconnected");
            break;
        case SYSTEM_EVENT_STA_STOP:
            Serial.println("STA Stopped");
            break;
        default:
            break;
    }
}

void setup() {
    Serial.begin(115200);
    pinMode(0, INPUT_PULLUP);
    WiFi.onEvent(WiFiEvent);
    Serial.print("ESP32 SDK: ");
    Serial.println(ESP.getSdkVersion());
    Serial.println("Press the button to select the next mode");
}

void loop() {
    static uint8_t lastPinState = 1;
    uint8_t pinState = digitalRead(0);
    if(!pinState && lastPinState){
        onButton();
    }
    lastPinState = pinState;
}
```

STEP3 Start the Serial Monitor(If printing error, press reset button "EN" several more times to refresh or re-upload code connection. )  
![Esp32ss6.png](https://wiki.elecrow.com/images/a/ac/Esp32ss6.png){ loading=lazy }  
STEP4 Press the BOOT key to set the mode to STASTION. The serial port print is as follows  
![Esp32ss7.png](https://wiki.elecrow.com/images/2/24/Esp32ss7.png){ loading=lazy }  
If the information in the red box is displayed, the connection is successful.  
STEP5 Press the BOOT key again to set the module to AP mode. The serial port print is as follows:  
![Esp32ss8.png](https://wiki.elecrow.com/images/2/24/Esp32ss8.png){ loading=lazy }  
The AP mode is set successfully. Open the WiFi function of the mobile phone, find the account named "ESP32" to connect. (Press EN to reset several times or power on again if printing error occurs.)
  
## FAQ
---

You can list you question here or contact with techsupport@elecrow.com for technology support.

## Resources
---------

[ESP32S\_WIFI\_BLE\_Board-V1.0-Eagle.zip](https://wiki.elecrow.com/images/8/83/ESP32S_WIFI_BLE_Board-V1.0-Eagle.zip)  
[Wifitest.zip](https://wiki.elecrow.com/images/2/24/Wifitest.zip)  
[SoftwareFiles.zip](https://www.elecrow.com/download/product/ARS01119B/ESP32S-WIFI-BLE-Board_SoftwareFiles.zip)