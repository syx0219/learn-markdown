---
title: Lesson15 Smart Agriculture Monitoring:IoT-Based Real-Time ESP32 Display Project
---

## **Project Introduction:**
-----

The Smart Agriculture Monitoring Station is an intelligent agricultural monitoring system based on IoT technology that can monitor and record real-time environmental information such as temperature, humidity, and light intensity of crops. The UI of the Smart Agriculture Monitoring Station developed by Squareline Studio can visually display this information, helping farmers better understand the environmental conditions of crops and make better agricultural management decisions.   
In this UI, information such as temperature, humidity, and light intensity will be displayed in the form of charts, making it easy for farmers to understand the changing trends of this information. Additionally, value ranges can be set so that when temperature, humidity, and light intensity exceed the set values, a buzzer will sound an alarm.   
It is worth mentioning that the design style of this UI is simple and elegant, the interface layout is reasonable, easy to operate and use. At the same time, the UI has a fast response speed and smooth operation, which can meet the real-time monitoring needs of farmers.

## **Introduction to Knowledge Points:**
------

**Digital light sensor:**    
It is a sensor used to measure the intensity of environmental light, which can convert light intensity into a digital signal output. Digital light sensors usually use components such as photoresistors or photodiodes to sense light and convert light intensity into a digital signal through an internal ADC. In the Smart Agriculture Monitoring Station, digital light sensors can be used to monitor the light intensity of the environment in which crops are located so that farmers can understand the impact of light intensity on crop growth.   
**Soil moisture sensor:**   
It is a sensor used to measure soil moisture, which can convert soil moisture into resistance values. Soil moisture sensors usually use the resistance between two metal plates to sense soil moisture. When the soil moisture changes, the resistance value will also change accordingly. In the Smart Agriculture Monitoring Station, soil moisture sensors can be used to monitor the moisture of the soil in which crops are located so that farmers can understand the impact of soil moisture on crop growth and take timely measures such as irrigation.   
**DHT11 temperature sensor:**

```
It is a sensor used to measure environmental temperature and humidity, which can convert temperature and humidity into digital signal output. DHT11 temperature sensors usually use a chip that integrates temperature and humidity sensors and converts temperature and humidity into digital signals through an internal ADC. In the Smart Agriculture Monitoring Station, DHT11 temperature sensors can be used to monitor the temperature and humidity of the environment in which crops are located so that farmers can understand the impact of environmental temperature and humidity on crop growth.
```

All of these hardware modules play an important role in the Smart Agriculture Central Control UI design, and through their collaboration, the terminal screen can accurately display information such as temperature, humidity, light intensity, and soil moisture.

## **Project steps:**
------

Note: First, add the provided image materials! (Add according to the actual materials provided)   
![15-1.png](https://wiki.elecrow.com/images/3/34/15-1.png){ loading=lazy }   
1.Create a new project in Squareline Studio as before. First, select the Arduino module, and then perform simple settings for the project, such as project name and display size (480*320), and select 16-bit color. Click create.   
![15-2.png](https://wiki.elecrow.com/images/c/cf/15-2.png){ loading=lazy }    
2.Add the required components as shown in the figure, adjust and set the position according to the hierarchical diagram.   
![15-3.png](https://wiki.elecrow.com/images/5/5a/15-3.png){ loading=lazy }   
3.Arrange the components in the positions shown in the figure and add background image materials to the screen.   
![15-4.png](https://wiki.elecrow.com/images/9/94/15-4.png){ loading=lazy }   
4.Add keyboard events to the corresponding text labels, which can smoothly call input-related content (including AX, AN, DN, DX, IN, and IX six labels);   
![15-5.png](https://wiki.elecrow.com/images/5/50/15-5.png){ loading=lazy }   
Program part:   
5.Humidity display program. After obtaining the humidity, compare it with the set value. If it exceeds the range, the buzzer will sound an alarm;   
![15-6.png](https://wiki.elecrow.com/images/a/a8/15-6.png){ loading=lazy }   
6.Temperature display program. After obtaining the temperature, compare it with the set value. If it exceeds the range, the buzzer will sound an alarm.   
![15-7.png](https://wiki.elecrow.com/images/7/7a/15-7.png){ loading=lazy }
![15-8.png](https://wiki.elecrow.com/images/0/0c/15-8.png){ loading=lazy }    
7.Light intensity display program. After obtaining the light intensity, compare it with the set value. If it exceeds the range, the buzzer will sound an alarm.    
![15-9.png](https://wiki.elecrow.com/images/2/2f/15-9.png){ loading=lazy }   
Running effect:   

After the program is successfully downloaded, check the effect on the screen. Click on the screen to set different limit values. When the checked value exceeds the range   
![15-10.png](https://wiki.elecrow.com/images/7/75/15-10.png){ loading=lazy }

## **Summary:**
-----

Overall, the Smart Agriculture Monitoring Station UI can effectively help agricultural producers grasp environmental conditions, adjust equipment and management methods in a timely manner, and improve agricultural productivity and quality. Through visualization, the interface is concise, clear, easy to operate and understand, and suitable for different user groups.

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
- Lesson15 Smart Agriculture Monitoring: IoT-Based Real-Time ESP32 Display Project
- [Lesson16 ESP32 Display for Smart Home Central Control: A Home Automation Solution](./lesson16-esp32-display-for-smart-home-central-control-a-home-automation-solution.md)

## **[Back to Main Content](../../Tutorials/index.md)** 

## Resources
----

[lesson15.zip](https://wiki.elecrow.com/images/9/90/ESP-Display-lesson15.zip)