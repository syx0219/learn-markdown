---
title: Crowtail- Dry-Reed Relay
---

## Description
-----------

The Crowtail- Dry-Reed Relay is a relay module which works through magnetizing the vibration reed via the current in the coils. Compared to electromagnetic relays, the contacts completely sealed is the biggest feature of the Dry-Reed Relay. Besides, it features simplicity in construct, compactness, fast speed and long life, which make it widely applied in many fields such as microelectronic detection, Automatic Control etc.  
**Model: [CT008559D](https://www.elecrow.com/crowtail-dry-reed-relay.html)**
![Crotail- Dry-Reed Relay.jpg](https://wiki.elecrow.com/images/thumb/b/bd/Crotail-_Dry-Reed_Relay.jpg/600px-Crotail-_Dry-Reed_Relay.jpg){ loading=lazy }

## Features
--------

- Crowtail Interface
- High Speed
- Good stability
- Long contact life
- Contact fully sealed

## Specification
--------

Dimensions(mm):40.0(L)x20.0(W)x12.0(H)

![603.png](https://wiki.elecrow.com/images/thumb/4/44/603.png/1100px-603.png){ loading=lazy }

## Usage
--------

The Dry-Reed Relay can support up to 60VDC 1A load. You can use it to control resistance load, but it is not applicable to inductive load(such as Motor). 
The usage like this Dry-reed relay is quite alike that of common relays.
1.Connect electric light to Crowtail- Dry-Reed Relay and power for electric light.

2.Connect Crowtail- Dry-Reed Relay to port D2 of Crowtail- Base Shield and plug it into Arduino/Crowduino.

![Dry reed112.jpg](https://wiki.elecrow.com/images/thumb/6/64/Dry_reed112.jpg/400px-Dry_reed112.jpg){ loading=lazy }

3.Upload the code as bellow:

```
int Relay = 2;

// the setup routine runs once when you press reset:
void setup() {                
  // initialize the digital pin as an output.
  pinMode(Relay, OUTPUT);     
}

// the loop routine runs over and over again forever:
void loop() {
  digitalWrite(Relay, HIGH);   //the Relay close(HIGH is the voltage level)
  delay(5000);               // wait for five seconds
  digitalWrite(Relay, LOW);    //the Relay normally open by making the voltage LOW
  delay(5000);               // wait for five seconds
}
```

4.When you upload completed, you can see the indicator led will light on five seconds and the output port is connected ,then indicator led will light off five seconds,and the output is disconnected.

## Resources
---------

- [Crowtail- Dry-Reed Relay Eagle files](./files/Crowtail-Dry-Reed-Relay-zip.md)