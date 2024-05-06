---
title: Crowtail- GPS
---

## Description
-----------

This Crowtail - GPS module is a cost-efficient and field-programmable gadget armed with a SIM28 (U-blox 6 is old version) and serial communication configuration. It features 22 tracking / 66 acquisition channel GPS receiver. The sensitivity of tracking and acquisition both reach up to -160dBm, making it a great choice for personal navigation projects and location services, as well as an outstanding one among products of the same price class.

**Model: [CT0055GPS](http://www.elecrow.com/crowtailgps-p-1515.html)**

![Crowtail- GPS.JPG](https://wiki.elecrow.com/images/thumb/c/c7/Crowtail-_GPS.JPG/400px-Crowtail-_GPS.JPG){ loading=lazy }

## Specification
-------------

- Input Voltage: 3.3V, 5V
- BaudRate: 4800 - 57600( u-blox version)
- BaudRate: 9600 - 115200
- Default BaudRate: 9600
- Supports NMEA and U-Blox 6 protocols
- Low power consumption
- Baud rates configurable
- Crowtail compatible interface
- Dimensions(mm):40.0(L)x20.0(W)x6.8(H)

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

Third, Open the serial monitor, select the serial rate as 9600. you will get the data return from the GPS module.  
![Return data.jpg](https://wiki.elecrow.com/images/3/37/Return_data.jpg){ loading=lazy }

### **Application 2: Use the u-center software to Locate your place**

1\. Down load the [U-center software](http://www.elecrow.com/wiki/images/4/4a/U-centersetup-7.0.2.1.zip). you can also go to the U-blox office website to download this software. And install it.  
2\. Upload the demo code in Application 1 to Arduino.  
3\. Open U-center, choose the serial port and set the serial rate as 9600. After a while, you will get the location of the GPS shield.  
![U-center.jpg](https://wiki.elecrow.com/images/thumb/e/e3/U-center.jpg/800px-U-center.jpg){ loading=lazy }

## Resource
--------

- [u-centersetup\_v8.18](./files/U-centersetup-v8.18.zip.md)
- [u-center\_UserGuide\_(UBX-13005250)](./files/U-center-UserGuide(UBX-13005250)pdf.md)
- [UART-GPS-NEO-6M](./files/UART-GPS-NEO-6M-zip.md)
- [Crowtail GPS Program](./files/Crowtail-GPS.zip.md)
- [Crowtail- GPS v1.0 eagle files](./files/Crowtail-GPS-v1.0-zip.md)