---
title: Smart Pump Shield
---

## Description
-----------

The smart Pump Shield is based on Arduino Lenardo which has integrated into the mainboard. The mainboard will send the command to turn on the pump and suck water into the switch, the switch will separate the stream and will give just enough water for your plants. Then it will close the pump and the switch and continue to check when does your plant needs water. We add a RTC to set timing watering and a 0.96 inch OLED to show the time and the soil moisture status.

**Model: [PSMC18001M](https://www.elecrow.com/crowtail-smart-pump-shield-v2-1.html)**  
![Crowtail- smart pump shield 3 .jpg](https://wiki.elecrow.com/images/thumb/3/36/Crowtail-_smart_pump_shield_3_.jpg/600px-Crowtail-_smart_pump_shield_3_.jpg){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png)](https://www.elecrow.com/crowtail-smart-pump-shield-v2-1.html?wiki "Title text")

## Features
--------

- Eliminates the need for messy jumpers and breadboards, connect all sensors and modules with ease!
- Integrated Arduino UNO into the main board, program it easily.
- Power the board with single 12V power supply directly.
- 4 interfaces for sensors, one interface for water switch and one interface for motor or pump.

## Specifications
--------------

| **Item** | **Value** |
|---|---|
| Size of the box | 25 x 19 x 5.7cm |
| Length of water pipe | 5m |
| Length of 4 Pin Crowtail cable | 1m |

## Interfaces
----------

![Crowtail- smart pump shield 6 .jpg](https://wiki.elecrow.com/images/d/d1/Crowtail-_smart_pump_shield_6_.jpg){ loading=lazy }

## Usage
-----

### **Hardware Connection**

Connect the Smart Pump Board to your computer system   
Attach the micro USB side of the cable to the Smart Pump Board and the other end of the USB cable to an USB port in your computer.  
<font color="red">Notice：Please power the board by DC power when you upload the code  </font>
![Pump shield connect2PC.png](https://wiki.elecrow.com/images/thumb/3/3b/Pump_shield_connect2PC.png/800px-Pump_shield_connect2PC.png){ loading=lazy }

### **Software**

**STEP 1. Download the library and the program**  

- 1.Download the Library: [Watering\_kit\_library.zip](https://www.elecrow.com/download/Watering_kit_library.zip) and extract it. Copy it to the file-libraries in the arduino IDE file,i.e. D:\\Program Files (x86)\\Arduino\\libraries.
- 2.Download the program at [watering\_kit.zip](https://www.elecrow.com/download/watering_kit.zip) Extract the file from the zip file. The filename is watering\_kit.ino

**STEP 2. Configure which controller board will be used in the Arduino IDE**

On top of the Arduino IDE, click “Tools&gt;Board&gt;” and select “Arduino Leonardo”from the available options.  
![Select arduino board.png](https://wiki.elecrow.com/images/thumb/7/7f/Select_arduino_board.png/800px-Select_arduino_board.png){ loading=lazy }

**STEP 3. Configure which communication port to use**

The Arduino IDE needs to know in which USB computer port the Arduino Leonardo controller is connected in order to communicate with it.  
To do so, select “Tools&gt;Port” and select the COM port that indicates Arduino Leonardo. Please note that the actual numbers after the “COM” word will vary from computer to computer, so they could be different from the ones shown in the figure.  
![Select port.png](https://wiki.elecrow.com/images/thumb/a/ae/Select_port.png/800px-Select_port.png){ loading=lazy }   
Once completed, proceed to the next section to upload the program into the Arduino IDE and program the Arduino Leonard controller in the Smart Pump Board.

**STEP 4. Load the program in the Arduino IDE**

![Open.png](https://wiki.elecrow.com/images/thumb/7/7f/Open.png/800px-Open.png){ loading=lazy }
![Select file.png](https://wiki.elecrow.com/images/thumb/3/30/Select_file.png/850px-Select_file.png){ loading=lazy }
![Samrt pump shield code.png](https://wiki.elecrow.com/images/thumb/1/1a/Samrt_pump_shield_code.png/800px-Samrt_pump_shield_code.png){ loading=lazy }

**STEP 5. Click the ![Upload.png](./assets/images/30px-Upload.png){ loading=lazy } to upload the code to the Arduino board**

### Assembling the components

Note: For an overview of the process please watch this [YouTube video](https://www.youtube.com/watch?v=3WieNWgikEQ) .
1. Attach the cable to the Soil Humidity Sensors as shown in the figure. Repeat for each sensor.  
    ![Smart pump shield step1.png](https://wiki.elecrow.com/images/thumb/5/50/Smart_pump_shield_step1.png/800px-Smart_pump_shield_step1.png){ loading=lazy }
2. Connect the Soil Humidity Sensors to the Smart Pump Board  
    ![Smart pump shield step2.png](https://wiki.elecrow.com/images/thumb/5/55/Smart_pump_shield_step2.png/800px-Smart_pump_shield_step2.png){ loading=lazy }
3. Connect the Water Pump and the Four-way Valve to the Smart Pump Board  
    ![Smart pump shield step3.png](https://wiki.elecrow.com/images/thumb/0/09/Smart_pump_shield_step3.png/800px-Smart_pump_shield_step3.png){ loading=lazy }
4. Cut the plastic water pipe  
    First cut: for water source to water pump input (depends on water source height)  
    Second cut: water pump output to five-way valve input. (depends on how you locate the plants)  
    Third cut: 4 pieces for the output valves in the five-way valve to the input of the four-way water valves. (depends on how you locate the plants)  
    Fourth cut: 4 pieces for the output valves of the four-way water valves to the soil where each plant is planted. (depends on how you locate the plants)  
    ![Smart pump shield step4.png](https://wiki.elecrow.com/images/thumb/6/6f/Smart_pump_shield_step4.png/800px-Smart_pump_shield_step4.png){ loading=lazy }  
5. Connect the Water Pipes  
    Cut the water pipe and divide them to 6 parts. Make sure the pipe that goes inside the water source will be long enough to reach the water. We’ll connect 2 of the pipes to the pump, one sucks the water from the water sources while the other connects to the five-way water pipe.  
    ![Smart pump shield step6.png](https://wiki.elecrow.com/images/thumb/2/21/Smart_pump_shield_step6.png/800px-Smart_pump_shield_step6.png){ loading=lazy }  
    Connect five pipes to the valves.  
    ![Smart pump shield step7.png](https://wiki.elecrow.com/images/thumb/5/51/Smart_pump_shield_step7.png/800px-Smart_pump_shield_step7.png){ loading=lazy } 
6. Power it Up!  
    Just power the board with single 12V power supply directly! The shield will split the power between the Leonardo and the other devices. That way, the Leonardo will get 5V while the pump and the switch will get 12V.
    ![Smart pump shield step3.png](https://wiki.elecrow.com/images/thumb/0/09/Smart_pump_shield_step3.png/800px-Smart_pump_shield_step3.png){ loading=lazy }  

## FAQs
----

You can list you question here or contact with techsupport@elecrow.com for technology support.

## Resources
---------

[Crowtail-Smart\_Pump\_Shield-V3.2.zip](https://wiki.elecrow.com/images/a/ac/Crowtail-Smart_Pump_Shield-V3.2.zip)