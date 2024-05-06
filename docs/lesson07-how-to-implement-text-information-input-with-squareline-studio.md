---
title: Lesson07 How to implement text information input with Squareline Studio
---

## **Project Description:**
-----

This project is a simple text input box where users can input text using a keyboard widget and see the inputted content in a text information widget. The main purpose of this project is to demonstrate the basic usage of the keyboard and text information widgets in Squareline Studio.

## **Introduction to Knowledge Points:**
-----

The following are the basic introductions to the widgets used in this project:

**Keyboard Widget:**   
The keyboard widget can be used to capture the characters or keys that the user inputs on the keyboard. The keyboard widget's style, position, and size can be set in the properties panel, and it can also be connected to the corresponding events in a Python script to execute specific functions when the user inputs information. For example, you can listen to the "Key Down" event of the keyboard and connect it to a corresponding function in a Python script to execute specific code when the user presses a key on the keyboard.

**Text Information Widget:**   
The text information widget can be used to display text information on the interface, such as explanatory text, prompt information, error messages, etc. The text information widget's style, position, and size can be set in the properties panel, and the text content to be displayed can also be set. Python scripts can be used to dynamically change the text information widget's text content, such as updating the text information widget's content when the user clicks a button.

**Image Widget:**   
The image widget in Squareline Studio can be used to display images. The image widget can be added to the application's view and the image's source, size, position, and scaling properties can be set. Developers can also use APIs to dynamically change the image widget's properties, such as changing the image's source or changing the image's size and position.

## **[Lesson7](https://wiki.elecrow.com/images/2/28/ESP-Display-lesson7.zip) Project Steps:**

1 Create a new project in Squareline Studio. First, select the Arduino module, and then set up the project with simple settings, such as the project name and display size. Click "Create" to create the project.   
![7-1.png](https://wiki.elecrow.com/images/thumb/4/4d/7-1.png/789px-7-1.png){ loading=lazy }   
2 Find the text information, label, and image widgets in the left toolbar and add them to the properties panel.   
![7-2.png](https://wiki.elecrow.com/images/b/b7/7-2.png){ loading=lazy }   
3 Adjust the positions with the mouse and set the text of the label according to the diagram.   
![7-3.png](https://wiki.elecrow.com/images/b/b7/7-3.png){ loading=lazy }   
4 Set the "Placeholder" content of the three texts, which is the content that prompts the user to fill in.   
![7-4.png](https://wiki.elecrow.com/images/a/a2/7-4.png){ loading=lazy }    
5 Add the image information for the image widget.    
First add the material file, currently the software only supports png format.    
![7-5-1.png](https://wiki.elecrow.com/images/thumb/8/84/7-5-1.png/198px-7-5-1.png){ loading=lazy }   
![7-5-2.png](https://wiki.elecrow.com/images/7/7a/7-5-2.png){ loading=lazy }    
6 Then, go to the text widget's attribute settings, and in the "Add Event" settings at the bottom, select the keyboard target as "KEYBOARD SET TARGET" and then select Keyboard2 as the keyboard and TextArea as the target. This way, the text and keyboard can be linked. The same settings apply to the other two texts.    
![7-6.png](https://wiki.elecrow.com/images/thumb/b/b8/7-6.png/276px-7-6.png){ loading=lazy }
![7-7.png](https://wiki.elecrow.com/images/f/fa/7-7.png){ loading=lazy }   
7 After setting up, click "Run", then click on the text widget, and when the cursor appears, press the button to enter text information.   
![7-8.png](https://wiki.elecrow.com/images/thumb/a/ad/7-8.png/382px-7-8.png){ loading=lazy }
This example project is straightforward, but it can help beginners quickly understand the basic usage of the keyboard and text information widgets. In practical applications, it can be modified and expanded as needed, such as adding a clear button or adding formatted text functionality.   
![7-9.png](https://wiki.elecrow.com/images/thumb/8/87/7-9.png/594px-7-9.png){ loading=lazy }

## **Summary:**
-----

This project is straightforward, but it can help beginners quickly understand the basic usage of the keyboard and text information widgets. In practical applications, it can be modified and expanded as needed, such as adding a clear button or adding formatted text functionality.

## **HMI Display Tutorial Contents**
-----

- [Lesson01 Introducing the ESP32 Display series and environment configuration](./lesson01-introducing-the-esp32-display-series-and-environment-configuration.md)
- [Lesson02 Start the ESP32 DISPLAY GUI drawing via LovyanGFX Graphics Library](./lesson02-start-the-esp32-display-gui-drawing-via-lovyangfx-graphics-library.md)
- [Lesson03 How to Display Pictures on ESP32 Boards](./lesson03-how-to-display-pictures-on-esp32-boards.md)
- [Lesson04 LVGL Basics: How to install LVGL for ESP32 Displays](./lesson04-lvgl-basics-how-to-install-lvgl-for-esp32-displays.md)
- [Lesson05 Introduction to the 5 categories of LVGL GUI library Widgets](./lesson05-introduction-to-the-5-categories-of-lvgl-gui-library-widgets.md)
- [Lesson06 Use Squareline Studio to start your 1st human machine interface project](./lesson06-use-squareline-studio-to-start-your-1st-human-machine-interface-project.md)
- Lesson07 How to implement text information input with Squareline Studio
- [Lesson08 How to make the menu and a progress bar with Squareline Studio](./lesson08-how-to-make-the-menu-and-a-progress-bar-with-squareline-studio.md)
- [Lesson09 How to make an analysis report on ESP32 Display](./lesson09-how-to-make-an-analysis-report-on-esp32-display.md)
- [Lesson10 Create a 3D Printer UI Project on ESP32 Display](./lesson10-create-a-3d-printer-ui-project-on-esp32-display.md)
- [Lesson11 How to Make a Mixer Interface on ESP32 Display](./lesson11-how-to-make-a-mixer-interface-on-esp32-display.md)
- [Lesson12 Make Your ESP32 Display the Lantern Control terminal](./lesson12-make-your-esp32-display-the-lantern-control-terminal.md)
- [Lesson13 DIY Electronic Control Terminal on ESP32 Display with Squareline Studio](./lesson13-diy-electronic-control-terminal-on-esp32-display-with-squareline-studio.md)
- [Lesson14 Create Car Control Screen on ESP32 Display: A Step-by-Step Guide](./lesson14-create-car-control-screen-on-esp32-display-a-step-by-step-guide.md)
- [Lesson15 Smart Agriculture Monitoring: IoT-Based Real-Time ESP32 Display Project](./lesson15-smart-agriculture-monitoring-lot-based-real-time-esp32-display-project.md)
- [Lesson16 ESP32 Display for Smart Home Central Control: A Home Automation Solution](./lesson16-esp32-display-for-smart-home-central-control-a-home-automation-solution.md)

## **[Back to Main Content](./Tutorials.md)** 

## Resources
-----

[Lesson7.zip](https://wiki.elecrow.com/images/2/28/ESP-Display-lesson7.zip)