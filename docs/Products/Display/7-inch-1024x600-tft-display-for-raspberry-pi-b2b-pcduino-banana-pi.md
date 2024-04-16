---
title: 7 Inch 1024x600 TFT Display for Raspberry Pi B+ Pcduino Banana Pi
---

## Description
-----------

This LCD module is 1024x600 dots 7 " color TFT LCD module display with HDMI, VGA, Video, AV signal driver board, superior display quality, super wide view angle. It can be used in any embedded system, car, industrial device, security and hand-held equipment which requires display in high quality and colorful video. Its HDMI interface is fully compatible with Raspberry Pi, pcduino and Banana Pi platform.


**Model:[RPA07800R](https://www.elecrow.com/7-inch-800x480-tft-display-for-raspberry-pi-b-pcduino-banana-pi-p-1413.html)**

```
==Interface Function ==
```

![7 Inch 800x480 TFT Display for Raspberry Pi B+ Pcduino Banana Pi.png](https://wiki.elecrow.com/images/3/35/7_Inch_800x480_TFT_Display_for_Raspberry_Pi_B%2B_Pcduino_Banana_Pi.png){ loading=lazy }

## Features
--------

- A good solution for those seeking for a bigger resolution display
- Good touch response
- Supports Banana Pi / Banana Pro, comes with Lubuntu, Raspbian images
- Supports BB Black, comes with Angstrom image
- Supports Raspberry Pi, comes with Raspbian driver (works with your Raspbian directly), and Ubuntu image
- Not only for mini-PCs, it can work as a computer monitor just like any other general HDMI screen (touch function is unavailable in this case)
- Backlight control to lower power consumption
- HDMI interface for displaying, USB interface for touch control

## Specifications
--------------

- LCD Type:TFT
- 7 inch TFT Capacitive touch screen display, 1024x600 Resolution
- HDMI input
- USB touch and power, 5V@1A
- Lcd Size：164.7mm\*107.1mm
- Weight:360g

## Usage
-----

When users connect the Raspberry Pi to use, they need to configure the official system. Or you can also burn the configured system image directly.

### **Hardware Connection**

1\. Connect the HDMI Connector to both the HDMI interfaces on the LCD and the Pi.  
2\. LCD and Pi connect power.  
3\. Turn on the "backlight" switch on the back of the LCD.  
![Ex.jpg](https://wiki.elecrow.com/images/thumb/d/d2/Ex.jpg/600px-Ex.jpg){ loading=lazy }

### **Bruning the Image**

### **Method 1. Using Ready-to-use image**

The image file with pre-installed driver is located in the IMAGE directory of the DVD. Extract the IMAGE file and you will get an .img file.
you can refer to the :[5 Inch 800x480 TFT Display](./hdmi-interface-5-inch-800x480-tft-display.md)

### **Method 2. Driver installation**

### **Step1: Download the latest system and unzip the image**

For Raspbian: (Not LITE version)  
[https://www.raspberrypi.org/downloads/raspbian/](https://www.raspberrypi.org/downloads/raspbian/)  
For Ubuntu Mate:  
[https://ubuntu-mate.org/download/#xenial](https://ubuntu-mate.org/download/#xenial)  
For Kali:  
[https://www.offensive-security.com/kali-linux-arm-images/](https://www.offensive-security.com/kali-linux-arm-images/)  
For Retropie:  
[https://retropie.org.uk/download/](https://retropie.org.uk/download/)  
And then unzip the image file.(Next step will use it.)  

### **Step2: Bruning the Image to SD Card**

How to bruning an image to a micro SD card for your Pi? you can refer to the :[5 Inch 800x480 TFT Display](./hdmi-interface-5-inch-800x480-tft-display.md)

### **Step3: Find the config.txt in the SD`s root and open it. Then add the following code in the end according to resolution.**

```
hdmi_force_hotplug=1
max_usb_current=1
hdmi_group=2
hdmi_mode=1
hdmi_mode=87
hdmi_cvt 1024 600 60 6 0 0 0
hdmi_drive=1
```

### **Step2: Insert SD card and Power ON**

The screen should be working now.
![E.jpg](https://wiki.elecrow.com/images/thumb/3/30/E.jpg/600px-E.jpg){ loading=lazy }

## Install Soft Keyboard
---------------------

- Install the reference link：[https://github.com/Elecrow-keen/Elecrow-LCD5/wiki/How-to-Install-Soft-Keyboard](https://github.com/Elecrow-keen/Elecrow-LCD5/wiki/How-to-Install-Soft-Keyboard)