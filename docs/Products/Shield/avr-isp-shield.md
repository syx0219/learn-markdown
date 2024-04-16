---
title: AVR ISP Shield
---

## Introduction
------------

Did you know your Arduino can burn bootloaderds onto Atmega chips, turning them into Arduino compatible microcontrollers. It required a breadboard and a whole mess of jumper wires but we've just made it a ton easier on you with the AVR ISP Shield!  
It is very easy to use. Just following the Arduino tutorial, You can turn your Atmega chips to Arduino compatible microcontrollers or change the bootloader of the Arduino boards. Such as you can turn the Crowduino to a Arduino UNO board.

**Model: [ACS26020S](http://www.elecrow.com/avr-isp-shield-v11-p-563.html)**  
![AVR ISP Shield.jpg](https://wiki.elecrow.com/images/thumb/5/5d/AVR_ISP_Shield.jpg/600px-AVR_ISP_Shield.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){ loading=lazy }](https://www.elecrow.com/avr-isp-shield-v11-p-563.html?wiki "Title text")

## Features
--------

Dimensions(mm):60.0(L)x53.5(W)x34.0(H)

## Usage
-----

1.Plug AVR ISP Shield onto the Arduino/Crowduino. Connect the board to PC using USB cable.

![AVR ISP Shield1.jpg](https://wiki.elecrow.com/images/thumb/f/fa/AVR_ISP_Shield1.jpg/400px-AVR_ISP_Shield1.jpg){ loading=lazy }

2.Upload the ArduinoISP firmware (in Examples) to your Arduino board.(File&gt;examples&gt;ArduinoISP)

![AVR ISP Shield4.jpg](https://wiki.elecrow.com/images/thumb/b/b3/AVR_ISP_Shield4.jpg/400px-AVR_ISP_Shield4.jpg){ loading=lazy }

3.Select the items in the Tools &gt; Board and Serial Port menus that correspond to the board you are using as the programmer (not the board being programmed).

<img loading="lazy" alt="AVR ISP Shield5.jpg" src="https://wiki.elecrow.com/images/thumb/6/6d/AVR_ISP_Shield5.jpg/400px-AVR_ISP_Shield5.jpg" style="zoom:90%;vertical-align: top;" />
<img loading="lazy" alt="AVR ISP Shield6.jpg" src="https://wiki.elecrow.com/images/thumb/4/44/AVR_ISP_Shield6.jpg/400px-AVR_ISP_Shield6.jpg" style="zoom:90%;" />

4.Upload the ArduinoISP sketch.

![AVR ISP Shield7.jpg](https://wiki.elecrow.com/images/thumb/7/7b/AVR_ISP_Shield7.jpg/400px-AVR_ISP_Shield7.jpg){ loading=lazy }

5.Plug the atmega328P-PU IC into the IC holder of the AVR ISP shield. please be careful about the direction of the atmega328 Or Wire your Arduino board to the target as shown in the diagram below.

<img loading="lazy" alt="AVR ISP Shield2.jpg" src="https://wiki.elecrow.com/images/thumb/8/80/AVR_ISP_Shield2.jpg/400px-AVR_ISP_Shield2.jpg" style="zoom:90%;" />
<img loading="lazy" alt="AVR ISP Shield3.jpg" src="https://wiki.elecrow.com/images/thumb/1/13/AVR_ISP_Shield3.jpg/400px-AVR_ISP_Shield3.jpg" style="zoom:90%;" />

7.Select the item in the Tools &gt; Board menu that corresponds to the board on which you want to burn the bootloader (not the board that you're using as the programmer). See the board descriptions on the environment page for details.  
For example: 
Burn the bootloader to the Arduino UNO.

![AVR ISP Shield11.jpg](https://wiki.elecrow.com/images/thumb/4/44/AVR_ISP_Shield11.jpg/400px-AVR_ISP_Shield11.jpg){ loading=lazy }

Burn the bootloader to the Crowduino Leonardo.

![AVR ISP Shield8.jpg](https://wiki.elecrow.com/images/thumb/c/c8/AVR_ISP_Shield8.jpg/400px-AVR_ISP_Shield8.jpg){ loading=lazy }

8.Use the Burn Bootloader &gt; Arduino as ISP command.

<img loading="lazy" alt="AVR ISP Shield9.jpg" src="https://wiki.elecrow.com/images/thumb/c/cb/AVR_ISP_Shield9.jpg/400px-AVR_ISP_Shield9.jpg" style="zoom:90%;" />
<img loading="lazy" alt="AVR ISP Shield10.jpg" src="https://wiki.elecrow.com/images/thumb/8/85/AVR_ISP_Shield10.jpg/400px-AVR_ISP_Shield10.jpg" style="zoom:90%;" />

9.When burning the bootloader, you will see the LED(PROG) on AVR ISP Shield is blinking, and it will put out when completing the burn. 

<img loading="lazy" alt="AVR ISP Shield12.jpg" src="https://wiki.elecrow.com/images/thumb/c/c2/AVR_ISP_Shield12.jpg/400px-AVR_ISP_Shield12.jpg" style="zoom:90%;" />
<img loading="lazy" alt="AVR ISP Shield13.jpg" src="https://wiki.elecrow.com/images/thumb/8/80/AVR_ISP_Shield13.jpg/400px-AVR_ISP_Shield13.jpg" style="zoom:90%;" />  

## Resources
---------

- [Schematic](../../files/ELE-AVR-ISP-Sheld-pdf.md)
- [ArduinoISP Tutorial](https://www.arduino.cc/en/Tutorial/ArduinoISP)