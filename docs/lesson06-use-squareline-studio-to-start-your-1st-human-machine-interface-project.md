---
title: Lesson06 Use Squareline Studio to start your 1st human machine interface project
---

## **Project Introduction:**
-----

The project uses Squareline Studio software to create a simple button interface. In this interface, users can click the button, and then the interface will display the text information that the button has been clicked. This interface includes small widgets such as buttons, labels, and panels, and a beautiful and practical interface can be created through simple dragging and setting of properties. Through this project, we can learn about the basic usage of small widgets in Squareline Studio software, and how to use these small widgets to create a basic interface and application.

## **Introduction to Knowledge Points:**
-----

Here are the basic introductions of the small widgets used in the project:   
**Button**: A button is a commonly used interactive widget that is usually used to trigger an operation or event. In Squareline Studio, the text, background color, font, size, position, and other properties of the button can be set, and event response functions can be set for the button.   

**Label**: A label is a widget used to display text or images, usually without interactivity. In Squareline Studio, the text, font, size, position, alignment, and other properties of the label can be set, and background images or background colors can be set for the label.

**Panel:** A panel is a container used to organize other small widgets, usually used to place multiple small widgets together to achieve a certain layout effect. In Squareline Studio, the size, position, background color, border, and other properties of the panel can be set, and other small widgets can be added to the panel.

## **project steps:**
-----

1 Open the Squareline Studio software and create a new project. First select the Arduino module, and then make basic settings such as project name, display size and 16-bit color depth. Click Create to continue.   
![7-1.png](https://wiki.elecrow.com/images/thumb/4/4d/7-1.png/789px-7-1.png){ loading=lazy }   
2 Find the button widget in the left toolbar and drag it to the canvas, then set the button position in the properties panel on the right.   
![6-2.png](https://wiki.elecrow.com/images/thumb/5/51/6-2.png/789px-6-2.png){ loading=lazy }   
3 Find the label widget in the left toolbar and drag it onto the button. Then, in the properties panel on the right, set the label text to "Click me" with a default size of 16.   
![6-3.png](https://wiki.elecrow.com/images/thumb/8/8d/6-3.png/789px-6-3.png){ loading=lazy }    
4 Find the label widget in the left toolbar and drag it onto the panel, set its position and size, and write "Hello everyone!" in the text.   
![6-4.png](https://wiki.elecrow.com/images/thumb/0/0c/6-4.png/820px-6-4.png){ loading=lazy }    
5 Click the button component on the left and add two events in the properties panel on the right: one for the "pressed" event, which will make label 2 show the text "This is ELECROW!" when the button is pressed; the other for the "clicked" event, which will show the text "Hello everyone!" when the button is clicked.

![6-6.png](https://wiki.elecrow.com/images/b/be/6-6.png){ loading=lazy } 
![6-5.png](https://wiki.elecrow.com/images/0/00/6-5.png){ loading=lazy } 
![6-7.png](https://wiki.elecrow.com/images/thumb/4/48/6-7.png/250px-6-7.png){ loading=lazy }

6 Finally, find the panel widget in the left toolbar, drag three of them onto the panel, set them to circular and arrange them in order. Apply the same settings for all three panels, including a default style and a pressed style. Only the color is different between the two styles.   
![6-8.png](https://wiki.elecrow.com/images/thumb/1/1b/6-8.png/789px-6-8.png){ loading=lazy }    
Select the "PRESSED" state and set a different background color.

![6-9-1.png](https://wiki.elecrow.com/images/thumb/d/dd/6-9-1.png/297px-6-9-1.png){ loading=lazy }    
7 Click the "Run" button at the top of the Squareline Studio editor interface to run the application and test the button interface. Clicking the button should update the label text to "This is ELECROW!" and release the button should show "Hello everyone!". Clicking the three panels will switch between different colors.     
![6-10.png](https://wiki.elecrow.com/images/thumb/3/37/6-10.png/273px-6-10.png){ loading=lazy }   
8 Put the generated UI file in the Arduino library and download and run the source program we provide to see the same effect on the screen.   
① Generate UI files，First set the export path, then export the UI file;   
![6-11 1.png](https://wiki.elecrow.com/images/thumb/a/a4/6-11_1.png/500px-6-11_1.png)]{ loading=lazy } 
![6-11.png](https://wiki.elecrow.com/images/1/14/6-11.png){ loading=lazy }
![6-11-3.png](https://wiki.elecrow.com/images/d/db/6-11-3.png){ loading=lazy }

②Install the [ui library](https://wiki.elecrow.com/images/2/26/Ui.zip) into the library directory of Arduino;   
![6-12.png](https://wiki.elecrow.com/images/thumb/e/ea/6-12.png/356px-6-12.png){ loading=lazy }   
③Download [LVGL_RGB_.zip](https://wiki.elecrow.com/images/0/0f/Lesson06-LVGL_RGB_.zip);   
![6-13.png](https://wiki.elecrow.com/images/thumb/b/ba/6-13.png/300px-6-13.png){ loading=lazy }
![6-14.png](https://wiki.elecrow.com/images/thumb/0/0b/6-14.png/750px-6-14.png){ loading=lazy }

## **Summary**
-------

This project is very simple, but can help beginners quickly understand the basic usage of small widgets in the Squareline Studio platform. In practical applications, it can be modified and expanded as needed, for example, by adding background or background image functions.

## **HMI Display Tutorial Contents**
-------

- [Lesson01 Introducing the ESP32 Display series and environment configuration](./lesson01-introducing-the-esp32-display-series-and-environment-configuration.md)
- [Lesson02 Start the ESP32 DISPLAY GUI drawing via LovyanGFX Graphics Library](./lesson02-start-the-esp32-display-gui-drawing-via-lovyangfx-graphics-library.md)
- [Lesson03 How to Display Pictures on ESP32 Boards](./lesson03-how-to-display-pictures-on-esp32-boards.md)
- [Lesson04 LVGL Basics: How to install LVGL for ESP32 Displays](./lesson04-lvgl-basics-how-to-install-lvgl-for-esp32-displays.md)
- [Lesson05 Introduction to the 5 categories of LVGL GUI library Widgets](./lesson05-introduction-to-the-5-categories-of-lvgl-gui-library-widgets.md)
- Lesson06 Use Squareline Studio to start your 1st human machine interface project
- [Lesson07 How to implement text information input with Squareline Studio](./lesson07-how-to-implement-text-information-input-with-squareline-studio.md)
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
----

[ui library](https://wiki.elecrow.com/images/2/26/Ui.zip)
[LVGL_RGB_.zip](https://wiki.elecrow.com/images/0/0f/Lesson06-LVGL_RGB_.zip)