---
title: Lesson10 Create a 3D Printer UI Project on ESP32 Display
---

## **Project Introduction:**
----

The 3D printer interface is a UI project based on Squareline studio software, which uses other components such as rollers and switches, as well as text boxes and buttons, to allow users to easily adjust the printer's parameters.

## **Introduction to Knowledge Points:**
-----

The following is a basic introduction to the components used in the project:

**Roller:** A roller is a control used to adjust values or parameters, typically consisting of a rotating disc and a central indicator. Users can adjust values or parameters by rotating the disc, and the indicator will move to display the current value or parameter. Roller components are typically used in 3D modeling, graphics design, game development, and audio editing.

**Switch:** A switch is a control used to switch states or options, typically consisting of a toggle button and a text label. Users can switch states or options by clicking the button, and the text label will update to display the current state or option. Switch components are typically used in setting panels, configuration options, and user settings.

In Squareline Studio, designers can customize the appearance and functionality of roller and switch components, such as adjusting their size, color, shape, and label. In addition, these components have responsive design, adapting to different screen sizes and resolutions to provide a better user experience. The UI content will be showcased using an ESP32 Terminal 3.5 inch RGB screen as an example.

## **Project Steps:**
-----

1 Create a new project in Squareline Studio as before. First, select the Arduino module, and then make some simple settings for the project, such as the project name and display size. Click Create to continue.     
![10-1.png](https://wiki.elecrow.com/images/thumb/f/f1/10-1.png/640px-10-1.png){ loading=lazy }  
2 Add two buttons and two labels to display the content of the buttons. Adjust their positions as shown in the figure and set the appropriate display properties.     
![10-2.png](https://wiki.elecrow.com/images/thumb/a/ab/10-2.png/300px-10-2.png){ loading=lazy }
![10-3.png](https://wiki.elecrow.com/images/thumb/3/3e/10-3.png/367px-10-3.png){ loading=lazy }  
3 Add a slider component to simulate the printing progress. Add a label below the slider to display the progress value.

① Add the slider and label components, with the label located under the progress bar. Use the mouse to adjust their positions.     
![10-4.png](https://wiki.elecrow.com/images/d/d8/10-4.png){ loading=lazy }   
②Add related assets. At the bottom of the software, there is an Assets component. Click Add Assets and select the required assets to add them.     
![10-5.png](https://wiki.elecrow.com/images/5/51/10-5.png){ loading=lazy }   
③Set the progress bar. Set the background image, event, indicator, and KNOB display properties of the progress bar.

- Set the background image

![10-6.png](https://wiki.elecrow.com/images/thumb/9/95/10-6.png/235px-10-6.png){ loading=lazy }

- Set the event

![10-7.png](https://wiki.elecrow.com/images/thumb/0/04/10-7.png/235px-10-7.png){ loading=lazy }

- Set the indicator

![10-8.png](https://wiki.elecrow.com/images/thumb/9/95/10-8.png/235px-10-8.png){ loading=lazy }

- Set the KNOB

![10-9.png](https://wiki.elecrow.com/images/thumb/f/f8/10-9.png/235px-10-9.png){ loading=lazy }

- Full effect

![10-10.png](https://wiki.elecrow.com/images/b/b4/10-10.png){ loading=lazy }   
④Set label display properties;     
![10-11.png](https://wiki.elecrow.com/images/thumb/a/a3/10-11.png/223px-10-11.png){ loading=lazy }  
4 Add a panel to display the printing status. Add four labels below the panel to display the printing time and temperature.   
①Add the panel and four labels below it.   
![10-12.png](https://wiki.elecrow.com/images/f/ff/10-12.png){ loading=lazy }   
②Set the panel properties and label contents as shown in the figure.   
![10-13.png](https://wiki.elecrow.com/images/0/09/10-13.png){ loading=lazy }   
5 Finally, add two buttons, add button images, and set the shadow effect when the button is pressed.  
① Add the buttons and button images.   
![10-14.png](https://wiki.elecrow.com/images/8/89/10-14.png){ loading=lazy }   
![10-15.png](https://wiki.elecrow.com/images/thumb/4/43/10-15.png/138px-10-15.png){ loading=lazy }   
② Set the shadow state when the button is pressed. Make the same settings for both buttons.  
![10-16.png](https://wiki.elecrow.com/images/thumb/2/2c/10-16.png/238px-10-16.png){ loading=lazy }   
6 Click Screen 1 and then click Copy Page to generate the same page.   
① Delete the extra components and leave only the button components to switch pages.   
![10-17.png](https://wiki.elecrow.com/images/8/80/10-17.png){ loading=lazy }   
② Set the Screen 2 button to switch pages. Make the same settings as for Screen 1.    
![10-18.png](https://wiki.elecrow.com/images/7/73/10-18.png){ loading=lazy }
![10-19.png](https://wiki.elecrow.com/images/0/07/10-19.png){ loading=lazy }   
③ Select the target page to switch to. Select Screen 1 for the PRINT button and Screen 2 for the SETTING button. Make the same settings for both buttons on both screens.   
![10-20.png](https://wiki.elecrow.com/images/thumb/1/1a/10-20.png/243px-10-20.png){ loading=lazy }  
①Drag two panels and add a Roller component under each panel. Use the mouse to move the components and adjust them to the appropriate position.  
![10-21.png](https://wiki.elecrow.com/images/2/2d/10-21.png){ loading=lazy }
![10-22.png](https://wiki.elecrow.com/images/0/01/10-22.png){ loading=lazy }   
②Use the mouse and position parameters to adjust the position of the components. Enter the Roller component to set the data parameters.   
![10-23.png](https://wiki.elecrow.com/images/c/cf/10-23.png){ loading=lazy }
![10-24.png](https://wiki.elecrow.com/images/6/61/10-24.png){ loading=lazy }   
③Adjust the background color and other related properties according to the background requirements.   
![10-25.png](https://wiki.elecrow.com/images/8/88/10-25.png){ loading=lazy }   
8 Add two labels below the selection to indicate the temperature and material.   
![10-27.png](https://wiki.elecrow.com/images/6/6f/10-27.png){ loading=lazy }   
9 Finally, set the fan switch to control the fan.

①Drag two Switch components and adjust their positions by moving the components with the mouse.   
![10-28.png](https://wiki.elecrow.com/images/4/4d/10-28.png){ loading=lazy }   
②Drag two label components and place them below the switch to identify FAN 1 and FAN 2.   
![10-29.png](https://wiki.elecrow.com/images/e/ee/10-29.png){ loading=lazy }   
③Set different page targets for the two buttons.   
After all settings are completed, click Run to see the effect.   
![10-30.png](https://wiki.elecrow.com/images/d/d3/10-30.png){ loading=lazy }  

**Running effect:**

①Click Export in the software to generate the UI file and place the new UI file in the Arduino library. Then download the LVGL_RGB example provided by the official to the ESP32_rgb terminal.   
![10-31.png](https://wiki.elecrow.com/images/thumb/9/9a/10-31.png/246px-10-31.png){ loading=lazy }  
②After the program is successfully downloaded, check the effect on the screen.   
![10-32.png](https://wiki.elecrow.com/images/1/13/10-32.png){ loading=lazy } 
![10-33.png](https://wiki.elecrow.com/images/0/01/10-33.png){ loading=lazy }

## **Summary:**
-----

This project helps beginners to quickly understand the basic usage of the Roller and Switch components and adds page jump function to replicate the UI interface of a 3D printer, which is very practical. In practical applications, it can be modified and extended according to needs, adding more settings and functions.

## **HMI Display Tutorial Contents**
------

- [Lesson01 Introducing the ESP32 Display series and environment configuration](./lesson01-introducing-the-esp32-display-series-and-environment-configuration.md)
- [Lesson02 Start the ESP32 DISPLAY GUI drawing via LovyanGFX Graphics Library](./lesson02-start-the-esp32-display-gui-drawing-via-lovyangfx-graphics-library.md)
- [Lesson03 How to Display Pictures on ESP32 Boards](./lesson03-how-to-display-pictures-on-esp32-boards.md)
- [Lesson04 LVGL Basics: How to install LVGL for ESP32 Displays](./lesson04-lvgl-basics-how-to-install-lvgl-for-esp32-displays.md)
- [Lesson05 Introduction to the 5 categories of LVGL GUI library Widgets](./lesson05-introduction-to-the-5-categories-of-lvgl-gui-library-widgets.md)
- [Lesson06 Use Squareline Studio to start your 1st human machine interface project](./lesson06-use-squareline-studio-to-start-your-1st-human-machine-interface-project.md)
- [Lesson07 How to implement text information input with Squareline Studio](./lesson07-how-to-implement-text-information-input-with-squareline-studio.md)
- [Lesson08 How to make the menu and a progress bar with Squareline Studio](./lesson08-how-to-make-the-menu-and-a-progress-bar-with-squareline-studio.md)
- [Lesson09 How to make an analysis report on ESP32 Display](./lesson09-how-to-make-an-analysis-report-on-esp32-display.md)
- Lesson10 Create a 3D Printer UI Project on ESP32 Display
- [Lesson11 How to Make a Mixer Interface on ESP32 Display](./lesson11-how-to-make-a-mixer-interface-on-esp32-display.md)
- [Lesson12 Make Your ESP32 Display the Lantern Control terminal](./lesson12-make-your-esp32-display-the-lantern-control-terminal.md)
- [Lesson13 DIY Electronic Control Terminal on ESP32 Display with Squareline Studio](./lesson13-diy-electronic-control-terminal-on-esp32-display-with-squareline-studio.md)
- [Lesson14 Create Car Control Screen on ESP32 Display: A Step-by-Step Guide](./lesson14-create-car-control-screen-on-esp32-display-a-step-by-step-guide.md)
- [Lesson15 Smart Agriculture Monitoring: IoT-Based Real-Time ESP32 Display Project](./lesson15-smart-agriculture-monitoring-lot-based-real-time-esp32-display-project.md)
- [Lesson16 ESP32 Display for Smart Home Central Control: A Home Automation Solution](./lesson16-esp32-display-for-smart-home-central-control-a-home-automation-solution.md)

## **[Back to Main Content](./Tutorials.md)** 

## Resources
----

[lesson10.zip](https://wiki.elecrow.com/images/7/75/ESP-Display-lesson10.zip)