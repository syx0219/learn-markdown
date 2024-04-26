---
title: Crowtail- Recorder
---

## Description
-----------

Crowtail - Recorder is based on the ISD1820P chip, and can record 8-20 secs of audio. It offers true single-chip voice recording and provides non-volatile storage. The recording time can be varied by changing the sampling resistor (R3) on the module's PCB. By default, the resistor on-board has a value of 100KΩ and thus the module offers a default recording time of 10 secs. The audio recording can be directly controlled by the on-board push button or by a micro-controller such as a Crowduino.

**Model: [CT010892R](https://www.elecrow.com/crowtail-anemometer-p-1672.html)**

![Crowtail- Recorder.jpg](https://wiki.elecrow.com/images/thumb/6/6a/Crowtail-_Recorder.jpg/600px-Crowtail-_Recorder.jpg){ loading=lazy }

## Features
--------

- Low power consumption
- Non-volatile storage
- User-friendly operation
- Replace a single resistor to change recording duration and sampling frequency
- Add a resistor to set play cycle mode
- Ships with and connects to an 8Ω/1W mini-speaker
- Uses Standard 4-pin Crowtail Cables to connect to other Crowtail modules or a micro-controller such as the Seeeduino.
- Dimensions(mm):40.0(L)x20.0(W)x9.8(H)

## Interface Function
------------------

![Recorder103.jpg](https://wiki.elecrow.com/images/thumb/2/25/Recorder103.jpg/500px-Recorder103.jpg){ loading=lazy } 
![Recorder104.jpg](https://wiki.elecrow.com/images/thumb/0/05/Recorder104.jpg/500px-Recorder104.jpg){ loading=lazy }

① LED Indicator

Modes:

Record: Red LED light stays ON from the beginning of the recording duration until the end.
Playback: Red LED flashes to signal end of audio playback.

② Sampling resistor

You can set the recording duration and sampling rate by change sampling resistor (R6) based on the following table:

| ROSC | Duration | Sampling Frequency | Input Bandwidth |
|---|---|---|---|
| 80 KΩ | 8 secs | 8.0 KHz | 3.4 KHz |
| 100 KΩ (default) | 10 secs | 6.4 KHz | 2.6 KHz |
| 120 KΩ | 12 secs | 5.3 KHz | 2.3 KHz |
| 160 KΩ | 16 secs | 4.0 KHz | 1.7 KHz |
| 200 KΩ | 20 secs | 3.2 KHz | 1.3 KHz |


③ Play Key

④ REC Key

⑤ Crowtail Interface

⑥ Loudspeaker Interface

⑦ REC IC：ISD1820P

## Usage
-----

Follow these steps to build a sample circuit using the Crowtail- Recorder module:

1.Connect the recorder module to the output side of the Crowtail base shield (U2 port ).

2.Power up the Crowduino and stacked the base shield on it.

![Crowtail- Recorder011.jpg](https://wiki.elecrow.com/images/thumb/7/72/Crowtail-_Recorder011.jpg/500px-Crowtail-_Recorder011.jpg){ loading=lazy }

3.Press and hold down the REC button on the recorder module and start recording the audio. The on-board red LED will turn ON. Continue to record the audio until the red LED gets turned OFF. The LED getting turned OFF is indicative of the fact that the recording time is now over.

4.To play back the audio segment that has been recorded.You should now hear the audio segment you recorded being played back. Continue to press and hold down PLAY Button until you see the red LED on-board the recorder module flash. The flash indicates that playback of audio is now complete.

5.To override the recorded audio, simply repeat step 3 above. The new message will override the old one.

## Resources
---------

- [Crowtail-\_Recorder\_eagle\_file](../../files/Crowtail-Recorder-eagle-file-zip.md)