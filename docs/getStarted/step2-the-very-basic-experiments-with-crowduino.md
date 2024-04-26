---
title: Step2:The very basic experiments with Crowduino
---

## Task for this Step
------------------

**Light up and control the LED which is controlled by Digital 13!**

### **step1: Connect Crowduino to PC**

As you read this section, I beleve you have connected your Croduino to PC and installed the Driver as the [Step1](./step1-download-arduino-ide-and-install-arduino-driver.md).

### **step2: Open the Blink example**

Open the LED blink example sketch: File-&gt;Examples-&gt;01.Basics-&gt;Blink. 
![Getting Started1.png](https://wiki.elecrow.com/images/e/ed/Getting_Started1.png){ loading=lazy }

### **step3: Select your board**

You'll need to select the entry in the Tools &gt; Board menu that corresponds to your Arduino. 在Here we need to select ATmega328. 
![Getting Started2.png](https://wiki.elecrow.com/images/2/2b/Getting_Started2.png){ loading=lazy }

### **step4: Select your Serial Port**

Select the serial device of the Arduino board from the Tools | Serial Port menu. 
![Getting Started3.png](https://wiki.elecrow.com/images/e/e1/Getting_Started3.png){ loading=lazy }

### **step5: Upload the program**

Now, simply click the "Upload" button in the environment. Wait a few seconds - you should see the RX and TX leds on the board flashing. If the upload is successful, the message "Done uploading." will appear in the status bar. 
![Getting Started4.png](https://wiki.elecrow.com/images/b/b7/Getting_Started4.png){ loading=lazy }

### **step6: Modify the code as you like**

As you see the "Uploading Done", it means that the program has been download to your Crowduino. You should see the pin 13 (L) LED on the board start to blink with a interval of 1s. Try to modify the val of *delay()* , you will see the blink interval changing. 
![Getting Started4.jpg](https://wiki.elecrow.com/images/thumb/c/c1/Getting_Started4.jpg/400px-Getting_Started4.jpg){ loading=lazy }