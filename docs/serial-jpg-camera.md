---
title: Serial JPG Camera
---

## Introduction
------------

This Serial Camera is a JPEG color camera module easy for PC&amp; MCU use.It has integrated image processing DSP to generate 320\*240 or 640\*480 JPEG image without thumbnail information, captured picture will be stored in internal buffer and transferred via UART port.
**Model: [SOD03010S](http://www.elecrow.com/sensor-c-111/object-dectect-c-111_113/serial-jpg-camera-p-422.html)**

<img loading="lazy" src="https://wiki.elecrow.com/images/thumb/6/60/SerialCamera101.jpg/400px-SerialCamera101.jpg" alt="SerialCamera101.jpg" style="zoom:90%;" />
<img loading="lazy" src="https://wiki.elecrow.com/images/thumb/f/f0/SerialCamera111.jpg/400px-SerialCamera111.jpg" alt="SerialCamera111.jpg" style="zoom:90%;" />

## Features
--------

- Default baud rate of serial port is 38400
- 640x480/320x240(default) resolution
- JPEG compressed image without Thumbnail Information
- 5v power supply
- Controlled by UART protocol

## Application
-----------

- Digital Camara with [Wireless SD Card Shield](http://www.elecrow.com/arduino-compatiable-c-109/shield-c-109_110/wireless-sd-shield-p-333.html)
- Vidio Monitoring

## Interface
---------

The Serial JPG Camera module use RS232 to communicate with PC or Microcontrollers.
![SerialCamera interface.jpg](https://wiki.elecrow.com/images/f/f4/SerialCamera_interface.jpg){ loading=lazy }

## Usage
-----

### Use the Serial JPG Camera with PC

**Step 1**:Download dedicated serial port debugging tool [File:Serial Camera software.zip](./files/Serial-Camera-software-zip.md) and install it.  
**Step 2**: Connect Serial camera to PC UART Port with a USB2UART module such as the [USB convertor.](http://www.elecrow.com/arduino-compatiable-c-109/programmer-c-109_118/usbserial-adapter-p-344.html)  
**Step 3:** Open the tool on PC.Choose the correct COM number of the port you link to the camera ,default bautrate 38400,and then open the port.
 ![Debugtool.png](https://wiki.elecrow.com/images/c/c0/Debugtool.png) { loading=lazy }

**Step 4:** Click the button "Reset" to reset the camera.

**Step 5:**:Click "单张拍摄"(Single capture mode) to take a picture. Of course you can modify the image to 640x480 mode, note that you should click the resume button after you modidy the setting.

### Use Camera with Arduino and wirelss SD card shield

Here we use the Serial JPG Camera to make a Arduino Camera.   
First, you need to install a [SD card shield](http://www.elecrow.com/arduino-compatiable-c-109/shield-c-109_110/wireless-sd-shield-p-333.html) to Arduino, to store the pictures with SD card, and a [proto shield](http://www.elecrow.com/arduino-compatiable-c-109/shield-c-109_110/proto-shield-for-arduino-p-336.html) onto the SD shield, install a button on the protoshield so that when the button pressed, the voltage on A5 would be HIGH and LOW when not pressed.  
 And then connect the Serial Camera to Arduino:  
**Camera** &lt;------------&gt; **Arduino**  
TX &lt;-----------&gt; Pin0  
RX &lt;------------&gt;Pin1  
Vcc &lt;------------&gt;5V  
GND &lt;------------&gt; GND  

2\. And then upload the [demo code](#resource) to your Arduino board, note that you may need to take away the RX/TX of camera from Arduino when uploading the code:

![Camera with ArduinoUART.png](https://wiki.elecrow.com/images/thumb/0/0d/Camera_with_ArduinoUART.png/400px-Camera_with_ArduinoUART.png){ loading=lazy }

3\. Press the button , the Camera will take a picture and store the picture into the SD card. you can adjust the camera lens to change the focal distance, to make the picture more clear.

![Camera with Arduino pincture.png](https://wiki.elecrow.com/images/e/e1/Camera_with_Arduino_pincture.png){ loading=lazy }

## Resource
--------

[File:SerialCameral DemoCode.zip](./files/SerialCameral-DemoCode-zip.md)  
Note that it may not work ok in Arduino1.01 sometimes, please download Arduino IDE beyond V1.0.2.