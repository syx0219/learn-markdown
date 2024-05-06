---
title: Crowtail- MEMS Microphone
---

## Description
-----------

The Crowtail- MEMS Microphone is a simple and easy-to-use microphone for a variety of sound-sensing projects. The on-board mic is an ADMP401, which is a low-power, omnidirectional microphone with an analog output. It works for both near and long-range uses and is particularly good for portable applications due to its low power consumption. The amplifier’s AUD output will float at one half Vcc when no sound is being picked up. The amplifier produces a peak-to-peak output of about 200mV when the microphone is held at arms length and is being talked into at normal conversational volume levels. So the AUD output can easily be connected to the ADC of a micro.

**Model:** [CRT00238M](https://www.elecrow.com/crowtail-mems-microphone.html)

![Crowtail- MEMS Microphone.jpg](https://wiki.elecrow.com/images/thumb/e/e7/Crowtail-_MEMS_Microphone.jpg/500px-Crowtail-_MEMS_Microphone.jpg){ loading=lazy }

## **Features**
------------

Low-power, omnidirectional microphone

Both near and long-range uses

Mic: ADMP401

volatog:5v

current: 250 μA.

## Specification(ADMP401)
----------------------

High Signal-to-Noise Ratio (“SNR”) of 62 dBA

Sensitivity of about -42 dBV

Flat frequency response from 100 Hz to 15 kHz

Low current consumption of &lt;250 μA

Maximum acoustic input of 120 dB

Dimensions(mm):20.0(L)x20.0(W)x9.8(H)

## **Application**
---------------

smartphones, digital video cameras etc.

## Usage
-----

The microcontroller analog (ADC) input converts our audio signal into an integer. The range of possible ADC values depends on which microcontroller you are using. For an Arduino microcontroller, this range is between 0 and 1023, so the resolution of our ADC measurement is 1024. Connect Crowtail- Solid-State Relay to port D2(one button to D5) of Crowtail - Base Shield and plug it into Arduino/Crowduino.

```


// Connect the MEMS AUD output to the Arduino A0 pin
int mic = A0;

// Variables to find the peak-to-peak amplitude of AUD output
const int sampleTime = 50; 
int micOut;


void setup() {
  Serial.begin(9600);
}

void loop() {
   int micOutput = findPTPAmp();
   VUMeter(micOutput);   
}   


// Find the Peak-to-Peak Amplitude Function
int findPTPAmp(){
// Time variables to find the peak-to-peak amplitude
   unsigned long startTime= millis();  // Start of sample window
   unsigned int PTPAmp = 0; 

// Signal variables to find the peak-to-peak amplitude
   unsigned int maxAmp = 0;
   unsigned int minAmp = 1023;

// Find the max and min of the mic output within the 50 ms timeframe
   while(millis() - startTime < sampleTime) 
   {
      micOut = analogRead(mic);
      if( micOut < 1023) //prevent erroneous readings
      {
        if (micOut > maxAmp)
        {
          maxAmp = micOut; //save only the max reading
        }
        else if (micOut < minAmp)
        {
          minAmp = micOut; //save only the min reading
        }
      }
   }

  PTPAmp = maxAmp - minAmp; // (max amp) - (min amp) = peak-to-peak amplitude
  double micOut_Volts = (PTPAmp * 3.3) / 1023; // Convert ADC into voltage

  //Uncomment this line for help debugging (be sure to also comment out the VUMeter function)
  //Serial.println(PTPAmp); 

  //Return the PTP amplitude to use in the soundLevel function. 
  // You can also return the micOut_Volts if you prefer to use the voltage level.
  return PTPAmp;   
}

// Volume Unit Meter function: map the PTP amplitude to a volume unit between 0 and 10.
int VUMeter(int micAmp){
  int preValue = 0;

  // Map the mic peak-to-peak amplitude to a volume unit between 0 and 10.
   // Amplitude is used instead of voltage to give a larger (and more accurate) range for the map function.
   // This is just one way to do this -- test out different approaches!
  int fill = map(micAmp, 23, 750, 0, 10); 

  // Only print the volume unit value if it changes from previous value
  while(fill != preValue)
  {
    Serial.println(fill);
    preValue = fill;
  }
}


```

Upload the code and open the serial monitor. You an observe the data is changing when you making the sound on the Microphone.

![Examgfhrhple.png](https://wiki.elecrow.com/images/thumb/e/e2/Examgfhrhple.png/500px-Examgfhrhple.png){ loading=lazy }

## **Resource**
------------

[ADMP401.pdf](./files/ADMP401-pdf.md)