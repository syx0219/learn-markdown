---
title: Crazepony MINI Quadcopter
---

## Description
-----------

Crazepony MINI is an ultra-compact quadcopter kit that fits the size of your palm. It is remote controllable by smart phone or tablet through bluetooth. It is open sourced. It is designed for those who are interested in learning, experimenting and coaching how to develop your very own drone. let's begin our flying dream.

**Model:[AKA04020A](http://www.elecrow.com/crazepony-mini-quadcopter-open-source-development-platform-p-1478.html)**

![Crazepony MINI Quadcopter.jpg](https://wiki.elecrow.com/images/thumb/3/37/Crazepony_MINI_Quadcopter.jpg/400px-Crazepony_MINI_Quadcopter.jpg){ loading=lazy }

## Specifications of the Crazepony MINI Quadcopter Body
----------------------------------------------------

- Sized 100mm \* 100mm (wheelbase 140mm with 75mm propeller), ultra-compact as its name suggests
- Light weight: 46g (incl. battery)
- Up to 6 minutes when fully charged (with standard 650mAh Li-Po rechargeable battery)
- Charge time about 40min to 100% with Standard Micro USB connector on a 2A adapter
- On-board low-energy radio based on the nRF24L01+ chip
- Powerful 32 bit MCU: STM32F103T8U6 72 MHz (64Kbs flash, 20kb RAM)
- 3-axis high-performance MEMs gyros with 3-axis accelerometer: Invensense MPU-6050
- High precision altimeter MS5611-01BA03
- Extended reservation position for compass HMC5883L
- With common USB to UART bridge CP2102,micro USB connector to download and debug firmware
- Bluetooth 4.0 LE wireless connection (with TI CC2541 chip) to enable remote control by smartphone or tablet

## Specifications of the Crazepony MINI Remote Controller
------------------------------------------------------

- Powerful 32 bit MCU: STM32F103T8U6 72 MHz (64Kbs flash, 20kb RAM).
- Pluggable nRF24L01+ dongle for 20m range,up to 100m with power amplifier(PA) and SMA antenna.
- With common USB to UART bridge CP2102,micro USB connector to download and debug firmware.

## User Guide
----------

1.Place the Crazepony on a stable ground.The Arrow on the center of the PCB indicate the front.  
![Manual-1-0.png](https://wiki.elecrow.com/images/thumb/6/65/Manual-1-0.png/800px-Manual-1-0.png){ loading=lazy }

2.Firstly switch on the Crazepony RC, then quadcopter.About 10s later, blue LEDs on M1/M2 flashing,IMU is calibrated.  
![Manual-2-0.png](https://wiki.elecrow.com/images/thumb/3/36/Manual-2-0.png/800px-Manual-2-0.png){ loading=lazy }

3.Press the "-" button on RC to start IMU calibration.Press the "+" button on RC to start the motors.  
![Manual-3-0.png](https://wiki.elecrow.com/images/thumb/4/4b/Manual-3-0.png/800px-Manual-3-0.png){ loading=lazy }

4.Push the throttle on the left joystick to take off.Press the "+" button again to stop motors after landing.  
![Manual-4-0.jpg](https://wiki.elecrow.com/images/thumb/7/7f/Manual-4-0.jpg/800px-Manual-4-0.jpg){ loading=lazy }

## Resources
---------

### **Source Code &amp; Firmware**

1.Flight Control Source Code

- Crazepony 5.2 Bluetooth 4.0 LE version flight control firmware.
- Search the 2.4G remote control connected last time first when power on
- Support the Bluetooth LE connection by smartphone(Bluetooth 2.1 not supported now)
- Communication with PC assistant is closed by default

Download:

- [Crazepony-5.2-ble-fc-0929-6f07e60.hex](../../files/Crazepony-5.2-ble-fc-0929-6f07e60-hex-zip.md)
- [crazepony-firmware-none-5.2-ble.zip](../../files/Crazepony-firmware-none-5.2-ble-zip.md)

2.Remote Control Source Code

Crazepony 5.2 Bluetooth 4.0 LE version remote control firmware.

- Generate a rand 2.4G address for the remote control
- Press 'Mode' button to 2.4G address

Download:

- [Remote Control Source Code](../../files/Remote-Control-Source-Code-zip.md)

### **Schematic &amp; Datasheet**

- [Schematic](../../files/Crazepony-Schematic-zip.md)
- [Datasheet](../../files/Crazepony-Datasheet-zip.md)

### **Android Client &amp; PC GUI**

- [Android APP APK File](../../files/Crazepony-5.2-ble-zip.md)
- [Crazepony GUI](../../files/CrazeponyV5.1-GUI-zip.md)

## External links
--------------

- [Related Data Download](http://www.crazepony.com/en/download.html)
- [Crazepony Official Website](http://www.crazepony.com/en/index.html)
- [Users Manual](http://www.crazepony.com/en/manual.html)