---
title: Lesson04 LVGL Basics:How to install LVGL for ESP32 Displays
---

## **LVGL (Light and Versatile Graphics Library):**
-----

LVGL is an open-source GUI library developed in C language, used for implementing graphic user interfaces (GUI) on embedded devices. It provides a range of GUI components and graphics effects and supports different types of input devices such as touchscreens and buttons, making it easy to implement visual interfaces on embedded devices.   
LVGL can be used on different operating systems and platforms, and its code size is very small, making it suitable for use on resource-constrained devices. LVGL also provides a visual GUI design tool that allows users to quickly design and layout their interfaces, greatly improving development efficiency.   
In summary, LVGL is a powerful and easy-to-use open-source GUI library that provides rich graphical interface capabilities on embedded devices.

## **The main application scenarios of LVGL:**
-------

LVGL is mainly used for developing graphical user interfaces (GUI) in embedded systems, such as smart home control panels, IoT device control interfaces, vending machines, electronic scales, and other embedded devices. LVGL's advantages, such as small memory footprint, easy portability, rich functionality, and beautiful interfaces, make it suitable for use in embedded systems of various sizes, from low-end microprocessors and small microcontrollers to high-end embedded Linux systems. Additionally, LVGL provides a visual GUI design tool that allows for quick creation and design of user interfaces, reducing development and debugging time and further improving the efficiency of embedded system development. Therefore, LVGL is widely used in the field of embedded devices.

## **Use of LVGL:**
-----

SquareLine_Studio is an IDE based on the LVGL framework, designed for designing and developing graphical user interfaces for embedded systems. Here are some simple steps to use SquareLine_Studio:   
1.**Download and install SquareLine_Studio:** Download the software from the official website https://squareline.io/ and follow the installation wizard to install it.   
①Click DOWNLOAD, TRY to enter the download page, and select the file that matches your system to download (here we take the Windows version 1.2.3 as an example).  
![444](https://wiki.elecrow.com/images/b/ba/4-1.png){ loading=lazy }   
![4-3-1.png](https://wiki.elecrow.com/images/thumb/7/7d/4-3-1.png/797px-4-3-1.png){ loading=lazy }

②After the download is successful, click on the file to install it；   
![4-3.png](https://wiki.elecrow.com/images/thumb/4/4e/4-3.png/407px-4-3.png){ loading=lazy }
![4-4.png](https://wiki.elecrow.com/images/thumb/f/f9/4-4.png/375px-4-4.png){ loading=lazy }

2 **Page introduction:** Double-click to enter the software, the first is to choose to create a project page;   
![4-5.png](https://wiki.elecrow.com/images/thumb/2/28/4-5.png/710px-4-5.png){ loading=lazy }

After opening the project, enter our operation main page, divided into multiple areas   
![4-6.png](https://wiki.elecrow.com/images/thumb/c/cf/4-6.png/712px-4-6.png){ loading=lazy }

①A toolbar with action buttons for manipulating and exporting files, and a help menu.  
②Page hierarchy and animation panel, displaying all content and animation effects of the page by hierarchy.   
③The control panel, located on the left side of the software, contains commonly used controls, such as buttons, text boxes, labels, etc., which can be added to the interface by dragging and dropping.   
④ Canvas area, located in the center of the software, is the main editing area of the interface, where you can drag controls, adjust control properties, layout interface, etc.  
⑤Materials and console, located below the center of the software, including personal uploaded materials and program control interface.   
⑥Properties panel, located on the right side of the software, is used to edit the properties of the control, such as text content, position, size, font, color, etc.   
3 **Create a new project:** start SquareLine_Studio, click "Creat", select the embedded platform, screen size and driver, etc., and then give the project a name.   
There are four optional embedded platforms here, namely Adruino, Desktop, Espressif and Nuvoton, which can be selected according to your own needs.   
Here we take Arduino as an example for introduction.    
![4-7.png](https://wiki.elecrow.com/images/thumb/1/1e/4-7.png/720px-4-7.png){ loading=lazy }

4 **Design the UI interface:** Select the components that need to be added to the interface in the "Widget" panel, such as buttons, labels, progress bars, etc., and then drag and drop them into the UI editor. The properties and styles of each component can be adjusted in the editor.    
![4-8-1.png](https://wiki.elecrow.com/images/thumb/b/b0/4-8-1.png/708px-4-8-1.png){ loading=lazy }

5 **Running and testing:** After the page design is completed, select the Emulator (simulator) in SquareLine_Studio, and you can run your application, so that your application will be presented on the screen immediately, and then you can perform functional and performance tests to ensure that all Parts all work effectively.    
![4-9.png](https://wiki.elecrow.com/images/thumb/d/dd/4-9.png/406px-4-9.png){ loading=lazy }

6 **Export UI Files:** The pages designed above can generate corresponding UI files, which can be used in the code.
First set the path of the exported UI file in the project settings, and then export the UI file.
![4-10-1.png](https://wiki.elecrow.com/images/thumb/8/82/4-10-1.png/615px-4-10-1.png){ loading=lazy } 
![4-10.png](https://wiki.elecrow.com/images/e/e6/4-10.png){ loading=lazy }

7**Generate code:** After completing the design, you can generate code with one click through SquareLine_Studio to achieve rapid development. The generated code can be used directly on the embedded device.   
![4-11.png](https://wiki.elecrow.com/images/thumb/b/b8/4-11.png/259px-4-11.png){ loading=lazy }

**Show results:**   
![4-11-1.png](https://wiki.elecrow.com/images/thumb/b/b1/4-11-1.png/580px-4-11-1.png){ loading=lazy }

## **HMI Display Tutorial Contents**
------

- [Lesson01 Introducing the ESP32 Display series and environment configuration](./lesson01-introducing-the-esp32-display-series-and-environment-configuration.md)
- [Lesson02 Start the ESP32 DISPLAY GUI drawing via LovyanGFX Graphics Library](./lesson02-start-the-esp32-display-gui-drawing-via-lovyangfx-graphics-library.md)
- [Lesson03 How to Display Pictures on ESP32 Boards](./lesson03-how-to-display-pictures-on-esp32-boards.md)
- Lesson04 LVGL Basics: How to install LVGL for ESP32 Displays
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
- [Lesson16 ESP32 Display for Smart Home Central Control: A Home Automation Solution](./lesson16-esp32-display-for-smart-home-central-control-a-home-automation-solution.md)

## **[Back to Main Content](../../Tutorials/index.md)**