---
title: Lesson09 How to make an analysis report on ESP32 Display
---

## **Project Introduction:**
-----

The Rotation Analysis Report is a small project based on Squareline Studio software. It uses charts to create a simple analysis report. The analysis report can display various types of data charts on the screen. This project can be used to display data analysis, reports, trends, and provide valuable data support for decision-makers.

## **Introduction to Knowledge Points:**
------

The following is a basic introduction to the widgets used in the project:   
**Chart:**    
Charts are a graphical representation used to display data, trends, or relationships. In software design, charts are usually used in data visualization, report display, trend analysis, and other fields. Charts can include different types such as bar charts, line charts, pie charts, and can be customized with various styles and colors to meet different application scenarios and requirements.

These UI elements are very common in many data analysis and reporting applications. They can help users better understand and analyze data, improve the efficiency and accuracy of data visualization and data analysis. In software development, ready-made UI libraries or frameworks can be used to create these UI elements, or you can write code to implement them.

## **Project Steps:**
-----

1. Create a new project in Squareline Studio as before. First, select the Arduino module, and then make some basic settings for the project, such as project name and display size. Click "Create" to create the project.   
   ![9-1.png](https://wiki.elecrow.com/images/thumb/1/11/9-1.png/809px-9-1.png){ loading=lazy }

2. Find the widgets used in this lesson in the left toolbar and add them to the attribute panel. The widgets used here include charts, buttons, labels, and panel widgets. After adding them, set the hierarchy and position and size. You can also do some basic property settings based on what you learned in the previous lesson to make the menu more visually appealing.   
   ![9-2.png](https://wiki.elecrow.com/images/thumb/5/5d/9-2.png/894px-9-2.png){ loading=lazy }

3. Set the text-related settings for the buttons and labels.   
   ![9-3.png](https://wiki.elecrow.com/images/thumb/d/de/9-3.png/372px-9-3.png){ loading=lazy }

4. Focus on the chart settings. You can set it to the required style according to your needs. Here are two chart styles:   
   ① Select the BAR style display.     
   ![9-4.png](https://wiki.elecrow.com/images/b/b1/9-4.png){ loading=lazy }   
   ② Select double data display and modify the data according to the actual situation.     
   ![9-5.png](https://wiki.elecrow.com/images/8/86/9-5.png){ loading=lazy }   
   ③ Set different colors to distinguish.   
   ![9-6.png](https://wiki.elecrow.com/images/e/e5/9-6.png){ loading=lazy }

5. After setting the first page, directly click the copy button on the page to generate a new page.  
   ![9-7.png](https://wiki.elecrow.com/images/4/4d/9-7.png){ loading=lazy }   
   ![9-8.png](https://wiki.elecrow.com/images/a/a6/9-8.png){ loading=lazy }

6. At this point, the two pages are the same. We will set the second page to display different table contents.  
   ![9-9.png](https://wiki.elecrow.com/images/2/26/9-9.png){ loading=lazy }

7. Finally, set the buttons to implement the page jumping function.  
   ① Select the jump page event setting.   
   ![9-10.png](https://wiki.elecrow.com/images/9/9f/9-10.png){ loading=lazy }   
   ② Select the jump target.   
   ![9-11.png](https://wiki.elecrow.com/images/e/e5/9-11.png){ loading=lazy }   
   ③ Set different page targets for the two buttons.   
   ![214px231px](https://wiki.elecrow.com/images/b/bf/9-12.png){ loading=lazy }

**Running Effect:**   
According to the way of downloading the program learned earlier, put the generated UI file in the Arduino library and see the effect on the screen.   
![9-13.png](https://wiki.elecrow.com/images/thumb/7/7d/9-13.png/750px-9-13.png){ loading=lazy }
![9-14.png](https://wiki.elecrow.com/images/thumb/a/a8/9-14.png/750px-9-14.png){ loading=lazy }

## **Summary:**
-------

This project helps beginners quickly understand the basic usage of chart widgets and adds page jumping function to view multiple charts. In actual applications, it can be modified and extended according to needs to add more chart functions.

## **HMI Display Tutorial Contents**
----

- [Lesson01 Introducing the ESP32 Display series and environment configuration](./lesson01-introducing-the-esp32-display-series-and-environment-configuration.md)
- [Lesson02 Start the ESP32 DISPLAY GUI drawing via LovyanGFX Graphics Library](./lesson02-start-the-esp32-display-gui-drawing-via-lovyangfx-graphics-library.md)
- [Lesson03 How to Display Pictures on ESP32 Boards](./lesson03-how-to-display-pictures-on-esp32-boards.md)
- [Lesson04 LVGL Basics: How to install LVGL for ESP32 Displays](./lesson04-lvgl-basics-how-to-install-lvgl-for-esp32-displays.md)
- [Lesson05 Introduction to the 5 categories of LVGL GUI library Widgets](./lesson05-introduction-to-the-5-categories-of-lvgl-gui-library-widgets.md)
- [Lesson06 Use Squareline Studio to start your 1st human machine interface project](./lesson06-use-squareline-studio-to-start-your-1st-human-machine-interface-project.md)
- [Lesson07 How to implement text information input with Squareline Studio](./lesson07-how-to-implement-text-information-input-with-squareline-studio.md)
- [Lesson08 How to make the menu and a progress bar with Squareline Studio](./lesson08-how-to-make-the-menu-and-a-progress-bar-with-squareline-studio.md)
- Lesson09 How to make an analysis report on ESP32 Display
- [Lesson10 Create a 3D Printer UI Project on ESP32 Display](./lesson10-create-a-3d-printer-ui-project-on-esp32-display.md)
- [Lesson11 How to Make a Mixer Interface on ESP32 Display](./lesson11-how-to-make-a-mixer-interface-on-esp32-display.md)
- [Lesson12 Make Your ESP32 Display the Lantern Control terminal](./lesson12-make-your-esp32-display-the-lantern-control-terminal.md)
- [Lesson13 DIY Electronic Control Terminal on ESP32 Display with Squareline Studio](./lesson13-diy-electronic-control-terminal-on-esp32-display-with-squareline-studio.md)
- [Lesson14 Create Car Control Screen on ESP32 Display: A Step-by-Step Guide](./lesson14-create-car-control-screen-on-esp32-display-a-step-by-step-guide.md)
- [Lesson15 Smart Agriculture Monitoring: IoT-Based Real-Time ESP32 Display Project](./lesson15-smart-agriculture-monitoring-lot-based-real-time-esp32-display-project.md)
- [Lesson16 ESP32 Display for Smart Home Central Control: A Home Automation Solution](./lesson16-esp32-display-for-smart-home-central-control-a-home-automation-solution.md)

## **[Back to Main Content](../../Tutorials/index.md)** 

## Resources
----

[lesson9.zip](https://wiki.elecrow.com/images/3/31/ESP-Display-lesson9.zip)