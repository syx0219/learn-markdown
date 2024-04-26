---
title: USB Host Shield for Arduino
---

## Introduction
------------

USB Host Shield is an inexpensive development board designed to be used in embedded applications which require USB Host functionality. The board supports USB 2.0 full/low speed operation. Primary target platform is Arduino, however, it can also be used with any other micro equipped with SPI interface. This board’s layout is now compatible with much more Arduino compatible boards - not only UNO and Duemilanove, but also big Mega and Mega 2560 work with Standard variant of this shield out of the box. Of course it is compatible with Crowduino, too.

**Model: [ARS3421U](http://www.elecrow.com/usb-host-shield-for-arduino-p-686.html)**

![USB Host Shield for Arduino.jpg](https://wiki.elecrow.com/images/thumb/1/1a/USB_Host_Shield_for_Arduino.jpg/600px-USB_Host_Shield_for_Arduino.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png)](https://www.elecrow.com/usb-host-shield-for-arduino-p-686.html?wiki "Title text")

## Features
--------

Arduino, Crowduino, Seeeduino, Arduino Mega and Crowduino Mega compatible

SPI interface

Power Supply:5V

Dimensions(mm):55.5(L)x53.5(W)x23.5(H)

## Usage
-----

### **Hardware Installation**

Assemble these parts together like the picture below. And mount the shield onto your Arduino/Crowduino.
![USB Host Shield.jpg](https://wiki.elecrow.com/images/thumb/d/d5/USB_Host_Shield.jpg/600px-USB_Host_Shield.jpg){ loading=lazy }

### **Software Programming**

1.First you have to make sure that Arduino1.6.6 has already been installed on your computer.  
2.Download the USB Host Shield 2.0 library here [USB\_Host\_Shield\_2.0-master.zip](https://wiki.elecrow.com/images/8/8a/USB_Host_Shield_2.0-master.zip) and unzip it into the libraries file of Arduino via this path: ..\\arduino-1.6.6\\libraries  
3.Open the code directly by the path:File -&gt; Example -&gt;USB\_Host\_Shield\_2.0-&gt;HID-&gt;USBHIDBootMouse

```
 #include <hidboot.h>
 #include <usbhub.h>
 
 // Satisfy the IDE, which needs to see the include statment in the ino too.
 #ifdef dobogusinclude
 #include <spi4teensy3.h>
 #include <SPI.h>
 #endif
  
 class MouseRptParser : public MouseReportParser
 {
 protected:
 	void OnMouseMove	(MOUSEINFO *mi);
 	void OnLeftButtonUp	(MOUSEINFO *mi);
 	void OnLeftButtonDown	(MOUSEINFO *mi);
 	void OnRightButtonUp	(MOUSEINFO *mi);
 	void OnRightButtonDown	(MOUSEINFO *mi);
 	void OnMiddleButtonUp	(MOUSEINFO *mi);
 	void OnMiddleButtonDown	(MOUSEINFO *mi);
 };
 void MouseRptParser::OnMouseMove(MOUSEINFO *mi)
 {
    Serial.print("dx=");
    Serial.print(mi->dX, DEC);
    Serial.print(" dy=");
    Serial.println(mi->dY, DEC);
 };
 void MouseRptParser::OnLeftButtonUp	(MOUSEINFO *mi)
 {
    Serial.println("L Butt Up");
 };
 void MouseRptParser::OnLeftButtonDown	(MOUSEINFO *mi)
 {
    Serial.println("L Butt Dn");
 };
 void MouseRptParser::OnRightButtonUp	(MOUSEINFO *mi)
 {
    Serial.println("R Butt Up");
 };
 void MouseRptParser::OnRightButtonDown	(MOUSEINFO *mi)
 {
    Serial.println("R Butt Dn");
 };
 void MouseRptParser::OnMiddleButtonUp	(MOUSEINFO *mi)
 {
    Serial.println("M Butt Up");
 };
 void MouseRptParser::OnMiddleButtonDown	(MOUSEINFO *mi)
 {
    Serial.println("M Butt Dn");
 };
 
 USB     Usb;
 USBHub     Hub(&Usb);
 HIDBoot<HID_PROTOCOL_MOUSE>    HidMouse(&Usb);
 
 uint32_t next_time;
 
 MouseRptParser                               Prs;
 
 void setup()
 {
    Serial.begin( 115200 );
 #if !defined(__MIPSEL__)
    while (!Serial); // Wait for serial port to connect - used on Leonardo, Teensy and other boards with built-in USB CDC serial connection
 #endif
    Serial.println("Start");

    if (Usb.Init() == -1)
        Serial.println("OSC did not start.");

    delay( 200 );

    next_time = millis() + 5000;

    HidMouse.SetReportParser(0,(HIDReportParser*)&Prs);
 }
 
 void loop()
 {
  Usb.Task();
 }
```

4.Upload the Code.  
![USB Host1.jpg](https://wiki.elecrow.com/images/thumb/d/d0/USB_Host1.jpg/400px-USB_Host1.jpg){ loading=lazy }   
5.Open the serial monitor. Control the mouse,you can see some information of the mouse.    
![USB Host.png](https://wiki.elecrow.com/images/thumb/b/bd/USB_Host.png/400px-USB_Host.png){ loading=lazy } 

## Resources
---------

- [Arduino library and examples](https://github.com/felis/USB_Host_Shield_2.0)
- [Eagle Files](https://wiki.elecrow.com/images/3/36/UHS_20r10.zip)
- [Manual](https://www.circuitsathome.com/usb-host-shield-hardware-manual)
- [Arduino USB Host Library Introduction](https://www.arduino.cc/en/Reference/USBHost)