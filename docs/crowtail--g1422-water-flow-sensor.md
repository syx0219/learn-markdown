---
title: G1/4" Water Flow Sensor
---

## Description
-----------

Crowtail G1/4 water flow sensor is composed of magnetic core, rotating impeller, external casing and sensors, hall sensor. When the water flow through the rotor, the rotor coil, it activates the movement of the magnetic core trigger switch speed and different flow change. Using hall sensor output corresponding pulse signal, the user can through the test the speed of the pulse flow. It is suitable for the test flow in water machine or the coffee machine. There are also many other water flow sensor in choosing the diameter of the other.
Water flow sensor output pulse is proportional to the flow: \* 98 = flow pulse frequency.If the output frequency is 48, then water: 48/98 = 0.5 (L/min)

**Model: [CT007914W](http://www.elecrow.com/crowtail-g14-water-flow-sensor-p-1637.html)**

![13995480872.jpg](https://wiki.elecrow.com/images/thumb/b/b8/13995480872.jpg/500px-13995480872.jpg){ loading=lazy }

## Feature
-------

- Working Voltage: 5V～24V
- Flow Rate Range: 0.3～6L/min
- Crowtail Interface
- Easy to use

## specification
-------------

- Max. Working Current: 15mA (DC 5V)
- Load Capacity: ≤10mA (DC 5V)
- Operating Temperature: ≤80℃
- Liquid Temperature: ≤120℃
- Operating Humidity: 35%～90%RH
- Water Pressure: ≤2.0MPa
- Storage Temperature: -25～+ 80℃
- Storage Humidity: 25%～95%RH
- Dimensions(mm):80.2(L)x34.5(W)x26.2(H)

## Usage
-----

Here is an example showing how to turn on the Crowtail- G1/4" Water Flow Sensor.

1\. Plug it onto the Digital port 2 of Crowtail - Base Shield using a Crowtail cable.

2.Plug the Crowtail - Base Shield onto Arduino.

3\. Connect Arduino to PC by using a USB cable.

![Ater sensor1 41.jpg](https://wiki.elecrow.com/images/thumb/b/bc/Ater_sensor1_41.jpg/600px-Ater_sensor1_41.jpg){ loading=lazy }

4.Let the water flow connect to a water pipe.

5\. Copy and paste code below to a new Arduino sketch, and upload it to your Arduino.

```
  volatile int NbTopsFan; //measuring the rising edges of the signal
int Calc;                               
int hallsensor = 2;    //The pin location of the sensor
 
void rpm ()     //This is the function that the interupt calls 
{ 
  NbTopsFan++;  //This function measures the rising and falling edge of the 
 
hall effect sensors signal
} 
// The setup() method runs once, when the sketch starts
void setup() //
{ 
  pinMode(hallsensor, INPUT); //initializes digital pin 2 as an input
  Serial.begin(9600); //This is the setup function where the serial port is initialised,

  attachInterrupt(0, rpm, RISING); //and the interrupt is attached
} 
// the loop() method runs over and over again,
// as long as the Arduino has power
void loop ()    
{
  NbTopsFan = 0;   //Set NbTops to 0 ready for calculations
  sei();      //Enables interrupts
  delay (1000);   //Wait 1 second
  cli();      //Disable interrupts
  Calc = (NbTopsFan * 60 / 98); //(Pulse frequency x 60) / 98Q, = flow rate in L/hour 

  Serial.print (Calc, DEC); //Prints the number calculated above
  Serial.print (" L/hour\r\n"); //Prints "L/hour" and returns a  new line
}
```

6.When you upload the code complete,you can measure the water flow rate and see the result via the serial port debug window