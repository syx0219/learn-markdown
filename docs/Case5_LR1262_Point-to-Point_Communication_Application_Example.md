---
title: Case 5:LR1262 Point-to-Point Communication Application Example
---

### **1. Configure the transmitter and receiver**

Basic configuration of the receiver and transmitter using serial port tools.

![Receiver1.png](https://wiki.elecrow.com/images/1/1c/Receiver1.png){ loading=lazy }

Command Parsing:

![RF.png](https://wiki.elecrow.com/images/2/24/RF.png){ loading=lazy }

### **2. Receiving end settings**

AT+TRX=2 (the parameter is the number of receipts, the maximum number is 2147483647)

### **3. Setting the transmitter**

AT+TTX=2,ffff (the first parameter: the number of times to send, the maximum number of times for 2147483647; the second parameter for the hexadecimal data sent, the maximum 254 bytes, the number of even)

![Transmitter.png](https://wiki.elecrow.com/images/e/e9/Transmitter.png){ loading=lazy }

### **4.Exit P2P Test**

In the serial port tool type AT+RFS