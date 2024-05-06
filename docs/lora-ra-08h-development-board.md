---
title: Lora RA-08H Development Board
---

## Description
-----------

Lora RA-08H Development Board is a development board based on the combination of Raspberry Pi RP2040 main control chip and RA-08H, onboard TFT 1.8-inch SPI display, passive buzzer, RS485 communication module, customizable buttons, programmable indicator lights, multiple Crowtail and general IO interfaces, rich external interface resources, can be used with Crowtail series modules or modules with other interfaces. The onboard Lorawan module is connected to the Lorawan platform to realize remote module control, which can be applied to maker education, smart home, industrial control, etc.

**Model: [CRT01259B](https://www.elecrow.com/lorawan-ra-08h-development-board-integrated-rp2040-with-1-8-lcd-for-long-range-communication-868mhz-915mhz.html)**   
![Lora ra 08h module 3-wiki-main.jpg](https://wiki.elecrow.com/images/thumb/4/44/Lora_ra_08h_module_3-wiki-main.jpg/500px-Lora_ra_08h_module_3-wiki-main.jpg){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png){loading=lazy}](https://www.elecrow.com/lorawan-ra-08h-development-board-integrated-rp2040-with-1-8-lcd-for-long-range-communication-868mhz-915mhz.html?wiki "Title text")

## Feature
-------

- Integrate RP2040 and RA-08H (Lorawan module)
- Main control Raspberry Pi chip RP2040, built-in 264KB SRAM, onboard 4MB Flash
- Dual Core Arm Cortex-M0+ @ 133MHz
- RA-08H module adopts embedded memory, 128KB Flash, 16KB SRAM
- RA-08H module supports frequency band: 803MHZ-930MHZ
- RA-08H module supports external antenna, SMA interface or IPEX first generation interface
- Compatible with Arduino/Micropython
- Onboard 1.8-inch SPI-TFT-LCD, resolution: 128\*160 driver chip: ST7735S (4-wire SPI)
- 1 passive buzzer
- 4 user-defined buttons
- 6 programmable LEDs
- 1 RS485 communication interface
- 8 5V Crowtail interfaces (2 analog interfaces, 2 digital interfaces, 2 UART interfaces, 2 IIC interfaces)
- 12 5V universal pin header IO interfaces
- 14 3.3V universal pin header IO interfaces
- 1 3.3V/5V switchable SPI interface
- 1 3.3V/5V switchable UART interface
- 3 3.3V/5V switchable IIC interfaces

## Technical Specification
-----------------------

- Working input voltage: USB 5V-1A
- Operating temperature range: -10°C ~ 65°C
- Dimensions: 102mm(L)x76.5mm(W)

## Interface Function
------------------

![Lora RA-08H 0 2.png](https://wiki.elecrow.com/images/c/cb/Lora_RA-08H_0_2.png){ loading=lazy }

- Onboard Ports and Functions

| **Name** | **Interface/Function Definition** |
|:-:|:-:|
| DATA | RA-08H data sending and receiving indicator light, when RA-08H communicates with the outside world (need to be set by the user). |
| PWR | Power Indicator |
| RST | Reset button, press this button to reset the system. |
| (RP2040)BOOT | Download button, hold down the Boot button and press the RESET button to enter boot firmware download mode. Users can download firmware through the USB interface. |
| USB-C | USB-C interface, it is used for the power supply of the development board and the communication interface between PC and RP2040. |
| RS485 | RS485 interface, used to communicate with external RS485 module. |
| 485RX&lt;-RX-&gt;RX1 | 3P pin header interface RS485 chip and RP2040 communication pin switching interface, when using the RS485 module, it is necessary to short the RX and 485RX with a jumper cap, when not using the RS485 module, the default is to short the RX and RX1. |
| 485TX&lt;-TX-&gt;TX1 | 3P pin header interface RS485 chip and RP2040 communication pin switching interface, when using the RS485 module, it needs to short-circuit its TX and 485TX with a jumper cap, and when using the RS485 module, the default is to short-circuit the TX and TX1. |
| 3V3&lt;-VCC-&gt;5V | 3P pin header interface, used for switching the working voltage of these three interfaces: 6P-SPI interface, 3\*4P-IIC interface and 4P-UART interface. |
| SPI | 6P-SPI pin header interface, which can be used for external SPI interface communication modules and devices, and the power supply voltage is 3.3V/5V switchable. |
| I2C | 3\*4P-IIC pin header interface, can be used for external I2C interface communication modules and devices, power supply voltage 3.3V/5V switchable. |
| UART | 4P-UART pin header interface, can be used for external UART serial communication modules and devices, power supply voltage 3.3V/5V switchable. |
| GND-5V-SIG | 3\*12PIN, 5V general-purpose IO header interface, which can be used for external 5V sensor modules or devices. |
| GND-3V3-SIG | 3\*14PIN, 3.3V general-purpose IO header interface, which can be used for external 3.3V sensor modules or devices. |
| Crowtail-A0 | External Crowtail-5V-HY-4P-2.0 port. Sensors or modules that can be used to interface with 5V Crowtail analog signals. |
| Crowtail-A1 | External Crowtail-5V-HY-4P-2.0 port. Sensors or modules that can be used to interface with 5V Crowtail analog signals. |
| Crowtail-D0 | External Crowtail-5V-HY-4P-2.0 port. Sensors or modules that can be used to interface with 5V Crowtail digital signals. |
| Crowtail-D1 | External Crowtail-5V-HY-4P-2.0 port. Sensors or modules that can be used to interface with 5V Crowtail digital signals. |
| Crowtail-UART | External Crowtail-5V-HY-4P-2.0 port. Sensors or modules that can be used to connect to 5V Crowtail UART serial communication. |
| Crowtail-I2C | External Crowtail-5V-HY-4P-2.0 port. Sensors or modules that can be used to connect to 5V Crowtail I2C interface communication. |
| (RA-08H)BOOT | Long press the download button before power-on. Connect the external USB-to-serial port module. Connect the cables to the external USB-to-serial port module according to (GND~GND, RA-3V~3.3V, RA-RX~TX, RA-TX~RX) and update the firmware of the RA-08H module through the TremoProgrammer\_v0.8 software. |
| LCD | 1.8 inch SPI display |

- GPIO Pin Corresponding Port

| **RP2040** | **Lora RA-08H Development Board** |
|:-:|:-:|
| GPIO0 | Crowtail-UART0-TX0 |
| GPIO1 | Crowtail-UART0-RX0 |
| GPIO2 | GPIO2 |
| GPIO3 | GPIO3 |
| GPIO4 | RA-08H-LPRXD |
| GPIO5 | RA-08H-TXD |
| GPIO6 | GPIO6 |
| GPIO7 | GPIO7 |
| GPIO8 | GPIO8/UART1-TX1/Crowtail-UART1-TX1/485TX |
| GPIO9 | GPIO9/UART1-RX1Crowtail-UART1-RX1/485RX |
| GPIO10 | GPIO10/SPI1-SCK |
| GPIO11 | GPIO11/SPI1-MOSI |
| GPIO12 | GPIO12/SPI1-MISO |
| GPIO13 | GPIO13/SPI1-CS |
| GPIO14 | GPIO14/ Crowtail-D0 |
| GPIO15 | GPIO15/ Crowtail-D1 |
| GPIO16 | LCD-DC |
| GPIO17 | LCD-CS |
| GPIO18 | LCD-SCK |
| GPIO19 | LCD-DIN |
| GPIO20 | I2C0-SDA0/Crowtail-I2C-SDA/PCA9555-SDA |
| GPIO21 | I2C0-SCL0/Crowtail-I2C-SCL/ PCA9555-SCL |
| GPIO22 | LCD-RST |
| GPIO23 | LCD-BLK |
| GPIO24 | 485-EN |
| GPIO25 | DATA |
| GPIO26 | A0/ Crowtail-A0 |
| GPIO27 | A1/ Crowtail-A1 |
| GPIO28 | BUZZER |
| GPIO29 | ADC-KEY |

## Usage
-----

### **1. Development Environment Construction**

1.1 Directly visit the Arduino official website and download the Arduino development tools supported by the device. The link is as follows: ***[https://www.arduino.cc/en/software](https://www.arduino.cc/en/software)***.   
![Lora RA-08H 1 1.png](https://wiki.elecrow.com/images/2/23/Lora_RA-08H_1_1.png){ loading=lazy }

1.2 Click the downloaded Arduino development tool to install the software. After the software installation is complete, open it directly, as shown in the figure below:   
![Lora RA-08H 2 1 2 1.png](https://wiki.elecrow.com/images/thumb/c/c6/Lora_RA-08H_2_1_2_1.png/490px-Lora_RA-08H_2_1_2_1.png){ loading=lazy }

1.3 Click *"File" -&gt; "Preferences"* on the menu bar to pop up the preference setting interface.   
![Lora RA-08H 2 1 3 1.png](https://wiki.elecrow.com/images/thumb/c/ce/Lora_RA-08H_2_1_3_1.png/490px-Lora_RA-08H_2_1_3_1.png){ loading=lazy }

1.4 Click the icon on the far right of the Additional Boards Manager URLs column, enter ***[https://github.com/earlephilhower/arduino-pico/releases/download/global/package\_rp2040\_index.json](https://github.com/earlephilhower/arduino-pico/releases/download/global/package_rp2040_index.json)*** in the pop-up window, and add RP2040 Arduino IDE development board URLs.   
![Lora RA-08H 1 4.png](https://wiki.elecrow.com/images/9/9c/Lora_RA-08H_1_4.png){ loading=lazy }

1.5 Click *"Tools" -&gt; "Board:..." -&gt; "Boards Manager..."* in the menu bar to enter the Boards Manager interface.   
![Lora RA-08H 2 1 5 1.png](https://wiki.elecrow.com/images/thumb/5/51/Lora_RA-08H_2_1_5_1.png/490px-Lora_RA-08H_2_1_5_1.png){ loading=lazy }

1.6 Enter "RP2040" in the search box, select "Raspberry Pi Pico/RP2040" and install the development environment.   
It should be noted here that when selecting the development environment version, do not choose the latest one. It is recommended to choose version 2.6.0.    
![Lora RA-08H 1 6.png](https://wiki.elecrow.com/images/3/38/Lora_RA-08H_1_6.png){ loading=lazy }

1.7 After the environment is successfully installed, if you find "Rasperry Pi RP2040 Boards" in the Arduino IDE development board management, it means that the environment is successfully built.   
![Lora RA-08H 1 7.png](https://wiki.elecrow.com/images/0/08/Lora_RA-08H_1_7.png){ loading=lazy }

### **2. Software Settings**

2.1 For the first use, you need to set up and select the correct development board. Click *"Tools" -&gt; "Board:..." -&gt; "Rasperry Pi RP2040 Boards" -&gt; "Rasperry Pi Pico"* in the menu bar, as shown in the figure below:   
![Lora RA-08H 2 1.png](https://wiki.elecrow.com/images/c/c2/Lora_RA-08H_2_1.png){ loading=lazy }

2.2 Connect the Lora RA-08H Development Board to the computer via a TYPE-C USB cable. When the development board is connected to the computer for the first time, a "RPI-RP2" USB virtual U disk will appear.   
![Lora RA-08H 2 2.png](https://wiki.elecrow.com/images/d/dd/Lora_RA-08H_2_2.png){ loading=lazy }

2.3 Here you need to burn a sample code in the opened Arduino IDE to convert the "RPI-RP2" USB virtual U disk into a "COM port". The sample code path is shown in the figure below:   
![Lora RA-08H 2 3 1.png](https://wiki.elecrow.com/images/4/45/Lora_RA-08H_2_3_1.png){ loading=lazy }

The code after opening is as follows:    
![Lora RA-08H 2 2 3 1.png](https://wiki.elecrow.com/images/thumb/2/20/Lora_RA-08H_2_2_3_1.png/490px-Lora_RA-08H_2_2_3_1.png){ loading=lazy }

2.4 Click the download icon at the bottom of the menu bar to burn the code to the Lora RA-08H Development Board. After the code is burned successfully, COMXX (Raspberry Pi Pico) will be displayed in *"Tools" -&gt; "Port"*. Now you can program Lora RA-08H Development Board with Arduino IDE!

### **3. Sample Program**

**Example 1 - Driving the Onboard Passive Buzzer Let the buzzer go off!**   
3.1.1 The position of the onboard buzzer on the development board.   
![Lora RA-08H 3 1 1.png](https://wiki.elecrow.com/images/d/dc/Lora_RA-08H_3_1_1.png){ loading=lazy }

3.1.2 Open the *"Buzzer.ino"* sample program in the Arduino IDE, and then click the upload program icon to upload the program to the development board.   
![Lora RA-08H 3 1 2 4.png](https://wiki.elecrow.com/images/thumb/f/f6/Lora_RA-08H_3_1_2_4.png/500px-Lora_RA-08H_3_1_2_4.png){ loading=lazy }

3.1.3 After the program is uploaded successfully, the buzzer will sound automatically!

**Example 2 - Let the onboard 1.8-inch LCD display red, green and blue respectively**   
3.2.1 Copy the *"Adafruit-GFX-Library"* library file and *"Adafruit-ST7735-Library-master"* library file to the libraries folder of the Arduino IDE.  
*( Original path: **"...\\Lora\_RA-08H\_Development\_Board\\Library\\..."**; Copy path: **"...\\Arduino\\libraries\\..." )***   
![Lora RA-08H 3 2 1.png](https://wiki.elecrow.com/images/d/d6/Lora_RA-08H_3_2_1.png){ loading=lazy }

3.2.2 Open the *"LCD.ino"* sample program in the Arduino IDE, and then click the upload program icon to upload the program to the development board.    
![Lora RA-08H 3 2 2 3.png](https://wiki.elecrow.com/images/thumb/9/9c/Lora_RA-08H_3_2_2_3.png/500px-Lora_RA-08H_3_2_2_3.png){ loading=lazy }

3.2.3 After the upload is successful, the LCD screen will display blue, green and red backlight in turn.   
![Lora RA-08H 3 2 3.png](https://wiki.elecrow.com/images/thumb/3/33/Lora_RA-08H_3_2_3.png/500px-Lora_RA-08H_3_2_3.png){ loading=lazy }

**Example 3 - Light up 6 programmable LEDs on board through I2C control**   
3.3.1 Copy the *"PCA9557"* library file to the libraries folder of the Arduino IDE.   
![Lora RA-08H 3 3 1.png](https://wiki.elecrow.com/images/f/f7/Lora_RA-08H_3_3_1.png){ loading=lazy }

3.3.2 Open the *"PCA9557\_test.ino"* sample program in the Arduino IDE, and then click the upload program icon to upload the program to the development board.   
![Lora RA-08H 3 3 2 2.png](https://wiki.elecrow.com/images/thumb/f/f3/Lora_RA-08H_3_3_2_2.png/500px-Lora_RA-08H_3_3_2_2.png){ loading=lazy }

3.3.3 The effect after the program is uploaded successfully.   
![Lora RA-08H 3 3 3.png](https://wiki.elecrow.com/images/e/e2/Lora_RA-08H_3_3_3.png){ loading=lazy }

**Example 4 - Read the 4 ADC-KEYs on the board through the ADC, and print the corresponding key value in the COM port**   
3.4.1 Open the *"AD\_Key.ino"* sample program in the Arduino IDE, and then click the upload program icon to upload the program to the development board.   
![Lora RA-08H 3 4 1 1.png](https://wiki.elecrow.com/images/thumb/b/b3/Lora_RA-08H_3_4_1_1.png/500px-Lora_RA-08H_3_4_1_1.png){ loading=lazy }

3.4.2 After the program is uploaded successfully, open the Serial Monitor. After pressing the keys one by one, observe whether the serial port prints the corresponding key value.    
![Lora RA-08H 3 4 2.png](https://wiki.elecrow.com/images/c/ce/Lora_RA-08H_3_4_2.png){ loading=lazy }
![Lora RA-08H 3 4 3.png](https://wiki.elecrow.com/images/5/5d/Lora_RA-08H_3_4_3.png){ loading=lazy }

**Example 5 - Light up 6 programmable LEDs on board through I2C control**   
3.5.1 As shown in the figure below, connect the Crowtail OLED module and the Crowtail Potentiometer module to the Crowtail I2C interface of the Lora RA-08H Development Board.   
![Lora RA-08H 3 5 1.png](https://wiki.elecrow.com/images/c/c7/Lora_RA-08H_3_5_1.png){ loading=lazy }

3.5.2 Find the Pins arduino.h file under the *"... \\Users \\Administrator \\AppData \\Local \\Arduino15\\packages\\rp2040\\hardware\\rp2040\\2.0.0\\variants\\rpipico\\..."* path.   
Opening the file, and modify the default definition *"define PIN\_WIRE0\_SDA (4u)"* and *"define PIN\_WIRE0\_SDA (5u)"* to *"define PIN\_WIRE0\_SDA (20u)"* and *"define PIN\_WIRE0\_SDA (21)"*.    
![Lora RA-08H 3 5 2.png](https://wiki.elecrow.com/images/8/89/Lora_RA-08H_3_5_2.png){ loading=lazy }

3.5.3 Install u8g2 library in Arduino IDE. Click *"Sketch" -&gt; "Include Library" -&gt; "Manage Libraries"*, then enter "u8g2" in the pop-up interface, find "u8g2" and click "Install" to complete the installation of the u8g2 library.    
![Lora RA-08H 3 5 3.png](https://wiki.elecrow.com/images/1/1a/Lora_RA-08H_3_5_3.png){ loading=lazy }

3.5.4 Open the *"Crowtail\_OLED.ino"* sample program in the Arduino IDE, and then click the upload program icon to upload the program to the development board.     
![Lora RA-08H 3 5 4 2.png](https://wiki.elecrow.com/images/thumb/3/36/Lora_RA-08H_3_5_4_2.png/500px-Lora_RA-08H_3_5_4_2.png){ loading=lazy }

3.5.5 After power on, the value on the sliding potentiometer will be displayed on the OLED screen.     
![Lora RA-08H 3 5 5.png](https://wiki.elecrow.com/images/e/e9/Lora_RA-08H_3_5_5.png){ loading=lazy }

**Example 6 - Communication between RP2040 and RA-08H**     
3.6.1 Open the *"RA\_08H.ino"* sample program in the Arduino IDE, and then click the upload program icon to upload the program to the development board.     
![Lora RA-08H 3 6 1 1.png](https://wiki.elecrow.com/images/thumb/6/6c/Lora_RA-08H_3_6_1_1.png/500px-Lora_RA-08H_3_6_1_1.png){ loading=lazy }

3.6.2 After the program is successfully uploaded, open the serial monitor and send the AT command "AT+CGSN?" to RA\_08H.    
![Lora RA-08H 3 6 2.png](https://wiki.elecrow.com/images/d/d7/Lora_RA-08H_3_6_2.png){ loading=lazy }

3.6.3 After sending the command, if the monitor can display the returned "+CGSN=85521C0A02243201 OK" (the value returned by different RA-08H firmware is different), it proves that you can send AT commands through the Arduino IDE to control and set the RA\_08H module.    
![Lora RA-08H 3 6 3.png](https://wiki.elecrow.com/images/thumb/9/92/Lora_RA-08H_3_6_3.png/500px-Lora_RA-08H_3_6_3.png){ loading=lazy }

## Resource
--------

- [Lora\_RA-08H\_Development\_Board\_Sample\_Code](https://wiki.elecrow.com/images/9/99/Lora_RA-08H_Development_Board_Sample_Code.zip)
- [Lora RA-08H Development Board\_Eagle](https://wiki.elecrow.com/images/9/96/Lora_RA-08H_development_board_Eagle.zip)