---
title: Mechanical Keyboard ESP32-S3
---

## Description
-----------

Mechanical\_ Keyboard\_ ESP32-S3 is an open-source mechanical keyboard backplane based on the ESP32-S3 main control chip.

It carries 87 universal mechanical keyboard shaft sockets and SMD3528 reverse labeled (6028) programmable RGB LEDs (supporting WS2812/SK6812 chips), 3 USB power/program burning interfaces, PH2.0 lithium battery power interface, and 2 pre reserved 1 \* 4PIN 2.54mm spacing pin interfaces. All key functions and RGB light effects can be defined and designed through program programming.

The keyboard supports Bluetooth wireless connection and USB wired connection. It supports the Arduino open-source programming platform, making it particularly suitable for open-source creators and DIY design enthusiasts.

**Model: [DIS03024H](https://www.elecrow.com/wizee-esp32-2-4-inch-intelligent-tft-lcd-touch-screen-240-320-hmi-display-compatible-with-arduino-lvgl.html)**  
![Image1(14).png](https://wiki.elecrow.com/images/7/7f/Image1%2814%29.png){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){loading=lazy}](https://www.elecrow.com/wizee-esp32-2-4-inch-intelligent-tft-lcd-touch-screen-240-320-hmi-display-compatible-with-arduino-lvgl.html "Title text")

## PinOut
------

![Image1(15).png](https://wiki.elecrow.com/images/9/9f/Image1%2815%29.png){ loading=lazy }

| PWR | Power LED. |
|---|---|
| CAP | Letter case toggle indicator. |
| BT1 | Bluetooth Channel 1 toggle indicator. |
| BT2 | Bluetooth Channel 2 toggle indicator. |
| BT13 | Bluetooth Channel 3 toggle indicator. |
| CABLE | USB wired access indicator/lithium battery charging indicator. |
| BOOT | Download button.Push it to start the Firmware download mode.Through USB interface, users can download the upgraded firmware to modify the underlying software and add new function to the hardware. |
| USB-C\*3 | USB-C interface, which is used as the power supply of the keyboard board and the communication interface between the PC and ESP32 S3, and can charge the lithium battery when an external lithium battery is connected. |
| BAT | PH2.0-3.7V lithium battery interface, can be used for external 3.7V lithium battery |
| ON/OFF | System power toggle switch. |
| ESP32(UART) | ESP32 UART serial communication interface is reserved. |
| STC8(UART) | STC UART serial communication interface is reserved. |

## Feature
-------

- Integrated ESP32-WROOM-32 module and and STC8G1K08 chip, built-in 384KB ROM, 512KB SRA, 16KB RTC SRAM, onboard 4MB Flash;
- Xtensa 32-bit LX7 dual core processor, with a main frequency of 240MHz;
- built-in wireless communication 2.4 GHz Wi-Fi (802.11 b/g/n) and Bluetooth 5.0;
- Support development environment Arduino IDE, Micro python;
- 87 universal mechanical keyboard axes and SMD3528 anti stick (6028) programmable RGB LEDs (supporting WS2812/SK6812 chips);
- Support for USB charging and USB/lithium battery power supply.

## Specification
-------------

- Input voltage of TYPE C USB: DC-5V
- Input voltage of PH2.0 lithium battery interface: 3.7V-4.2V
- Operating temperature range: -10 ° C~65 ° C
- Size: 130mm\*354mm (W\*L)

## Development environment configuration
-------------------------------------

- 1.Please go to the official website [https://www.arduino.cc/](https://www.arduino.cc/) to download the Arduino IDE development tool and download the corresponding library file, install the tool. Open the Arduino IDE after the installation:

![Image (1).png](https://wiki.elecrow.com/images/3/3f/Image_%281%29.png){ loading=lazy }
![Image (2).png](https://wiki.elecrow.com/images/b/b2/Image_%282%29.png){ loading=lazy }
![Image (3).png](https://wiki.elecrow.com/images/6/6d/Image_%283%29.png){ loading=lazy }
![Esp32rgb 3.png](https://wiki.elecrow.com/images/thumb/d/d8/Esp32rgb_3.png/469px-Esp32rgb_3.png){ loading=lazy }

- 2.Click the "File" menu, select "Preferences" in the drop-down menu, and then the picture will appear: Unzip the downloaded library file and put it in the libraries folder.

![Esp32rgb 4.png](https://wiki.elecrow.com/images/thumb/c/cc/Esp32rgb_4.png/762px-Esp32rgb_4.png){ loading=lazy }

- Add the ESP32 S3 URL as follows：

[https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package\_esp32\_index.json](https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json)
![Esp32rgb 5.png](https://wiki.elecrow.com/images/thumb/7/75/Esp32rgb_5.png/616px-Esp32rgb_5.png){ loading=lazy }

- The tool automatically downloads and updates the corresponding model, check the steps as shown in the figure:

![Image (7).png](https://wiki.elecrow.com/images/thumb/9/93/Image_%287%29.png/490px-Image_%287%29.png){ loading=lazy }
![Image (8).png](https://wiki.elecrow.com/images/thumb/5/5b/Image_%288%29.png/490px-Image_%288%29.png){ loading=lazy }

- warn:

please install esp32 version 2.0.3, if you install another version,some modules may go wrong.

## Software settings:
------------------

- 1.Under the "Tools" menu, see "Board: ESP32-XXX" and select ESP32 Dev MODULE as shown in the figure.

![Image1(1).png](https://wiki.elecrow.com/images/thumb/f/f1/Image1%281%29.png/490px-Image1%281%29.png){ loading=lazy }

- 2.After connecting the Mechanical\_Keyboard\_ESP32-S3 to the computer through the TYPE-C USB cable, the computer will automatically recognize the USB COM port (if the USB is not recognized successfully, please disconnect the USB cable and connect to the computer, press and hold the BOOT button, and connect the computer again at power-on).

![Image1(31).png](https://wiki.elecrow.com/images/thumb/9/94/Image1%2831%29.png/490px-Image1%2831%29.png){ loading=lazy }

- 3.After the USB COM port is successfully recognized, open the Arduino IDE to download a sample code, as shown in the following figure: File-&gt;Examples-&gt;Basics-&gt;Blink.

![Image1(16).png](https://wiki.elecrow.com/images/2/27/Image1%2816%29.png){ loading=lazy }
The code that opens is as follows:  
![Image1(17).png](https://wiki.elecrow.com/images/c/c2/Image1%2817%29.png){ loading=lazy }

- Noted:
- If the CH340 driver is not installed on your PC, please install the CH340 driver first, or switch the SWITCH to the USB position and connect it with a USB cable.

## Download process
----------------

- 1.Connect the keyboard and computer through a USB to type-c data cable;
- 2.Click on the tool on the arduino software and select the corresponding serial port number;

![Esp32rgb 15.png](https://wiki.elecrow.com/images/2/20/Esp32rgb_15.png){ loading=lazy }

- 3.Click "upload" to upload the program to the ESP32 keyrboard

![Esp32rgb 17.png](https://wiki.elecrow.com/images/thumb/b/bc/Esp32rgb_17.png/87px-Esp32rgb_17.png){ loading=lazy }

- Until the prompt upload is successful, as shown in the figure:

![Esp32rgb 18.png](https://wiki.elecrow.com/images/thumb/e/e5/Esp32rgb_18.png/564px-Esp32rgb_18.png){ loading=lazy }

## I/O Port
--------

| ESP32 S3 | Mechanical\_Keyboard\_ESP32-S3 |  | ESP32 S3 | Mechanical\_Keyboard\_ESP32-S3 |
|---|---|---|---|---|
| GPIO0 | BOOT |  | GPIO1 | KEY\_IN5(6X17 Matrix keyboard line control signal) |
| GPIO2 | KEY\_IN4(6X17 Matrix keyboard line control signal) |  | GPIO3 | KEY\_IN3(6X17 Matrix keyboard line control signal) |
| GPIO4 | KEY\_IN2(6X17 Matrix keyboard line control signal) |  | GPIO5 | KEY\_IN1(6X17 Matrix keyboard line control signal) |
| GPIO6 | KEY\_IN0(6X17 Matrix keyboard line control signal) |  | GPIO7 | KEY\_OUT0(6X17 Matrix keyboard line control signal) |
| GPIO8 | KEY\_OUT1(6X17 Matrix keyboard line control signal) |  | GPIO9 | KEY\_OUT2(6X17 Matrix keyboard line control signal) |
| GPIO10 | KEY\_OUT3(6X17 Matrix keyboard line control signal) |  | GPIO11 | KEY\_OUT4(6X17 Matrix keyboard line control signal) |
| GPIO12 | KEY\_OUT5(6X17 Matrix keyboard line control signal) |  | GPIO13 | KEY\_OUT6(6X17 Matrix keyboard line control signal) |
| GPIO14 | KEY\_OUT7(6X17 Matrix keyboard line control signal) |  | GPIO15 | KEY\_OUT8(6X17 Matrix keyboard line control signal) |
| GPIO16 | KEY\_OUT9(6X17 Matrix keyboard line control signal) |  | GPIO17 | KEY\_OUT10(6X17 Matrix keyboard line control signal) |
| GPIO18 | KEY\_OUT11(6X17 Matrix keyboard line control signal) |  | GPIO19 | USB\_D - differential signaling |
| GPIO20 | USB\_D + differential signaling |  | GPIO21 | KEY\_OUT12(6X17 Matrix keyboard line control signal) |
| GPIO26 | NC |  | GPIO27 | SPIHD |
| GPIO28 | SPIWP |  | GPIO29 | SPICS0 |
| GPIO30 | SPICLK |  | GPIO31 | SPIQ |
| GPIO32 | SPID |  | GPIO33 | NC |
| GPIO34 | NC |  | GPIO35 | SCL |
| GPIO36 | SDA |  | GPIO37 | NC |
| GPIO38 | KEY\_OUT13(6X17 Matrix keyboard line control signal) |  | GPIO39 | KEY\_OUT14(6X17 Matrix keyboard line control signal) |
| GPIO40 | KEY\_OUT15(6X17 Matrix keyboard line control signal) |  | GPIO41 | KEY\_OUT16(6X17 Matrix keyboard line control signal) |
| GPIO42 | BAT\_DET\_CON |  | GPIO43 | ESP32-U0TXD |
| GPIO44 | ESP32-U0RXD |  | GPIO45 | NC |
| GPIO46 | NC |  | GPIO47 | NC |
| GPIO48 | RGB\_DI |

| STC8G1K08 | Mechanical\_Keyboard\_ESP32-S3 |  | STC8G1K08 | Mechanical\_Keyboard\_ESP32-S3 |
|---|---|---|---|---|
| P1.0 | CABLE |  | P1.1 | BT2 |
| P1.2 | BT3 |  | P1.3 | BAT\_DET\_CON |
| P1.4 | SDA |  | P1.5 | SCL |
| P1.6 | BT1 |  | P1.7 | NC |
| P3.0 | STC\_TXD |  | P3.1 | STC\_RXD |
| P3.2 | NC |  | P3.3 | ON/OFF |
| P3.4 | CHRG |  | P3.5 | BAT\_DET |
| P3.6 | PWR |  | P3.7 | CAP |

## Example
-------

- Before using the Mechanical\_Keyboard\_ESP32-S3 keyboard, you need to flash the program firmware of STC8G1K08.
- Example1. The STC8G1K08 programming program is downloaded through the USB to serial port module by reserving the STC8 UART interface.

The wiring method is as follows:

| STC8 UART | USB TO TTL |
|---|---|
| GND | GND |
| 3V3 | VO-3V3 |
| RXD | TXD |
| TXD | RXD |

- Open the "stc-isp-v6.91M.exe" STC single-chip microcomputer special programming tool in the STC8 firmware and programming tool folder, and connect the USB to serial port module with the computer through the USB data cable.

The "stc-isp-v6.91M.exe" tool interface is as follows:  
![Image1(19).png](https://wiki.elecrow.com/images/d/d7/Image1%2819%29.png){ loading=lazy }

- Select STC8G1K08-20/16PIN, click Auto to automatically identify and select COM port (confirm that it is the COM port of the USB to serial port module you access), and keep other settings as default.

![Image1(20).png](https://wiki.elecrow.com/images/b/b6/Image1%2820%29.png){ loading=lazy }

- Click "Open Code File" in the downloading tool and select the "keyboard-0\_4\_2.bin" file in the "KEYBOARD\_STC\_BIN" folder.

![Image1(21).png](https://wiki.elecrow.com/images/b/b3/Image1%2821%29.png){ loading=lazy }

- Click "Download/Program" to start flashing the firmware.

![Image1(22).png](https://wiki.elecrow.com/images/f/ff/Image1%2822%29.png){ loading=lazy }

- Special note: After clicking "Download/Program", the downloading tool print window prints "Checking target MCU ... ", disconnect the STC8G1K08 from the 3V3/GND connection of the USB to serial port module, and power it back on to perform the downloading normally.

![Image1(23).png](https://wiki.elecrow.com/images/3/3b/Image1%2823%29.png){ loading=lazy }

- Until the prompt download is successful, as shown in the figure:

![Image1(24).png](https://wiki.elecrow.com/images/d/d8/Image1%2824%29.png){ loading=lazy }

- Example2. Use the Arduino IDE to flash the sample program for ESP32-S3.

Before flashing the sample program, copy the used library files to the "libraries" folder, as shown in the following figure.Open the library file in the "Arduino Program Source" folder and copy "ESP32-BLE-Keyboard-0.3.2-beta" and "FastLED" to the Arduino IDE's libraries folder.  
![Image1(25).png](https://wiki.elecrow.com/images/8/8a/Image1%2825%29.png){ loading=lazy }

- Use the Arduino IDE software to open the "keyboard\_main.ino" sample program in the sample code folder.

![Image1(26).png](https://wiki.elecrow.com/images/2/29/Image1%2826%29.png){ loading=lazy }

- Note: After the program downloading is completed, you need to toggle the power switch on the keyboard board, power on and reset again, and the mechanical keyboard can work normally!

- Wireless Bluetooth keyboard connection mode usage demo:

The sample program defaults to "FN+1", "FN+2", and "FN+3" key combinations for Bluetooth channel switching, and the corresponding "BT1", "BT2", "BT3" on the keyboard will always light up for 3S and then turn off when the corresponding key combination is pressed.

- Press "FN+1" to switch to Bluetooth channel 1 mode, corresponding to the indicator "BT1" solid 3S.

![Image1(27).png](https://wiki.elecrow.com/images/5/51/Image1%2827%29.png){ loading=lazy }

- Using a computer with wireless Bluetooth, turn on the Bluetooth device, click Add Bluetooth or other device,Select "ELECROW\_BT" and connect.

![Image1(28).png](https://wiki.elecrow.com/images/8/80/Image1%2828%29.png){ loading=lazy }

- USB wired keyboard connection mode demo:

The example program defaults to "FN+4" key combination for switching to USB wired connection keyboard mode, after pressing the key combination, the "CABLE" indicator light is solid for 3S, and then off, then it can be operated directly using the Mechanical\_Keyboard\_ESP32-S3 keyboard.  
![Image1(29).png](https://wiki.elecrow.com/images/2/2d/Image1%2829%29.png){ loading=lazy }

- RGB equivalent switching demo:

By default, the sample program uses the "FN+Insert" key combination to switch different lighting effects.  
![Image1(30).png](https://wiki.elecrow.com/images/0/0e/Image1%2830%29.png){ loading=lazy }

## FAQS
----

You can list you question here or contact with techsupport@elecrow.com for technology support.

## Resource
--------

- [Code &amp; STC8.zip](https://www.elecrow.com/wiki/images/2/23/Code_%26_STC8.zip)
- [Other\_files.zip](https://www.elecrow.com/wiki/images/d/d2/Other_files.zip)