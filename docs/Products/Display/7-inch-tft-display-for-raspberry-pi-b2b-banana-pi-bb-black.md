---
title: 7 Inch TFT Display for Raspberry Pi B+ Banana Pi BB BLACK
---

## Description
-----------

This LCD module is 800x480 dots 7 " color TFT LCD module display with HDMI signal driver board, superior display quality, super wide view angle. It can be used in any embedded system, car, industrial device, security and hand-held equipment which requires display in high quality and colorful video. Its HDMI interface is fully compatible with Raspberry PI, and Banana Pi platform.

**Model:[7inch](https://www.elecrow.com/7-inch-tft-display-for-raspberry-pi-b-banana-pi-bb-black-p-1460.html)**

![7 Inch TFT Display for Raspberry Pi B+ Banana Pi BB BLACK 1.jpg](https://wiki.elecrow.com/images/thumb/d/d3/7_Inch_TFT_Display_for_Raspberry_Pi_B%2B_Banana_Pi_BB_BLACK_1.jpg/600px-7_Inch_TFT_Display_for_Raspberry_Pi_B%2B_Banana_Pi_BB_BLACK_1.jpg){ loading=lazy }

## Features
--------

- Resolution: 800\*480
- Touch Control: Capacitive
- Raspberry Pi: Support Raspberry Pi 2 B/ B+/A+
- Banana Pi / Banana Pro: Support, comes with related images like : Lubuntu, Raspbian
- BB Black: Support, comes with related images like : Angstrom
- HDMI interface: For Displaying
- USB Interface: For touch control
- Back light control to lower power consumption
- Sizes:165 x 107mm

## Usage
-----

### **1: Connect Raspberry Pi to use**

- Step 1: 1)Please download the image of the latest version from Raspberry Pi's website.

[https://www.raspberrypi.org/downloads/raspbian/](https://www.raspberrypi.org/downloads/raspbian/)

- Step 2: Download the compressed file to your PC and unpack it to get the .Img file.
- Step 3: 3)The TF card is connected to the PC and formatted using the “SDFormatter” software.
- Step 4: Open the “Win32DiskImager” software, select the system image prepared in step 1), and click write to burn the system image.
- Step 5: 5)After the programming is completed, open the “config.txt” file in the root directory of the TF card, and add the following code at the end of “config.txt” to save and safely eject the TF card.

max\_usb\_current=1 hdmi\_group=2 hdmi\_mode=1 hdmi\_mode=87 hdmi\_cvt 800 480 60 6 0 0 0 hdmi\_drive=1

- Step 6: Save and insert the TF card into the Raspberry Pi.
- Step 7: Connect the touch interface of the 7-inch screen to the USB interface of the Raspberry Pi with Micro USB cable.
- Step 8: Connect the HDMI interface of the 7-inch screen to the HDMI interface of the Raspberry Pi, power on the Raspberry Pi, and turn on the “backlight” switch on the back of the LCD. Wait for a few seconds to display normally.

![7 Inch TFT Display for Raspberry Pi B+ Banana Pi BB BLACK 2.jpg](https://wiki.elecrow.com/images/thumb/9/9c/7_Inch_TFT_Display_for_Raspberry_Pi_B%2B_Banana_Pi_BB_BLACK_2.jpg/600px-7_Inch_TFT_Display_for_Raspberry_Pi_B%2B_Banana_Pi_BB_BLACK_2.jpg){ loading=lazy }

### **2: Use as PC monitor**

- Step 1: Connect the computer HDMI output signal to the LCD HDMI interface by using the HDMI cable.
- Step 2: Connect the LCD's USB Touch interface to the USB port of the device.
- Step 3: If there are several monitors, please unplug other monitor connectors first, and use LCD as the only monitor for testing.