---
title: Crowbits-MOSFET
---

## Description
-----------

The MOSFET is a digital output module, it’s a kind of switch that enables you to control large current with small current.

![Crowbits-MOSFET-1.jpg](https://wiki.elecrow.com/images/thumb/d/db/Crowbits-MOSFET-1.jpg/600px-Crowbits-MOSFET-1.jpg){ loading=lazy }

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

1.Control fan with relay

1)You also need a power module, such as Crowbits-Power Supply; An input module, such as Crowbits-Switch; An extension module, such as Crowbits-Terminal.

2)The connection mode is shown in the figure, but the signal feet of the input module and the output module must be connected.

![Crowbits-MOSFET-Wiki 1.jpg](https://wiki.elecrow.com/images/thumb/9/9a/Crowbits-MOSFET-Wiki_1.jpg/600px-Crowbits-MOSFET-Wiki_1.jpg){ loading=lazy }

3)We need to connect the S\_IN interface on the Crowbits-MOSFET board to a 3.3V power supply. So, we connect the VCC interface on Crowbits-terminal board to the S\_IN Interface on Crowbits-MOSFET board with Dupont line.

4)We need to connect the fan's negative pole on the GND interface on the Crowbits-MOSFET board, the positive pole of the fan on the D\_OUT Interface on Crowbits-MOSFET board.

![Crowbits-MOSFET-Wiki 2.JPG](https://wiki.elecrow.com/images/thumb/2/2a/Crowbits-MOSFET-Wiki_2.JPG/600px-Crowbits-MOSFET-Wiki_2.JPG){ loading=lazy }

5)Then, turn on the power. When you press the self-locking switch, the small fan starts to turn. When you release the self-locking switch, the small fan stops to turn.

![Crowbits-MOSFET-Wiki 3.JPG](https://wiki.elecrow.com/images/thumb/a/a8/Crowbits-MOSFET-Wiki_3.JPG/600px-Crowbits-MOSFET-Wiki_3.JPG){ loading=lazy }