---
title: Crowbits-Relay
---

## Description
-----------

The relay is a digital output module, it's an electronic control device that has a control system (also known as an input circuit) and a controlled system (also known as an output circuit), which is usually used in automatic control circuits.

![Crowbits-Relay-1.jpg](https://wiki.elecrow.com/images/thumb/1/1d/Crowbits-Relay-1.jpg/600px-Crowbits-Relay-1.jpg){ loading=lazy }

## Features
--------

- A small current to control large currents

## Specification
-------------

- Operating Voltage: 3.3V DC
- Supply mode: Crowbits Power Module
- Dimensions: 31.5(L)\*24.5(W)\*13(H) mm

## Usage
-----

#### 1.Control fan with relay

1)You also need a power module, such as Crowbits-Power Supply; An input module, such as Crowbits-Switch; An extension module, such as Crowbits-Terminal.

2)The connection mode is shown in the figure, but the signal feet of the input module and the output module must be connected.

3)We need to connect the COM interface on the Crowbits-relay board to a 3.3V power supply. So, we connect the VCC interface on Crowbits-terminal board to the COM port on Crowbits-Relay board with Dupont line.

4)We need to connect the fan's negative pole on the GND interface on the Crowbits-terminal board, the positive pole of the fan on the NC Interface or NO Interface on Crowbits-Relay board. For example, I'm connecting to the NO interface.