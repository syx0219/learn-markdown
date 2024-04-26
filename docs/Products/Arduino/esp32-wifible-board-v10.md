---
title: ESP32 WIFI/BLE Board v1.0
---

## Introduction
------------

ESP-WROOM-32 is a powerful, generic Wi-Fi+BT+BLE MCU module that targets a wide variety of applications, ranging from low-power sensor networks to the most demanding tasks, such as voice encoding, music streaming and MP3 decoding.

The development board breaks out all the module's pins to 0.1" headers and provides a CP2102 USB-TTL serial adapter, programming and reset buttons, and a power regulator to supply the ESP-WROOM-32 with a stable 3.3 V. Espressif doubled-down on the CPU resources for ESP-WROOM-32 with a dual core, running at 160MHz and tons more pins and peripherals.

The integration of Bluetooth, Bluetooth LE and Wi-Fi ensures that a wide range of applications can be targeted, and that the module is future proof: using Wi-Fi allows a large physical range and direct connection to the internet through a Wi-Fi router, while using Bluetooth allows the user to conveniently connect to the phone or broadcast low energy beacons for its detection. The sleep current of the ESP32 chip is less than 5 µA, making it suitable for battery powered and wearable electronics applications. ESP-WROOM-32 supports data rates of up to 150 Mbps, and 22 dBm output power at the PA to ensure the widest physical range. As such the chip does offer industry-leading specifications and the best performance for electronic integration, range, power consumption, and connectivity.

