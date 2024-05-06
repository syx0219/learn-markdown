---
title: Crowtail- Infrared Temperature Sensor
---

## Description
-----------

This Infrared temperature sensor is a non-contact temperature measure model by using the MLX90614,which one is in small size and low cost with measurement resolution of 0.02℃.Thanks to its low noise amplifier,17-bit ADC and powerful DSP unit,a high accuracy and resolution of the thermometer is achieved.

**Model: [CT0050ITS ](http://www.elecrow.com/crowtail-infrared-temperature-sensor-p-1509.html)**

![CT0050ITS-01.jpg](https://wiki.elecrow.com/images/thumb/b/b9/CT0050ITS-01.jpg/600px-CT0050ITS-01.jpg){ loading=lazy }

## Specification
-------------

- Work Voltage: 3.3V ~ 5V
- Temperature measure range: -40~125°C
- Measure accuracy: ±0.5°C
- Compatible digital interface
- Dimensions(mm):20.0(L)x20.0(W)x6.8(H)

## Application ideas
-----------------

- Motion sensor
- Thief-guarding System
- Switch
- Body distance check
- Industrial automation
- movement detection

## Usage
-----

This demo is going to show you how to read temperature information from this Crowtail- Infrared Temperature Sensor.

1.Hardware Connection
The Infrared Temperature Sensor is connecting to IIC interface of Crowtail - Base Shield.

![Crowtail- Infrared Temperature Sensor1.jpg](https://wiki.elecrow.com/images/thumb/1/12/Crowtail-_Infrared_Temperature_Sensor1.jpg/600px-Crowtail-_Infrared_Temperature_Sensor1.jpg){ loading=lazy }

2.Download [I2Cmaster library](./files/Crowtail-Infrared-Temperature-Sensor-zip.md) for Arduino boards with 16MHz XTAL; Unzip and put it in the libraries file of Arduino IDE by the path: ..\\arduino-1.0\\libraries;

3.Open “MLX90614” example via the path: File --&gt;Examples --&gt;I2Cmaster --&gt; MLX90614.

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

4.Upload it into your Arduino board and open the serial monitor to observe the temperature information of the environment.

![Theresult.png](https://wiki.elecrow.com/images/e/ef/Theresult.png){ loading=lazy }

## Resource
--------

- [I2Cmaster Program](./files/Crowtail-Infrared-Temperature-Sensor-zip.md)
- [Crowtail-Infrared Temperature Sensor eagle files v1.0](./files/Crowtail-Infrared-Temperature-Sensorv1.0-zip.md)