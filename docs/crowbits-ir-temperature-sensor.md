---
title: Crowbits-IR Temperature Sensor
---

## Description
-----------

This IR temperature sensor is a non-contact temperature measure model by using the MLX90614, which one is in small size and low cost with a measurement resolution of 0.02℃. Thanks to its low noise amplifier, 17-bit ADC and powerful DSP unit, high accuracy and resolution of the thermometer are achieved.

![Crowbits-IR Temperature Sensor 1.jpg](https://wiki.elecrow.com/images/thumb/1/1f/Crowbits-IR_Temperature_Sensor_1.jpg/600px-Crowbits-IR_Temperature_Sensor_1.jpg){ loading=lazy }

## Features
--------

- High precision
- Easy to use

## Specification
-------------

- Interface Type: I2C
- Operating Voltage: 3.3V DC
- Dimensions: 31.5(L)\*24.5(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2\. Connect the module to the I2C interface on the Crowbits-UNO board, as shown in the figure:

![Crowbits-IR Temperature Sensor-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/c/c5/Crowbits-IR_Temperature_Sensor-Wiki_1.JPG/600px-Crowbits-IR_Temperature_Sensor-Wiki_1.JPG){ loading=lazy }

3\. Download the library “I2Cmaster”. Unzip and put it in the libraries file, for example: C:\\Program Files (x86)\\Arduino\\libraries.

4\. Upload the following code to the Crowbits-UNO board.

```
#include <i2cmaster.h>


void setup(){
	Serial.begin(9600);
	Serial.println("Setup...");
	
	i2c_init(); //Initialise the i2c bus
	PORTC = (1 << PORTC4) | (1 << PORTC5);//enable pullups
}

void loop(){
    int dev = 0x5A<<1;
    int data_low = 0;
    int data_high = 0;
    int pec = 0;
    
    i2c_start_wait(dev+I2C_WRITE);
    i2c_write(0x07);
    
    // read
    i2c_rep_start(dev+I2C_READ);
    data_low = i2c_readAck(); //Read 1 byte and then send ack
    data_high = i2c_readAck(); //Read 1 byte and then send ack
    pec = i2c_readNak();
    i2c_stop();
    
    //This converts high and low bytes together and processes temperature, MSB is a error bit and is ignored for temps
    double tempFactor = 0.02; // 0.02 degrees per LSB (measurement resolution of the MLX90614)
    double tempData = 0x0000; // zero out the data
    int frac; // data past the decimal point
    
    // This masks off the error bit of the high byte, then moves it left 8 bits and adds the low byte.
    tempData = (double)(((data_high & 0x007F) << 8) + data_low);
    tempData = (tempData * tempFactor)-0.01;
    
    float celcius = tempData - 273.15;
    float fahrenheit = (celcius*1.8) + 32;

    Serial.print("Celcius: ");
    Serial.println(celcius);

    Serial.print("Fahrenheit: ");
    Serial.println(fahrenheit);

    delay(1000); // wait a second before printing again
}
```

5\. After the upload is successful, open the serial port monitor, the baud rate is set to 9600. The serial port will print out temperature information.

![Crowbits-IR Temperature Sensor-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/7/7c/Crowbits-IR_Temperature_Sensor-Wiki_2.jpg/600px-Crowbits-IR_Temperature_Sensor-Wiki_2.jpg){ loading=lazy }