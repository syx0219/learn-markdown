---
title: Smart car with ESP32-CAM Board
---

## Description
-----------

This video tank robot vehicle uses ESP32 as the main board, with OV2640 camera, and can control the movement via WiFi. It has a digital microphone interface, which can adjust the volume. The APP can control the shooting, and transmit video recordings to the APP in real-time. It has two lights at the same time, and the dark environment can be unobstructed. Support secondary development, app running environment supports Android 5.0 or above, but does not support IOS system.

**Model: [ACC35076R](https://www.elecrow.com/smart-car-with-camera-video-tracked-car-robot-wireless-chassis-car-with-esp32-cam-board-suit-for-arduino.html)**  
![Smart car 1.jpg](https://wiki.elecrow.com/images/thumb/e/e7/Smart_car_1.jpg/500px-Smart_car_1.jpg){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){loading=lazy}](https://www.elecrow.com/smart-car-with-camera-video-tracked-car-robot-wireless-chassis-car-with-esp32-cam-board-suit-for-arduino.html?wiki "Title text")

## Feature
-------

- Simple connection, say goodbye to complicated cable connection
- Control the smart car via WiFi
- Real-time transmission of photos and videos

## Specification
-------------

![SPECIFICATION.png](https://wiki.elecrow.com/images/9/90/SPECIFICATION.png){ loading=lazy }

## Interface
---------

![Smart car 4.jpg](https://wiki.elecrow.com/images/thumb/f/f7/Smart_car_4.jpg/700px-Smart_car_4.jpg){ loading=lazy }

## Usage
-----

### **Bluethooth Mode**

To modify the WiFi, robot name, password of the robot connection, you need to set it through Bluetooth.   
When the robot can not be found in WiFi mode, the robot IP can be obtained through Bluetooth mode.

Step 1: Turn on the smart car, click the BOOT button when the lights on. If the lights keep on(not of or flash), that means the car has entered BT mode.  
Step 2: Turn on the Bluetooth on your phone. Open the [ReconnaissanceRobot](https://wiki.elecrow.com/images/2/2c/ReconnaissanceRobot.zip) APP, click **Set Up Robot**,  
![Screenshot 20221103 151134 com.example.inspection.jpg](https://wiki.elecrow.com/images/thumb/1/1c/Screenshot_20221103_151134_com.example.inspection.jpg/400px-Screenshot_20221103_151134_com.example.inspection.jpg){ loading=lazy }  
Step 3: Find "esp32-robot" device and click it to enter settings page. Enter your home/office WiFi name and password, set the name and WiFi for your robot car. Then click **Send to robot** to send these data to smart car. The smart car will connect to your WLAN.  
<font color="blue">Note: The paired car will appear at the bottom of the "Used" window (if it has entered the Bluetooth mode)  
The unpaired car will appear in the "New" window.</font>  
![Screenshot 20221103 152055 com.example.inspection.jpg](https://wiki.elecrow.com/images/thumb/b/b7/Screenshot_20221103_152055_com.example.inspection.jpg/400px-Screenshot_20221103_152055_com.example.inspection.jpg){ loading=lazy }
![Settingsmartrobot.png](https://wiki.elecrow.com/images/thumb/9/97/Settingsmartrobot.png/400px-Settingsmartrobot.png){ loading=lazy }

### **WiFi Mode**

Step 1: Return to home page of APP, click Scan to find your smart car and select it. Here my car's name is esp32-robot.  
![Screenshot 20221103 151215 com.example.inspection.jpg](https://wiki.elecrow.com/images/thumb/a/a1/Screenshot_20221103_151215_com.example.inspection.jpg/400px-Screenshot_20221103_151215_com.example.inspection.jpg){ loading=lazy }  
Step 2: Enter the robot access password(the one you set at BT mode). I use the default password "1234". Then click **Start** to connect. Wait for a second... If there's no respond, please try to click the **Start** button again.  
Step 3: Then you will successfully go into operating interface!  
![Interfaceofsmartcar.png](https://wiki.elecrow.com/images/thumb/2/21/Interfaceofsmartcar.png/900px-Interfaceofsmartcar.png){ loading=lazy }

## FAQS
----

You can post your questions on our [forum](https://forum.elecrow.com/) or contact with techsupport@elecrow.com for technology support.

## Resourse
--------

[ReconnaissanceRobot APP](https://wiki.elecrow.com/images/2/2c/ReconnaissanceRobot.zip)