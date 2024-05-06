---
title: 32u4 with A6 GPRS/GSM
---

## Introduction
------------

The 32U4 with A6 GSM/GPRS Board is based on mega32U4 and A6 GSM/GPRS module. It can be used to call and seed text messages, via GPRS to upload data to server. At the same time it leads to an analog interface, an IIC interface and 2 digital interface. which you can connect to other module more easily.

**Model: (Discontinued)**
![GSM.JPG](https://wiki.elecrow.com/images/thumb/0/08/GSM.JPG/600px-GSM.JPG){ loading=lazy }

## Features
--------

- 32U4+A6
- Work voltage: 5V
- Operating temperature -30 ℃ to + 80 ℃;
- Three kinds of interface
- 3.7V Battery power supply
- Low standby current
- Standby average current 3ma less;
- Support the GSM / GPRS Quad-band, including 850,900,1800,1900MHZ;
- Support China Mobile and China Unicom's 2G GSM network worldwide;
- GPRS Class 10;
- Sensitivity &lt;-105;
- Support voice calls;
- Support SMS text messaging;
- Support GPRS data traffic, the maximum data rate, download 85.6Kbps, upload 42.8Kbps;
- Supports standard GSM07.07,07.05 AT commands and extended commands Ai-Thinker;
- Supports two serial ports, a serial port to download an AT command port;
- AT command supports the standard AT and TCP / IP command interface;
- Support digital audio and analog audio support for HR, FR, EFR, AMR speech coding;
- Support ROHS, FCC, CE, CTA certification;

## Specifications
--------------

- Quad-band: 850/900/1800/1900 MHz
- GPRS multi-slot: 12, 1 to 12 may be configured
- GPRS mobile station: Class B
- Compatible with GSM Phase 2/2 +: Class 4 (2W @ 850/900 MHz) Class 1 (1W @ 1800 / 1900MHz)
- Current consumption: 1.3mA @ DRX = 5; 1.2mA @ DRX = 9
- AT command control: Standard GSM07.07,07.05 AT commands and extended commands Ai-Thinker
- SIM Application Toolkit
- GPRS Class 10: Up 85.6 kbps (upstream) &amp; 42.8Kbps (downlink)
- PBCCH support
- Coding scheme: CS 1, 2, 3, 4
- Support CSD: Up 14.4 kbps
- Support USSD
- Stack: PPP / TCP / UDP / HTTP / FTP / SMTP / MUX

## Cautions
--------

- <font color="red">Make sure your SIM card is unlocked.</font>
- <font color="red">The product is provided as is without an insulating enclosure. Please observe ESD precautions specially in dry (low humidity) weather.</font>
- <font color="red">It just supports baud rate 115200bps.</font>

## Interface Function
------------------

![32u4 with A6002.jpg](https://wiki.elecrow.com/images/thumb/e/eb/32u4_with_A6002.jpg/600px-32u4_with_A6002.jpg){ loading=lazy }

Usage
-----

### **Connect the Antenna**

1.A miniature coaxial RF connector is present on the 32u4 with A6 GPRS/GSM to connect with a GSM Antenna. The connector present on the 32u4 with A6 GPRS/GSM is called a [U.FL connecto](http://en.wikipedia.org/wiki/Hirose_U.FL).The GSM Antenna supplied with the GPRS Shield has an [SMA connector](http://en.wikipedia.org/wiki/SMA_connector) (and not an RP-SMA connector) on it.The connection topology is shown in the diagram below:

![32u4 with A6003.jpg](https://wiki.elecrow.com/images/thumb/1/13/32u4_with_A6003.jpg/500px-32u4_with_A6003.jpg){ loading=lazy }

### **Insert an Micro SIM card to SIM Card Holder**

2.Pin Holder for SIM Cards. Both 1.8 volts and 3.0 volts SIM Cards are supported by A6 GPRS/GSM Module, the SIM card voltage type is automatically detected.
![32u4 with A6004.jpg](https://wiki.elecrow.com/images/thumb/e/ea/32u4_with_A6004.jpg/500px-32u4_with_A6004.jpg){ loading=lazy }

### **Download Code**

Connect the USB cable to the 32u4 with A6 GPRS/GSM board,then download the code as below:

```


#include<stdio.h>
#include<string.h>
#define DEBUG true
 
void setup()
{
  Serial.begin(115200);
  Serial1.begin(115200);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(8,OUTPUT);
  digitalWrite(5, HIGH); 
  digitalWrite(4, LOW); 
  digitalWrite(8, LOW); 
  Serial.println("After 5s, test begin!!");
  delay(5000);
}

void loop()
{
  Serial.println("Test begin!!");
  digitalWrite(8, HIGH); 
  delay(3000);       
  digitalWrite(8, LOW);
  Serial.println("A6 Power ON!");
  Serial.println("You may receive the AT   OK"); 
   sendData( "AT",1000,DEBUG);
  sendData( "AT",1000,DEBUG);
  Serial.println("A6 go to sleep now!"); 
   digitalWrite(5, LOW);  //sleep
   delay(2000);
   Serial.println("call 10086");
   call();          //no call, A6 sleeping   
   sendData( "AT",1000,DEBUG);
   Serial.println("if you hear the voice and receive AT   OK,test failed!");
   digitalWrite(5, HIGH);   // wake up
   delay(1000);
   Serial.println("A6 WAKE UP!"); 
   Serial.println("test it weather wakaup, if re ok, a6 wakeup"); 
   sendData( "AT",1000,DEBUG);     
   Serial.println("A6 power off!"); 
   digitalWrite(4, HIGH); // power off A6
   delay(2000);
   digitalWrite(4, LOW);
   Serial.println("pringt AT and you not re OK"); 
   sendData( "AT",1000,DEBUG);      //NO RE OK
     Serial.println("A6 NO RESBOND"); 
   digitalWrite(8, HIGH);           //POWER UP
  delay(3000);       
  digitalWrite(8, LOW);
  delay(5000);
  Serial.println("A6 Power ON!"); 
   delay(5000);
   Serial.println("................................."); 
   sendData( "AT",1000,DEBUG); //TEST AND MAKE CALL
   delay(3000);
   call();
   Serial.println("A6 Test complete!");
   while(1);
}

void call(void)
   {
         sendData( "AT+CSQ",1000,DEBUG);     
         sendData("AT+SNFS=0",1000,DEBUG);
         sendData("ATD10086;",1000,DEBUG);
         delay(10000);
         sendData( "ATH",1000,DEBUG);
   }

String sendData(String command, const int timeout, boolean debug)
{
    String response = "";    
    Serial1.println(command); 
    long int time = millis();   
    while( (time+timeout) > millis())
    {
      while(Serial1.available())
      {       
        char c = Serial1.read(); 
        response+=c;
      }  
    }    
    if(debug)
    {
      Serial.print(response);
    }    
    return response;
}



```

After you complete download the code, open the serial debug window(notice set the baud rate 115200), you will see some information as bellow:

![32u4 with A6005.jpg](https://wiki.elecrow.com/images/thumb/3/33/32u4_with_A6005.jpg/500px-32u4_with_A6005.jpg){ loading=lazy }

## Resource
--------

- [32u4 with A6 GPRS/GSM eagle file](./files/32u4-with-A6-GPRSGSM-zip.md)