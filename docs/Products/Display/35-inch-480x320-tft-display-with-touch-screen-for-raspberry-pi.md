---
title: 3.5 Inch 480x320 TFT Display with Touch Screen for Raspberry Pi
---

## Description
----------- 
It is the cutest, little display for the Raspberry Pi. It features a 3.5" display with 480x320 16-bit color pixels and a resistive touch overlay. It's designed to fit nicely not only to the Pi Model A or B but also works perfectly fine with the Model B+.

**Model:[RPA03510R](http://www.elecrow.com/35-inch-480x320-tft-display-with-touch-screen-for-raspberry-pi-p-1385.html)**

![3.5 Inch 480x320 TFT Display with Touch Screen for Raspberry Pi.jpg](https://wiki.elecrow.com/images/thumb/9/9b/3.5_Inch_480x320_TFT_Display_with_Touch_Screen_for_Raspberry_Pi.jpg/400px-3.5_Inch_480x320_TFT_Display_with_Touch_Screen_for_Raspberry_Pi.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/35-inch-480x320-tft-display-with-touch-screen-for-raspberry-pi-p-1385.html?wiki "Title text")

## Features
-------- 
- **480x320 resolution**
- **Universal 3.5” Display for the Raspberry Pi**
- **Compatible with Raspberry Pi A, B, A+, B+, and Pi2 versions**
- **Powered not only from your computer, but also from your portable power**
- **Adapt for Raspbian system**

## Specifications
-------------- 
- **LCD Type:TFT**
- **LCD Interface:SPI**
- **Touch Screen Type:Resistive**
- **Touch Screen Controller:XPT2046**
- **Colors:65536**
- **Backlight:LED**
- **Resolution:480\*320 (Pixel)**

## Interface Function
------------------ 
![Example1567.jpg](https://wiki.elecrow.com/images/1/15/Example1567.jpg){ loading=lazy }

## Usage
----- 
**When users connect the Raspberry Pi to use, they need to configure the official system. Or you can also burn the configured system image directly.**  
**Tips:Basic for Raspbian Jessie with PIXEL (2017-04-10-raspbian-jessie.img)**

### **Step 1：Download the Raspbian IMG [https://www.raspberrypi.org/downloads/raspbian/](https://www.raspberrypi.org/downloads/raspbian/)**

### **Step 2: Burn the system image If you don't know how to do that,you can refer to the [Raspberry Pi office tutorial](https://www.raspberrypi.org/documentation/installation/installing-images/README.md)**

### **Step 3: Open terminal and Download the driver on RPI**
**Run:**

```
sudo git clone https://github.com/goodtft/LCD-show.git
``` 
### **Step 4: Install driver**   
**Run:**

```
cd LCD-show/
sudo chmod +x LCD35-show
sudo ./LCD35-show
``` 
## Touch screen calibration
------------------------ 
- **This LCD can be calibrated using a program called xinput\_calibrator**
- **Install it with the commands: **
```
cd Elecrow-LCD35<br></br>
sudo dpkg -i -B xinput-calibrator_0.7.5-1_armhf.deb
```
- **Click the Men button on the task bar, choose Preference -&gt; Calibrate Touchscreen**.
- **Finish the touch calibration following the prompts. Maybe rebooting is required to make calibration active.**
- **You can create a 99-calibration.conf file to save the touch parameters (not necessary if file exists).**
```
/ect/X11/xorg.conf.d/99-calibration.conf
``` 
- **Save the touch parameters (may differ depending on LCD) to 99-calibration.conf, as shown in the picture:**  
![124.jpg](https://wiki.elecrow.com/images/0/02/124.jpg){ loading=lazy }

## Install Soft Keyboard
--------------------- 
- **Install the reference link：[https://github.com/Elecrow-keen/Elecrow-LCD5/wiki/How-to-Install-Soft-Keyboard](https://github.com/Elecrow-keen/Elecrow-LCD5/wiki/How-to-Install-Soft-Keyboard)**