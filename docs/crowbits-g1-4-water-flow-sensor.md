---
title: Crowbits-G1-4 Water Flow Sensor
---

## Description
-----------

Water flow sensor consists of magnetic core, rotating impeller, external casing and sensor and a hall-effect sensor. When water flows through the rotor, rotor rolls, it activates the magnetic core to trigger switch action speed changes with different rate of flow. The hall-effect sensor outputs the corresponding pulse signals, users can get the flow speed via detecting the pulse. It is suitable to detect flow in water dispenser or coffee machine

![Crowbits-G1-4 Water Flow Sensor 1.jpg](https://wiki.elecrow.com/images/thumb/9/9f/Crowbits-G1-4_Water_Flow_Sensor_1.jpg/600px-Crowbits-G1-4_Water_Flow_Sensor_1.jpg){ loading=lazy }

## Features
--------

- Easy to use

## Specification
-------------

- Operating Voltage: 3.3V DC
- Operating Temperature: ≤80℃
- Liquid Temperature: ≤120℃
- Operating Humidity: 35%～90%RH
- Water Pressure: ≤2.0MPa
- Storage Temperature: -25～+ 80℃
- Storage Humidity: 25%～95%RH

## Usage
-----

The following sketch demonstrates a simple application of the module.

1.You need to prepare a Crowbits motherboard, such as Crowbits-UNO board.

2.Connect the module to the D2 interface of the Crowbits-UNO board, as shown in the figure:

![Crowbits-G1-4 Water Flow Sensor-Wiki 1.jpg](https://wiki.elecrow.com/images/thumb/2/22/Crowbits-G1-4_Water_Flow_Sensor-Wiki_1.jpg/600px-Crowbits-G1-4_Water_Flow_Sensor-Wiki_1.jpg){ loading=lazy }

3.Upload the following code to the Crowbits-UNO board.

```
// reading liquid flow rate using Crowduino and Water Flow Sensor

volatile int NbTopsFan; //measuring the rising edges of the signal
int Calc;                               
int WaterFlowsensor = 2;    //The pin location of the sensor

void rpm ()     //This is the function that the interupt calls 
{ 
  NbTopsFan++;  //This function measures the rising and falling edge of the hall effect sensors signal
} 
void setup() 
{ 
  pinMode(WaterFlowsensor, INPUT); //initializes digital pin 2 as an input
  Serial.begin(9600); //This is the setup function where the serial port is initialised,
  attachInterrupt(0, rpm, RISING); //and the interrupt is attached
} 
// the loop() method runs over and over again,
// as long as the Arduino has power
void loop ()    
{
  NbTopsFan = 0;   //Set NbTops to 0 ready for calculations
  sei();          //Enables interrupts
  delay (1000);   //Wait 1 second
  cli();      //Disable interrupts
  Calc = (NbTopsFan * 60 / 73); //(Pulse frequency x 60) / 73Q, = flow rate in L/hour 
  Serial.print (Calc, DEC); //Prints the number calculated above
  Serial.print (" L/hour\r\n"); //Prints "L/hour" and returns a  new line
}
```

4.After the upload is successful, open the serial port monitor, the baud rate is set to 9600. The serial port will print out the current water flow.

![Water Flow Sensor result.jpg](https://wiki.elecrow.com/images/3/33/Water_Flow_Sensor_result.jpg){ loading=lazy }