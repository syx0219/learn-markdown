---
title: 1.3 inch IPS TFT LCD Display ST7789
---

## Discription
-----------

This is a 1.3 inch display screen with a resolution of 240 (RGB) x240. It is an IPS full view LCD display panel so the color looks great in any direction. The drive IC is ST7789, and the universal 7-pin SPI interface is used.

The bottom has an SD card slot, which makes it easy to load full-color bitmaps from the MicroSD card in FAT16/FAT32 format.

Support the main control MCU such as ESP32/ESP8266/Arduino/STM32.

## Specification
-------------

- 1.3 inch TFT LCD Display
- Built-in microSD slot
- Operating Voltage: 3.3V
- Backlight: 2-Chip white LED, Vf=3.2V(If=20mA)
- Resolution: 240 (RGB) x240
- Interface: SPI serial
- Drive IC: ST7789
- Operating Temperature: -20℃~+70℃
- Storage Temperature: -30℃~+80℃
- Dimension: 35.8mm x 35.8mm x 5.3mm
- Weight: 7.6g

## Pin Discription
---------------

![1.3inchTFTLCD ST7789Display.png](https://wiki.elecrow.com/images/thumb/5/53/1.3inchTFTLCD_ST7789Display.png/700px-1.3inchTFTLCD_ST7789Display.png){ loading=lazy }

![1.3inchTFTLCD ST7789Display Pin3.png](https://wiki.elecrow.com/images/1/1b/1.3inchTFTLCD_ST7789Display_Pin3.png){ loading=lazy }

![1.3inchTFTLCD ST7789Display Pin4.png](https://wiki.elecrow.com/images/e/e2/1.3inchTFTLCD_ST7789Display_Pin4.png){ loading=lazy }

## Usage
-----

### **Hardware Connection**

STEP1 Prepare the below stuffs:  

| **Crowduino Uno**                                            | **1.3 inch IPS TFT LCD Display** |
| :------------------------------------------------------------: | :--------------------------------: |
| ![Crowduino 2.jpg](https://wiki.elecrow.com/images/thumb/d/d4/Crowduino_2.jpg/300px-Crowduino_2.jpg){ loading=lazy } |     [[File:\|300px]     |
| [**Get one now**](https://www.elecrow.com/crowduino-unosd-v15-p-840.html) | <font color="#4051b5">[**Get one now**]</font>            |

STEP2 Connect wires according to the following wiring diagram  
![1.3INCH WIRING 1.png](https://wiki.elecrow.com/images/thumb/1/1d/1.3INCH_WIRING_1.png/600px-1.3INCH_WIRING_1.png){ loading=lazy }

### Software

STEP1 Download [Adafruit-ST7735-Library](https://github.com/adafruit/Adafruit-ST7735-Library) and [Adafruit-GFX-Library](https://github.com/adafruit/Adafruit-GFX-Library)  
STEP2 Configure controller board&amp;communication port  
On top of the Arduino IDE, click “Tools&gt;Board&gt;” and select “Arduino Uno” from the available options  
![SELECT BOARD.png](https://wiki.elecrow.com/images/thumb/c/c5/SELECT_BOARD.png/700px-SELECT_BOARD.png){ loading=lazy }  
Select the COM port that indicates Arduino Uno. Please note that the actual numbers after the “COM” word will vary from computer to computer, so they could be different from the ones shown in the figure.
![S 2 2.png](https://wiki.elecrow.com/images/thumb/d/d5/S_2_2.png/700px-S_2_2.png){ loading=lazy }  
STEP3 Install Library: Unzip the files and copy them to the Libraries directory under the Arduino installation directory  
![1.3inchtftlibrary.png](https://wiki.elecrow.com/images/2/28/1.3inchtftlibrary.png){ loading=lazy }    
<font color="red">**Note: Please change "-" in the folder name to "\_", and delete"\_ master"**</font>  

STEP4 Open Arduino IDE, click "File"--&gt;"Example"--&gt;"Adafruit ST7735 and ST7789 Library"--&gt;"graphicstest\_st7789" to load the code  

STEP5 Click the ![Upload.png](./assets/images/30px-Upload.png){ loading=lazy } to upload the code to the Crowduino board  
![1.3inchtestcode.png](https://wiki.elecrow.com/images/thumb/0/0b/1.3inchtestcode.png/700px-1.3inchtestcode.png){ loading=lazy }  

STEP6 The graphs will show on display  
![1.3inchtftdisplay.png](https://wiki.elecrow.com/images/0/08/1.3inchtftdisplay.png){ loading=lazy }

## FAQS
----

You can list you question here or contact with techsupport@elecrow.com for technology support.