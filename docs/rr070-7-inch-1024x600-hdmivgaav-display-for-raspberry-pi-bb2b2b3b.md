---
title: RR070 7 Inch 1024x600 HDMI/VGA/AV Display for Raspberry Pi B/B+/2B/3B
---

## Description
-----------

This is an adorable small HDMI television with incredibly high resolution! We tried to get the smallest possible HDMI display with high-res, high-contrast visibility. The display is very easy to use - simply connect the 12VDC adapter to the 2.1mm center-positive DC jack, then connect a digital video source to one of the ports. It work connect to any device with direct HDMI such as raspberry pi, banana pi and pcduino. The biggest difference is that it can work when you plug it on device without any software support. Wish you have a better experience.

**Model:[RR070](https://www.elecrow.com/cheapest-7-800x600-hdmi-display-for-raspberry-pi-bb-p-1455.html)**

## Specifications
--------------

- Input voltage: DC 11-13V
- Power consumption: ≤6W
- 16:9 display ratio
- Pixels: 1024 × 600 (1,152,000) pixels, the maximum support 1920X1440.
- Multi-language menu: English, French, Italian, German, Japanese, Spanish, Russian, Chinese.
- Brightness: 300cd / m2
- VGA input: H: 30-60KHZ, V: 60-75HZ
- Sound output: ≥250mW / 8Ω
- Specifications (mm): 188 (L) x 129 (W) x 40 (H)
- Working temperature: -20 ~ 55 ℃
- Storage temperature: -30 ~ 65 ℃

## Usage
-----

### **1: Connect Raspberry Pi to use**

- Step 1: Please download the image of the latest version from Raspberry Pi's website.

[https://www.raspberrypi.org/downloads/raspbian/](https://www.raspberrypi.org/downloads/raspbian/)

- Step 2: Download the compressed file to your PC and unpack it to get the .Img file.
- Step 3: The TF card is connected to the PC and formatted using the SDFormatter software.
- Step 4: Open the Win32DiskImager software, select the system image prepared in step 1, and click write to burn the system image.
- Step 5: After the programming is completed, open the config.txt file in the root directory of the TF card, and add the following code at the end of “config.txt” to save and safely eject the TF card.

hdmi\_force\_hotplug=1 max\_usb\_current=1 hdmi\_group=2 hdmi\_mode=1 hdmi\_mode=87 hdmi\_cvt 1024 600 60 6 0 0 0 hdmi\_drive=1

- Step 6: Save and insert the TF card into the Raspberry Pi.
- Step 7: Connect the HDMI interface of the 7-inch screen to the HDMI interface of the Raspberry Pi, power on the Raspberry Pi, and wait for a few seconds to display normally.
- Step 8: Connect the 12V/2A power adapter to the DC interface on the screen. Then power on the Raspberry Pi, and wait for a few seconds to display normally.

### **2：Use as PC Monitor**

Install drivers in the Raspbian system (Raspberry Pi requires Internet connection).

- Step 1: Connect the computer HDMI output signal to the display’s HDMI interface by using the HDMI cable.
- Step 2: Connect the 12V/2A power adapter to the DC interface on the screen.
- Step 3: Then it can display normally.