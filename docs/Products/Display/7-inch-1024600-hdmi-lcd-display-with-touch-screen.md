---
title: 7 Inch 1024*600 HDMI LCD Display with Touch Screen
---

## Description
-----------

This 7 inch HDMI LCD supports various systems like Raspberry Pi,Banana Pi,Banana Pro,BB Black to provide Lubuntu，Raspbian with and Angstrom images with high resolution of 1024×600 and capacitive Touch Screen. Besides it upgrades to IPS screen with larger visible angle and more clear display effect. Broadly you can apply it to raspberry pi, HDMI display screen and other mini PC or even computer display.

**Model:[RPD10246D](https://www.elecrow.com/7-inch-1024-600-hdmi-lcd-display-with-touch-screen.html)**

![01.jpg](https://wiki.elecrow.com/images/thumb/4/4e/01.jpg/600px-01.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/7-inch-1024-600-hdmi-lcd-display-with-touch-screen.html?wiki "Title text")

## Features
--------

- A good solution for those seeking for a bigger resolution display
- Good touch response
- Supports Banana Pi / Banana Pro, comes with Lubuntu, Raspbian images
- Supports BB Black, comes with Angstrom image
- Supports Raspberry Pi, comes with Raspbian driver (works with your Raspbian directly), and Ubuntu image
- Not only for mini-PCs, it can work as a computer monitor just like any other general HDMI screen (touch function is unavailable in this case)
- Back light control to lower power consumption
- HDMI interface for displaying, USB interface for touch control

## Specifications
--------------

- LCD Type:TFT
- 7 inch TFT Capacitive touch screen display, 1024x600 Resolution
- HDMI input
- Usb touch and power, 5V@1A
- Lcd Size ：164.7mm\*107.1mm
- Weight:360g

## Usage
-----

When users connect the Raspberry Pi to use, they need to configure the official system. Or you can also burn the configured system image directly.

### **Hardware Connection**

1\. Connect the HDMI Connector to both the HDMI interfaces on the LCD and the Pi.  
2\. LCD and Pi connect power.  
3.Turn on the "backlight" switch on the back of the LCD.  
![Ex.jpg](https://wiki.elecrow.com/images/thumb/d/d2/Ex.jpg/600px-Ex.jpg){ loading=lazy }

### **Bruning the Image**

### **Method 1. Using Ready-to-use image**

The image file with pre-installed driver is located in the IMAGE directory of the DVD. Extract the IMAGE file and you will get an .img file.
you can refer to the :[5 Inch 800x480 TFT Display](./hdmi-interface-5-inch-800x480-tft-display.md)

### Method 2. Driver installation

### Step1: Download the latest system and unzip the image

For Raspbian: (Not LITE version)
[https://www.raspberrypi.org/downloads/raspbian/](https://www.raspberrypi.org/downloads/raspbian/)
For Ubuntu Mate:
[https://ubuntu-mate.org/download/#xenial](https://ubuntu-mate.org/download/#xenial)
For Kali:
[https://www.offensive-security.com/kali-linux-arm-images/](https://www.offensive-security.com/kali-linux-arm-images/)
For Retropie:
[https://retropie.org.uk/download/](https://retropie.org.uk/download/)
And then unzip the image file.(Next step will use it.)

### Step2: Bruning the Image to SD Card

How to bruning an image to a micro SD card for your Pi? you can refer to the :[5 Inch 800x480 TFT Display](./hdmi-interface-5-inch-800x480-tft-display.md)

### Step3: Find the config.txt in the SD`s root and open it. Then add the following code in the end according to resolution.

```
hdmi_force_hotplug=1
max_usb_current=1
hdmi_group=2
hdmi_mode=1
hdmi_mode=87
hdmi_cvt 1024 600 60 6 0 0 0
hdmi_drive=1
```

### Step2: Insert SD card and Power ON

The screen should be working now.
![E.jpg](https://wiki.elecrow.com/images/thumb/3/30/E.jpg/600px-E.jpg){ loading=lazy }

## Install Soft Keyboard
---------------------

- Install the reference link：[https://github.com/Elecrow-keen/Elecrow-LCD5/wiki/How-to-Install-Soft-Keyboard](https://github.com/Elecrow-keen/Elecrow-LCD5/wiki/How-to-Install-Soft-Keyboard)