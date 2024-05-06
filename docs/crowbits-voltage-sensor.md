---
title: Crowbits-Voltage Sensor
---

## Description
-----------

This module can detect the voltage in the circuit, which is very convenient for your design.

![Crowbits-Voltage-Sensor-1.jpg](https://wiki.elecrow.com/images/thumb/4/49/Crowbits-Voltage-Sensor-1.jpg/600px-Crowbits-Voltage-Sensor-1.jpg){ loading=lazy }

## Features
--------

- Easy to use

## Specification
-------------

- Interface Type: Analog input
- Operating Voltage: 3.3V DC
- Measuring voltage range: DC 0-15V
- Dimensions: 31.5(L)\*24.5(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board. You also need an expansion board, such as Crowbits-Terminal board.

2\. Connect the module to the A2 interface on the Crowbits-UNO board. Crowbits-Terminal board is behind it.

3\. Connect the positive pole of the power supply to be tested to the positive terminal on the Crowbits-Voltage Sensor board, and the negative terminal to the negative terminal on the Crowbits-Voltage Sensor board.

![Crowbits-Voltage Sensor-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/0/0b/Crowbits-Voltage_Sensor-Wiki_1.JPG/600px-Crowbits-Voltage_Sensor-Wiki_1.JPG){ loading=lazy }

4.Upload the following code to the Crowbits-UNO board.

```
float val11; 
int pin = A2;
void setup() 
{    
 Serial.begin(9600);   
 pinMode(pin,INPUT);
 Serial.println("Emartee.Com");   
 Serial.println("Voltage: ");   
 Serial.print("V  "); 
} 
void loop() 
{       
 float temp;       
 val11=analogRead(pin);       
// temp=(val11/1024*3.3)*2;   
  temp=(val11/1024*3.3)*4;            //temp=(val11/1024*3.3)*((R101+R102)/R102);   
 Serial.println(temp);        
// Serial.println(val11);   
 delay(1000); 
}
```

5\. After the upload is successful, open the serial port monitor, the baud rate is set to 9600. You can see that the serial port will print out the corresponding voltage value.

![Crowbits-Voltage Sensor-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/4/4b/Crowbits-Voltage_Sensor-Wiki_2.jpg/600px-Crowbits-Voltage_Sensor-Wiki_2.jpg){ loading=lazy }