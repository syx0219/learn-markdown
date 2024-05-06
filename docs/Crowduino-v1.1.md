---
title: Crowduino v1.1
---

## Description

Crowuino V1.1 is almost the same as Crowduino V1.0. It adds Wireless program funtion and improved a little that the RX and TX will be lighting when only plug 9v DC supply in the version 1.0. it will be lighting only when program the 328 now.

The Crowduino is Arduino compatible board. Based on arduino Duemilanuve Schematic, 100% compatible to its existing program, shield and IDEs.

it is a microcontroller board based on the ATmega328 (datasheet). It has 14 digital input/output pins (of which 6 can be used as PWM outputs), 6 analog inputs, a 16 MHz ceramic resonator, a USB connection, a power jack, an ICSP header, a reset button, and a XBee socket. It contains everything needed to support the microcontroller; simply connect it to a computer with a USB cable or power it with a AC-to-DC adapter or battery to get started.

Crowduino differs from all preceding boards in that it contains Shield and XBee socket . it adapts to all the shield that compatible with arduino Uno. it also adapts to the Xbee modules from Digi,and any module with the same footprint.

**Model [MCA01328A](https://www.elecrow.com/crowduino-with-atmega-328-v11-p-338.html)**

![Crowduino v1.1.JPG](https://wiki.elecrow.com/images/thumb/7/7b/Crowduino_v1.1.JPG/600px-Crowduino_v1.1.JPG){ loading=lazy }

## Summary

| **Microcontroller**         | **ATmega328**                                        |
| --------------------------- | ---------------------------------------------------- |
| Operating Voltage           | 5v                                                   |
| Input Voltage (recommended) | 7-12V                                                |
| Input Voltage (limits)      | 6-20V                                                |
| Digital I/O Pins            | 14 (of which 6PINs provide PWM output)               |
| Analog Input Pins           | 8                                                    |
| DC Current per I/O Pin      | 40mA                                                 |
| DC Current for 3.3V Pin     | 50 mA                                                |
| Flash Memory                | 32 KB (ATmega328) of which 0.5 KB used by bootloader |
| SRAM                        | 2 KB (ATmega328)                                     |
| EEPROM                      | 1 KB (ATmega328)                                     |
| Clock Speed                 | 16 MHz                                               |



## Features

- It contains Bee Shield that you can wireless communicate to the microcontroller
- Flat DC Jack.
- Inherits all of Arduino Duemilanuve's features.
- Compatible to Uno's pin layout, screw hole and dimensions.
- Evolved with SMD components.
- Dimensions(mm):70.0(L)x58.3(W)x11.8(H)

## Interface Function

![Crowduino.png](https://wiki.elecrow.com/images/a/a3/Crowduino.png){ loading=lazy }

## Usage

Except 100% compatible with Arduino,Crowduino has another funtion that it also adapts to the Xbee modules from Digi,and other Bee module with the same footprint.

### Wireless program

Hardware needed:
1. [Crowduino V1.1](http://www.elecrow.com/arduino-compatiable-c-109/micro-controller-c-109_117/crowduino-with-atmega-328-p-338.html)  
2. Two XBee module.  
3. [USBSerial Adapter.](http://www.elecrow.com/arduino-compatiable-c-109/programmers-c-109_118/usbserial-adapter-p-344.html)  
4. USB cable.  
![Hardware needed.jpg](https://wiki.elecrow.com/images/1/19/Hardware_needed.jpg){ loading=lazy }

Software needed:
1. [Arduino IDE](http://arduino.cc/en/Main/Software)  
2. [X-CUT software](http://www.digi.com/support/productdetail?pid=3352)  


**Configure the XBee Module**

#### Step 1. Configure the transmitter

One XBee will act as the 'reset transmitter', it will be attached to the computer via USBSerial adapter and wireless send programming commands to the receiver. Lets set this one up first

Connect XBee modem to your computer using USBSrial Adapter.
Note: push the switch to 3V3.

![Wireless programing1.JPG](https://wiki.elecrow.com/images/thumb/4/42/Wireless_programing1.JPG/400px-Wireless_programing1.JPG){ loading=lazy }


And start to configure the X-CTU.

![Wireless programing2.gif](https://wiki.elecrow.com/images/a/a2/Wireless_programing2.gif){ loading=lazy }


Once you've connected/tested that you can communicate with the modem, go to the configure tab and read in the current setup

Then set the following:

The PAN ID should be some 4 digit hex number that will only be used by these two modems - to prevent confusion

![Wireless programing3.gif](https://wiki.elecrow.com/images/6/66/Wireless_programing3.gif){ loading=lazy }

Set the baud rate to 57600.

![Wireless programing4.gif](https://wiki.elecrow.com/images/a/a8/Wireless_programing4.gif){ loading=lazy }

Next we'll set the Packetization Timeout. This is what determines how long to wait before sending the characters over. We're doing some 'bulk transfer' when sending 10K programs over, so you'll probably want this number high like 10

![Wireless programing5.gif](https://wiki.elecrow.com/images/2/25/Wireless_programing5.gif){ loading=lazy }

Set pin D3 to be a digital input

![Wireless programing6.gif](https://wiki.elecrow.com/images/9/9a/Wireless_programing6.gif){ loading=lazy }

And set the Digital IO change detect to FF. Technically you can set it to 0x08, which is the mask to listen for only D3 but this certainly works fine.

![Wireless programing7.gif](https://wiki.elecrow.com/images/c/c3/Wireless_programing7.gif){ loading=lazy }

Then press the Write Button, the transmitter is set up to send the current status of pin D3 to any listening modems.
Note: If one of the steps is set to wrong.press the restore button, then set all of the steps again.

![Wireless programing8.jpg](https://wiki.elecrow.com/images/b/bd/Wireless_programing8.jpg){ loading=lazy }

Finally setup the USBSerail Adapter so that the RTS pin will reset the Arduino. For Mac/Linux it will already be done but if you're using Windows you'll need to make a slight change to the driver preferences. In the Device Manager, select the USB COM port

![Wireless programing9.jpg](https://wiki.elecrow.com/images/6/6d/Wireless_programing9.jpg){ loading=lazy }

Then right click and select **Properties**

![Wireless programing10.jpg](https://wiki.elecrow.com/images/5/5d/Wireless_programing10.jpg){ loading=lazy }

Click on the **Port Settings** tab, and click on **Advanced**...

![Wireless programing11.jpg](https://wiki.elecrow.com/images/a/a6/Wireless_programing11.jpg){ loading=lazy }

Make sure Set RTS On Close is selected. Click OK.

#### Step 2. Configure the receiver

Now we will set up the other XBee so that it will listen to changes on pin D3. Connect it to the FTDI cable and read in the current configuration just like the first one.

The PAN ID should match the transmitter's

![Wireless programing12.gif](https://wiki.elecrow.com/images/0/02/Wireless_programing12.gif){ loading=lazy }

Set the baud rate to 57600 to match the transmitter, again

![File:Wireless programing13.gif](https://wiki.elecrow.com/index.php?title=Special:Upload&wpDestFile=Wireless_programing13.gif){ loading=lazy }

Next we'll set the Packetization Timeout. This is what determines how long to wait before sending the characters over. We're doing some 'bulk transfer' when sending 10K programs over, so you'll probably want this number high like 10

![Wireless programing14.gif](https://wiki.elecrow.com/images/6/6c/Wireless_programing14.gif){ loading=lazy }

Set pin D3 to be a digital output, default **LOW.**

![Wireless programing15.jpg](https://wiki.elecrow.com/images/9/9f/Wireless_programing15.jpg){ loading=lazy }

Set the I/O Output to Disabled. This will prevent the receiver from displaying the status update in the serial line and instead just toggle the matching pin.

![Wireless programing16.gif](https://wiki.elecrow.com/images/9/9e/Wireless_programing16.gif){ loading=lazy }

Finally, set I/O line passing input address to FFFF. If you set up unique addresses for the receiver and transmitter xbees, of course you should change this to match but FFFF will match all addresses.

![Wireless programing17.gif](https://wiki.elecrow.com/images/f/fc/Wireless_programing17.gif){ loading=lazy }

![Wireless programing18.gif](https://wiki.elecrow.com/images/d/d0/Wireless_programing18.gif){ loading=lazy }


Now write the changes to the receiver XBee.

#### Step 3. Hardware install

solder to connect JP1 at the bottom of Crowduino V1.1.
![ConnectJP1.JPG](https://wiki.elecrow.com/images/c/c1/ConnectJP1.JPG){ loading=lazy }  
Plug the receiver XBee to Crowduino, Plug the transmitter XBee to USBSerial Adapter. Power the Crowduino via DC 9v power supply or USB, connect the USB serial Adapter to computer via USB.  
![Finished install.JPG](https://wiki.elecrow.com/images/1/1d/Finished_install.JPG){ loading=lazy }  
Now you can reprogram the Crowduino and also watch the serial monitor from more than 100 feet away. Don't forget the serial monitor must be at the same baud rate as programming because the XBees can only talk at their configured baud rate.

## FAQ

There are a number of switches that I am unsure of the function of, not having seen them on another Arduino board:

***Q:*** *3V3_VCC_5V: Does this convert the entire board to output 3V3 or 5V, or is it input voltage?*

**A:** This is the input voltage choice switch.  
If you push the switch to 3v3, and set the output pin to high, the votage of it is 3v3.  
If you push the switch to 5v, and set the output pin to high, the votage of it is 5v.  

***Q*** *:What does the "serial select" switch do?*

**A:** This switch is to choose Rx, Tx PIN of XBee connect to RX, TX of atmega328 or RX, TX of XBee connect to TX, RX pin of atmega328.  
The theory is that if you connect the RX pin of XBee to TX pin of atmega328, The Xbee or XBee compatible Bee can communicate with atmega328 through Serial port. if you connect the RX pin of XBee to the RX pin of atmega328, the RX pin of XBee will connect to the TX of FTDI, the XBee can commucate with you computer through Serial port.

## Resources

- [Crowduino Schematic in PDF](https://wiki.elecrow.com/images/0/0b/Crowduino_v1.1.pdf)
- [Crowduino V1.1 eagle files](https://wiki.elecrow.com/images/f/f1/Ele_crowduino_v1.1.zip)
- [Adafruit XBee radios Wireless Arduino programming/serial link](http://www.ladyada.net/make/xbee/arduino.html)
- [X-CUT software](http://www.digi.com/support/productdetail?pid=3352)

## How to buy

Please visit [this page](http://www.elecrow.com/arduino-compatiable-c-109/micro-controller-c-109_117/crowduino-with-atmega-328-p-338.html) to purchase Crowduino.

## Support

If you have any problem about how to use it, you can connect to us at [the bottom-right of bazzer](http://www.elecrow.com/) or contact to **techsupport@elecrow.com** to get technology support.