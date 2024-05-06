---
title: Crowtail- MP3
---

## Description
-----------

Crowtail- MP3 is a tiny-size and compact audio module. It supports operations including shuffle and play in an order of various audio files such as WAV and WMV ones. With serial communication, you can use all predefined commands or even the combinations of them to play the music. This module also supports general file systems like FAT16 and FAT32. It gets a Crowtail UART interface, a 3.5mm audio jack and a micro-SD slot. With this module, you can get some “voices” for silent applications.

## Features
--------

- General operations on audio files
- On-board micro-SD slot and 3.5 mm audio jack
- Support sample rate of 8/11.025/12/16/22.05/24/32/44.1/48(KHz)
- 24-bit DAC output, 90 dB (at Max.) dynamic output range, signal-noise ratio at 85 dB
- MP3, WMV and WAV audio format and FAT16, FAT32 files system supported
- Embed 10 levels of equalization in total

## Specification
-------------

| Input | 5 V (DC) |
|---|---|
| Operating current (no signal output state) | less than 15 mA |
| Operating current | less than 40 mA |
| Chip | KT403A[(datasheet)](./files/KT403-pdf.md) |
| Chip LDO output voltage | 3.3 V |
| Chip output current | 100mA(at Max.) |
| File formats supported | MP3, WAV, WMA |
| Maximum memory supported for SD card | 32 GB |
| Sampled rate | 8/11.025/12/16/22.05/24/32/44.1/48 (KHz) |

## Interface function
------------------

## Usage
-----

### **Material required**

- Crowduino × 1
- Grove CrowtailGrove - MP3 v2.0 × 1
- SD card with music inside × 1
- USB cable (type A to micro type-B) × 1
- Headset, earphone or stereo with 3.5 mm audio jack × 1

### **Hardware connections**

![1110547.jpg](https://wiki.elecrow.com/images/thumb/f/ff/1110547.jpg/400px-1110547.jpg){ loading=lazy }

1\. Connect the MP3 Player from U port, SD card slot card entities. insert a Card with MP3 songs into the SD card slot, the indicator lamp lights on the MP3 Player will be observed at this time (unplug the SD card, lights off).

2.Download the [MP3\_test demo code](./files/MP3Player-KT403A-zip.md),unzip it ,copy it to libraries folder of Arduino.

3.Open Arduino IDE, File -&gt; examples -&gt; MP3Player\_KT403A -&gt;MP3\_Play\_Test, you can open the demo code,and upload to the main controller board.

![MP3 Player test.png](https://wiki.elecrow.com/images/thumb/e/e3/MP3_Player_test.png/400px-MP3_Player_test.png){ loading=lazy }

4.Open Serial Monitor,you can send different command (1~8) to control the MP3 Player.

| 1 | Specify the music index to play |
|---|---|
| 2 | Pause the MP3 player |
| 3 | Resume the MP3 player |
| 4 | Play the next song |
| 5 | Play the previous song |
| 6 | Play loop for all the songs |
| 7 | Increase volume |
| 8 | Decrease volume |

5.Now enjoy the music.

## Resource
--------

- [MP3\_test demo code](./files/MP3Player-KT403A-zip.md)
- KT403A[(datasheet)](./files/KT403-pdf.md)
- [Crowtail- MP3 eagle files](./files/Crowtail-MP3eagle-files-zip.md)