---
title: DHT11
---

## Introduction
------------

This DHT11 Temperature &amp; Humidity Sensor features a temperature &amp; humidity sensor complex with a calibrated digital signal output. By using the exclusive digital-signal-acquisition technique and temperature &amp; humidity sensing technology, it ensures high reliability and excellent long-term stability. This sensor includes a resistive-type humidity measurement component and an NTC temperature measurement component, and connects to a high-performance 8-bit microcontroller, offering excellent quality, fast response, anti-interference ability and cost-effectiveness

**Model:[STH01101S](https://www.elecrow.com/dht11-temperature-humidity-sensor-p-313.html)**

![DHT111.jpg](https://wiki.elecrow.com/images/thumb/0/06/DHT111.jpg/400px-DHT111.jpg){ loading=lazy }

[![Alt text](./assets/images/Get_one_now.png)](https://www.elecrow.com/dht11-temperature-humidity-sensor-p-313.html?wiki "Title text")

Each DHT11 element is calibrated in the laboratory that is extremely accurate on humidity calibration. The calibration coefficients are stored as programmes in the OTP memory, which are used by the sensor’s internal signal detecting process. The single-wire serial interface makes system integration quick and easy. Its small size, low power consumption and up-to-20 meter signal transmission making it the best choice for various applications, including those most demanding ones. The component is 4-pin single row pin package. It is convenient to connect and special packages can be provided according to users’ request.

## Specification
-------------

<table border="1" cellspacing="0" width="100%">
  <tbody>
    <tr>
      <td style="background: #F99D30; color: white" width="300" align="center"><b>Items</b></td>
      <td style="background: #F99D30; color: white" width="300" align="center"><b>Conditions</b></td>
      <td style="background: #F99D30; color: white" width="100" align="center"><b>Min</b></td>
      <td style="background: #F99D30; color: white" width="100" align="center"><b>Norm</b></td>
      <td style="background: #F99D30; color: white" width="100" align="center"><b>Max</b></td>
      <td style="background: #F99D30; color: white" width="100" align="center"><b>Unit</b></td>
    </tr>
    <tr>
      <td align="center">VCC</td>
      <td align="center">-</td>
      <td align="center">3.3</td>
      <td align="center">-</td>
      <td align="center">5&nbsp;</td>
      <td align="center">Volts</td>
    </tr>
    <tr>
      <td rowspan="2" align="center">Measuring Range<br></td>
      <td align="center">Humidity</td>
      <td align="center">20%</td>
      <td align="center">-</td>
      <td align="center">90%</td>
      <td align="center">RH</td>
    </tr>
    <tr>
      <td align="center">Temperature</td>
      <td align="center">0;</td>
      <td align="center">-</td>
      <td align="center">50</td>
      <td align="center">°C</td>
    </tr>
    <tr>
      <td rowspan="2" align="center">Sensitivity</td>
      <td align="center">Humidity</td>
      <td align="center">-</td>
      <td align="center">-</td>
      <td align="center">±1%</td>
      <td align="center">RH</td>
    </tr>
    <tr>
      <td align="center">Temperature</td>
      <td align="center">-</td>
      <td align="center">-</td>
      <td align="center">±1</td>
      <td align="center">°C</td>
    </tr>
    <tr>
      <td align="center">Signal Collecting Period</td>
      <td align="center">-</td>
      <td align="center">-</td>
      <td align="center">2</td>
      <td align="center">-</td>
      <td align="center">S</td>
    </tr>
  </tbody>
</table>

## Interface
---------

![DHT11 interface.jpg](https://wiki.elecrow.com/images/0/07/DHT11_interface.jpg){ loading=lazy }

## Usage
-----

When the connecting cable is shorter than 20 metres, a 5K pull-up resistor is recommended; when the connecting cable is longer than 20 metres, choose a appropriate pull-up resistor as needed.

### **Hardware**

The sensor has 3 wires: red (VCC), black (GND) and white (DATA). Connect the red to +5V, the black to GND and the white to the digital pin D10. Then, put a 4.7kohm resistor between the white wire and the +5V.   
![DHT11 hard.png](https://wiki.elecrow.com/images/thumb/3/38/DHT11_hard.png/500px-DHT11_hard.png){ loading=lazy } 
![DHT11 hard1.jpg](https://wiki.elecrow.com/images/thumb/7/75/DHT11_hard1.jpg/500px-DHT11_hard1.jpg){ loading=lazy }  
**Power**  
DHT11’s power supply is 3-5.5V DC. When power is supplied to the sensor, do not send any instruction to the sensor in within one second in order to pass the unstable status. One capacitor valued 100nF can be added between VDD and GND for power filtering.  
**Communication**  
When MCU sends a start signal, DHT11 changes from the low-power-consumption mode to the running-mode, waiting for MCU completing the start signal. Once it is completed, DHT11 sends a response signal of 40-bit data that include the relative humidity and temperature information to MCU. Users can choose to collect (read) some data. Without the start signal from MCU, DHT11 will not give the response signal to MCU. Once data is collected, DHT11 will change to the low-power-consumption mode until it receives a start signal from MCU again.  
![DHT11 communication1.jpg](https://wiki.elecrow.com/images/thumb/a/a0/DHT11_communication1.jpg/800px-DHT11_communication1.jpg){ loading=lazy }  
**MCU Sends out Start Signal to DHT**  
Data Single-bus free status is at high voltage level. When the communication between MCU and DHT11 begins, the programme of MCU will set Data Single-bus voltage level from high to low and this process must take at least 18ms to ensure DHT’s detection of MCU's signal, then MCU will pull up voltage and wait 20-40us for DHT’s response.  

**DHT Responses to MCU**   
Once DHT detects the start signal, it will send out a low-voltage-level response signal, which lasts 80us. Then the programme of DHT sets Data Single-bus voltage level from low to high and keeps it for 80us for DHT’s preparation for sending data. When DATA Single-Bus is at the low voltage level, this means that DHT is sending the response signal. Once DHT sent out the response signal, it pulls up voltage and keeps it for 80us and prepares for data transmission.  
When DHT is sending data to MCU, every bit of data begins with the 50us low-voltage-level and the length of the following high-voltage-level signal determines whether data bit is "0" or "1"  
![DHT11 communication3.png](https://wiki.elecrow.com/images/thumb/c/cd/DHT11_communication3.png/500px-DHT11_communication3.png){ loading=lazy }
![DHT11 communication4.png](https://wiki.elecrow.com/images/thumb/3/33/DHT11_communication4.png/550px-DHT11_communication4.png){ loading=lazy }  
If the response signal from DHT is always at high-voltage-level, it suggests that DHT is not responding properly and please check the connection. When the last bit data is transmitted, DHT11 pulls down the voltage level and keeps it for 50us. Then the Single-Bus voltage will be pulled up by the resistor to set it back to the free status.

### **Programming**

1.Download [Temperature\_humidity\_sensor library](https://wiki.elecrow.com/images/1/10/Humidity_Temperature_Lib_For_Arduino.zip) for Arduino boards with 16MHz XTAL; Unzip and put it in the libraries file of Arduino IDE by the path: ..\\arduino-1.0\\libraries;

2.Open “DHTtester” example via the path: File --&gt; Examples --&gt; Humidity\_Temperature\_Sensor --&gt; DHTtester.

```
// Example testing sketch for various DHT humidity/temperature sensors

#include "DHT.h"
 
#define DHTPIN 5     // what pin we're connected to
 
// Uncomment whatever type you're using!
#define DHTTYPE DHT11   // DHT 11 
//#define DHTTYPE DHT22   // DHT 22  (AM2302)
//#define DHTTYPE DHT21   // DHT 21 (AM2301)

// Connect pin 1 (on the left) of the sensor to +5V
// Connect pin 2 of the sensor to whatever your DHTPIN is
// Connect pin 4 (on the right) of the sensor to GROUND
// Connect a 10K resistor from pin 2 (data) to pin 1 (power) of the sensor

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(9600); 
  Serial.println("DHTxx test!");
 
  dht.begin();
}
  
void loop() {
 // Reading temperature or humidity takes about 250 milliseconds!
 // Sensor readings may also be up to 2 seconds 'old' (its a very slow sensor)
 float h = dht.readHumidity();
 float t = dht.readTemperature();

 // check if returns are valid, if they are NaN (not a number) then something went wrong!
 if (isnan(t) || isnan(h)) {
   Serial.println("Failed to read from DHT");
 } else {
   Serial.print("Humidity: "); 
   Serial.print(h);
   Serial.print(" %\t");
   Serial.print("Temperature: "); 
   Serial.print(t);
   Serial.println(" *C");
  }
}
```

3.Upload it into your Arduino board and open the serial monitor to observe the temperature and relative humidity information of the environment.

![DHT11result.jpg](https://wiki.elecrow.com/images/thumb/d/d4/DHT11result.jpg/400px-DHT11result.jpg){ loading=lazy }

### **Resource**

[File:Humidity Temperature Lib For Arduino.zip](https://wiki.elecrow.com/images/1/10/Humidity_Temperature_Lib_For_Arduino.zip "File:Humidity Temperature Lib For Arduino.zip")