---
title: RR040I 4 inch HD 800x480 Resolution IPS TFT Touch Screen Display for Raspberry Pi
---

## Description
-----------

4.0-inch IPS full-angle display, support HDMI input, refresh rate up to 60FPS。 The physical resolution is 800x480

**Model:[DIS10204D](https://www.elecrow.com/elecrow-rr040i-4-0-inch-hd-800x480-ips-tft-touch-screen-display-for-raspberry-pi.html)**

## Features
--------

- Raspberry Pi monitor with touch control (need to install touch driver)
- It can be used as standard HDMI output device for computer display (no touch function)
- Compatible with and can be directly inserted into all versions of raspberry PI motherboards (raspberry PI 1 generation B and Zero need additional HDMI cable)
- Support HDMI audio output, backlight brightness adjustable

## Specifications
--------------

- Screen Size 4.0inch
- LCD Type TFT
- Module Interface HDMI
- Resolution 800\*480 (Pixel)
- Touch Screen Controller XPT2046
- LCD Driver IC NT35510
- Backlight LED
- power consumption 0.16A\*5V
- Working temperature（℃） -20~60
- Module PCB Size 98.60\*58.05 (mm)
- Package Size 143\*134\*51 (mm)
- Rough Weight (Package containing) (g) 126 (g)

## Interface Function
------------------

![RR040I 4 inch HD 800x480 Resolution IPS TFT Touch Screen Display for Raspberry Pi.png](https://wiki.elecrow.com/images/thumb/c/c7/RR040I_4_inch_HD_800x480_Resolution_IPS_TFT_Touch_Screen_Display_for_Raspberry_Pi.png/600px-RR040I_4_inch_HD_800x480_Resolution_IPS_TFT_Touch_Screen_Display_for_Raspberry_Pi.png){ loading=lazy }

① 3.5mm Headphone Jack: Output audio signal

② HDMI：Used to connect the main board and LCD display for HDMI transmission

③ Micro USB：Get 5V Power from USB, If ⑤-13\*2 Pin Socket has been connected, that this USB interface can be No Connect.

④ Backlight adjustment button: Short press backlight change 10%, long press a few seconds to close backlight; short press to open backlight

⑤ 13\*2 Pin Socket：Get +5V Power from raspberry Pi to LCD, at the same time transfer touch signal back to Raspberry Pi.

![Elecrow rr040i 4.0-inch hd 800x480 ips tft touch screen display for raspberry pi 2.jpg](https://wiki.elecrow.com/images/7/70/Elecrow_rr040i_4.0-inch_hd_800x480_ips_tft_touch_screen_display_for_raspberry_pi_2.jpg){loading=lazy}


## Usage
-----

### **A. Use with Raspbian**


Step 1：Install Raspbian official image

1)Please download the image of the latest version from Raspberry Pi's website：[https://www.raspberrypi.org/downloads/raspbian/](https://www.raspberrypi.org/downloads/raspbian/)

2)Download the compressed file to your PC and unpack it to get the .Img file.

3)The TF card is connected to the PC and formatted using the “SDFormatter” software.

4)Open the “Win32DiskImager” software, select the system image prepared in step 1), and click write to burn the system image.

5)Insert the TF card into the Raspberry Pi.

6)Connect to Raspberry Pi

![Elecrow rr040i 4.0-inch hd 800x480 ips tft touch screen display for raspberry pi 3.png](https://wiki.elecrow.com/images/thumb/4/44/Elecrow_rr040i_4.0-inch_hd_800x480_ips_tft_touch_screen_display_for_raspberry_pi_3.png/600px-Elecrow_rr040i_4.0-inch_hd_800x480_ips_tft_touch_screen_display_for_raspberry_pi_3.png){ loading=lazy }

![Elecrow rr040i 4.0-inch hd 800x480 ips tft touch screen display for raspberry pi 4.png](https://wiki.elecrow.com/images/thumb/0/04/Elecrow_rr040i_4.0-inch_hd_800x480_ips_tft_touch_screen_display_for_raspberry_pi_4.png/600px-Elecrow_rr040i_4.0-inch_hd_800x480_ips_tft_touch_screen_display_for_raspberry_pi_4.png){ loading=lazy }

As shown in the figure, connect the LCD module to the Raspberry Pi

Step 2: Install the LCD driver

Install drivers in the Raspbian system (Raspberry Pi requires Internet connection)

1)Log on to the Raspberry Pi terminal (User: pi; Password: raspberry)

2)Execute the following command (copy and paste it by right-clicking on the Putty window):

```
 sudo rm -rf LCD-show<br></br>
 git clone https://github.com/goodtft/LCD-show.git
 chmod -R 755 LCD-show
 cd LCD-show/
 sudo ./MPI4008-show
```

3)Wait for a moment after executing, the system will restart automatically. If the LCD can be normally displayed and touched, the installation of the driver is successful.

### **B.Use with Ubuntu, Kali or RetroPie official image**


A.Install Ubuntu, Kali or RetroPie official image

1)Please download the image of the latest version from blew websites. Ubuntu: [https://ubuntu-mate.org/raspberry-pi/](https://ubuntu-mate.org/raspberry-pi/)RetroPie: [https://retropie.org.uk/download/](https://retropie.org.uk/download/)Kali: [https://www.offensive-security.com/kali-linux-arm-images/](https://www.offensive-security.com/kali-linux-arm-images/)

2)Download the compressed file to your PC and unpack it to get the .Img file.

3)The TF card is connected to the PC and formatted using the “SDFormatter” software.

4)Open the “Win32DiskImager” software, select the system image prepared in step 1), and click write to burn the system image.

5)Insert the TF card into the Raspberry Pi.

6)Connect to Raspberry Pi.


B.Install the LCD driver

Due to system differences, Ubuntu, Kali, RetroPie are temporarily unable to install drivers online. Only the offline installation method can be used.

1)Download local drivers "LCD-show.tar.gz" (Note: if the version does not match, the LCD may not display properly)

Kali-2019.1-Drivers （see attachment）

Ubuntu-18.04-Drivers （see attachment）

RetroPie-Pi2-Pi3-Drivers （see attachment）

RetroPie-Pi1-ZERO-Drivers （see attachment）

2)Copy "LCD-show.tar.gz" to the Raspberry Pi system

3)Log on to the Raspberry Pi terminal, Execute the following command

```
 tar -xvzf LCD-show.tar.gz
 chmod -R 755 LCD-show 
 cd LCD-show/
 sudo ./MPI4008-show
```


4)After the installation of the LCD driver is completed, the system will restart automatically. If the LCD can be normally displayed and touched, the installation of the driver is successful.

3: Use as PC Monitor

1)Connected the computer HDMI output to the LCD HDMI interface by HDMI cable.

2)Power to Micro USB interface

3)If you have multiple monitors, please pull the other displayer, and make this LCD as the only displayer for testing.

4)As computer monitors, the touch function will not be available.

## Image Download
--------------

If you have difficulty installing the driver, or if you still can't use the display properly after installing the driver, please try our already configured images for tested. Just need download and write the image into the Micro SD card. DO NOT need any driver installation steps. (see attachment for miror)