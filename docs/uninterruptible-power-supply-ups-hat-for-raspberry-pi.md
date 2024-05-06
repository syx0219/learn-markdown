---
title: Uninterruptible Power Supply UPS HAT For Raspberry Pi
---

## **Introduction**
----------------

UPS HAT For Raspberry Pi, 5V Uninterruptible Power Supply, Multi Battery Protection Circuits

**Model: [RPA20901S](https://www.elecrow.com/power-over-internet-poe-hat-for-raspberry-pi-4-3b.html)**

## **Features**
------------

- Standard Raspberry Pi 40PIN GPIO extension header, supports Raspberry Pi series boards
- I2C bus communication, monitoring the batteries voltage, current, power, and remaining capacity in real-time
- Multi battery protection circuits: overcharge/discharge protection, over current protection, short circuit protection, and reverse protection, along with the equalizing charge feature, more safe and stable
- Onboard 5V regulator, up to 2.5A continuous output current
- 5V USB output, convenient for powering other boards
- Batteries warning indicators, easy to check if the battery is connected correctly

## **Specification**
-----------------

- Output voltage：5V
- Charger：8.4V 2A
- Control bus：I2C
- Battery supported：18650 Li battery (NOT included)
- Dimensions：56mm × 85mm
- Mounting hole：3.0mm

## **Hardware**
------------

![Uninterruptible Power Supply UPS HAT For Raspberry Pi 2.jpg](https://wiki.elecrow.com/images/2/2f/Uninterruptible_Power_Supply_UPS_HAT_For_Raspberry_Pi_2.jpg){ loading=lazy }

The 8.4V interface is the charge port. You can plug the 8.4V 2A charger provided for charging the batteries. The switched is the power switch, you can turn it into ON/OFF to turn on/off Jetson Nano Developer Kit WARNING LED are the indicators of batteries, they turn on if you reverse batteries.

- **Note 1: Please check the WARNING LED when you mounting batteries, make sure that you set all the batteries in the correct way. You cannot charge batteries if you reverse them.**
- **Note 2: The board may not work when you mount the batteries for the first time, you need to charge batteries on board for a while to activate them.**
- **Note 3: Please use the charger provided, the module may be destroyed by other unsuitable power adapters/chargers.**

## **Usage**
---------

You can just attach the UPS HAT on the 40PIN GPIO of Raspberry Pi or connect the i2c interface and to Raspberry Pi by wires. VCC should be connected to 3.3V Open a terminal and run the following commands:

```
sudo apt-get install p7zip
wget https://www.waveshare.com/w/upload/d/d9/UPS_HAT.7z
7zr x UPS_HAT.7z -r -o./UPS_HAT
cd UPS_HAT
python3 INA219.py
```

The terminal will print the IP address, battery voltage, current and the percentage of battery quantity, as well as the CPU, GPU and memory information after starting the server

![Uninterruptible Power Supply UPS HAT For Raspberry Pi 1.png](https://wiki.elecrow.com/images/f/ff/Uninterruptible_Power_Supply_UPS_HAT_For_Raspberry_Pi_1.png){ loading=lazy }

Note: if the current value is negative, it means that the batteries are feeding the Raspberry Pi. If the current value is positive, it means that the batteries are charging.

## **Resources**
-------------