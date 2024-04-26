---
title: Step1:Download Arduino IDE and install Arduino driver
---

## Download the Arduino IDE
------------------------


"Arduino"" is not only the name of the microcontroller board, but also the name of a programming IDE based on C/C++. After you getting your Arduino board or compatible board such as Crowduino, you should install the IDE. Depending on OS version, the specific installation varies. Thankfully Arduino team provides us a detailed installation guide for most OS systems.

Please download the latest version of Arduino IDE at: [http://arduino.cc/en/Main/Software](http://arduino.cc/en/Main/Software)
![ArduinoIDE.jpg](https://wiki.elecrow.com/images/7/79/ArduinoIDE.jpg){loading=lazy}

## Connect Crowduino to PC
-----------------------

Connect the Crowduino board to your computer using the [USB cable](http://www.elecrow.com/prototyping-c-80/cables-wire-c-80_86/mini-usb-cable-3m-p-348.html).

## Install Driver
--------------

### **Installing drivers for the Crowduino In Windows**

- Plug in your Crowduino, Windows will try to install the driver automatically. If you are lucy enougth, the installation will be Done automatically in about 1 minute. If not, follow the next steps.
- Open the Device Manager by right clicking “My computer” and selecting control panel.
- Look under Ports (COM &amp; LPT). You should see an open port named "USB Serial Port" Right click on the "USB Serial Port" and choose the "Update Driver Software" option.


![Driver1.jpg](https://wiki.elecrow.com/images/thumb/d/dc/Driver1.jpg/400px-Driver1.jpg){loading=lazy}

- Choose the "Browse my computer for Driver software" option.


![Driver2.jpg](https://wiki.elecrow.com/images/thumb/8/8c/Driver2.jpg/400px-Driver2.jpg){loading=lazy}

- Select the driver file named <font color="red">FTDI USB Drivers</font>, located in the "Drivers" folder in the Arduino IDE


![Driver3.jpg](https://wiki.elecrow.com/images/7/79/Driver3.jpg){loading=lazy}

- If you installed driver successfully:


![Driver4.jpg](https://wiki.elecrow.com/images/thumb/6/67/Driver4.jpg/400px-Driver4.jpg){loading=lazy}

- Check with serial port the Crowduino is using by opening the Windows Device Manager:


![Driver5.jpg](https://wiki.elecrow.com/images/thumb/6/64/Driver5.jpg/400px-Driver5.jpg){loading=lazy}

### Installing drivers for the Crowduino with Mac OS

- Enter page: [http://www.ftdichip.com/Drivers/VCP.htm](http://www.ftdichip.com/Drivers/VCP.htm).
- Download Driver for the Mac OS X version, and the right version for your own computer


![Driver6.jpg](https://wiki.elecrow.com/images/thumb/d/de/Driver6.jpg/500px-Driver6.jpg){loading=lazy}

- Open the driver file which you just download, and double click FTDIUSBSerialDriver\_10\_4\_10\_5\_10\_6\_10\_7.mpkg and continue


![Driver7.png](https://wiki.elecrow.com/images/b/b2/Driver7.png){loading=lazy}
![Driver8.png](https://wiki.elecrow.com/images/1/12/Driver8.png){loading=lazy}
![Driver9.png](https://wiki.elecrow.com/images/2/24/Driver9.png){loading=lazy}

- You can see the below dialog boxes if you have installed driver successfully.


![Driver10.png](https://wiki.elecrow.com/images/2/2e/Driver10.png){loading=lazy}