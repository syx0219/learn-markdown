---
title: Case 3:Single-channel Application Routines for Raspberry Pi Gateways and Nodes
---

Equipment: LR1302(915) Gateway Module , LR1302 LoRaWAN Hat

Website：[LR1302(915) Gateway Module](https://www.elecrow.com/lr1302-lorawan-gateway-module-spi-us915-sx1302-long-range-gateway-module-support-8-channels.html) , [LR1302 LoRaWAN Hat](https://www.elecrow.com/lr1302-868m-915m-lorawan-hat-for-rpi-sx1302-long-range-module-support-rpi-1-2-3-4-5-series.html)

## Raspberry Pi setup steps
------

### **Step 1. Installing the LR1302 LoRaWAN HAT onto the Raspberry Pi and installing the LR1302 Gateway Module**

Easily install the Hat onto the Raspberry Pi 40-pin connector. Firstly power down the Raspberry Pi. Insert the LR1302 module into the Hat as shown below and tighten it

![Gateway hat.png](https://wiki.elecrow.com/images/9/9f/Gateway_hat.png){ loading=lazy }

### **Step 2. Enabling Raspbian I2C and SPI Interfaces**

The LR1302 module communicates with the Raspberry Pi via SPI and I2C. However, these two interfaces are not enabled by default in Raspbian, so developers need to enable them before using the LR1302. Here, we introduce a command line way to enable the SPI and I2C interfaces.

Firstly, log in to the Raspberry Pi via SSH or using a monitor (do not use the serial console as the GPS module on the Pi Hat will take over the Pi's hardware UART pins), and then enter the command line sudo raspi-config to open the Rasberry Pi Software Configuration Tool.

![Command.png](https://wiki.elecrow.com/images/thumb/9/94/Command.png/500px-Command.png){ loading=lazy }

1.Select "Interface Options".

2.Select SPI, and then select Yes to enable it.

3.Select I2C and select Yes to enable it.

4.Select Serial Port, then select No "Do you want to log into the shell..." and select Yes "Do you want serial port hardware...".

5.Afterwards, please reboot the Raspberry Pi to make sure these settings are valid.

### **Step 3. Getting and compiling the SX1302 source**

#### **Now let's install git from github and download sx1302_hal (libraries and programs for the SX1302 LoRa gateway)**

```
sudo apt update
sudo apt install -y git
cd ~
git clone https://github.com/Elecrow-RD/LR1302_loraWAN.git
```

#### **Move to the sx1302_hal folder and compile everything**

```
cd ~/sx1302_hal
make
```

## Configuring TTN-related content
-------

Log in to the TTNv3 console, click Go to Gateway, and then click Add Gateway on the Add Gateway page. You need to pay attention to the gateway EUI and gateway server address as well as the corresponding frequency, and just keep the other settings as default. (Refer to the wiki of Lora_Basic_Gateway_Module for specific steps, the part about ttn creation, [Lora Basic Gateway Module](../Lora/lora-basic-gateway-module.md))

### **Gateway EUI**

64-bit Extended Unique Identifier of the gateway, set to AA555A0000000000 in this wiki.

### **Gateway Server Address**

The address of the server that the gateway will connect to, copy it to the clipboard, the developer will need to save it to the configuration file later on.

### **Frequency Selection**

Using the US915 module, select "United States 902-928 MHz, FSB 2".

![Frequency.png](https://wiki.elecrow.com/images/7/76/Frequency.png){ loading=lazy }

After adding the gateway, go back to the Raspberry Pi and press 'CTRL + c' to stop 'lora_pkt_fwd', then edit the 'global_conf.json.sx1250.xxxx' configuration file you just used with the text editor `nano`:

```
# for WM1302 LoRaWAN Gateway Module (SPI) - US915
nano global_conf.json.sx1250.US915
```

Basically, just change these parameters: "server_address", "serv_port_up" and "serv_port_down" are located at the end of the configuration file. Copy the gateway server address to "server_address", change "serv_port_up" and "serv_port_down" to 1700, these parameters should be edited like this:

```
"gateway_conf": {
"gateway_ID": "AA555A0000000000",
/* change with default server address/ports */
"server_address": "eu1.cloud.thethings.network",
```


Press CTRL + x to save these changes, then y, and finally Enter to close the text editor. To restart lora_pkt_fwd type in the terminal：

```
# for WM1302 LoRaWAN Gateway Module (SPI) - US915
. /lora_pkt_fwd -c global_conf.json.sx1250.US915
```

You will notice that the Raspberry Pi Gateway is connected to the TTN.

#### **Note: Make sure you have the reset_lgw.sh file under the current path when running lora_pkt_fwd.**

## Functional debugging of loRa nodes with LR1262 terminal
------

### **Raspberry Pi LoraWan Gateway**

#### **1. Connect to the network (wifi or wired)**

#### **2. Run the programme**

1). Open Raspberry Pi shell

2). Run the command

Note: Please make sure there is reset_lgw.sh file under current path when running lora_pkt_fwd. 915SPI mode:

```
Sudo /home/pi/sx1302_hal/packet_forwarder/lora_pkt_fwd -c 
/home/pi/sx1302_hal/packet_forwarder/global_conf.json.sx1250.US915.USB
```

3). Check if you are connected to the TTN server and receiving heartbeat packets.

![Heartbeat.png](https://wiki.elecrow.com/images/2/2b/Heartbeat.png){ loading=lazy }

### **LR1262 connects to PC serial port**

#### **1. OTAA distribution network**

You need to modify DEVEUI according to the relevant data displayed by the TTN, APPEUI and APPKEY. (The setting of the TTN node is taken as an example in Case 1, and users need to set it according to their own TTN node, and also configure different frequency parameters according to different modes.)

#### **2. LR1262 node**

1). open the serial port tool, serial port settings

- Baud rate: 9600

- Tick the serial port carriage return line feed

2). Node access single channel gateway configuration steps (send AT command)

- Select the node for single channel/multi-channel mode mode: AT + ChannelMode = 0 (0 for single channel)

- Set the node into the network band: AT+BAND=8,0 (the first digit 8 is 915 band, in single channel mode, the second digit is the band number, 915 is optional (0-7)).

3). Set the node into the network three elements (OTAA):

- Set node DevEui: AT+DevEui=70B3D57ED005B7FF

- Set node AppEui: AT+AppEui=000000000000000003

- Set node AppKey: AT+AppKey=A8D7E5959F7746D902BF52BA2F899E3E

![OTAA.png](https://wiki.elecrow.com/images/1/13/OTAA.png){ loading=lazy }

4). Setting the node to start netting: AT+JOIN=1,8 (parameter description: the first parameter is to select the netting mode, 0 is ABP mode, 1 is OTAA mode, the second parameter is the number of times of cyclic request for netting in OTAA mode (1-8), no cycle is needed in ABP mode)

![915.png](https://wiki.elecrow.com/images/thumb/2/2e/915.png/700px-915.png){ loading=lazy }

5). Start sending data: AT+SEND=1:1:223333 (parameter description: the last parameter is the data to be sent, and only an even number of data can be sent)

![Send data successfully.png](https://wiki.elecrow.com/images/8/85/Send_data_successfully.png){ loading=lazy }