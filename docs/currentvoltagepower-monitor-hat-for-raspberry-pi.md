---
title: Current/Voltage/Power Monitor HAT for Raspberry Pi
---

## **Introduction**
----------------

This is current and power monitor HAT designed for Raspberry Pi. Support 4-channel, it is easy to monitor current, voltage, and power consumption, voltage across the sampling resistor via the I2C or SMBus interface.

**Model: [RPA20901S](https://www.elecrow.com/power-over-internet-poe-hat-for-raspberry-pi-4-3b.html)**

![CurrentVoltagePower Monitor HAT for Raspberry Pi 1.jpg](https://wiki.elecrow.com/images/thumb/6/6d/CurrentVoltagePower_Monitor_HAT_for_Raspberry_Pi_1.jpg/600px-CurrentVoltagePower_Monitor_HAT_for_Raspberry_Pi_1.jpg){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png)](https://www.elecrow.com/power-over-internet-poe-hat-for-raspberry-pi-4-3b.html?wiki "Title text")

## **Features**
------------

- Standard Raspberry Pi 40PIN GPIO extension header, suitable for all Raspberry Pi boards
- Support 4-channel detection, can communicate through I2C/SMBus interface
- Onboard 0.1Ω 1％ sampling resistor, allows measuring bi-directional current up to 3.2A
- Embedded 12-bit ADC, supports multiple successive converting, 0~26V voltage measuring range
- The output measurement power can be directly calculated through the additional multiplication register
- I2C control pins for connecting with other main boards easily

## **Specification**
-----------------

- Operating voltage: 3.3V/5V
- Control interface: I2C/SMBus
- Sampling resistor: 0.1Ω 1%
- Voltage range: 0~26V
- Current range: ±3.2A
- Resolution: 0.8mA (±3.2A range) OR 0.1mA (±400mA range)
- Dimensions: 65mm × 30mm
- Mounting hole size: 3.0mm

## **Interface Description**
-------------------------

![CurrentVoltagePower Monitor HAT for Raspberry Pi 3.jpg](https://wiki.elecrow.com/images/thumb/4/40/CurrentVoltagePower_Monitor_HAT_for_Raspberry_Pi_3.jpg/600px-CurrentVoltagePower_Monitor_HAT_for_Raspberry_Pi_3.jpg){ loading=lazy }

The module can measure the current and voltage of four channels, which correspond to (IN1+ IN1-), (IN2+ IN2-), (IN3+ IN3-) and (IN4+ IN4-) respectively. INx+ and INx- represent the input and output of the current respectively. The module obtains the magnitude of the current flowing by measuring the differential voltage of the sampling resistor connected in series with INx+ and INx-. The module can test bidirectional current, and all input and output connections can be reversed.

Note: In addition, it should be noted that measuring different power supplies needs to be connected to the GND common ground, otherwise the bus voltage cannot be measured, only the differential voltage and current can be measured.

## **Usage**
---------

Use with Raspberry Pi

1\. Open the I2C interface

1\) Execute in the terminal:

```
sudo raspi-config
Select Interfacing Options -> I2C -> yes to start the i2C kernel driver
```

![CurrentVoltagePower Monitor HAT for Raspberry Pi 2.png](https://wiki.elecrow.com/images/2/2f/CurrentVoltagePower_Monitor_HAT_for_Raspberry_Pi_2.png){ loading=lazy }

Then restart the Raspberry Pi:

```
sudo reboot
```

2\. When using the Raspberry Pi to demonstrate this routine, you only need to insert the module into the Raspberry Pi header, or connect it to the Raspberry Pi’s I2C interface via a Dupont cable, connect VCC to 3.3V and enter the following command to run the program.

```
sudo pip3 install adafruit-circuitpython-ina219
sudo apt-get install p7zip
wget http://www.waveshare.net/w/upload/6/69/Current-Power_Monitor_HAT_Code.7z
7zr x Current-Power_Monitor_HAT_Code.7z -r -o./Current-Power_Monitor_HAT
cd Current-Power_Monitor_HAT/RaspberryPi
python3 ina219.py
```

After the program runs, the bus voltage, sampling resistor differential voltage, input voltage, power, current and other values ​​will be output.