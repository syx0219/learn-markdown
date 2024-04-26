---
title: Elecrow RR040I 4 inch HD 800x480 Resolution IPS TFT Touch Screen Display for Raspberry Pi
---

## Description
-----------

4.0-inch IPS full-angle display, support HDMI input, refresh rate up to 60FPS. The physical resolution is 800x480. Compatible with and can be directly inserted into all versions of raspberry PI motherboards. With HDMI interface, used to connect the main board and LCD display for HDMI transmission. Support Raspbian/Ubuntu Mate/Kali/Retropie system. It can be used as Raspberry Pi monitor with touch control (need to install touch driver) and standard HDMI output device for computer display(no touch function). Connect Raspberry Pi with GPIO, support backlight brightness adjustable.

**Model:[RR040I](https://www.elecrow.com/elecrow-rr040i-4-0-inch-hd-800x480-ips-tft-touch-screen-display-for-raspberry-pi.html)**

![Elecrow RR040I 4.0-inch HD 800x480 IPS TFT Touch Screen Display for Raspberry Pi 1.jpg](https://wiki.elecrow.com/images/thumb/8/83/Elecrow_RR040I_4.0-inch_HD_800x480_IPS_TFT_Touch_Screen_Display_for_Raspberry_Pi_1.jpg/600px-Elecrow_RR040I_4.0-inch_HD_800x480_IPS_TFT_Touch_Screen_Display_for_Raspberry_Pi_1.jpg){ loading=lazy }

## Features
--------

- Raspberry Pi monitor with touch control (need to install touch driver)
- It can be used as a standard HDMI output device for computer display (no touch function)
- Compatible with and can be directly inserted into all versions of raspberry PI motherboards (raspberry PI 1 generation B and Zero need additional HDMI cable)
- Support HDMI audio output, backlight brightness adjustable

## Specifications
--------------

- Screen Size: 4inch
- LCD Type: TFT
- Module Interface: HDMI
- Touch Screen Controller: XPT2046
- LCD Driver IC: NT35510
- Backlight: LED
- Working temperature（℃）: -20~60
- Power consumption: 0.16A\*5V
- Module PCB Size: 98.60\*58.05 (mm)
- Package size: 14 \*13\*4.7(mm)

## Interface Function
------------------

![RR040I 4 inch HD 800x480 Resolution IPS TFT Touch Screen Display for Raspberry Pi 1.jpg](https://wiki.elecrow.com/images/thumb/6/61/RR040I_4_inch_HD_800x480_Resolution_IPS_TFT_Touch_Screen_Display_for_Raspberry_Pi_1.jpg/600px-RR040I_4_inch_HD_800x480_Resolution_IPS_TFT_Touch_Screen_Display_for_Raspberry_Pi_1.jpg){ loading=lazy }

- ① 3.5mm Headphone Jack: Output audio signal
- ② HDMI：Used to connect the mainboard and LCD display for HDMI transmission
- ③ Micro USB：Get 5V Power from USB, If ⑤-13\*2 Pin Socket has been connected, that this USB interface can be No Connect.
- ④ Backlight adjustment button: Short press backlight change 10%, long press a few seconds to close backlight; short press to open backlight
- ⑤ 13\*2 Pin Socket：Get +5V Power from raspberry Pi to LCD, at the same time transfer touch signal back to Raspberry Pi.

![RR040I 4 inch HD 800x480 Resolution IPS TFT Touch Screen Display for Raspberry Pi.jpg](https://wiki.elecrow.com/images/thumb/e/ec/RR040I_4_inch_HD_800x480_Resolution_IPS_TFT_Touch_Screen_Display_for_Raspberry_Pi.jpg/600px-RR040I_4_inch_HD_800x480_Resolution_IPS_TFT_Touch_Screen_Display_for_Raspberry_Pi.jpg){ loading=lazy }

### **Usage**

### **1: Use with Raspbian**

### **A.Install Raspbian official image**

- Step 1: Please download the image of the latest version from Raspberry Pi's website.

[https://www.raspberrypi.org/downloads/raspbian/](https://www.raspberrypi.org/downloads/raspbian/)

- Step 2: Download the compressed file to your PC and unpack it to get the. Image file.
- Step 3: The TF card is connected to the PC and formatted using the “SDFormatter” software.
- Step 4: Open the “Win32DiskImager” software, select the system image prepared in step 1, and click write to burn the system image.
- Step 5: Insert the TF card into the Raspberry Pi.
- Step 6: Connect to Raspberry Pi

![RR040I 4 inch HD 800x480 Resolution IPS TFT Touch Screen Display for Raspberry Pi 2.jpg](https://wiki.elecrow.com/images/thumb/4/4a/RR040I_4_inch_HD_800x480_Resolution_IPS_TFT_Touch_Screen_Display_for_Raspberry_Pi_2.jpg/600px-RR040I_4_inch_HD_800x480_Resolution_IPS_TFT_Touch_Screen_Display_for_Raspberry_Pi_2.jpg){ loading=lazy }
![RR040I 4 inch HD 800x480 Resolution IPS TFT Touch Screen Display for Raspberry Pi 3.jpg](https://wiki.elecrow.com/images/f/f1/RR040I_4_inch_HD_800x480_Resolution_IPS_TFT_Touch_Screen_Display_for_Raspberry_Pi_3.jpg){ loading=lazy }

### **B.Install the LCD driver**

Install drivers in the Raspbian system (Raspberry Pi requires Internet connection).

- Step 1: Log on to the Raspberry Pi terminal (User: pi; Password: raspberry)
- Step 2: Execute the following command (copy and paste it by right-clicking on the Putty window):

sudo rm -rf LCD-show  
git clone [https://github.com/goodtft/LCD-show.git](https://github.com/goodtft/LCD-show.git) 
chmod -R 755 LCD-show  
cd LCD-show/  
sudo ./MPI4008-show  
 
- Step 3: Wait for a moment after executing, the system will restart automatically. If the LCD can be normally displayed and touched, the installation of the driver is successful.

![RR040I 4 inch HD 800x480 Resolution IPS TFT Touch Screen Display for Raspberry Pi 4.jpg](https://wiki.elecrow.com/images/thumb/a/a0/RR040I_4_inch_HD_800x480_Resolution_IPS_TFT_Touch_Screen_Display_for_Raspberry_Pi_4.jpg/600px-RR040I_4_inch_HD_800x480_Resolution_IPS_TFT_Touch_Screen_Display_for_Raspberry_Pi_4.jpg){ loading=lazy }

### **2: Use with Ubuntu, Kali or RetroPie official image**

### **A.Install Ubuntu, Kali or RetroPie official image**

- Step 1: Please download the image of the latest version from blew websites.

Ubuntu: [https://ubuntu-mate.org/raspberry-pi/](https://ubuntu-mate.org/raspberry-pi/)  
RetroPie: [https://retropie.org.uk/download/](https://retropie.org.uk/download/)  
Kali: [https://www.offensive-security.com/kali-linux-arm-images/](https://www.offensive-security.com/kali-linux-arm-images/)  

- Step 2: Download the compressed file to your PC and unpack it to get the. Image file.
- Step 3: The TF card is connected to the PC and formatted using the “SDFormatter” software.
- Step 4: Open the “Win32DiskImager” software, select the system image prepared in step 1), and click write to burn the system image.
- Step 5: Insert the TF card into the Raspberry Pi.
- Step 6: Connect to Raspberry Pi.

### **B.Install the LCD driver**

Due to system differences, Ubuntu, Kali, RetroPie are temporarily unable to install drivers online. Only the offline installation method can be used.

- Step 1: Download local drivers "LCD-show.tar.gz" (Note: if the version does not match, the LCD may not display properly)

```
 Kali-2019.1-Drivers   （see attached file）
 Ubuntu-18.04-Drivers    （see attached file）
 RetroPie-Pi2-Pi3-Drivers  （see attached file）
 RetroPie-Pi1-ZERO-Drivers  （see attached file）
```

- Step 2: Copy "LCD-show.tar.gz" to the Raspberry Pi system
- Step 3: Log on to the Raspberry Pi terminal, Execute the following command

```
tar -xvzf LCD-show.tar.gz  
chmod -R 755 LCD-show   
cd LCD-show/  
sudo ./MPI4008-show 
```

- Step 3: After the installation of the LCD driver is completed, the system will restart automatically. If the LCD can be normally displayed and touched, the installation of the driver is successful.

### **3: Use as PC Monitor**

- Step 1: Connected the computer HDMI output to the LCD HDMI interface by HDMI cable.
- Step 2: Power to Micro USB interface
- Step 3: If you have multiple monitors, please pull the other displayer, and make this LCD as the only displayer for testing.
- Step 4: As computer monitors, the touch function will not be available.

### **Image Download**

If you have difficulty installing the driver, or if you still can't use the display properly after installing the driver, please try our already configured images for tested. Just need download and write the image into the Micro SD card. DO NOT need any driver installation steps.