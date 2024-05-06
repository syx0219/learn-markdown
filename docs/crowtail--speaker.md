---
title: Crowtail- Speaker
---

## Description
-----------

The Crowtail- Speaker is a module which consists of power amplification and voice outputs. The loudness can be adjusted by the on-board potentiometer. With different input frequency, the loud-speaker generated different tones. Coding the music into arduino, DIY your own music box!

**Model: [CT009440S](http://www.elecrow.com/crowtail-speaker-p-1660.html)**

![Crowtail- Speaker.jpg](https://wiki.elecrow.com/images/thumb/7/75/Crowtail-_Speaker.jpg/600px-Crowtail-_Speaker.jpg){ loading=lazy }

## Feature
-------

- Volume Adjustable
- Crowtail Interface

## Specification
-------------

Dimensions(mm):40.0(L)x20.0(W)x9.8(H)

| Item | Min | Typical | Max | Unit |
|---|---|---|---|---|
| Working Voltage | 4.0 | 5 | 5.5 | VDC |
| Voltage Gain | - | - | 46 | db |
| Band Width | - | - | 20 | KHz |

## Usage
-----

The speaker can emit a variety of sounds like a car horn, doorbell and ignition . The different sounds are based on the frequency of the input signal.

You can supply different frequency signal to this module with Arduino. Arduino generates these signal via PWM or even digital write and delay.Here we are going to show you how to generate these signals using delay(), the speaker sound bass 1~7.

| Notes | The corresponding frequency(Hz) | semioscillation(us) |
|---|---|---|
| 1 | 261.6255653 | 1911.128216 |
| 1.5 | 277.182631 | 1803.864832 |
| 2 | 293.6647679 | 1702.621678 |
| 2.5 | 311.1269837 | 1607.060866 |
| 3 | 329.6275569 | 1516.863471 |
| 4 | 349.2282314 | 1431.728466 |
| 4.5 | 369.9944227 | 1351.371722 |
| 5 | 391.995436 | 1275.525055 |
| 5.5 | 415.3046976 | 1203.935334 |
| 6 | 440 | 1136.363636 |
| 6.5 | 466.1637615 | 1072.584446 |
| 7 | 493.8833013 | 1012.384907 |

1\. Plug it onto the Digital port 2 of Crowtail - Base Shield using a Crowtail cable.

![Speaker 91.jpg](https://wiki.elecrow.com/images/thumb/c/ca/Speaker_91.jpg/600px-Speaker_91.jpg){ loading=lazy }

2.Copy and paste the code as bellow to your arduino:

```
/*macro definition of Speaker pin*/
#define SPEAKER 2

int BassTab[]={1911,1702,1516,1431,1275,1136,1012};//bass 1~7

void setup() 
{
	pinInit();
}
void loop()
{
	/*sound bass 1~7*/
	for(int note_index=0;note_index<7;note_index++)
  	{
    	sound(note_index);
		delay(500);
  	}
}
void pinInit()
{
	pinMode(SPEAKER,OUTPUT);
	digitalWrite(SPEAKER,LOW);
}
void sound(uint8_t note_index)
{
	for(int i=0;i<100;i++)   
 	{
		digitalWrite(SPEAKER,HIGH);
		delayMicroseconds(BassTab[note_index]);
		digitalWrite(SPEAKER,LOW);
		delayMicroseconds(BassTab[note_index]);
	}
}

```

4.When you upload the code complete,you can heard of seven different tones looping.

Note: Due to the influence of the capacitance, the module can only output the bass signal, and the treble is unable to emit.

## Resource
--------

- [How to generate different tone with MCU](./files/Tone-pdf.md)
- [LM386 Low Voltage Audio Power Amplifier Datasheet](./files/LM386-Low-Voltage-Audio-Power-Amplifier-Datasheet-pdf.md)
- [Crowtail- Speaker eagle file](./files/Crowtail-Speaker-eagle-zip.md)