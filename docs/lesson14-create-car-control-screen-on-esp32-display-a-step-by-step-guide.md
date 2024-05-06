---
title: Lesson14 Create Car Control Screen on ESP32 Display:A Step-by-Step Guide
---

## **Project Description:**
-----

The goal of this project is to design and implement a user interface (UI) for a car's central control screen that can display the speed and RPM, and use a counting sensor to control this information. In addition, the UI includes image buttons to display the direction of the turn signal, and a slider to display the car's fuel level. Finally, there is an electric steering module used to simulate the function of the windshield wipers.    
The UI design for this project needs to consider user usability and readability, so that drivers can quickly obtain the necessary information while driving. To achieve this, the UI needs to present information in a simple and intuitive way, and use easily understood icons and symbols to represent control functions. This lesson will use the esp32 spi terminal screen as an example to introduce the project.

## **Introduction to Knowledge Points:**
------

Here are some basic introductions to the functions used in the project:   
**void lv_slider_set_value(lv_obj_t \* slider, int16_t value, lv_anim_enable_t anim_en)**   
In this function, the first parameter 'slider' is a pointer to the slider control object that needs to be set, the second parameter 'value' is the value to be set, and the third parameter 'anim_en' specifies whether to use animation effects to change the value of the slider. If set to LV_ANIM_OFF, no animation effect will be used, and the value of the slider will be directly set to the specified 'value'.   
For example, to set the value of a slider control object named "ui_Slider2" to 50 without using animation effects, the following code can be used:   
**lv_slider_set_value(ui_Slider2, 50, LV_ANIM_OFF);**   
Note that the lv_slider_create() function needs to be used to create the slider control object and add it to the screen object before using lv_slider_set_value() to set its value.   
The **lv_img_set_src(lv_obj_t \* img, const void \* src)** function is used to set the source data of an image object. The 'src' parameter can be image source data in various formats, such as:   
\- The file path of an image file stored in the file system.   
\- A pointer to a memory block containing image data in a format supported by LVGL.   
\- The URL of an image file that can be accessed through the network.   
After setting the image source data, LVGL will automatically decode and display the image on the image object specified by the 'img' parameter.
It should be noted that the 'src' parameter is declared as const void *, which means that the function will not modify the data pointed to by 'src'. This is a good practice for functions that only need to read input data, as it can prevent the function from accidentally modifying the input data.   
In general, the lv_img_set_src() function is a useful function for displaying various image data on embedded systems and displays, allowing developers to display various image data on embedded systems and displays.   
**Required hardware modules**:   
The **counter (photoelectric counter)** is a digital circuit used to count the number of electrical signals. In cars, counters are commonly used to measure vehicle speed and engine RPM. The counter can receive pulse signals from counting sensors and convert them into digital counting values. Counters usually have a reset function that can reset the counter's value to zero when needed.   
The button is a switch device used to control the on-off state of the circuit. In the car's central control screen, buttons can be used to control the on-off state of the turn signal. When the button is pressed, it connects the circuit, allowing current to flow. When the button is released, the circuit is disconnected, stopping the flow of current.   
The **servo module** is a device used to control mechanical motion, usually used to control the steering wheel of a car. The servo module can receive signals from the controller and control the position of the servo according to the size of the signal. The servo module usually has an angle limit that can limit the rotation range of the servo. In the car's central control screen, the servo module can be used to control the rotation of the windshield wipers, thereby controlling the movement of the wipers.   
All of these hardware modules play an important role in the UI design of the car's central control screen. Through their collaboration, the UI design can accurately display information such as vehicle speed, RPM, and fuel level, and also implement functions such as button control of turn signals and servo module control of windshield wiper rotation.

## **Project steps:**
-----

