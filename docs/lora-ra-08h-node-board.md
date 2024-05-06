---
title: Lora RA-08H Node Board
---

## Description
-----------

Lora RA-08H Node Board is a development board based on the combination of Raspberry Pi RP2040 main control chip and RA-08H, multiple Crowtail general IO interfaces, can be used with Crowtail series modules. The onboard Lorawan module is connected to the Lorawan platform to realize remote module control, which can be applied to maker education, smart home, industrial control, etc.

**Model: [CRT01261N](https://www.elecrow.com/lora-ra-08h-node-board-lorawan-node-module-for-long-range-communication-868mhz-915mhz.html)**   
![LoRa RA-08H Node Board.jpg](https://wiki.elecrow.com/images/thumb/d/dd/LoRa_RA-08H_Node_Board.jpg/600px-LoRa_RA-08H_Node_Board.jpg){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png){loading=lazy}](https://www.elecrow.com/lora-ra-08h-node-board-lorawan-node-module-for-long-range-communication-868mhz-915mhz.html?wiki "Title text")

## Feature
-------

- Integrate RP2040 and RA-08H (Lorawan module)
- Main control Raspberry Pi chip RP2040, built-in 264KB SRAM, onboard 4MB Flash
- Dual Core Arm Cortex-M0+ @ 133MHz
- RA-08H module adopts embedded memory, 128KB Flash, 16KB SRAM
- RA-08H module supports frequency band: 803MHZ-930MHZ
- RA-08H module supports external antenna, SMA interface or IPEX first generation interface
- Compatible with Arduino/Micropython
- 6 5V Crowtail interfaces (2 analog interfaces, 2 digital interfaces, 1 UART interfaces, 1 IIC interfaces)
- 2\*10 universal GPIO interfaces
- 1 Battery interface
- 1 Solar interface

## Technical Specification
-----------------------

- Working input voltage: USB 5V-1A
- Operating temperature range: -10°C ~ 65°C

## Interface Function
------------------

![Lora RA-08H Node 1 1.png](https://wiki.elecrow.com/images/0/0a/Lora_RA-08H_Node_1_1.png){ loading=lazy }![Lora RA-08H Node 1 2.png](https://wiki.elecrow.com/images/5/5a/Lora_RA-08H_Node_1_2.png){ loading=lazy }

| **Name** | **Interface/Function Definition** |
|:-:|:-:|
| USB-C | USB-C interface, it is used for the power supply of the development board and the communication interface between PC and RP2040. |
| PWR | Power Indicator |
| RST | Reset button, press this button to reset the system. |
| (RP2040)BOOT | Download button, hold down the Boot button and press the RESET button to enter boot firmware download mode. Users can download firmware through the USB interface. |
| (RA-08H)BOOT | Long press the download button before power-on. Connect the external USB-to-serial port module. Connect the cables to the external USB-to-serial port module according to (GND~GND, RA-3V~3.3V, RA-RX~TX, RA-TX~RX) and update the firmware of the RA-08H module through the TremoProgrammer\_v0.8 software. |
| USB-C | USB-C interface, it is used for the power supply of the development board and the communication interface between PC and RP2040. |
| GND-3V3-SIG | 3\*14PIN, 3.3V general-purpose IO header interface, which can be used for external 3.3V sensor modules or devices. |
| Crowtail-A0 | External Crowtail-5V-HY-4P-2.0 port. Sensors or modules that can be used to interface with 5V Crowtail analog signals. |
| Crowtail-A1 | External Crowtail-5V-HY-4P-2.0 port. Sensors or modules that can be used to interface with 5V Crowtail analog signals. |
| Crowtail-D0 | External Crowtail-5V-HY-4P-2.0 port. Sensors or modules that can be used to interface with 5V Crowtail digital signals. |
| Crowtail-D1 | External Crowtail-5V-HY-4P-2.0 port. Sensors or modules that can be used to interface with 5V Crowtail digital signals. |
| Crowtail-UART | External Crowtail-5V-HY-4P-2.0 port. Sensors or modules that can be used to connect to 5V Crowtail UART serial communication. |
| Crowtail-I2C | External Crowtail-5V-HY-4P-2.0 port. Sensors or modules that can be used to connect to 5V Crowtail I2C interface communication. |
| BAT | None. |
| SOLAR | None. |

## Usage
-----

### **Development Environment Construction**

1\. Directly visit the Arduino official website and download the Arduino development tools supported by the device. The link is as follows: *[https://www.arduino.cc/en/software](https://www.arduino.cc/en/software)*.   
![Lora RA-08H 1 1.png](https://wiki.elecrow.com/images/2/23/Lora_RA-08H_1_1.png){ loading=lazy }

2\. Click the downloaded Arduino development tool to install the software. After the software installation is complete, open it directly, as shown in the figure below:   
![Lora RA-08H 2 1 2 1.png](https://wiki.elecrow.com/images/thumb/c/c6/Lora_RA-08H_2_1_2_1.png/490px-Lora_RA-08H_2_1_2_1.png){ loading=lazy }

3\. Click *"File" -&gt; "Preferences"* on the menu bar to pop up the preference setting interface.   
![Lora RA-08H 2 1 3 1.png](https://wiki.elecrow.com/images/thumb/c/ce/Lora_RA-08H_2_1_3_1.png/490px-Lora_RA-08H_2_1_3_1.png){ loading=lazy }

4\. Click the icon on the far right of the Additional Boards Manager URLs column, enter ***[https://github.com/earlephilhower/arduino-pico/releases/download/global/package\_rp2040\_index.json](https://github.com/earlephilhower/arduino-pico/releases/download/global/package_rp2040_index.json)*** in the pop-up window, and add RP2040 Arduino IDE development board URLs.    
![Lora RA-08H 1 4.png](https://wiki.elecrow.com/images/9/9c/Lora_RA-08H_1_4.png){ loading=lazy }

5\. Click *"Tools" -&gt; "Board:..." -&gt; "Boards Manager..."* in the menu bar to enter the Boards Manager interface.    
![Lora RA-08H 2 1 5 1.png](https://wiki.elecrow.com/images/thumb/5/51/Lora_RA-08H_2_1_5_1.png/490px-Lora_RA-08H_2_1_5_1.png){ loading=lazy }

6\. Enter "RP2040" in the search box, select "Raspberry Pi Pico/RP2040" and install the development environment.    
It should be noted here that when selecting the development environment version, do not choose the latest one. It is recommended to choose version 2.6.0.   
![Lora RA-08H 1 6.png](https://wiki.elecrow.com/images/3/38/Lora_RA-08H_1_6.png){ loading=lazy }

7\. After the environment is successfully installed, if you find "Rasperry Pi RP2040 Boards" in the Arduino IDE development board management, it means that the environment is successfully built.   
![Lora RA-08H 1 7.png](https://wiki.elecrow.com/images/0/08/Lora_RA-08H_1_7.png){ loading=lazy }

### **Software Settings**

1\. For the first use, you need to set up and select the correct development board. Click *"Tools" -&gt; "Board:..." -&gt; "Rasperry Pi RP2040 Boards" -&gt; "Rasperry Pi Pico"* in the menu bar, as shown in the figure below:     
![Lora RA-08H 2 1.png](https://wiki.elecrow.com/images/c/c2/Lora_RA-08H_2_1.png){ loading=lazy }

2\. Connect the Lora RA-08H Development Board to the computer via a TYPE-C USB cable. When the development board is connected to the computer for the first time, a "RPI-RP2" USB virtual U disk will appear.   
![Lora RA-08H 2 2.png](https://wiki.elecrow.com/images/d/dd/Lora_RA-08H_2_2.png){ loading=lazy }

3\. Here you need to burn a sample code in the opened Arduino IDE to convert the "RPI-RP2" USB virtual U disk into a "COM port". The sample code path is shown in the figure below:    
![Lora RA-08H 2 3 1.png](https://wiki.elecrow.com/images/4/45/Lora_RA-08H_2_3_1.png){ loading=lazy }

The code after opening is as follows:    
![Lora RA-08H 2 2 3 1.png](https://wiki.elecrow.com/images/thumb/2/20/Lora_RA-08H_2_2_3_1.png/490px-Lora_RA-08H_2_2_3_1.png){ loading=lazy }

4\. Click the download icon at the bottom of the menu bar to burn the code to the Lora RA-08H Development Board. After the code is burned successfully, COMXX (Raspberry Pi Pico) will be displayed in *"Tools" -&gt; "Port"*. Now you can program Lora RA-08H Development Board with Arduino IDE!

### **Sample Program**

**Example 1 - Switch Light**   
1.1 Connect the Crowtail-LED and Crowtail-Button to the D3 port and D2 port of the Lora RA-08H Node board respectively.    
![Lora RA-08H Node Program 1.jpg](https://wiki.elecrow.com/images/thumb/c/c6/Lora_RA-08H_Node_Program_1.jpg/600px-Lora_RA-08H_Node_Program_1.jpg){ loading=lazy }

1.2 Open the *"Switch\_Light.ino"* sample program in the Arduino IDE, and then click the upload program icon to upload the program to the development board.

```
void setup() {
  pinMode(2, INPUT_PULLUP);
  pinMode(3, OUTPUT);
}

void loop() {
  if (digitalRead(2) == HIGH){
    digitalWrite(3, HIGH);
  }
  else{
    digitalWrite(3, LOW);
  }
}
```

1.3 After the program is successfully uploaded, press the button, the led will light up; release it to turn off.

**Example 2 - OLED Display**   
2.1 Connect the Crowtail OLED module and Crowtail linear potentiometer to the Crowtail I2C port and A0 port of the Lora RA-08H node board respectively.    
![Lora RA-08H Node Program 2.jpg](https://wiki.elecrow.com/images/thumb/9/90/Lora_RA-08H_Node_Program_2.jpg/600px-Lora_RA-08H_Node_Program_2.jpg){ loading=lazy }

2.2 Open the *"OLED.ino"* sample program in the Arduino IDE, and then click the upload program icon to upload the program to the development board.

```
#include "hardware/adc.h"
#include <U8x8lib.h>
#include <Wire.h>
int val;
U8X8_SSD1306_128X64_NONAME_HW_I2C u8x8(/* reset=*/ U8X8_PIN_NONE);
void setup() {
  u8x8.begin();
  u8x8.setFont(u8x8_font_chroma48medium8_r);//Small Font 16 Characters  
  u8x8.noInverse();//Normal
  u8x8.clear();
  u8x8.setCursor(5,2);
  u8x8.print("Lora DEV");
  u8x8.setCursor(1,4);
  u8x8.print("VALUE = ");
}
void loop() {
  int sensorValue = analogRead(A0);
  delay(500);
  u8x8.setCursor(9,4);
  u8x8.print("    "); 
  u8x8.setCursor(9,4);
  u8x8.print(sensorValue);
  delay(100);
}
```

2.3 After the upload is successful, when you slide the handle of the linear potentiometer, the OLED displays the current analog value in real time.

**Example 3 - Ultrasonic Ranging**    
3.1 Connect the Crowtail Ultrasonic Sensor to the Crowtail UART port of the Lora RA-08H node board.     
![Lora RA-08H Node Program 3.jpg](https://wiki.elecrow.com/images/thumb/6/61/Lora_RA-08H_Node_Program_3.jpg/600px-Lora_RA-08H_Node_Program_3.jpg){ loading=lazy }

3.2 Open the *"Ultrasonic\_ranging.ino"* sample program in the Arduino IDE, and then click the upload program icon to upload the program to the development board.

```
const int TrigPin = 9;
const int EchoPin = 8;
float cm;
void setup() 
{ 
  Serial.begin(9600);
  pinMode(TrigPin, OUTPUT); 
  pinMode(EchoPin, INPUT); 
} 
void loop() 
{ 
  digitalWrite(TrigPin, LOW); 
  delayMicroseconds(2);
  digitalWrite(TrigPin, HIGH); 
  delayMicroseconds(10); 
  digitalWrite(TrigPin, LOW);
  cm = pulseIn(EchoPin, HIGH) / 58.0;  
  cm = (int(cm * 100.0)) / 100.0;  
  Serial.print("Distance:"); 
  Serial.print(cm); 
  Serial.print("cm"); 
  Serial.println(); 
  delay(1000); 
}
```

3.3 After the upload is successful, open the serial monitor to check the serial port printing.   
![Lora RA-08H Node 3-1.png](https://wiki.elecrow.com/images/thumb/a/af/Lora_RA-08H_Node_3-1.png/490px-Lora_RA-08H_Node_3-1.png){ loading=lazy }

**Example 4 - Communication between RP2040 and RA-08H**   
4.1 Open the *"RA\_08H.ino"* sample program in the Arduino IDE, and then click the upload program icon to upload the program to the development board.

```
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  Serial1.setRX(1);
  Serial1.setTX(0);
  Serial1.begin(9600);
}
void loop() {
  if (Serial.available())
  {
    Serial1.write(Serial.read());
  }

  if (Serial1.available())
  {
    Serial.write(Serial1.read());
  }
}
```

4.2 After the program is successfully uploaded, open the serial monitor and send the AT command "AT+CGSN?" to RA\_08H.    
![Lora RA-08H 3 6 2.png](https://wiki.elecrow.com/images/d/d7/Lora_RA-08H_3_6_2.png){ loading=lazy }


4.3 After sending the command, if the monitor can display the returned "+CGSN=85521C0A02243201 OK" (the value returned by different RA-08H firmware is different), it proves that you can send AT commands through the Arduino IDE to control and set the RA\_08H module.    
![Lora RA-08H 3 6 3.png](https://wiki.elecrow.com/images/thumb/9/92/Lora_RA-08H_3_6_3.png/490px-Lora_RA-08H_3_6_3.png){ loading=lazy }


**Example 5 - Ra-08 transparent transmission application**    
5.1Connect the leads according to the diagram.   
![Lora RA-08H 5 1.jpg](https://wiki.elecrow.com/images/thumb/0/0c/Lora_RA-08H_5_1.jpg/490px-Lora_RA-08H_5_1.jpg){ loading=lazy }

5.2First prepare the transparent firmware, and use the firmware download tool to download the firmware.    
After connecting the wires according to the above instructions, unplug the RST pin on the module, open the firmware burning tool, select the firmware to be burned, click "Erase All", clear the original firmware in the module, and erase After success, click "Start" to burn the new firmware.    
![Lora RA-08H 5 2.png](https://wiki.elecrow.com/images/thumb/0/0f/Lora_RA-08H_5_2.png/490px-Lora_RA-08H_5_2.png){ loading=lazy }  

5.3Download the program for the two modules separately to realize the transparent transmission function.    
![Lora RA-08H 5 3.png](https://wiki.elecrow.com/images/thumb/a/ab/Lora_RA-08H_5_3.png/490px-Lora_RA-08H_5_3.png){ loading=lazy }

## Resource
--------

- [Lora RA-08H Node Board Code](https://wiki.elecrow.com/images/0/00/Lora_Node_Board_Code.zip)
- [Lora\_RA-08H\_Node\_ Board\_Eagle](https://wiki.elecrow.com/images/8/8f/Lora_RA-08H_Node_Board_Eagle.zip)