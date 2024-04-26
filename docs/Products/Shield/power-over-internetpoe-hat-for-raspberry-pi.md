---
title: Power over Internet(POE) Hat for Raspberry Pi
---

## **Introduction**
----------------

Do you still worry about Raspberry Pi Zero access to various USB devices? So,it's your right choice. It is a USB Hub for RPI Zero, it has 4 USB extension interface and external battery. The 4 pogo pins on the back will connect the PP1, PP6, PP22 and PP23 testing pads on your Raspberry Pi Zero – no soldering required! You can also power PRI zero by USB cable or a chargeable battery. Only need a few studs can connect it with RPI Zero, it so convenient for saving a lot of wiring problems.

**Model: [RPA20901S](https://www.elecrow.com/power-over-internet-poe-hat-for-raspberry-pi-4-3b.html)**

![Power over Internet(POE) Hat for Raspberry Pi 43B+ 1.jpg](https://wiki.elecrow.com/images/thumb/5/59/Power_over_Internet%28POE%29_Hat_for_Raspberry_Pi_43B%2B_1.jpg/600px-Power_over_Internet%28POE%29_Hat_for_Raspberry_Pi_43B%2B_1.jpg){ loading=lazy }

## **Features**
------------

- Support PoE Power over Ethernet, support 802.3af PoE network standard
- Fully isolated switch mode power supply (SMPS)
- With 0.91" OLED for monitoring processor temperature, IP address, and fan status in real-time.
- Support real-time temperature reading and intelligent cooling
- With cooling fan, allows auto running on powerup or programmable control configured by switch
- Integrates PCF8574, 8 channels of I/O ports can be expanded through I2C, which can directly control the fan

## **Specification**
-----------------

- POE input voltage: 37V ~ 57V DC
- POE output voltage: 5V 2.5A DC
- Network standard: 802.3af PoE
- OLED control interface: I2C
- OLED size: 0.91 inches
- OLED resolution: 128×32
- OLED driver chip: SSD1306
- OLED resolution: 65.0x56.5mm
- OLED display color: white
- OLED viewing angle: greater than 160°
- GPIO expansion interface: I2C
- GPIO expansion chip: PCF8574

## **Usage**
---------

Plug PoE\_HAT(B) into the Raspberry Pi, as shown in the figure below.

![Power over Internet(POE) Hat for Raspberry Pi 43B+ wiki.jpg](https://wiki.elecrow.com/images/thumb/0/00/Power_over_Internet%28POE%29_Hat_for_Raspberry_Pi_43B%2B_wiki.jpg/600px-Power_over_Internet%28POE%29_Hat_for_Raspberry_Pi_43B%2B_wiki.jpg){ loading=lazy }

- **Step 1. Install the necessary library**

1\) Install BCM2835, open the Raspberry Pi terminal, and run the following command

```
HTTP wget : //www.airspayce.com/mikem/bcm2835/bcm2835-1.60.tar.gz
zxvf bcm2835 tar - 1.60 . tar . GZ
bcm2835 cd - 1.60 /
sudo ./ the configure
sudo make && sudo make check && sudo make install
```

2\) Update wiringPi to version 2.52

```
sudo apt - get install wiringpi
HTTPS wget : //project-downloads.drogon.net/wiringpi-latest.deb
sudo dpkg - i wiringpi - latest . deb
gpio - v
#You will see gpio version: 2.52, indicating successful installation
```

3\) Install Python library

```
#python2
sudo apt - get update
sudo apt - get install python - pip
sudo pip install RPi . GPIO
#python3
sudo apt - get update
sudo apt - get install python3 - pip
sudo pip install RPi . GPIO
```

- **Step 2. Download the sample program**

```
sudo apt - get install p7zip - full
HTTP wget : //www.waveshare.net/w/upload/b/b7/PoE_HAT_B_code.7z
7z x PoE_HAT_B_code . 7z - r - o ./ PoE_HAT_B_code
```

- **Step3. Run the test routine**

1\) C

```
cd PoE_HAT_B_code / c /
make clean 
make
sudo ./ main
```

2\) Python

```
cd PoE_HAT_B_code / python /
sudo python main . py
```

- **Set the fan start temperature**

```
#C
Nano examples the sudo / main . C
# POE_HAT_Display() The last parameter of the function sets the fan opening temperature
 
#python 
Nano examples sudo / main . Py
# POE.POE_HAT_Display() Function parameter to set the fan opening temperature
```

- **Set boot up**

1\) Before setting the startup, compile the routine first.

```
Nano sudo / etc / rc . local
```


2\) Set boot up. Add sudo /home/pi/Fan\_HAT/c/main &amp; before exit 0. Note that you must add "&amp;" to run in the background, otherwise the system may not start.

```
fi
sudo / home / pi / PoE_HAT_B_code / c / main &
exit 0
```