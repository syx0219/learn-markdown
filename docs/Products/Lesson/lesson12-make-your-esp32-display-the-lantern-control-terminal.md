---
title: Lesson12 Make Your ESP32 Display the Lantern Control terminal
---

## **Project description:**
------

This project uses Squareline Studio to create an RGB light control terminal based on ESP32. Users can control the color of the RGB light by clicking on different buttons on the screen.

## **Introduction to Knowledge Points:**
-----

The following is a basic introduction to the widgets used in the project:

Squareline Studio's terminal control uses an **image** widget, which is a user interface element used to display images or graphics. The image widget is usually a rectangular area that can display various types of images, such as bitmaps, vector graphics, or animations.

The image widget can be used for various purposes, such as:

- Displaying icons or logos: The image widget can be used to display brand logos, application icons, or other icon-style elements.

- Displaying image content: The image widget can be used to display images, photos, or other visual elements, such as product images or user avatars.

- Visualizing data: The image widget can be used to display graphics, charts, or other data visualization elements, such as maps or statistical charts.

The image widget usually has the ability to resize and scale to fit different screen sizes and resolutions. In addition, the image widget can usually be used in conjunction with other user interface elements, such as text labels or buttons.

In Squareline Studio's terminal control, the image widget may be used to display the output of command-line tools, file or directory lists, code examples, or other visual elements. The image widget may also be used to implement some graphical interactive elements, such as drag-and-drop files for operations.

## **Project Steps:**
----

Note: Add the provided image material files first!   
![11-1.png](https://wiki.elecrow.com/images/6/68/11-1.png){ loading=lazy }   
1 Create a new project in Squareline Studio in the same way as before. First, select the Arduino module, and then perform simple settings for the project, such as project name and display size, etc. Since this UI is vertical, the size needs to be changed to 480*320. Click Create to complete.   
![11-2-1.png](https://wiki.elecrow.com/images/e/e3/11-2-1.png){ loading=lazy }   
2 Add a panel, add labels and 5 image widgets, adjust and set their positions according to the diagram.   
![12-3.png](https://wiki.elecrow.com/images/e/e0/12-3.png){ loading=lazy }   
3 Arrange each widget in the position shown in the diagram and add image materials to the image widgets.   
![12-4.png](https://wiki.elecrow.com/images/5/5b/12-4.png){ loading=lazy }   
4 Check the Clickable option for each image widget's flags.   
![12-5.png](https://wiki.elecrow.com/images/2/26/12-5.png){ loading=lazy }   
5 Add an event to each image widget. After generating the UI file, the relevant functions will be generated, which will be set in the program file later.   
![12-6.png](https://wiki.elecrow.com/images/e/e6/12-6.png){ loading=lazy }   
6 In the generated UI file, open the ui.c and ui.h files.   
![12-7.png](https://wiki.elecrow.com/images/b/b0/12-7.png){ loading=lazy }    
7 In the ui.c file, add a variable, and add a program to set the variable value in each image widget's event function.   
![12-8.png](https://wiki.elecrow.com/images/5/51/12-8.png){ loading=lazy }    
![12-9.png](https://wiki.elecrow.com/images/thumb/a/a2/12-9.png/459px-12-9.png){ loading=lazy }   
8 Declare the variable set above in ui.h.    
![12-10.png](https://wiki.elecrow.com/images/1/16/12-10.png){ loading=lazy }    
9 In the main program, set the program to control the light. Depending on the value of the variable, display different colors. Note: This main program adds the RGB light library function on the original basis, which can be viewed by yourself.    
![12-11.png](https://wiki.elecrow.com/images/d/dd/12-11.png){ loading=lazy }   
**Running effect:** After successfully downloading the program, check the effect on the screen.   
![12-12.png](https://wiki.elecrow.com/images/7/77/12-12.png){ loading=lazy }
![12-13.png](https://wiki.elecrow.com/images/a/ab/12-13.png){ loading=lazy }

## **Summary:**
----

This project helps beginners quickly understand the combination of UI interface and external sensors, how to modify using generated functions, and achieve the function of controlling sensors through the interface. In actual applications, it can be modified and extended according to needs, and more settings and functions can be added.

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
- Lesson12 Make Your ESP32 Display the Lantern Control terminal
- [Lesson13 DIY Electronic Control Terminal on ESP32 Display with Squareline Studio](./lesson13-diy-electronic-control-terminal-on-esp32-display-with-squareline-studio.md)
- [Lesson14 Create Car Control Screen on ESP32 Display: A Step-by-Step Guide](./lesson14-create-car-control-screen-on-esp32-display-a-step-by-step-guide.md)
- [Lesson15 Smart Agriculture Monitoring: IoT-Based Real-Time ESP32 Display Project](./lesson15-smart-agriculture-monitoring-lot-based-real-time-esp32-display-project.md)
- [Lesson16 ESP32 Display for Smart Home Central Control: A Home Automation Solution](./lesson16-esp32-display-for-smart-home-central-control-a-home-automation-solution.md)

## **[Back to Main Content](../../Tutorials/index.md)** 

## Resources
----

[lesson12.zip](https://wiki.elecrow.com/images/5/5a/ESP-Display-lesson12.zip)