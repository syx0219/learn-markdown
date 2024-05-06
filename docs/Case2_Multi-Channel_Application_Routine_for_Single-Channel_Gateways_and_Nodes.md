---
title: Case 2:Multi-Channel Application Routine for Single-Channel Gateways and Nodes
---

Equipment: Lorawan gateway module

Website: https://www.elecrow.com/lorawan-gateway-module-ased-on-eso32-with-1-8-lcd-1-channel-for-long-range-communication.html

## Gateway configuration
-------

### **1.Initialise the gateway:**

Long press the BOOT key for 3s to initialise the gateway, check the initialisation information on the gateway display. As shown in the picture.

### **2. Go to the web side to initialise the gateway configuration:**

Connect the wifi of the gateway, enter 192.168.4.1 on the browser to enter the webpage; Configure the gateway networking method WIFI (you must enter the correct wifi account password); Press Gateway Default to get the default ID of the gateway, or enter the 16-digit ID by yourself (the ID needs to be the same as the TTN gateway ID); Enter the server address port; REGION set the gateway working band (US915 for example); set the gateway channel (CHANNEL) (915 band has 8 ranges of 0-7, the band should be the same as the node band) and the spreading factor (SF note: use LR1262 node 915 band set spreading factor is 10). As shown in the pictures.

![Config1.png](https://wiki.elecrow.com/images/c/ce/Config1.png){ loading=lazy }
![Config2.png](https://wiki.elecrow.com/images/e/e6/Config2.png){ loading=lazy }

Generally, SF10 is used for long communication distance, and the channel selection is 0. Time zone setting, set the corresponding time zone can be set.

### **3. After confirming that there are no errors, click Submit to submit the configuration information, and the gateway will load the corresponding configuration**

![Gateway1.png](https://wiki.elecrow.com/images/thumb/d/d7/Gateway1.png/200px-Gateway1.png){ loading=lazy }

You can check the time when the last gateway sent and received data by switching to the next page.

![Gateway2.png](https://wiki.elecrow.com/images/thumb/6/68/Gateway2.png/200px-Gateway2.png){ loading=lazy }

## TTN configuration
------

### **1. Add gateway (TTN address eu1.cloud.thethings.network, you need to register an account to access the console to add)**

![TTN.png](https://wiki.elecrow.com/images/b/ba/TTN.png){ loading=lazy }

Enter the gateway ID, click Confirm, enter the gateway name, and select the operating band.

![TTN1.png](https://wiki.elecrow.com/images/6/6c/TTN1.png){ loading=lazy }

![Register gateway.png](https://wiki.elecrow.com/images/thumb/3/3d/Register_gateway.png/500px-Register_gateway.png){ loading=lazy }

#### **Note: Select the band "United States 902-928MHz FSB1" (select this band when testing LoRa nodes using the 915MHz band).**

### **2. Add Node**

![Add node.png](https://wiki.elecrow.com/images/9/94/Add_node.png){ loading=lazy }

Enter the node ID, name, and description

![Enter1.png](https://wiki.elecrow.com/images/4/40/Enter1.png){ loading=lazy }

![Enter2.png](https://wiki.elecrow.com/images/f/fe/Enter2.png){ loading=lazy }

![Enter 3.png](https://wiki.elecrow.com/images/6/64/Enter_3.png){ loading=lazy }

![Enter4.png](https://wiki.elecrow.com/images/b/b6/Enter4.png){ loading=lazy }

Configure the node parameters added by TTN to the node.

![Ttn node.png](https://wiki.elecrow.com/images/3/39/Ttn_node.png){ loading=lazy }

It must be confirmed that the LR1262 module has been burned with the factory firmware programme. Open the serial port tool and enter the network.

## LR1262 Node
-----

### **1. Open the serial port tool, serial port settings**

1). Baud rate: 9600 2). Tick the serial port carriage return line feed

### **2. Node access multi-channel gateway configuration steps (send AT command)**

1). Select the node for single channel/multi-channel mode mode: AT+ChannelMode=1 (1 for multi-channel)

2). Set the node into the network frequency band: AT + BAND = 8 (8 for 915 band)

3). Set the node entry triad (OTAA):

Set node DevEui: AT+DevEui=70B3D57ED005B7FF

Set node AppEui: AT+AppEui=000000000000000003

Set node AppKey: AT+AppKey=A8D7E5959F7746D902BF52BA2F899E3E

![Ttn2.png](https://wiki.elecrow.com/images/a/ac/Ttn2.png){ loading=lazy }

4). Setting the node to start netting: AT+JOIN=1,8 (parameter description: the first parameter is to select the netting mode, 0 is ABP mode, 1 is OTAA mode, the second parameter is the number of times of cyclic request for netting in OTAA mode (1-8), no cycle is needed in ABP mode)

![915.0.png](https://wiki.elecrow.com/images/8/84/915.0.png){ loading=lazy }


5). Start sending data: AT+SEND=1:1:223333 (parameter description: the last parameter is the data to be sent, and only an even number of data can be sent)

![Data3.png](https://wiki.elecrow.com/images/f/f3/Data3.png){ loading=lazy }