---
title: CC3000 WiFi Shield
---

## Introduction
------------

This is a shield for the CC3000 WiFi Module. The CC3000 from TI (Texas Instruments) is a self-contained wireless network processor that makes incorporating internet connectivity into your project simple. Instead of the more standard UART communication method, the CC3000 module utilizes an SPI interface allowing you, the user, to control the flow of data as you please. What makes the CC3000 unique is its ability to associate to a WiFi access point using a cell phone app in the Texas Instruments process called SmartConfig.

**Model: (Discontinued)**   
![CC3000 WiFi Shield.jpg](https://wiki.elecrow.com/images/thumb/3/38/CC3000_WiFi_Shield1.jpg/600px-CC3000_WiFi_Shield1.jpg){ loading=lazy }

## Features
--------

1. Arduino, Crowduino, Seeeduino, Arduino Mega and Crowduino Mega compatible
2. Support SD card 2GB and 4GB
3. Wireless network processor 
    - IEEE 802.11 b/g ( 2.4GHz)
    - Embedded IPv4 TCP/IP stack
4. Best-in-class radio performance 
    - TX power: +18.0 dBm at 11 Mbps, CCK
    - RX sensitivity: –88 dBm, 8% PER, 11 Mbps
5. Works with low MIPS and low-cost MCUs with compact memory footprint 
    - Small code size (Flash and RAM) required for MCU
6. FCC, IC, CE and TELEC certified reference design with a chip antenna
7. Integrated crystal and power management
8. Small form factor 
    - 16.3 mm × 13.5 mm × 2 mm
9. Operating temperature: –20°C to 70°C
10. SmartConfig technology enables simple Wi-Fi configuration using a smartphone, tablet or PC
11. Proven Wi-Fi interoperability; based on TI’s seventh generation of proven Wi-Fi solutions
12. Complete platform solution including user and porting guides, API guide, sample applications, and support community

## Specifications
--------------
<p style="text-align:center;"><b>CC3000 Specifications</b></p>
|                        | CC3000's Characteristics                                     |
| ---------------------- | ------------------------------------------------------------ |
| Standards              | 802.11 b/g, BSS Station                                      |
| Wi-Fi Security Modes   | WEP, WPA/WPA2 (AES and TKIP – Personal)                      |
| Embedded Wi-Fi         | TCP/IP stack (IPv4 – DHCP client, DNS, mDNS, ARP), Wi-Fi driver, security supplicant, Auto-calibrated radio |
| Required Code size     | As low as 5KB Flash & 360B RAM                               |
| Host Interface         | SPI at 16MHz                                                 |
| Power Modes            | Active Mode (92mA typ RX current), Shutdown Mode (<5uA)      |
| Power Supply           | 2.9V – 4.8V                                                  |
| I/O Voltage            | 1.8V – 3.6V                                                  |
| Connections            | 4 Sockets (UDP or TCP)                                       |
| Throughput (TCP)       | ~4 Mbps***Note** This was measured for CC3000, when combined with MSP430FR5739 |
| Headless Configuration | SmartConfig™ Technology                                      |


## Usage
-----

### **Hardware Installation**

Assemble these parts together like the picture below. and mount the shield onto your Arduino/Crowduino.

### **Software Programming**

1.First you have to make sure that Arduino1.0 has already been installed on your computer.
2.Download the CC3000 WiFi Shield library here [CC3000\_Library.zip](../../files/CC3000-Library-zip.md) and unzip it into the libraries file of Arduino via this path: ..\\arduino-1.0\\libraries  
3.Open the code directly by the path:File -&gt; Example -&gt;CC3000\_Library-&gt;buildtest.

```
#include <Adafruit_CC3000.h>
#include <ccspi.h>
#include <SPI.h>
#include <string.h>
#include "utility/debug.h"

// These are the interrupt and control pins
#define ADAFRUIT_CC3000_IRQ   3  // MUST be an interrupt pin!
// These can be any two pins
#define ADAFRUIT_CC3000_VBAT  5
#define ADAFRUIT_CC3000_CS    10
// Use hardware SPI for the remaining pins
// On an UNO, SCK = 13, MISO = 12, and MOSI = 11
Adafruit_CC3000 cc3000 = Adafruit_CC3000(ADAFRUIT_CC3000_CS, ADAFRUIT_CC3000_IRQ, ADAFRUIT_CC3000_VBAT,
                                         SPI_CLOCK_DIVIDER); // you can change this clock speed but DI

#define WLAN_SSID       "myNetwork"        // cannot be longer than 32 characters!
#define WLAN_PASS       "myPassword"
// Security can be WLAN_SEC_UNSEC, WLAN_SEC_WEP, WLAN_SEC_WPA or WLAN_SEC_WPA2
#define WLAN_SECURITY   WLAN_SEC_WPA2



/**************************************************************************/
/*!
    @brief  Sets up the HW and the CC3000 module (called automatically
            on startup)
*/
/**************************************************************************/
void setup(void)
{
  Serial.begin(115200);
  Serial.println(F("Hello, CC3000!\n")); 

  displayDriverMode();
  Serial.print("Free RAM: "); Serial.println(getFreeRam(), DEC);
  
  /* Initialise the module */
  Serial.println(F("\nInitialising the CC3000 ..."));
  if (!cc3000.begin())
  {
    Serial.println(F("Unable to initialise the CC3000! Check your wiring?"));
    while(1);
  }

  /* Optional: Update the Mac Address to a known value */
/*
  uint8_t macAddress[6] = { 0x08, 0x00, 0x28, 0x01, 0x79, 0xB7 };
   if (!cc3000.setMacAddress(macAddress))
   {
     Serial.println(F("Failed trying to update the MAC address"));
     while(1);
   }
*/
  
  uint16_t firmware = checkFirmwareVersion();
  if (firmware < 0x113) {
    Serial.println(F("Wrong firmware version!"));
    for(;;);
  } 
  
  displayMACAddress();
  
  /* Optional: Get the SSID list (not available in 'tiny' mode) */
#ifndef CC3000_TINY_DRIVER
  listSSIDResults();
#endif
  
  /* Delete any old connection data on the module */
  Serial.println(F("\nDeleting old connection profiles"));
  if (!cc3000.deleteProfiles()) {
    Serial.println(F("Failed!"));
    while(1);
  }

  /* Optional: Set a static IP address instead of using DHCP.
     Note that the setStaticIPAddress function will save its state
     in the CC3000's internal non-volatile memory and the details
     will be used the next time the CC3000 connects to a network.
     This means you only need to call the function once and the
     CC3000 will remember the connection details.  To switch back
     to using DHCP, call the setDHCP() function (again only needs
     to be called once).
  */
  /*
  uint32_t ipAddress = cc3000.IP2U32(192, 168, 1, 19);
  uint32_t netMask = cc3000.IP2U32(255, 255, 255, 0);
  uint32_t defaultGateway = cc3000.IP2U32(192, 168, 1, 1);
  uint32_t dns = cc3000.IP2U32(8, 8, 4, 4);
  if (!cc3000.setStaticIPAddress(ipAddress, netMask, defaultGateway, dns)) {
    Serial.println(F("Failed to set static IP!"));
    while(1);
  }
  */
  /* Optional: Revert back from static IP addres to use DHCP.
     See note for setStaticIPAddress above, this only needs to be
     called once and will be remembered afterwards by the CC3000.
  */
  /*
  if (!cc3000.setDHCP()) {
    Serial.println(F("Failed to set DHCP!"));
    while(1);
  }
  */

  /* Attempt to connect to an access point */
  char *ssid = WLAN_SSID;             /* Max 32 chars */
  Serial.print(F("\nAttempting to connect to ")); Serial.println(ssid);
  
  /* NOTE: Secure connections are not available in 'Tiny' mode!
     By default connectToAP will retry indefinitely, however you can pass an
     optional maximum number of retries (greater than zero) as the fourth parameter.
     
     ALSO NOTE: By default connectToAP will retry forever until it can connect to
     the access point.  This means if the access point doesn't exist the call
     will _never_ return!  You can however put in an optional maximum retry count
     by passing a 4th parameter to the connectToAP function below.  This should
     be a number of retries to make before giving up, for example 5 would retry
     5 times and then fail if a connection couldn't be made.
  */
  if (!cc3000.connectToAP(WLAN_SSID, WLAN_PASS, WLAN_SECURITY)) {
    Serial.println(F("Failed!"));
    while(1);
  }
   
  Serial.println(F("Connected!"));
  
  /* Wait for DHCP to complete */
  Serial.println(F("Request DHCP"));
  while (!cc3000.checkDHCP())
  {
    delay(100); // ToDo: Insert a DHCP timeout!
  }  

  /* Display the IP address DNS, Gateway, etc. */  
  while (! displayConnectionDetails()) {
    delay(1000);
  }
  
#ifndef CC3000_TINY_DRIVER
  /* Try looking up www.adafruit.com */
  uint32_t ip = 0;
  Serial.print(F("www.adafruit.com -> "));
  while  (ip  ==  0)  {
    if  (!  cc3000.getHostByName("www.adafruit.com", &ip))  {
      Serial.println(F("Couldn't resolve!"));
    }
    delay(500);
  }  
  cc3000.printIPdotsRev(ip);
  
  /* Do a quick ping test on adafruit.com */  
  Serial.print(F("\n\rPinging ")); cc3000.printIPdotsRev(ip); Serial.print("...");  
  uint8_t replies = cc3000.ping(ip, 5);
  Serial.print(replies); Serial.println(F(" replies"));
  if (replies)
    Serial.println(F("Ping successful!"));
#endif

  /* You need to make sure to clean up after yourself or the CC3000 can freak out */
  /* the next time you try to connect ... */
  Serial.println(F("\n\nClosing the connection"));
  cc3000.disconnect();
}

void loop(void)
{
  delay(1000);
}

/**************************************************************************/
/*!
    @brief  Displays the driver mode (tiny of normal), and the buffer
            size if tiny mode is not being used

    @note   The buffer size and driver mode are defined in cc3000_common.h
*/
/**************************************************************************/
void displayDriverMode(void)
{
  #ifdef CC3000_TINY_DRIVER
    Serial.println(F("CC3000 is configure in 'Tiny' mode"));
  #else
    Serial.print(F("RX Buffer : "));
    Serial.print(CC3000_RX_BUFFER_SIZE);
    Serial.println(F(" bytes"));
    Serial.print(F("TX Buffer : "));
    Serial.print(CC3000_TX_BUFFER_SIZE);
    Serial.println(F(" bytes"));
  #endif
}

/**************************************************************************/
/*!
    @brief  Tries to read the CC3000's internal firmware patch ID
*/
/**************************************************************************/
uint16_t checkFirmwareVersion(void)
{
  uint8_t major, minor;
  uint16_t version;
  
#ifndef CC3000_TINY_DRIVER  
  if(!cc3000.getFirmwareVersion(&major, &minor))
  {
    Serial.println(F("Unable to retrieve the firmware version!\r\n"));
    version = 0;
  }
  else
  {
    Serial.print(F("Firmware V. : "));
    Serial.print(major); Serial.print(F(".")); Serial.println(minor);
    version = major; version <<= 8; version |= minor;
  }
#endif
  return version;
}

/**************************************************************************/
/*!
    @brief  Tries to read the 6-byte MAC address of the CC3000 module
*/
/**************************************************************************/
void displayMACAddress(void)
{
  uint8_t macAddress[6];
  
  if(!cc3000.getMacAddress(macAddress))
  {
    Serial.println(F("Unable to retrieve MAC Address!\r\n"));
  }
  else
  {
    Serial.print(F("MAC Address : "));
    cc3000.printHex((byte*)&macAddress, 6);
  }
}


/**************************************************************************/
/*!
    @brief  Tries to read the IP address and other connection details
*/
/**************************************************************************/
bool displayConnectionDetails(void)
{
  uint32_t ipAddress, netmask, gateway, dhcpserv, dnsserv;
  
  if(!cc3000.getIPAddress(&ipAddress, &netmask, &gateway, &dhcpserv, &dnsserv))
  {
    Serial.println(F("Unable to retrieve the IP Address!\r\n"));
    return false;
  }
  else
  {
    Serial.print(F("\nIP Addr: ")); cc3000.printIPdotsRev(ipAddress);
    Serial.print(F("\nNetmask: ")); cc3000.printIPdotsRev(netmask);
    Serial.print(F("\nGateway: ")); cc3000.printIPdotsRev(gateway);
    Serial.print(F("\nDHCPsrv: ")); cc3000.printIPdotsRev(dhcpserv);
    Serial.print(F("\nDNSserv: ")); cc3000.printIPdotsRev(dnsserv);
    Serial.println();
    return true;
  }
}

/**************************************************************************/
/*!
    @brief  Begins an SSID scan and prints out all the visible networks
*/
/**************************************************************************/

void listSSIDResults(void)
{
  uint32_t index;
  uint8_t valid, rssi, sec;
  char ssidname[33]; 

  if (!cc3000.startSSIDscan(&index)) {
    Serial.println(F("SSID scan failed!"));
    return;
  }

  Serial.print(F("Networks found: ")); Serial.println(index);
  Serial.println(F("================================================"));

  while (index) {
    index--;

    valid = cc3000.getNextSSID(&rssi, &sec, ssidname);
    
    Serial.print(F("SSID Name    : ")); Serial.print(ssidname);
    Serial.println();
    Serial.print(F("RSSI         : "));
    Serial.println(rssi);
    Serial.print(F("Security Mode: "));
    Serial.println(sec);
    Serial.println();
  }
  Serial.println(F("================================================"));

  cc3000.stopSSIDscan();
}
```

4.Before you run the sketch, edit it to replace the dummy SSID and password with your own:

```
 #define WLAN_SSID       "yourNetwork"        // cannot be longer than 32 characters!
 #define WLAN_PASS       "yourPassword"
```

If you're using WEP, the password should look like this:

```
const char WLAN_PASS[] = {0x1A, 0x2B, 0x3C, 0x4D, 0x5E, 0x00}; 
```

Since it's a collection of bytes not 'passphrase' style key Also, make sure that the right wireless security scheme is selected (unsecured, WEP, WPA, or WPA2) Copy Code

// Security can be WLAN\_SEC\_UNSEC, WLAN\_SEC\_WEP, WLAN\_SEC\_WPA or WLAN\_SEC\_WPA2

```
#define WLAN_SECURITY   WLAN_SEC_WPA2
```

5.Here's a sample of the Serial Monitor output of buildtest. You should see something similar:
![CC3000 WiFi Shield serial1.jpg](https://wiki.elecrow.com/images/thumb/7/78/CC3000_WiFi_Shield_serial1.jpg/500px-CC3000_WiFi_Shield_serial1.jpg){ loading=lazy }
![CC3000 WiFi Shield serial2.jpg](https://wiki.elecrow.com/images/thumb/b/b0/CC3000_WiFi_Shield_serial2.jpg/500px-CC3000_WiFi_Shield_serial2.jpg){ loading=lazy }

## Resource
--------

- [CC3000 Library](../../files/CC3000-Library-zip.md)
- [More usage](https://learn.adafruit.com/adafruit-cc3000-wifi/cc3000-library-software)
- [File:CC3000 Module.pdf](../../files/CC3000-Module-pdf.md "File:CC3000 Module.pdf")