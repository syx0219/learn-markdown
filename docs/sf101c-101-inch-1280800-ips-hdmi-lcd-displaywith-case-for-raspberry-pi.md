---
title: SF101C 10.1 inch 1280*800 IPS HDMI LCD Display(with case) for Raspberry Pi
---

## Description
-----------

This is the latest 10.1-inch screen for raspberry pi, under normal circumstances we used to match the raspberry pi, of course, it is compatible with many occasions due to its HDMI interface. Its IPS screen has 1280 \* 800 high resolution, and this is a capacitive screen, which means high sensitivity, supports up to ten-points touch, when it works with raspberry pi, it is not required to driver support, and compatible with many systems, including win10/8/7 .

**Model:[DRD01230D](https://www.elecrow.com/10-1-inch-1280-800-ips-hdmi-lcd-display-with-case-for-raspberry-pi.html)**

![SF101C 10.1 inch 1280800 IPS HDMI LCD Display(with case) for Raspberry Pi 1.jpg](https://wiki.elecrow.com/images/thumb/3/3b/SF101C_10.1_inch_1280800_IPS_HDMI_LCD_Display%28with_case%29_for_Raspberry_Pi_1.jpg/600px-SF101C_10.1_inch_1280800_IPS_HDMI_LCD_Display%28with_case%29_for_Raspberry_Pi_1.jpg){ loading=lazy }

## Features
--------

- IPS raspberry pi screen,1280×800 high resolution.
- Capacitive touch control, supports up to ten-points touch.
- When works with Raspberry Pi, supports Raspbian, Ubuntu, single touch, and driver free.
- Supports Banana Pi, Banana Pro, comes with Ubuntu, Raspbian images.
- Supports BB Black, comes with Angstrom image.
- HDMI interface for displaying, USB interface for touch control.
- Backlight control to lower power consumption.

## Specifications
--------------

- Model: SF101C
- Working Voltage：DC 5V
- Resolution: 1280 x 800

## Usage
-----

### **1: Working with Raspberry Pi**

When working with Raspberry Pi, you should set the resolution of the LCD by yourself, or else the LCD screen will not work.

Step 1: Please download the image of the latest version from Raspberry Pi's website.
[https://www.raspberrypi.org/downloads/raspbian/](https://www.raspberrypi.org/downloads/raspbian/)
Step 2: Download the compressed file to your PC and unpack it to get the .Img file.  
Step 3: The TF card is connected to the PC and formatted using the SDFormatter software.  
Step 4Open the Win32DiskImager software, select the system image prepared in step 1, and click write to burn the system image.  
Step 5:After the programming is completed, open the config.txt file in the root directory of the TF card, and add the following code at the end of "config.txt" to save and safely eject the TF card.  


max\_usb\_current=1  
hdmi\_group=2  
hdmi\_mode=87  
hdmi\_cvt 1280 800 60 6 0 0 0  
hdmi\_drive=1  

Step 6: Save and insert the TF card into the Raspberry Pi.  
Step 7: Connect the HDMI port of the LCD to the HDMI port on your Pi with a HDMI cable.  
Step 8: Connect the Touch port of the LCD to one of the USB ports on your Pi.  
Step 9: Connect the Power Only Port of the LCD to 5V 2.5A power adapter with a Type A to micro USB cable.  
Step 10: Turn on the “backlight” switch on the back of the LCD.  
![SF101C 10.1 inch 1280800 IPS HDMI LCD Display(with case) for Raspberry Pi 2.jpg](https://wiki.elecrow.com/images/thumb/0/0e/SF101C_10.1_inch_1280800_IPS_HDMI_LCD_Display%28with_case%29_for_Raspberry_Pi_2.jpg/600px-SF101C_10.1_inch_1280800_IPS_HDMI_LCD_Display%28with_case%29_for_Raspberry_Pi_2.jpg){ loading=lazy }

### **2：Use as PC Monitor**

This product supports Windows 10/8.1/7.  
Step 1: Connect the HDMI port of the LCD to the HDMI port on your PC with a HDMI cable.  
Step 2: Connect the Touch port of the LCD to one of the USB ports on your PC.  
Step 3: Connect the Power Only Port of the LCD to a 5V 2.5A power adapter with a Type A to micro USB cable.  
Step 4: Turn on the backlight switch on the back of LCD.  