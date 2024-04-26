---
title: Sound Recorder- ISD1760
---

## Description
-----------

The Sound Recorder Module uses the ISD1760 Chip to record and store voice signals. ISD1700 series recording chip is a kind of high integration, high performance chip. This module can be multiple recording, the sampling rate can be set to 6k or 8k by the on-board resistor. There are also some inside sounds to remind the user working state of the module, such as record beginning, record stopping, record erasing , etc. The recording data is stored in the FLASH, without any compression to ensure a good quality. You can easily control this module manually or by Arduino. There are some keys on the module including “REC”,”PLAY”,”EARSE”, you can control the module with these keys. The module can be also controlled by SPI, with an Arduino, you can control the detail function such as the analog path configuration, so you can integrated this module to your sound related applications.

**Model:[SISD1760SR](http://www.elecrow.com/sound-recorder-isd1760-p-730.html)**

![Sound Recorder- ISD1760.jpg](https://wiki.elecrow.com/images/thumb/b/bf/Sound_Recorder-_ISD1760.jpg/400px-Sound_Recorder-_ISD1760.jpg){ loading=lazy }

## Features
--------

- Size: 52x 55mm
- Power supply: DC5V
- The recording time: 6K/75Sec, 8K/60Sec
- Frequency 6 KHz or 8 KHz
- Power LED, IC LED
- Simple operation , not need to SCM or other module work direct
- Output all PIN For Chip control , Convenient for control

## Usage
-----

The module detects one-axis rotation with analog signal.

1.Hardware Connection

![Sound Recorder- ISD1760 hardware.jpg](https://wiki.elecrow.com/images/thumb/e/ef/Sound_Recorder-_ISD1760_hardware.jpg/600px-Sound_Recorder-_ISD1760_hardware.jpg){ loading=lazy }

2.Control the Elecrow Sound Recorder Manually

```
1. Recording-- REC:

    Press and hold the REC key, the LED will lights up. Speak to the onboard MIC, the content
of speech will be recorded into the ISD1700 voice chip.
    After recording, release the REC button, the LED will be off, you can press the REC button
again to start recording another speech.

2. Playback--- PLAY:
    There are two ways to control the module playback function: edge-triggered and
level-triggered . (Note: After recording, the inside pointer will remain in the final finished
recording segment, that’s to say, the module will play the last segment you recorded.)
    (1) Edge Trigger : Click the PLAY button and then release, the module will playback the
segment that the inside pointer pointed. Note that if click again, it will playback this segment
again because the inside pointer not moved. The LED flashes until the playback finished.
    (2) Level Trigger: Press the PLAY button and hold, the module will playback all the segment
until released.

3. Fast forward--- FWD:
    (1) Before the playback function, tap this button once to move the inside pointer to the next
section , double-click this button to move the inside pointer to the next-next section.
    (2) Click this button during playback to stop playback of the current segment and then play
the next paragraph, if you are currently playing the last paragraph , the last paragraph
playback t will stop, and begin to playback the first paragraph.

4. ERASE ---ERASE:
    (1) Single-segment erase operation: can only be effective for the first and last paragraph ,
when the playback pointer is the first or the last paragraph , press this button tol erase the
first or the last paragraph . of cause the inside pointer will jump to the second paragraph
before erasing or penultimate paragraph .
    (2) All Erase Operation: Press this button more than 3 seconds often chips into the " All Erase
operation mode " while the LED flashes twice, continue pressing this key , LED 7 flashes
off , then release the button , the chip inside the voice message is All erased.

5. Reset ---RESET:
    Click this button chip will reset the module. After reset, the inside pointer points to the last
paragraph, that to say, if Playback pressed, the module will playback the last segment, if REC pressed, the module will begin to record a new segment.

6. Tuning--- VOL:
    Click this button to adjust the size of the chip output sound . This module outputs maximum
on default. Each VOL clicking will reduce the sound attenuation by 4db until the smallest sound,
continue to click this button , each VOL clicking will increase the sound by 4db ( Note : the sound
output is the maximum after reset).

7. Passthrough Operations ---FT:
    Press this button to connect the FT pin with GND , the module will start passthrough mode.
The signal on “ANAL” will direct pull to the speaker or AUD output. During recording, if you
press the FT, the voice on “ANAL” will also be recorded into the FLASH of ISD1760
```

## Resource
--------

- [ISD1760 Datasheet](https://wiki.elecrow.com/images/f/fc/ISD17600_Series_datasheet.pdf)
- [Elecrow Sound Recorder Manual](https://wiki.elecrow.com/images/6/66/ISD17600_Manual.pdf)