---
title: CrowPi
---

## **Description**
---------------

CrowPi is an educational tool based on Raspberry Pi, designed to help people learn electronics, programming, and basic computer science. CrowPi was first released on Kickstarter in May 2018 and won a very successful campaign. The initial users spoke highly of CrowPi and left several good reviews. The success of CrowPi is based on the popularity of Raspberry Pi and on the unique advantages of the product itself, such as the compact development board, the neat and portable case, the step-by-step tutorials, and the affordable price. As we all know, computer science and programming are now regarded as essential abilities for 21st-century students and are becoming a key component of many curriculums, even in primary schools. And when we combine computer science and programming with electronics, we can build many useful devices both for industrial applications and for use in our daily life. Some examples of modern applications for IT are: running a weather station, PIR automatic lighting, line tracking robot car, vehicle radar, and so on. By mastering knowledge, and these skills, today's kids can be better prepared for a future in which AI, lOT, big data, and robotics dominate the world.   
**Model: [SER35001L](https://www.elecrow.com/crowpi-compact-raspberry-pi-educational-kit.html)**  
![CrowPi.png](https://wiki.elecrow.com/images/thumb/c/c2/CrowPi.png/500px-CrowPi.png){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png){loading=lazy}](https://www.elecrow.com/crowpi-compact-raspberry-pi-educational-kit.html?wiki "Title text") 

## <font color="red">**SAFETY WARNING**</font>
--------------------

Elecrow puts their customer's safety and security at the first priority, for the same reason Elecrow doesn't use dangerous materials while manufacturing, and we follow extremely strict QA tests to make sure the highest quality product will be shipped to our customers. The CrowPi is a safe-to-use product with 5V input by power supply. Even though it's completely safe to use it under normal circumstances there are a few rules that parents should be aware of when buying this product for their children.

- Children should be under parent's supervision while using such a product, the product contains small parts which might cause chocking to small children if swallowed.
- The relay module supplied inside our CrowPi board should ONLY be used within the breadboard circuit designing, standing with 3v/5v power supply and SHOULD NOT under any circumstances be used / connected or wired to a 220v/110v power plug like light bulb, air conditioner etc ...
- We care about your children's eyes and health just as you do, we do not recommend using the device in dark room with no light for safety reasons and to protect the eyes from the light of the LED’ s and LCD display.
- The device was designed to be portable. It's possible to take it anywhere including out-doors, school, train etc … The device should not be left out-doors without supervision and / or in bad weather conditions such as rain and snow. The device is neither water or dust proof.

## **Parameters**
---------------

![CrowPi-wiki-1.png](https://wiki.elecrow.com/images/thumb/b/b4/CrowPi-wiki-1.png/700px-CrowPi-wiki-1.png){ loading=lazy }
![CrowPi-wiki-1-1.png](https://wiki.elecrow.com/images/thumb/1/18/CrowPi-wiki-1-1.png/700px-CrowPi-wiki-1-1.png){ loading=lazy }
![CrowPi-wiki-2.png](https://wiki.elecrow.com/images/thumb/b/b3/CrowPi-wiki-2.png/700px-CrowPi-wiki-2.png){ loading=lazy }

## **Sensor Control Description**
-------------------------------

| **Sensor Name** | **Control Pin** | **Control Method** | **Remarks** |
|---|---|---|---|
| BUZZER | pin12/GPIO18 | GPIO OUTPUT |
| RELAY | pin40/GPIO21 | GPIO OUTPUT |  |
| SOUND SENSOR | pin18/GPIO24 | GPIO INTPUT |  |
| TILT SWITCH | pin15/GPIO22 | GPIO INTPUT | UX5-2 ON |
| VIBRATION MOTOR | pin13/GPIO27 | GPIO OUTPUT | UX5-1 ON |
| PIR MOTION SENSOR | pin16/GPIO23 | GPIO OUTPUT |  |
| TOUCH SENSOR | pin11/GPIO17 | GPIO INTPUT |  |
| STEPPER MOTOR | pin29/GPIO5 pin31/GPIO6 pin33/GPIO13 pin35/GPIO19 | GPIO OUTPUT | UX5-3 ON UX5-4 ON UX5-5 ON UX5-6 ON |
| SERVO | pin22/GPIO25 | GPIO OUTPUT | UX5-8 ON |
| IR RECEIVER | pin38/GPIO20 | GPIO BOTH |  |
| TEMPERATURE&amp;HUMIDITY | pin7/GPIO4 | GPIO INTPUT |  |
| ULTRASONIC SENSOR | ECHO:Pin32/GPIO12 TRIG:Pin36/GPIO16 | GPIO INTPUT |  |
| LIGHT SENSOR | I2C | I2C | Address:0x5c |
| I2C LCD | I2C | I2C | Address:0x21 |
| 4 BIT SEGMENT | I2C | I2C | Address:0x70 |
| LED MATRIX | SPI | SPI | CS: pin26/GPIO8 |
| NFC MOUDLE | SPI | SPI | CS: pin24/GPIO7 |
| INDEPENDENT BUTTON | UP: pin37/GPIO26 DOWN: pin33/GPIO13 RIGHT: pin35/GPIO19 LEFT:pin22/GPIO25 | GPIO INPUT | UX1-5 ON UX1-6 ON UX1-7 ON |
| BUTTON ARRAY | Row1: pin13/GPIO27 Row2: pin15/GPIO22 Row3: pin29/GPIO5 Row4: pin31/GPIO6 Col1: pin22/GPIO25 Col2: pin37/GPIO26 Col3: pin35/GPIO19 Col4: pin33/GPIO13 | GPIO INPUT | UX1-1 ON UX1-2 ON UX1-3 ON UX1-4 ON UX1-5 ON UX1-6 ON UX1-7 ON UX1-8 ON |

**NOTE:** UX1 and UX5 are dialing switches, some sensors use the same GPIO, so if you want to use those sensors, you have to turn on the right switch, for example: button-LEFT using the same GPIO with the SERVO 2, if you want to use the SERVO, You can open UX5-8, if you want to use button-LEFT , you can open UX1-8.

## **Uasage** 
-----------

### **Initial Installation**

#### **Pre-installation requirements**

Before diving right into the CrowPi Initial installation guide we'd like to confirm you have everything that is required in order to make the installation process as smooth as possible.Please go through the following checklist and make sure you have it allNote: These are not optional. They are all necessary for the installation process.
![CrowPi-wiki-3.png](https://wiki.elecrow.com/images/thumb/d/d0/CrowPi-wiki-3.png/500px-CrowPi-wiki-3.png){ loading=lazy }
![CrowPi-wiki-4.png](https://wiki.elecrow.com/images/thumb/8/89/CrowPi-wiki-4.png/500px-CrowPi-wiki-4.png){ loading=lazy }

#### **Downloading the CrowPi Image**

![CrowPi-wiki-5.png](https://wiki.elecrow.com/images/thumb/e/ea/CrowPi-wiki-5.png/500px-CrowPi-wiki-5.png){ loading=lazy }  
The Raspberry Pi uses an Linux-based operating system in order to function properly,it uses a Micro-SD card to boot the operating system into a use-friendly environment to enable customers like you to code and make amazing things.In the following steps we'll go through downloading the Raspberry Pi Image that we're going to use.  
In order to make the whole process much easier and user-friendly, we've created an image based on the stock Raspberry Pi Raspbian Image with all the necessary drivers and installation that will help you get you started right away without hassle .You can either use this method and burn our Image or use a stock Raspbian Image from the Raspberry Pi website and then install all the drivers manually.  
**We highly recommend the first method. To clarify, We didn't modify or add any thing unnecessary to the image, all the modifications are for the pure purpose of making our CrowPi working perfectly with the Raspbian OS. If you don't have any advanced knowledge with compiling packages from source / getting around Linux OS - We strongly recommend downloading our Image.** To download our Image, go to the following link on your favourite web   
browser:[https://www.elecrow.com/download/crowpi/Crowpi-image-RPI-4B-Version.zip](https://www.elecrow.com/download/crowpi/Crowpi-image-RPI-4B-Version.zip)   
And download the “.img” (image) file that contains the CrowPi Raspbian OS.  
To download the stock Raspbian image, go to the following link on your favourite web browser: [https://www.raspberrypi.org/downloads/](https://www.raspberrypi.org/downloads/)  
And download the official Raspberry pi Raspbian OS or any other Raspberry compatible image that works for you .

#### **Burning the image into an Micro SD Card**

After you've successfully downloaded the image, you should have a file called“&lt;file\_name&gt;.img” while “&lt;file\_name&gt;” can depend on where you downloaded from,either Elecrow website or the Raspberry Pi Official website.  
The file extension should be “.img” or “.zip” if it’ s an “.zip” you should extract it to have a file extension “.img” .  
In order to extract it,download the software “7zip” for Windows or “the unarchiver”for Mac OSX:  
Windows: [http://www.7-zip.org/download.html](http://www.7-zip.org/download.html)  
Mac OSX: [http://wakaba.c3.cx/s/apps/unarchiver.html](http://wakaba.c3.cx/s/apps/unarchiver.html)  
After you successfully confirmed you have the file, the next step will be burning the image into your Micro SD card. In order to burn the image, we'll need a tool called “Etcher” , Etcher is a graphical MicroSD card writing tool that works on Mac OS, Linux and Windows.  
You can download Etcher for your Operating System here: [https://etcher.io/](https://etcher.io/)  
After downloading and opening Etcher you should see something like this:  
![CrowPi-wiki-6.png](https://wiki.elecrow.com/images/thumb/9/96/CrowPi-wiki-6.png/500px-CrowPi-wiki-6.png){ loading=lazy }  
Follow the following steps:  
1\) Click the “Select Image” button and select your .img file which you downloaded from either Elecrow Website or Raspberry Pi official website  
2\) Click “Select Drive” button to select your Micro SD Card that you would like to burn the image on (if Micro SD Card inserted, Etcher will do this step for you automatically)  
3\) Click Flash Button to flash the image, wait for it to finish and we're done!  
**Attaching the Raspberry Pi to the CrowPi Board**After finishing the burning process it's time to disconnect the micro SD card from the PC/ laptop and plug it into the Raspberry Pi.  
![CrowPi-wiki-7.png](https://wiki.elecrow.com/images/thumb/a/a3/CrowPi-wiki-7.png/500px-CrowPi-wiki-7.png){ loading=lazy }  
**Note** : Make sure to follow the following steps carefully, don't apply extra pressure or strong force over the cable as you might damage the pins.  
After successfully plugging back in the Micro SD card, we'll need to lay the Raspberry Pi over it's location on top of the CrowPi board.  
![CrowPi-wiki-8.png](https://wiki.elecrow.com/images/thumb/9/96/CrowPi-wiki-8.png/500px-CrowPi-wiki-8.png){ loading=lazy }  
Afterwards, we'll need to plug it in by using “rainbow” (flat) cable. We'll first carefully plug it into the Raspberry pi making sure it covers the exact pins of the raspberry pi and very importantly doing it carefully not to damage the Raspberry Pi pins.  
![CrowPi-wiki-9.png](https://wiki.elecrow.com/images/thumb/e/e1/CrowPi-wiki-9.png/500px-CrowPi-wiki-9.png){ loading=lazy }     
The second step will be plugging the “rainbow” cable into the CrowPi board.We'll take the other end of the “rainbow” cable and carefully plug it directly into the board making sure it covers all the pins and placed at the right spots.  
![CrowPi-wiki-10.png](https://wiki.elecrow.com/images/thumb/9/9c/CrowPi-wiki-10.png/500px-CrowPi-wiki-10.png){ loading=lazy }   
And … We are done! Well … almost!   
To make sure that the Raspberry Pi won't move during your rapid development we will need to attach it using screws, the Raspberry Pi contains screws to be attached to the CrowPi board, take a look at the following picture for reference:  
![CrowPi-wiki-11.png](https://wiki.elecrow.com/images/thumb/1/1d/CrowPi-wiki-11.png/500px-CrowPi-wiki-11.png){ loading=lazy }   
Make sure to attach them tightly for your Raspberry Pi safety.   
Last thing will be to plug the power adapter into the CrowPi board , it's highly recommended to use the power supply we supply with the board, but also any other power supply like micro-USB / Battery will work as well.   
![CrowPi-wiki-12.png](https://wiki.elecrow.com/images/thumb/d/d1/CrowPi-wiki-12.png/500px-CrowPi-wiki-12.png){ loading=lazy }  
![CrowPi-wiki-13.png](https://wiki.elecrow.com/images/thumb/6/64/CrowPi-wiki-13.png/500px-CrowPi-wiki-13.png){ loading=lazy }  
**First time booting into the Operating System** After We've prepared everything and plugged the power on.  
After powering on the board by clicking on the power button of cable, the Raspberry Pi should load the operating system automatically. Give it few seconds up to one minute to load until you'll see the desktop environment and you'll be ready to go.  
![CrowPi-wiki-14.png](https://wiki.elecrow.com/images/thumb/2/20/CrowPi-wiki-14.png/500px-CrowPi-wiki-14.png){ loading=lazy }
![CrowPi-wiki-15.png](https://wiki.elecrow.com/images/thumb/4/43/CrowPi-wiki-15.png/500px-CrowPi-wiki-15.png){ loading=lazy }  
Congratulations!  
You've officially got your CrowPi up and running.  
You might have realized that you have no way to control the desktop environment except for the 7 inch touch screen … let's get it solved by plugging in a keyboard and external mouse.  
We can do it by simply plugging in a USB keyboard and USB mouse   
![CrowPi-wiki-16.png](https://wiki.elecrow.com/images/thumb/d/d1/CrowPi-wiki-16.png/500px-CrowPi-wiki-16.png){ loading=lazy }  
Or connect Bluetooth keyboard and mouse using the touch screen with the bluetooth configuration    
![CrowPi-wiki-17.png](https://wiki.elecrow.com/images/thumb/2/22/CrowPi-wiki-17.png/500px-CrowPi-wiki-17.png){ loading=lazy }   
Last thing will be connecting to a local wifi access point or using Ethernet cable if that works better for you (both are optional)   
![CrowPi-wiki-18.png](https://wiki.elecrow.com/images/thumb/9/9b/CrowPi-wiki-18.png/500px-CrowPi-wiki-18.png){ loading=lazy }   
After this, you should have fully functional CrowPi laptop that you can do everything you want to with it!

## **Summary**
-----------

What should you do next?  
Now, when the initial installation is complete - you're ready to go!   
We've prepared 21 lessons for you to get started with the CrowPi.   
The lessons will get you started using Python 2.7 and modules usages including all on-board sensors and creating your own first project using the breadboard.   
Download the lessons PDF Here:   
[https://www.elecrow.com/download/CrowPi-lessons.pdf](https://www.elecrow.com/download/CrowPi-lessons.pdf)