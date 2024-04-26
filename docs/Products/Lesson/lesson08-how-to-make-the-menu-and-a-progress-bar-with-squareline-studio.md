---
title: Lesson08 How to make the menu and a progress bar with Squareline Studio
---

## **Project introduction:**
------

This project is a simple dropdown menu and progress display. Users can use the dropdown menu to select corresponding options to determine the content, which can facilitate users to enter related information. The slider can display related progress.

## **Introduction to Knowledge Points:**
-----

The following are the basic introductions of the widgets used in the project:    
**Dropdown menu:**   
A dropdown menu is a user interface control component typically used to provide a list of options in an application. It typically consists of a button and a dropdown menu. When the user clicks the button, the dropdown menu expands to show the available options. The user can select an option from the dropdown menu and use it in the application. Dropdown menus are widely used in many applications, including operating systems, web pages, and mobile applications.

**Slider widget:**   
A slider widget is a user interface control typically used to adjust numeric values. It typically consists of a slider and a numeric display. Users can adjust the value by dragging the slider, and the value will be displayed in real-time in the numeric display area. Slider widgets are commonly used to adjust values such as volume, brightness, size, speed, etc. In many applications, slider widgets are also widely used, including operating systems, web pages, and mobile applications.

These UI elements are common in many applications and websites. They can help users complete tasks more easily and improve the user experience. In software development, pre-made UI libraries or frameworks can be used to create these UI elements, or code can be written to implement them.

## **[Lesson8](https://wiki.elecrow.com/images/5/54/ESP-Display-lesson8.zip) project steps:**
-----

1 Create a new project in Squareline Studio as before. First, select the Arduino module, and then do some simple project settings such as project name and display size. Click "Create" to proceed.   
![8-1.png](https://wiki.elecrow.com/images/4/46/8-1.png){ loading=lazy }

2 Find the drop-down menu, panel, label and other components on the left toolbar, drag them to the panel first, and put the label and drop-down menu under the panel directory. Set the position and size as shown. You can also set some basic properties based on the content of the previous lesson to make the menu look better.   
![8-2.png](https://wiki.elecrow.com/images/0/01/8-2.png){ loading=lazy }

3 Then set the content options in the drop-down menu, with each line representing an option.   
![8-3.png](https://wiki.elecrow.com/images/2/29/8-3.png){ loading=lazy }   
4 At this point, the selection of the drop-down menu is completed, and you can choose the correct option according to the actual situation.   
![8-4.png](https://wiki.elecrow.com/images/e/e1/8-4.png){ loading=lazy }   
5 Next, let's take a look at the progress bar. Similarly, add three widgets, and place the slider and label under the panel directory, and set the corresponding size and position.   
![8-5.png](https://wiki.elecrow.com/images/9/97/8-5.png){ loading=lazy }  
6 Set the slider and label, and here the key is to link the slider and label. Add an event to the slider and set it as follows:   
![8-6.png](https://wiki.elecrow.com/images/e/ed/8-6.png){ loading=lazy }
![8-7.png](https://wiki.elecrow.com/images/1/14/8-7.png){ loading=lazy }  
First, select "SET TEXT VALUE FROM SLIDER", then add an event setting, choose click trigger, the target is "Label4", and fill in the Postfix with "%".   
![8-8.png](https://wiki.elecrow.com/images/thumb/4/4f/8-8.png/235px-8-8.png){ loading=lazy }   
This example project is very simple, but it can help beginners quickly understand the basic usage of the drop-down menu and slider widgets.   
**Running effect:**   
![8-9.png](https://wiki.elecrow.com/images/3/36/8-9.png){ loading=lazy }   
Following the method of downloading the program learned earlier, put the generated UI file in the Arduino library and see the effect on the screen.   
![8-10.png](https://wiki.elecrow.com/images/f/f6/8-10.png){ loading=lazy }

## **Summary:**
-----

This project is very simple, but it can help beginners quickly understand the basic usage of the drop-down menu and slider widgets. In actual applications, it can be modified and extended as needed, such as adding a clear button, or formatting text.

## **HMI Display Tutorial Contents**
------

- [Lesson01 Introducing the ESP32 Display series and environment configuration](./lesson01-introducing-the-esp32-display-series-and-environment-configuration.md)
- [Lesson02 Start the ESP32 DISPLAY GUI drawing via LovyanGFX Graphics Library](./lesson02-start-the-esp32-display-gui-drawing-via-lovyangfx-graphics-library.md)
- [Lesson03 How to Display Pictures on ESP32 Boards](./lesson03-how-to-display-pictures-on-esp32-boards.md)
- [Lesson04 LVGL Basics: How to install LVGL for ESP32 Displays](./lesson04-lvgl-basics-how-to-install-lvgl-for-esp32-displays.md)
- [Lesson05 Introduction to the 5 categories of LVGL GUI library Widgets](./lesson05-introduction-to-the-5-categories-of-lvgl-gui-library-widgets.md)
- [Lesson06 Use Squareline Studio to start your 1st human machine interface project](./lesson06-use-squareline-studio-to-start-your-1st-human-machine-interface-project.md)
- [Lesson07 How to implement text information input with Squareline Studio](./lesson07-how-to-implement-text-information-input-with-squareline-studio.md)
- Lesson08 How to make the menu and a progress bar with Squareline Studio
- [Lesson09 How to make an analysis report on ESP32 Display](./lesson09-how-to-make-an-analysis-report-on-esp32-display.md)
- [Lesson10 Create a 3D Printer UI Project on ESP32 Display](./lesson10-create-a-3d-printer-ui-project-on-esp32-display.md)
- [Lesson11 How to Make a Mixer Interface on ESP32 Display](./lesson11-how-to-make-a-mixer-interface-on-esp32-display.md)
- [Lesson12 Make Your ESP32 Display the Lantern Control terminal](./lesson12-make-your-esp32-display-the-lantern-control-terminal.md)
- [Lesson13 DIY Electronic Control Terminal on ESP32 Display with Squareline Studio](./lesson13-diy-electronic-control-terminal-on-esp32-display-with-squareline-studio.md)
- [Lesson14 Create Car Control Screen on ESP32 Display: A Step-by-Step Guide](./lesson14-create-car-control-screen-on-esp32-display-a-step-by-step-guide.md)
- [Lesson15 Smart Agriculture Monitoring: IoT-Based Real-Time ESP32 Display Project](./lesson15-smart-agriculture-monitoring-lot-based-real-time-esp32-display-project.md)
- [Lesson16 ESP32 Display for Smart Home Central Control: A Home Automation Solution](./lesson16-esp32-display-for-smart-home-central-control-a-home-automation-solution.md)

## **[Back to Main Content](../../Tutorials/lvgl-esp32-display-tutorial-a-step-by-step-guide-to-lvgl-gui-development.md)** 

## Resources
-----

[lesson8.zip](https://wiki.elecrow.com/images/5/54/ESP-Display-lesson8.zip)