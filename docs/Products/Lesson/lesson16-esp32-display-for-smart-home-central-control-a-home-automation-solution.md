---
title: Lesson16 ESP32 Display for Smart Home Central Control:A Home Automation Solution
---

## **Project Introduction:**
-----

The smart home UI developed by Squareline is a smart home control panel based on ESP32 and a 3.5-inch SPI terminal screen. The panel integrates flame sensors, air quality sensors, temperature and humidity sensors, UV sensors, gesture sensors, and WiFi modules, which can monitor and control smart home devices.   
Through the flame sensor, the panel can detect whether there is a fire indoors and sound an alarm in time. The air quality sensor can detect the concentration of harmful gases such as carbon dioxide and PM2.5 indoors, reminding users to turn on the air purifier or ventilation. The temperature and humidity sensor can detect indoor temperature and humidity, allowing users to better grasp the indoor environment. The UV sensor can detect the outdoor ultraviolet intensity, reminding users to pay attention to sun protection. The gesture sensor can recognize user gestures and control smart home devices.   
The panel is connected to the Internet via WiFi, realizing remote control and data transmission functions. Users can control smart home devices through smartphones or tablets, and also view indoor environment data and device status.  

## **Introduction to Knowledge Points:**
-----

**Flame Sensor:**   
A flame sensor is a sensor used to detect flames. It judges whether there is a flame by detecting changes in light and heat in the environment. When a flame is detected, the sensor produces a signal output that can be used for alarms or to control other devices. Flame sensors are widely used in fire alarms, gas leak detection, and industrial control.   
**Air Quality Sensor:**   
An air quality sensor is a sensor used to detect pollutants in the air. It can detect the concentration of harmful substances such as carbon dioxide, PM2.5, formaldehyde, and benzene. Air quality sensors have a wide range of applications, including indoor air quality monitoring, air purifier control, industrial exhaust gas emission monitoring, etc.   
**Temperature and Humidity Sensor:**   
A temperature and humidity sensor is a sensor used to detect indoor temperature and humidity. It converts the detected temperature and humidity values into electrical signals. Temperature and humidity sensors are widely used in indoor environment monitoring, meteorological observations, temperature control, and other fields.   
**UV Sensor:**   
A UV sensor is a sensor used to detect the intensity of ultraviolet radiation. It can detect the intensity of UVB and UVC rays and is used for sun protection reminders and skin protection during outdoor activities. UV sensors can also be used in UV sterilization, plant growth control, and other fields.   
**Gesture Sensor:**    
A gesture sensor is a sensor used to detect gestures. It can detect hand movements and directions and convert gestures into digital signal outputs through algorithms. Gesture sensors are widely used in smart homes, game controls, industrial control, and other fields.   
**WiFi:**   
WiFi is a wireless LAN technology that can achieve high-speed wireless data transmission. WiFi can be used to connect to the Internet, realizing remote control and data transmission. In the field of smart homes, WiFi technology is widely used in the control and monitoring of smart home devices, such as smart lights, smart speakers, smart locks, etc.

## **Project steps:**
------

