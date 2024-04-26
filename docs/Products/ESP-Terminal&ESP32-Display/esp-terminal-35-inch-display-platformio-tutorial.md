---
title: ESP Terminal 3.5-inch Display PlatformIO Tutorial
---

## Overall
-----

This tutorial uses both RGB and SPI versions. Take the Terminal-SPI as an example.

## Software Preparation
-------

First download Visual Studio Code on https://code.visualstudio.com/. Choose the version that is compatible with your computer system and download it
![Vscode-download.jpg](https://wiki.elecrow.com/images/thumb/4/45/Vscode-download.jpg/800px-Vscode-download.jpg){ loading=lazy }

Open VSCode and click on Extension, search for Python and install.
![Platformio-terminal-python.png](https://wiki.elecrow.com/images/thumb/c/ca/Platformio-terminal-python.png/800px-Platformio-terminal-python.png){ loading=lazy }

Search for PlatformIO and install it.
![Platformio-terminal-platformio.png](https://wiki.elecrow.com/images/thumb/7/71/Platformio-terminal-platformio.png/800px-Platformio-terminal-platformio.png){ loading=lazy }

## Create new projects
-------

Click on the PlatformIO icon, click the quik access "Open", then click "+New Project"
![Platformio-terminal-new-project.png](https://wiki.elecrow.com/images/thumb/d/d5/Platformio-terminal-new-project.png/800px-Platformio-terminal-new-project.png){ loading=lazy }

Add the project name. The board select "ESP32-S3-DevKitC-1-NB(8 MB QD, No PSRAM)", framework select Arduino
![Platformio-terminal-project-wizard.png](https://wiki.elecrow.com/images/e/e9/Platformio-terminal-project-wizard.png){ loading=lazy }

The main part of the program will be written in main.cpp
![Platformio-terminal-main.png](https://wiki.elecrow.com/images/thumb/f/f2/Platformio-terminal-main.png/800px-Platformio-terminal-main.png){ loading=lazy }

Download the lvgl and LovyanGFX library
![Platformio-terminal-library.png](https://wiki.elecrow.com/images/thumb/5/56/Platformio-terminal-library.png/800px-Platformio-terminal-library.png){ loading=lazy }

![Platformio-terminal-library-lvgl.png](https://wiki.elecrow.com/images/thumb/2/2d/Platformio-terminal-library-lvgl.png/800px-Platformio-terminal-library-lvgl.png){ loading=lazy }

![Platformio-terminal-library-lvgl-1.png](https://wiki.elecrow.com/images/thumb/a/aa/Platformio-terminal-library-lvgl-1.png/800px-Platformio-terminal-library-lvgl-1.png){ loading=lazy }

![Platformio-terminal-library-lvgl-2.png](https://wiki.elecrow.com/images/thumb/a/a3/Platformio-terminal-library-lvgl-2.png/800px-Platformio-terminal-library-lvgl-2.png){ loading=lazy }

[![Platformio-terminal-library-lovyanGFX.png](https://wiki.elecrow.com/images/thumb/4/46/Platformio-terminal-library-lovyanGFX.png/800px-Platformio-terminal-library-lovyanGFX.png){ loading=lazy }

![Platformio-terminal-library-lovyanGFX-1.png](https://wiki.elecrow.com/images/thumb/6/60/Platformio-terminal-library-lovyanGFX-1.png/800px-Platformio-terminal-library-lovyanGFX-1.png){ loading=lazy }

![Platformio-terminal-library-lovyanGFX-2.png](https://wiki.elecrow.com/images/thumb/f/f9/Platformio-terminal-library-lovyanGFX-2.png/800px-Platformio-terminal-library-lovyanGFX-2.png){ loading=lazy }

![Platformio-terminal-library-lovyanGFX-3.png](https://wiki.elecrow.com/images/thumb/5/5e/Platformio-terminal-library-lovyanGFX-3.png/800px-Platformio-terminal-library-lovyanGFX-3.png){ loading=lazy }


We can see that the library has been added successfully!
![Platformio-terminal-library-added.png](https://wiki.elecrow.com/images/d/df/Platformio-terminal-library-added.png){ loading=lazy }

### Configure the LVGL library
------

Right-click the lvgl and open in files explorer
![Platformio-terminal-open-lvgl.png](https://wiki.elecrow.com/images/b/be/Platformio-terminal-open-lvgl.png){ loading=lazy }

Move the demos and examples folder to src folder
![Platformio-terminal-copy.png](https://wiki.elecrow.com/images/thumb/a/aa/Platformio-terminal-copy.png/800px-Platformio-terminal-copy.png){ loading=lazy }

![Platformio-terminal-copy-1.png](https://wiki.elecrow.com/images/thumb/8/8f/Platformio-terminal-copy-1.png/800px-Platformio-terminal-copy-1.png){ loading=lazy }

Place the lv_conf.h file under the esp32-s3-devkit-1 directory
![Platformio-terminal-lv conf.png](https://wiki.elecrow.com/images/thumb/2/23/Platformio-terminal-lv_conf.png/800px-Platformio-terminal-lv_conf.png){ loading=lazy }

Put the FT6236.cpp file into the /src folder
![Platformio-terminal-FT-CPP.png](https://wiki.elecrow.com/images/thumb/3/31/Platformio-terminal-FT-CPP.png/800px-Platformio-terminal-FT-CPP.png){ loading=lazy }

Put the FT6236.h file in the /include folder
![Platformio-terminal-FT-H.png](https://wiki.elecrow.com/images/thumb/0/08/Platformio-terminal-FT-H.png/800px-Platformio-terminal-FT-H.png){ loading=lazy }

### Compile and upload the code
-------

After the configuration is complete, write the code in main.cpp.
![Platformio-terminal-write-code.png](https://wiki.elecrow.com/images/thumb/e/e8/Platformio-terminal-write-code.png/800px-Platformio-terminal-write-code.png){ loading=lazy }

Compile the program
![Platformio-terminal-compile.png](https://wiki.elecrow.com/images/thumb/9/94/Platformio-terminal-compile.png/800px-Platformio-terminal-compile.png){ loading=lazy }

Then we can upload the code to the board.
![Platformio-terminal-upload.png](https://wiki.elecrow.com/images/thumb/4/4f/Platformio-terminal-upload.png/800px-Platformio-terminal-upload.png){ loading=lazy }

## Resources
----

- [PlatformIO_RGB.zip](https://wiki.elecrow.com/images/a/ad/PlatformIO_RGB.zip)