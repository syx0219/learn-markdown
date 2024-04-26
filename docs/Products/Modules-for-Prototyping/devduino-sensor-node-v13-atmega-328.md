---
title: DevDuino Sensor Node V1.3 (ATmega 328)
---

## Introduction
------------

Sensor Node is compact, Arduino-compatible microcontroller and is designed for wireless sensor networks using transceiver nRF24L01+.

Model: [CODI3976SN](https://www.elecrow.com/cooperated-designers-c-127/devicter-c-127_167/sensor-node-v12-atmega-328-p-759.html)

![Sensor Node v1.3](https://wiki.elecrow.com/images/thumb/1/18/DD_SN_1.3_face.jpg/300px-DD_SN_1.3_face.jpg){ loading=lazy }
![Sensor Node v1.3](https://wiki.elecrow.com/images/thumb/0/06/DD_SN_1.3_back.jpg/300px-DD_SN_1.3_back.jpg){ loading=lazy }

## Feature
-------

- Built on Arduino-compatible architecture
- Clock frequency - 16MHz (may be reduced in order to reduce energy consumption by up to 8MHz)
- Built-in temperature sensor MCP9700 (-40 ° C +125 ° C, accuracy of ± 2 ° C)
- Built-in voltage divider (to monitor the supply voltage)
- Built-in button
- Built-in LED
- 3 GROVE-compatible connector: I2C, Analog, Digital
- Powered by one element CR2032 (not included)
- Dimensions 30 x 40 mm

## Layout and schematics
---------------------

[Schematic of the device](https://wiki.devicter.ru/images/6/6b/Sn-sh.jpg)

## Basic functionality
-------------------

In the basic version (without additional sensors) module can be used as a wireless temperature sensor (using built-in sensor MCP9700, connected to A3) to control the battery charge level (via integrated voltage divider connected to A2).

## Expansion Capabilities
----------------------

Basic functionality can be greatly expanded by connecting the various components [GROVE](https://www.seeedstudio.com/depot/Grove-t-3.html?ref=top) from Seeed Studio.

![Sensor Node и GROVE-components](https://wiki.elecrow.com/images/8/81/Sn-grove.jpg){ loading=lazy }

Also you can use the modules own making, for example, a temperature sensor based on MCP9700 (a temperature sensor similar to that installed on board Sensor Node).

![Sensor Temperature](https://wiki.elecrow.com/images/thumb/6/62/OutT-sens.jpg/680px-OutT-sens.jpg){ loading=lazy }

## Interfaces
----------

- A0, A1 - displayed on the connector "Analog" (the other two pin connector - VCC and GND for sensor supply)
- D3, D4 - displayed on the connector "Digital" (the other two pin connector - VCC and GND for sensor supply)
- A4 (SDA), A5 (SCL) - displayed on the connector "I2C" (the other two pin connector - VCC and GND for sensor supply)
- Interface for RF-module nRF24L01 +: 
    - D11 - RF\_MOSI
    - D12 - RF\_MISO
    - D13 - RF\_SCK
    - D8 - RF\_CE
    - D7 - RF\_CSN
    - D2 - RF\_IRQ
- D4 - button
- D9 - LED
- A2 - voltage divider to monitor the battery level
- A3 - MCP9700 temperature sensor

## Features Sensor Node
--------------------

### **Module Programming**

#### **With the help of programmer based FT232RL (and such)**

By default, the standard boot stitched microcontroller Arduino, allowing to record the firmware in the module with the type of programmers [FOCA v2.2](https://devicter.ru/goods/Foca-v2-1-FT232RL).

Connecting the programmer via 5-pin (PROG) on the module (battery installed when programming is required - module receives power from the programmer)

**Warning!** Do not forget to set the programmer working voltage of 3.3V. When flashing the bootloader via ISP, be sure to disconnect the wireless module nRF24L01 +.

Just programmer can be used to debug (monitor port).

#### **Using ISP-Programmer**

If you want to get even further about 2K more memory for your sketch, you can use almost any ISP-Programmer for example, Arduino ISP (regular Arduino-compatible board and a standard example of the environment Arduino) or [USBtinyISP](http://devicter.ru/goods/USBtinyISP-Arduino-bootloader-programmer).

Connecting programmer via 6-pin connector (ISP) on the module (battery installed when programming is required - module receives power from the programmer).

### **Option module supply nRF24L01+**

- Power to the constantly fed - jumper RFpower position 1-2
- Power to the given with digital pin microcontroller (D6) - jumper RFpower position 2-3

In the first case, to maximize the operating time of a battery should be fitted in use nRF24L01+ power saving mechanisms:

```
...

      radio.powerUp();  //turn the power on NRF24
      
      // sending data
      
      ...

      radio.powerDown();  //turn off the power on NRF24

...
```


In the second case power is supplied to a module only when the high level signal D6:

```
...

      digitalWrite(6, HIGH);  //turn off the power on NRF24
      
      // sending data
      
      ...

      digitalWrite(6, LOW);  //turn the power on NRF24

...
```

### **Job button**

Button connected to digital pin of D4 without external pull-up resistor. This connection is necessary to use the built-in pull-up resistor microcontroller.

This is done as follows (in the example being polled button once 0.5s and if it is pressed - LED lights):

```
void setup (){
  // button
  pinMode(4, INPUT);
  // enable pull-up resistor
  digitalWrite(4, HIGH);

  // LED
  pinMode(9, OUTPUT);
}

void loop(){
  if(digitalRead(4) == LOW) {
    digitalWrite(9, HIGH);
  }
  else {
    digitalWrite(9, LOW);
  }
  delay(500);
}
```

### **Measurement voltage power**

Besides measuring the voltage at the voltage divider with a simple analogRead (A2), you can use more "advanced" way - use the built-in capabilities of the microcontroller.

You can use the following universal function:

```
long readVcc() {
  // Read 1.1V reference against AVcc
  // set the reference to Vcc and the measurement to the internal 1.1V reference
  #if defined(__AVR_ATmega32U4__) || defined(__AVR_ATmega1280__) || defined(__AVR_ATmega2560__)
    ADMUX = _BV(REFS0) | _BV(MUX4) | _BV(MUX3) | _BV(MUX2) | _BV(MUX1);
  #elif defined (__AVR_ATtiny24__) || defined(__AVR_ATtiny44__) || defined(__AVR_ATtiny84__)
    ADMUX = _BV(MUX5) | _BV(MUX0);
  #elif defined (__AVR_ATtiny25__) || defined(__AVR_ATtiny45__) || defined(__AVR_ATtiny85__)
    ADMUX = _BV(MUX3) | _BV(MUX2);
  #else
    ADMUX = _BV(REFS0) | _BV(MUX3) | _BV(MUX2) | _BV(MUX1);
  #endif  

  delay(75); // Wait for Vref to settle
  ADCSRA |= _BV(ADSC); // Start conversion
  while (bit_is_set(ADCSRA,ADSC)); // measuring

  uint8_t low  = ADCL; // must read ADCL first - it then locks ADCH  
  uint8_t high = ADCH; // unlocks both

  long result = (high<<8) | low;

  result = 1125300L / result; // Calculate Vcc (in mV); 1125300 = 1.1*1023*1000
  return result; // Vcc in millivolts
}
```

The function returns the voltage in millivolts.

### **Features connector Digital**

In the present pin connector Digital D3. The peculiarity of its use is that this digital signal to the pins of the interrupt can be processed (INT1).

### **Getting more time working Sensor Node**

To ensure longer battery module from one battery can reduce the frequency of the microcontroller to 1MHz and lower "threshold" voltage at which it will start to 1.8V.

This is done by adding the following section in the file boards.txt IDE Arduino:

```
s328o1.name=Sensor328p (int1MHz, 1.8V)

s328o1.upload.protocol=arduino
s328o1.upload.maximum_size=30720
s328o1.upload.speed=19200

s328o1.bootloader.low_fuses=0x62
s328o1.bootloader.high_fuses=0xda
s328o1.bootloader.extended_fuses=0x06
s328o1.bootloader.path=atmega

s328o1.bootloader.file=ATmegaBOOT_168_atmega328_pro_8MHz.hex

#s328o8.bootloader.file=ATmegaBOOT_168_atmega328.hex

s328o1.bootloader.unlock_bits=0x3F
s328o1.bootloader.lock_bits=0x0F

s328o1.build.mcu=atmega328p
s328o1.build.f_cpu=1000000L
s328o1.build.core=arduino
s328o1.build.variant=standard
```

After adding this code to the appropriate file (and restarting the Arduino) in the list of available cards will be a new line: Sensor328 (int1MHz, 1.8V)

**Warning!** Fuse bits specified in the file boards.txt and defining modes of microcontroller sewn Arduino environment only when writing the bootloader (but not the firmware of the microcontroller).

To correct fuse bits without changing the boot loader can be used, for example [avrdude GUI](http://sourceforge.net/projects/avrdude-gui/)

## Libraries
---------

### **Necessary libraries**

To use the Sensor Node requires the following libraries:

- Working with the transceiver nRF24L01+ - [RF24](https://github.com/maniacbug/RF24/archive/master.zip)

Requires the libraries that are used at work RF24:

- SPI

### **Features using libraries**

Library has used examples of them just to understand how it works.

Initialization RF-module as follows:

```
...

//RF24 radio(CE,CSN);
RF24 radio(8,7);

...
```

## Version Tracker
---------------

| **Revision** | **Description** | **Release** |
|:-:|:-:|:-:|
| 0.9 | Prototype | 07.06.2013 |
| 1.2 | Public version (Not produced) | 04.11.2013 |
| 1.3 | Public version | 28.03.2014 |

## Areas of application
--------------------

- Weather station sensors (basic functionality)
- Collect data with pulse sensors or gas flow (using interrupt (D3 - IRQ1))
- Universal sensor (with extensions Grove)
- Data transfer (on a similar device)

## Questions and Answers
---------------------

- Blog [Sensor Node](https://devicter.blogspot.ru/2013/12/shield-matrix-sensor-node.html)
- Ask a question by e-mail support@devicter.ru

## How to buy
----------

This product can be purchased:  
China (shipping worldwide)   
[Seeed store](http://www.seeedstudio.com/depot/DevDuino-Sensor-Node-V12-ATmega-328-p-1774.html)   
[Elecrow store](http://www.elecrow.com/arduino-compatiable-c-109/micro-controller-c-109_117/sensor-node-v12-atmega-328-p-759.html)   
Russia   
[Devicter store](http://devicter.ru/goods/Sensor-Node)

## Licensing
---------

This documentation is licensed under the Creative Commons [Attribution-ShareAlike License 3.0](http://creativecommons.org/licenses/by-sa/3.0/) Source code and libraries are

licensed under [GPL/LGPL](http://www.gnu.org/licenses/gpl.html), see source code files for details.

## Useful links
------------

[Schematic of the device](https://wiki.devicter.ru/images/6/6b/Sn-sh.jpg)

[Wireless communication is a "smart home"](http://habrahabr.ru/post/202898/) RU

[Measuring voltage microcontroller](http://blog.unlimite.net/?p=224)