**Model: [ARS01119B](https://www.elecrow.com/catalog/product/view/id/2392/)**  
![Esp32 0.jpg](https://wiki.elecrow.com/images/thumb/7/73/Esp32_0.jpg/400px-Esp32_0.jpg){ loading=lazy }

## Features
--------

- Support SD card, UART, SPI, SDIO, I2C, LED PWM, Motor PWM,I2S, I2C, IRUSB-UART
- Integrated 802.11 BGN WiFi transceiver and dual-mode Bluetooth (classic and BLE).
- Hardware accelerated encryption (AES, SHA2, ECC, RSA-4096)
- Integrated LiPo Battery Charger.
- 10-electrode capacitive touch support
- Up to 240MHz clock frequency and 520kB internal SRAM
- Support Station/SoftAP/SoftAP+Station/P2P
- Support WPA/WPA2/WPA2-Enterprise/WPS
- Support AES/RSA/ECC/SHA
- Include bridge, reset- and boot-mode buttons, LDO regulator and a micro-USB connector.

## Specification
-------------

- FCC/CE/IC/TELEC/KCC/SRRC/NCC
- Wi-Fi : 802.11 b/g/n/e/i (802.11n up to 150 Mbps)
- A- MPDU and A-MSDU aggregation and 0.4 \_s guard interval support
- Frequency range : 2.4 ~ 2.5 GHz
- Bluetooth : v4.2 BR/EDR and BLE specification
- Radio : NZIF receiver with -98 dBm sensitivity, Class-1, class-2 and class-3 transmitter
- Audio : CVSD and SBC
- On-board clock : 40 MHz crystal
- Operating voltage : 2.2 ~ 3.6V
- Operating current : Average: 80 mA
- Operating temperature range : -40°C ~ 85°C
- Dimensions(mm):58.5(L)x27.7(W)x16.0(H)

## Interface Function
------------------

![Esp321.jpg](https://wiki.elecrow.com/images/thumb/3/36/Esp321.jpg/800px-Esp321.jpg){ loading=lazy }

<font color="red">**EN**</font>  Reset button. Pressing this button resets the system.

<font color="red">**BOOT**</font>  Download button. Holding down the Boot button and pressing the EN button initiates the firmware download mode. Then users can download firmware through the serial port

<font color="red">**USB**</font>  USB interface. It functions as the power supply for the board and the communication interface between PC and ESP-WROOM-32.

<font color="red">**I/O**</font>  Most of the pins on the ESP-WROOM-32 are led out to the pin headers on the board. Users can program ESP32 to enable multiple functions such as PWM, ADC, DAC, I2C, I2S, SPI, etc.

## Usage
-----

### **Installing the ESP32 Arduino Core**

This tutorial covers setting up the ESP32 with Arduino IDE, and documents a few simple example sketches to help make your WiFi/BLE microcontroller work.

#### **Download the Core**

Espressif's official ESP32 Arduino core is hosted here. To install the ESP32 board definitions, you'll need download the contents of the esp32-arduino repository, and place them in a "hardware/espressif/esp32" directory in your Arduino sketchbook directory. First, you need to Create new folder espreesif/esp32, then Download Espressif's official ESP32 Arduino core on [here](https://github.com/espressif/arduino-esp32)and unzip it, copy those files to espreesif/esp32 directory.

![Esp3258.jpg](https://wiki.elecrow.com/images/thumb/e/ed/Esp3258.jpg/600px-Esp3258.jpg){ loading=lazy }

Copy "espreeif" folder to hardware directory. On windows, that may be  <font color="red">C:/program Files/Arduino/hardware </font>, and on Mac that may be <font color="red">/Applications/Arduino.app/Contents/Java/hardware</font>

#### **Install the Xtensa and ESP32 Tools**

To compile code for the ESP32, you need the Xtensa GNU compiler collection (GCC) installed on your machine. Windows users can run ![Esp322.jpg](https://wiki.elecrow.com/images/thumb/7/7b/Esp322.jpg/80px-Esp322.jpg){ loading=lazy }get.exe, found in the  <font color="red">“esp32/tools”</font> folder. Mac and Linux users should run the  <font color="red">tools/get.py</font> python script to download the tools. Using a terminal, navigate to the esp32/tools folder. Then type:

```
python get.py
```

The “get.py” python script will download the Xtensa GNU tools and the ESP32 software development kit (SDK), and unzip them to the proper location. You should see a few new folders in the “tools” directory, including <font color="red">“dist”</font> and <font color="red">“xtensa-esp32-elf”</font> once it’s done.

### **Example: Blink**

Once the ESP32 Arduino core is installed, you should see an “ESP32 Dev Module” option under your “Tools” &gt; “Board” menu. Select the “Upload Speed”-921600 baud, and serial port.

![Esp3221.jpg](https://wiki.elecrow.com/images/0/0e/Esp3221.jpg){ loading=lazy }

For this test. Plus, with the ESP32 attached to your computer, it’s a good time to test out serial. Copy and paste the example sketch below, into a fresh Arduino sketch.

```
int ledPin = 16;

void setup()
{
    pinMode(ledPin, OUTPUT);
    Serial.begin(115200);
}

void loop()
{
    Serial.println("Hello, world!");
    digitalWrite(ledPin, HIGH);
    delay(500);
    digitalWrite(ledPin, LOW);
    delay(500);
}
```

Upload the code! Once the code finishes transferring, open the serial monitor and set the baud rate to 115200. You should see the blue LED “L” keep flashing and “Hello, world” be printed on serial port interface.

![Esp323.jpg](https://wiki.elecrow.com/images/thumb/5/56/Esp323.jpg/600px-Esp323.jpg){ loading=lazy }

### **TEST: WIFI**

#### **Station**

Open the “station.ino” code, you need to change message in the code. Make sure you fill in the  <font color="red">YOUR\_NETWORK\_HERE</font>  and <font color="red">YOUR\_PASSWORD\_HERE</font>  variables with the name (SSID) and password of your WiFi network!

![Esp324.jpg](https://wiki.elecrow.com/images/0/0d/Esp324.jpg){ loading=lazy }

```
#include <WiFi.h>

// WiFi network name and password:
const char * networkName = "YOUR_NETWORK_HERE";
const char * networkPswd = "YOUR_PASSWORD_HERE";

// Internet domain to request from:
const char * hostDomain = "example.com";
const int hostPort = 80;

const int BUTTON_PIN = 0;
const int LED_PIN = 16;

void setup()
{
  // Initilize hardware:
  Serial.begin(115200);
  pinMode(BUTTON_PIN, INPUT_PULLUP);
  pinMode(LED_PIN, OUTPUT);

  // Connect to the WiFi network (see function below loop)
  connectToWiFi(networkName, networkPswd);

  digitalWrite(LED_PIN, LOW); // LED off
  Serial.print("Press button 0 to connect to ");
  Serial.println(hostDomain);
}

void loop()
{
  if (digitalRead(BUTTON_PIN) == LOW)
  { // Check if button has been pressed
    while (digitalRead(BUTTON_PIN) == LOW)
      ; // Wait for button to be released

    digitalWrite(LED_PIN, HIGH); // Turn on LED
    requestURL(hostDomain, hostPort); // Connect to server
    digitalWrite(LED_PIN, LOW); // Turn off LED
  }
}

void connectToWiFi(const char * ssid, const char * pwd)
{
  int ledState = 0;

  printLine();
  Serial.println("Connecting to WiFi network: " + String(ssid));

  WiFi.begin(ssid, pwd);

  while (WiFi.status() != WL_CONNECTED) 
  {
    // Blink LED while we're connecting:
    digitalWrite(LED_PIN, ledState);
    ledState = (ledState + 1) % 2; // Flip ledState
    delay(500);
    Serial.print(".");
  }

  Serial.println();
  Serial.println("WiFi connected!");
  Serial.print("IP address: ");
  Serial.println(WiFi.localIP());
}

void requestURL(const char * host, uint8_t port)
{
  printLine();
  Serial.println("Connecting to domain: " + String(host));

  // Use WiFiClient class to create TCP connections
  WiFiClient client;
  if (!client.connect(host, port))
  {
    Serial.println("connection failed");
    return;
  }
  Serial.println("Connected!");
  printLine();

  // This will send the request to the server
  client.print((String)"GET / HTTP/1.1\r\n" +
               "Host: " + String(host) + "\r\n" +
               "Connection: close\r\n\r\n");
  unsigned long timeout = millis();
  while (client.available() == 0) 
  {
    if (millis() - timeout > 5000) 
    {
      Serial.println(">>> Client Timeout !");
      client.stop();
      return;
    }
  }

  // Read all the lines of the reply from server and print them to Serial
  while (client.available()) 
  {
    String line = client.readStringUntil('\r');
    Serial.print(line);
  }

  Serial.println();
  Serial.println("closing connection");
  client.stop();
}

void printLine()
{
  Serial.println();
  for (int i=0; i<30; i++)
    Serial.print("-");
  Serial.println();
}
```

Then open the serial monitor .![Esp325.jpg](https://wiki.elecrow.com/images/e/e6/Esp325.jpg){ loading=lazy }

![Esp326.jpg](https://wiki.elecrow.com/images/8/8c/Esp326.jpg){ loading=lazy }

When the  <font color="red">“WiFi connected!”</font>  is printed on the serial monitor ,press the BOOT button, your ESP32 wifi/ble module will send a request to example.com and you can see a few message of HTML is printed the serial monitor.

![327.jpg](https://wiki.elecrow.com/images/thumb/3/3c/327.jpg/600px-327.jpg){ loading=lazy }

#### **AP**

Open and upload the “ap.ino” code.

```
#include "WiFi.h"

#define AP_SSID  "esp32"

enum {STEP_AP, STEP_END ,STEP};

void onButton(){
  static uint32_t step = STEP_AP;
  switch(step){

    case STEP_AP://AP Only
      WiFi.mode(WIFI_AP);
      Serial.println("** Starting AP");
      WiFi.softAP(AP_SSID);
    break;
    case STEP_END:
    Serial.println("** Stopping AP");
      WiFi.mode(WIFI_OFF);
 
    default:
    break;
  }
  
 if(step == STEP){
    step = STEP_AP;
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

![Esp3218.jpg](https://wiki.elecrow.com/images/3/3b/Esp3218.jpg){ loading=lazy }

Open the serial monitor.![Esp329.jpg](https://wiki.elecrow.com/images/3/3b/Esp329.jpg){ loading=lazy }

Then press the BOOT key to start AP pattern.

![Esp320.jpg](https://wiki.elecrow.com/images/thumb/7/7f/Esp320.jpg/600px-Esp320.jpg){ loading=lazy }


 The “AP started “ will be printed on the serial minotor. Now you can turn on mobile phones to search WIFI “esp32” and connect to it.

## Resource
--------

- [Code for arduino](https://wiki.elecrow.com/images/c/cf/Code_for_arduino.zip)
- [ESP32S\_WIFI\_BLE\_Board\_v1.0\_Eagle+schematic](https://wiki.elecrow.com/images/8/8b/ESP32S_WIFI_BLE_Board_v1.0.zip)