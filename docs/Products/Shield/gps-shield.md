---
title: GPS Shield
---

## Description
-----------

The GPS Shield is base on the ublox's NEO-6M receiver module , and the footprints is compatible with Arduino/MEGA boards. The regular GPS pins (RX, TX) can be connected to D0-D7 of Arduino. Support software SerialPort and Micro SD card interface.

It's very easy using. You just need read SerialPort and then will get the GPS data. It also could use with GPRS Shield(click here to know how to use GPRS). So you can send GPS data to phone by SMS, then you can get the position of the GPS Shield.

The GPS Shield module interfaces to the customerâ&#128;&#153;s application via one serial port, which uses CMOS voltage levels. support 3.3V / 5V IO operating. That's means 100% all Arduino main board compatible.

**Model: [MCS01107S](http://www.elecrow.com/gps-shield-with-antenna-p-696.html)**  
![GPS Shield.jpg](https://wiki.elecrow.com/images/thumb/7/7f/GPS_Shield.jpg/400px-GPS_Shield.jpg){ loading=lazy }

## Features
--------

- With standard Shield interfaceï¼&#140;it is compatible to all arduino main board.
- With Micro SD interface
- 3.3v and 5v logical voltage compatible
- Active antenna design with high receive sensitivity, compatible normal antenna
- Extremely fast time to first fix at low signal level
- Operation temperature: -40c&#132;&#131; ~ +85c

## Specifications
--------------

NEO-6M-0-001

## Interface function
------------------

![Interface GPS Shield.png](https://wiki.elecrow.com/images/0/01/Interface_GPS_Shield.png){ loading=lazy }

## Usage
-----

### **Application 1: Print the GPS data with serial port**

This example simply prints the output of the frames received by the GPS module to the serial port of an arduino.  
first, connect the UART\_RX to PD3, UART\_TX to PD2.  
second, upload the following demo code to Arduino or Crowduino.

```
//at 9600 bps 8-N-1
//Computer is connected to Arduino/Crowduino
//SoftSerial Shield is connected to the Software UART:D2&D3 
 
#include <SoftwareSerial.h>
 
SoftwareSerial SoftSerial(6, 7);
unsigned char buffer[256]; // buffer array for data recieve over serial port
int count=0;     // counter for buffer array 
void setup()
{
  SoftSerial.begin(9600);               // the SoftSerial baud rate   
  Serial.begin(9600);             // the Serial port of Arduino baud rate.
 
}
 
void loop()
{
  if (SoftSerial.available())              // if date is comming from softwareserial port ==> data is comming from SoftSerial shield
  {
    while(SoftSerial.available())          // reading data into char array 
    {
      buffer[count++]=SoftSerial.read();     // writing data into array
      if(count == 256)break;
  }
    Serial.write(buffer,count);            // if no data transmission ends, write buffer to hardware serial port
    clearBufferArray();              // call clearBufferArray function to clear the storaged data from the array
    count = 0;                       // set counter of while loop to zero
 
 
  }
  if (Serial.available())            // if data is available on hardwareserial port ==> data is comming from PC or notebook
    SoftSerial.write(Serial.read());       // write it to the SoftSerial shield
}
void clearBufferArray()              // function to clear buffer array
{
  for (int i=0; i<count;i++)
    { buffer[i]=NULL;}                  // clear all index of array with command NULL
}
```

Third, Open the serial monitor, select the serial rate as 9600. you will get the data return from the GPS modual.  
![Return data.jpg](https://wiki.elecrow.com/images/3/37/Return_data.jpg){ loading=lazy }

### **Application 2: Use the u-center software to Locate your place**

1\. Down load the [U-center software](http://www.elecrow.com/wiki/images/4/4a/U-centersetup-7.0.2.1.zip). you can also go to the U-blox office website to download this software. And install it.  
2\. Upload the demo code in Application 1 to Arduino.  
3\. Open U-center, choose the serial port and set the serial rate as 9600. After a while, you will get the location of the GPS shield.  
![U-center.jpg](https://wiki.elecrow.com/images/thumb/e/e3/U-center.jpg/800px-U-center.jpg){ loading=lazy }

## See Also
--------

- [GSM/GPRS wiki](./gprsgsm-shield-v10.md)
- [SD card shield wiki](./wireless-sdshield.md)

## FAQ
---

Please feel free to connect with techsupport@elecrow.com. We will list the normal question here and do our best to solve your problem.

## Resouce
-------

- [Schematic of GPS Shield](https://wiki.elecrow.com/images/7/7b/ELEC_GPS_Shield_v1.1.pdf)  
- [Gerber file&amp; eagle file of GPS Shield](https://wiki.elecrow.com/images/f/f3/Gps_gerber%26Eagle_file.zip)  
- [Test software U-centersetup-7.0.2.1](http://www.elecrow.com/wiki/images/4/4a/U-centersetup-7.0.2.1.zip)  
- [SD library for Arduino1.0.](https://wiki.elecrow.com/images/5/5c/SD_for_arduino1.0.zip)  
- [SdFat for Arduino1.0](http://code.google.com/p/beta-lib/downloads/detail?name=SdFatBeta20120327.zip&can=2&q=)
- [SoftwareSerial library for arduino1.0](../../files/SoftwareSerial-zip.md)  