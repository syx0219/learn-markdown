---
title: Crowbits-GPS
---

## Description
-----------

GPS is a high-precision radio navigation positioning system based on aerial satellites. It can provide accurate geographic location, vehicle speed and accurate time information anywhere in the world and near-Earth space.

![Crowbits-GPS-1.jpg](https://wiki.elecrow.com/images/thumb/a/ae/Crowbits-GPS-1.jpg/600px-Crowbits-GPS-1.jpg){ loading=lazy }

## Features
--------

- Low power consumption
- Easy to use

## Specification
-------------

- Interface Type: UART
- Operating Voltage: 3.3V DC
- Dimensions: 56(L)\*31(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the D2 and D3 interface on the Crowbits-UNO board, as shown in the figure:

![Crowbits-GPS-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/9/95/Crowbits-GPS-Wiki_1.JPG/600px-Crowbits-GPS-Wiki_1.JPG){ loading=lazy }

3\. Upload the following code to the Crowbits-UNO board.

```
//at 9600 bps 8-N-1
//Computer is connected to Arduino/Crowduino
//SoftSerial Shield is connected to the Software UART:D2&D3 
 
#include <SoftwareSerial.h>
 
SoftwareSerial SoftSerial(2, 3);
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

4\. After the upload is successful, open the serial port monitor, the baud rate is set to 9600. The serial port will print the GPS address information.

![Crowbits-GPS-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/4/4f/Crowbits-GPS-Wiki_2.jpg/600px-Crowbits-GPS-Wiki_2.jpg){ loading=lazy }