**Note:** Add the provided image material files first! (Add according to the actual material provided)   
![14-1.png](https://wiki.elecrow.com/images/3/35/14-1.png){ loading=lazy }   
1 Create a new project in Squareline Studio as before. Firstly, select the Arduino module, and then do some simple settings for the project, such as the project name and display size (480*320), choose 16-bit color, etc. Click create to continue.   
![14-2.png](https://wiki.elecrow.com/images/6/6b/14-2.png){ loading=lazy }   
2 Add panels, labels, sliders, and image components, adjust and set their positions according to the diagram hierarchy.   
![14-3.png](https://wiki.elecrow.com/images/a/aa/14-3.png){ loading=lazy }   
3 Arrange each component in the correct position according to the diagram and add image material to the image components.   
![14-4.png](https://wiki.elecrow.com/images/c/cf/14-4.png){ loading=lazy }   
4 Make simple settings for the slider component:   
①Set the main background color to transparent.   
![14-5.png](https://wiki.elecrow.com/images/2/24/14-5.png){ loading=lazy }   
②Set the indicator and add a background image.   
![14-6.png](https://wiki.elecrow.com/images/1/1c/14-6.png){ loading=lazy }   
③Finally, set the KNOB.   
![14-7.png](https://wiki.elecrow.com/images/a/a3/14-7.png){ loading=lazy }   
5 Perform the same setting for the Slider module on the right, or copy the Slider from step 4 and change the background image.
![14-8.png](https://wiki.elecrow.com/images/7/71/14-8.png){ loading=lazy }   
6 Set the two labels separately and change their values according to the values of the two sliders. Add an event in the Slider. Set the two labels the same way.   
![14-9.png](https://wiki.elecrow.com/images/3/3b/14-9.png){ loading=lazy }
![14-10.png](https://wiki.elecrow.com/images/4/4f/14-10.png){ loading=lazy }   
7 Set the slider for the excess fuel, set it to transparent without background image.   
![14-11.png](https://wiki.elecrow.com/images/d/da/14-11.png){ loading=lazy }
![14-12.png](https://wiki.elecrow.com/images/3/37/14-12.png){ loading=lazy }
![14-13.png](https://wiki.elecrow.com/images/8/8b/14-13.png){ loading=lazy }
![14-14.png](https://wiki.elecrow.com/images/7/70/14-14.png){ loading=lazy }   
8 Set the left and right turn arrows. Use a transparent image and set the position, then add an event for both images and save them in the program.   
![14-15.png](https://wiki.elecrow.com/images/8/8e/14-15.png){ loading=lazy }
![14-16.png](https://wiki.elecrow.com/images/4/4f/14-16.png){ loading=lazy }
![14-17.png](https://wiki.elecrow.com/images/3/36/14-17.png){ loading=lazy }   
9 Finally, set the added switch. Simply add an event.   
![14-18.png](https://wiki.elecrow.com/images/1/1a/14-18.png){ loading=lazy }
![14-19.png](https://wiki.elecrow.com/images/7/72/14-19.png){ loading=lazy }   
Program part:    
10 The slider slides according to the value of the counting sensor, displaying the RPM and vehicle speed. The data is only simulated and may differ from the actual data.   
![14-20.png](https://wiki.elecrow.com/images/e/e5/14-20.png){ loading=lazy }    
The counterSensor function checks the value of the counting sensor. The function details are as follows:   
![14-21.png](https://wiki.elecrow.com/images/c/cb/14-21.png){ loading=lazy }   
11 The left and right turn program. The turn image is displayed when the left or right touch sensor is triggered, and is not displayed when it is not triggered.   
![14-22.png](https://wiki.elecrow.com/images/7/72/14-22.png){ loading=lazy }   
12 Windshield wiper servo control. When flag equals 1, trigger the servo to simulate the windshield wiper. The setting of flag is consistent with lesson 12. When the UI switch is triggered, set the value of flag to 1, otherwise set it to 0.   
![14-23.png](https://wiki.elecrow.com/images/2/28/14-23.png){ loading=lazy }
Running effect:    
After the program is successfully downloaded, check the effect on the screen.   
![14-24.png](https://wiki.elecrow.com/images/a/a9/14-24.png){ loading=lazy }
![14-25.png](https://wiki.elecrow.com/images/thumb/2/26/14-25.png/589px-14-25.png){ loading=lazy }

## **Summary:**
-----

In summary, this project aims to design and implement a user-friendly car central control screen UI that can display vehicle speed, RPM, and fuel level, as well as other functions such as turn signals and fan simulation. In actual applications, it can be modified and expanded according to needs, and more settings and functions can be added.

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
- Lesson14 Create Car Control Screen on ESP32 Display: A Step-by-Step Guide
- [Lesson15 Smart Agriculture Monitoring: IoT-Based Real-Time ESP32 Display Project](./lesson15-smart-agriculture-monitoring-lot-based-real-time-esp32-display-project.md)
- [Lesson16 ESP32 Display for Smart Home Central Control: A Home Automation Solution](./lesson16-esp32-display-for-smart-home-central-control-a-home-automation-solution.md)

## **[Back to Main Content](./Tutorials.md)** 

## Resources
----

[lesson14.zip](https://wiki.elecrow.com/images/4/43/ESP-Display-lesson14.zip)