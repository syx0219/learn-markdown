---
title: Crowtail- Serial Camera
---

## Description
-----------

The Crowtail Serial Camera is a JPEG color camera module easy for PC&amp; MCU use.It has integrated image processing DSP to generate 320\*240 or 640\*480 JPEG image without thumbnail information, captured picture will be stored in internal buffer and transferred via UART port. The UART Can be configued to TTL or CMOS by hardware.

**Model: [CT009040C](http://www.elecrow.com/crowtail-serial-camera-p-1658.html)**  
![Serial camera 8348.jpg](https://wiki.elecrow.com/images/thumb/3/3d/Serial_camera_8348.jpg/400px-Serial_camera_8348.jpg){ loading=lazy }

## Feature
-------

- Default baud rate of serial port is 38400
- 640x480/320x240(default) resolution
- JPEG compressed image without Thumbnail Information
- 5v power supply
- Crowtail interface
- Easy to use
- Dimensions(mm):32.0(L)x32.0(W)x26.5(H)

## Application
-----------

- Digital Camara with [Wireless SD Card Shield](http://www.elecrow.com/arduino-compatiable-c-109/shield-c-109_110/wireless-sd-shield-p-333.html)
- Vidio Monitoring

## Usage
-----

Here is an example showing how to turn on the Crowtail- Serial camera.

1.Plug it onto the U2 port of Crowtail- Base Shield using a Crowtail cable and plug one button onto digital 12 port.

2.Plug the Crowtail- Base Shield onto Crowduino\_SD (or one Wireless SD Card Shield onto Crowduino)

3\. Connect Arduino to PC by using a USB cable.

![0706serial camera11.jpg](https://wiki.elecrow.com/images/thumb/5/5d/0706serial_camera11.jpg/500px-0706serial_camera11.jpg){ loading=lazy }

4.Download the [Crowtail- Serial Camera Demo Code](https://wiki.elecrow.com/images/6/63/VC0706_Serial_Camera.zip),unzip it and place it to your your arduino sketchfolder/libraries/ folder

5.Open Arduino IDE, File -&gt; examples -&gt;VC0706\_Serial\_Camera -&gt;MotionDetect, you can open the demo code.

![0706camera011.jpg](https://wiki.elecrow.com/images/thumb/e/ea/0706camera011.jpg/400px-0706camera011.jpg){ loading=lazy }

6.Download it to the Crowduino,and open the serial port debug window,you will see the result as bellow:

![0706camera012.jpg](https://wiki.elecrow.com/images/a/a9/0706camera012.jpg){ loading=lazy }

5\. when the check is over, you can move the camera and begin to take photos. the Camera will take a picture and store the picture into the SD card. you can adjust the camera lens to change the focal distance, to make the picture more clear.

![Camera with Arduino pincture.png](https://wiki.elecrow.com/images/thumb/e/e1/Camera_with_Arduino_pincture.png/500px-Camera_with_Arduino_pincture.png){ loading=lazy }

## Resource
--------

- [Crowtail- Serial Camera Demo Code](https://wiki.elecrow.com/images/6/63/VC0706_Serial_Camera.zip)