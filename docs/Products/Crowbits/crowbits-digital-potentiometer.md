---
title: Crowbits-Digital Potentiometer
---

## Description
-----------

The high-precision digital adjustable potentiometer is a potentiometer that can be adjusted by digital signals. It functions like a linear potentiometer. It controls the circuit by adjusting the resistance value in the circuit, but here it is controlled by digital signals.

![Crowbits-Digital-Potentiometer-1.jpg](https://wiki.elecrow.com/images/thumb/c/ce/Crowbits-Digital-Potentiometer-1.jpg/600px-Crowbits-Digital-Potentiometer-1.jpg){ loading=lazy }

## Features
--------

- Digital and Programmable
- High resistance resolution
- Temperature compensation

## Specification
-------------

- Operating Voltage: 3.3V DC
- Dimensions: 31.5(L)\*24.5(W)\*13(H)mm

## Usage
-----

The following sketch demonstrates a simple application of the module.

1\. You need to prepare a Crowbits motherboard, such as Crowbits-UNO board. 2 digital input modules, such as Crowbits-Button and Crowbits-touch sensor. 1 digital output module, such as Crowbits-LED.

2\. Connect the Crowbits-Digital Potentiometer to the D2 and D3 interface. The keys are connected to the D5 and D10 interfaces respectively. And the Crowbits-LED is connected to the SIG\_OUT pin on Crowbits-Digital Potentiometer board.

![Crowbits-Digital Potentiometer-Wiki 1.JPG](https://wiki.elecrow.com/images/thumb/0/00/Crowbits-Digital_Potentiometer-Wiki_1.JPG/600px-Crowbits-Digital_Potentiometer-Wiki_1.JPG){ loading=lazy }

3\. Upload the following code to the Crowbits-UNO board.

```
#define dig_INC 3
#define dig_UD  2
#define key_INC 5
#define key_UD 10

int dig_UD_status = HIGH;
int n;

void setup()
{
  pinMode(dig_INC, OUTPUT);
  pinMode(dig_UD, OUTPUT);
  pinMode(key_INC, INPUT);
  pinMode(key_UD, INPUT);
  Serial.begin(9600);
  init_digital_potentiometer(); //初始化
}


void loop()
{
  if (digitalRead(key_INC) == HIGH)
  {
    delay(10);
    if (digitalRead(key_INC) == HIGH)
    {
      dig_UD_status = !dig_UD_status;
      digitalWrite(dig_UD, dig_UD_status);
      delay(1);
      Serial.print("Status key pressed,");
      if (dig_UD_status == HIGH)
      {
        Serial.println("The current status is increased:");
      }
      else
      {
        Serial.println("The current status is reduced:");
      }
      while (digitalRead(key_INC) == HIGH);
    }
  }
  if (digitalRead(key_UD) == HIGH)
  {
    delay(10);
    if (digitalRead(key_UD) == HIGH)
    {
      for (n = 20; n >= 0; n--)
      {
        digitalWrite(dig_INC, LOW);
        delay(2);
        digitalWrite(dig_INC, HIGH);
        delay(2);
      }
      while (digitalRead(key_UD) == HIGH);
    }
  }
}

void init_digital_potentiometer()
{
  int i;
  for (i = 100; i >= 0; i--)
  {
    digitalWrite(dig_INC, LOW);
    delay(1);
    digitalWrite(dig_INC, HIGH);
  }
  digitalWrite(dig_UD, HIGH);
  delay(1);
}
```

4\. After the upload is successful, open the serial port monitor, the baud rate is set to 9600.

- When you press the button connected to the D5 port, the current status of serial port printing is increased, and then press the button connected to the D10 port, the LED light will gradually turn on.

- When you press the button connected to the D5 port, the current status of the serial port printing is reduced, and then press the button connected to the D10 port, the LED light will gradually dim.

![Crowbits-Digital Potentiometer-Wiki 2.jpg](https://wiki.elecrow.com/images/thumb/2/2a/Crowbits-Digital_Potentiometer-Wiki_2.jpg/600px-Crowbits-Digital_Potentiometer-Wiki_2.jpg){ loading=lazy }

![Crowbits-Digital-Potentiometer-Wiki 2.JPG](https://wiki.elecrow.com/images/thumb/c/c1/Crowbits-Digital-Potentiometer-Wiki_2.JPG/800px-Crowbits-Digital-Potentiometer-Wiki_2.JPG){ loading=lazy }