Note: First, add the provided image materials! (Add according to the actual materials provided)   
![16-1.png](https://wiki.elecrow.com/images/thumb/3/31/16-1.png/409px-16-1.png){ loading=lazy }   
1.Create a new project in Squareline Studio as before. First, select the Arduino module, and then perform simple settings for the project, such as project name and display size (480*320), and select 16-bit color. Click create.   
![16-2.png](https://wiki.elecrow.com/images/thumb/1/18/16-2.png/876px-16-2.png){ loading=lazy }    
2.Add the required components as shown in the figure, adjust and set the position according to the hierarchical diagram (see the provided project file for detailed components).   
![16-3.png](https://wiki.elecrow.com/images/2/29/16-3.png){ loading=lazy }   
3.Arrange the components in the positions shown in the figure and add background image materials to the screen.   
![16-4.png](https://wiki.elecrow.com/images/thumb/3/3a/16-4.png/544px-16-4.png){ loading=lazy }    
4.Add events to the corresponding components, which can operate the interface smoothly. For detailed event operations, refer to the project file (including Screen2, Screen3, Screen4, Image2, Image3, Image4, account, password, connect Button2, account1, password1, connect1, Button1);   
![16-5.png](https://wiki.elecrow.com/images/6/63/16-5.png){ loading=lazy }   
**Program part:**

5.After the program starts, first connect to WiFi;  
![16-6.png](https://wiki.elecrow.com/images/thumb/1/1a/16-6.png/550px-16-6.png){ loading=lazy }   
6.Detect the flame sensor and display normal or abnormal based on the fire situation.   
![16-7.png](https://wiki.elecrow.com/images/6/6b/16-7.png){ loading=lazy }   
7.Detect the temperature and humidity and update the information;   
![16-8.png](https://wiki.elecrow.com/images/thumb/0/0d/16-8.png/600px-16-8.png){ loading=lazy }   
8.Check the UV intensity and update the information;   
![16-9.png](https://wiki.elecrow.com/images/e/e1/16-9.png){ loading=lazy }   
9.The function to obtain the weather requires connecting to the network and obtaining relevant weather information from the weather website.   
![16-10.png](https://wiki.elecrow.com/images/thumb/d/db/16-10.png/1000px-16-10.png){ loading=lazy }   
**Running effect:**

After the program is successfully downloaded, check the effect on the screen.   
![16-11.png](https://wiki.elecrow.com/images/thumb/1/11/16-11.png/661px-16-11.png){ loading=lazy }

## **Summary:**
-----

Overall, the smart home UI developed by Squareline is a smart home control panel that integrates multiple sensors and wireless communication technologies, which can monitor and control smart home devices and improve users' quality of life.

## **HMI Display Tutorial Contents**
-----

- [Lesson01 Introducing the ESP32 Display series and environment configuration](./lesson01-introducing-the-esp32-display-series-and-environment-configuration.md)
- [Lesson02 Start the ESP32 DISPLAY GUI drawing via LovyanGFX Graphics Library](./lesson02-start-the-esp32-display-gui-drawing-via-lovyangfx-graphics-library.md)
- [Lesson03 How to Display Pictures on ESP32 Boards](./lesson03-how-to-display-pictures-on-esp32-boards.md)
- [Lesson04 LVGL Basics: How to install LVGL for ESP32 Displays](./lesson04-lvgl-basics-how-to-install-lvgl-for-esp32-displays.md)
- [Lesson05 Introduction to the 5 categories of LVGL GUI library Widgets](./lesson05-introduction-to-the-5-categories-of-lvgl-gui-library-widgets.md)
- [Lesson06 Use Squareline Studio to start your 1st human machine interface project](./lesson06-use-squareline-studio-to-start-your-1st-human-machine-interface-project.md)
- [Lesson07 How to implement text information input with Squareline Studio](./lesson07-how-to-implement-text-information-input-with-squareline-studio.md)
- [Lesson08 How to make the menu and a progress bar with Squareline Studio](./lesson08-how-to-make-the-menu-and-a-progress-bar-with-squareline-studio.md)
- [Lesson09 How to make an analysis report on ESP32 Display](./lesson09-how-to-make-an-analysis-report-on-esp32-display.md)
- [Lesson10 Create a 3D Printer UI Project on ESP32 Display](./lesson10-create-a-3d-printer-ui-project-on-esp32-display.md)
- [Lesson11 How to Make a Mixer Interface on ESP32 Display](./lesson11-how-to-make-a-mixer-interface-on-esp32-display.md)
- [Lesson12 Make Your ESP32 Display the Lantern Control terminal](./lesson12-make-your-esp32-display-the-lantern-control-terminal.md)
- [Lesson13 DIY Electronic Control Terminal on ESP32 Display with Squareline Studio](./lesson13-diy-electronic-control-terminal-on-esp32-display-with-squareline-studio.md)
- [Lesson14 Create Car Control Screen on ESP32 Display: A Step-by-Step Guide](./lesson14-create-car-control-screen-on-esp32-display-a-step-by-step-guide.md)
- [Lesson15 Smart Agriculture Monitoring: IoT-Based Real-Time ESP32 Display Project](./lesson15-smart-agriculture-monitoring-lot-based-real-time-esp32-display-project.md)
- Lesson16 ESP32 Display for Smart Home Central Control: A Home Automation Solution

## **[Back to Main Content](../../Tutorials/lvgl-esp32-display-tutorial-a-step-by-step-guide-to-lvgl-gui-development.md)** 

## Resources
----

[lesson16.zip](https://wiki.elecrow.com/images/e/ea/ESP-Display-lesson16.zip)