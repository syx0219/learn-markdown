---
title: LR1262 LoRaWAN Node Module
---

## Description
-----------

The LR1262 is a low power long range transceiver module based on the STM32WLE5CCU6 chip. It provides an easy-to-use, small size and low power solution for long range wireless data applications. The module is compliant with the LoRaWAN 1.0.3 specification for Class A, B and C standards. It can easily connect to different LoRaWAN server platforms such as TheThingsNetwork (TTN), Chirpstack, Actility and others. It also supports LoRa peer-to-peer (P2P) communication mode, which helps you quickly implement your own customised long-range LoRa network. You can configure the module's mode and operation using AT commands via the UART interface.The LR1262 also features low power consumption, making it ideal for battery-powered applications.


The LR1262 is a high-power remote module with a convenient stamp-hole form factor for easy integration into device motherboards without additional components. It supports multiple frequency plans such as EU868/US915/AU915/AS923/KR920/IN865 and is compatible with LoRaWAN® Class A/B/C protocol. In addition, the module is FCC/CE certified, making it cost-effective to quickly get your entire device certified and approved by any regulatory agency. With the built-in AT command firmware, beginners can easily create prototypes or applications with just a few simple commands. On the other hand, experienced developers can use the SDK to develop custom products.

**Model: [CRT01268N](https://www.elecrow.com/lr1262-lorawan-node-module-support-full-frequency-band.html)**

![1262 node.png](https://wiki.elecrow.com/images/e/e2/1262_node.png){ loading=lazy }

[![Alt text](../../assets/images/Get_one_now.png){loading=lazy}](https://www.elecrow.com/lr1262-lorawan-node-module-support-full-frequency-band.html "Title text")

## Feature
-------

- Based on STM32WLE5CCU6
- Compliant with LoRaWAN 1.0.3 specification
- Supported bands IN865, EU868, AU915, US915, KR920, RU864 and AS923-1/2/3/4
- LoRaWAN activation via OTAA/ABP
- LoRa peer-to-peer (P2P) communication
- Developed for Keil
- Easy-to-use AT command set via UART interface
- Long range - more than 2 km with optimised antennas
- ARM Cortex-M4 32-bit
- Flash 256 kbytes with ECC
- RAM 64 kbytes
- Ultra-low power consumption of 2.2 μA in sleep mode
- Supply voltage: 2.0 V ~ 3.6 V
- Temperature range: -20°C ~ 85°C

## Pin Function
------------

![Pinout.png](https://wiki.elecrow.com/images/1/15/Pinout.png){ loading=lazy }

| Pin number | Pin name | Pin type | Alternate funtions | Additional funtions |
|---|---|---|---|---|
| 1 | GND | GND |  |  |
| 2 | BOOT | I/O | CM4\_EVENTOUT |  |
| 3 | NRST | I/O |  |  |
| 4 | GND | GND |  |  |
| 5 | GND | GND |  |  |
| 6 | 1V55 |  |  |  |
| 7 | ADC(PB2) | I/O | LPTIM1\_OUT,I2C3\_SMBA,SPI1\_NSS,DEBUG\_RF\_SMPSRDY | COMP1\_INP,COMP2\_INM,ADC\_IN4 |
| 8 | PA10 | I/O | RTC\_REFIN,TIM1\_CH3,I2C1\_SDA,SPI2\_MOSI/I2S2\_SD,USART1\_RX,DEBUG\_RF\_HSE32RDY,TIM17\_BKIN,SM4\_EVENTOUT | COMP1\_INM,COMP2\_INM,DAC\_OUT1,ADC\_IN6 |
| 9 | GND |  |  |  |
| 10 | GND |  |  |  |
| 11 | PC13 | I/O | CM4\_EVENTOUT | TAMP\_IN1/RTC\_OUT1/RTC\_TS/WKUP2 |
| 12 | SWDIO(PA13) | I/O | JTMS-SWDIO,I2C2\_SMBA | ADC\_IN9 |
| 13 | SCL(PA12) | I/O | TIM1\_ETR,LPTIM3\_IN1,I2C2\_SCL,SPI1\_MOSI,RF\_BUSY,USART1\_RTS,CM4\_EVENTOUT | ADC\_IN8 |
| 14 | SDA(PA11) | I/O | TIM1\_CH4,TIM1\_BKIN2,LPTIM3\_ETR,I2C2\_SDA,SPI1\_MISO,USART1\_CTS,DEBUG\_RF\_NRESET | COMP1\_INM,COMP2\_INM,ADC\_IN7 |
| 15 | PA1 | I/O | TIM2\_CH2,LPTI3\_OUT,I2C1\_SMBA,SPI1\_SCK,USART2\_RTS,LPUART1\_RTS,DEBUG\_PWR\_REGLP2S,CM4\_EVENTOUT |  |
| 16 | PB3 | I/O | JTD0/TRACESWO,TIM2\_CH2,SPI1\_SCK,RF\_IRQO,USART1\_RTS,DEBUG\_RF\_DTB1,CM4\_EVENTOUT | COMP1\_INM,COMP2\_INM,ADC\_IN2,TAMP\_IN3/WKUP3 |
| 17 | PB4 | I/O | NJTRST,I2C3\_SDA,SPI1\_MISO,USART1\_CTS,DEBUG\_RF\_LDORDY,TIM17\_BKIN | COMP1\_INP,COMP2\_INP,ADC\_IN3 |
| 18 | SWCLK(PA14) | I/O | JTCK-SWCLK,LPTIM1\_OUT,I2C1\_SMBA,CM4\_EVENTOUT | ADC\_IN10 |
| 19 | PA15 | I/O |  |  |
| 20 | PB5 | I/O | LPTIM1\_IN1,I2C1\_SMBA,SPI1\_MOSI,RF\_IRQ1,USART1\_CK,COMP2\_OUT,TIM16\_BKIN |  |
| 21 | PB8 | I/O | TIM1\_CH2N,I2C1\_SCL,RF\_IRQ2,TIM16\_CH1,CM4\_EVENTOUT |  |
| 22 | PA0 | I/O | TIM2\_CH1,I2C3\_SMBA,I2S\_CKIN,USART2\_CTS,COMP1\_OUT,DEBUG\_PWR\_REGLP1S,TIM2\_ETR | TAMP\_IN2/WKUP1 |
| 23 | TX1(PA2) | I/O | LSCO,TIM2\_CH3,USART2\_TX,LPUART1\_TX,COMP2\_OUT,DEBUG\_PWR\_LDORDY | LSCO |
| 24 | RX1(PA3) | I/O | TIM2\_CH4,I2S2\_MCK,USART\_RX,LPUART1\_RX,CM4\_EVENTOUT |  |
| 25 | TX2(PB6) | I/O | LPTIM1\_ETR,I2C1\_SCL,USART1\_TX,TIM16\_CH1N |  |
| 26 | RX2(PB7) | I/O | LPTIM1\_IN2,TIM1\_BKIN,I2C1\_SDA,USART1\_RX,TIM17\_CH1N |  |
| 27 | PA8 | I/O | MCO,TIM1\_CH1,SPI2\_SCK/I2S2\_CK,USART1\_CK,LPTIM2\_OUT |  |
| 28 | MOSI(PA7) | I/O | TIM1\_CH1N,I2C3\_SCL,SPI1\_MOSI,COMP2\_OUT,DEBUG\_SUBGHZSPI\_MOSIOUT,TIM17\_CH1,CM4\_EVENTOUT |  |
| 29 | MISO(PA6) | I/O | TIM1\_BKIN.I2C2\_SMBA,SPI1\_MISO,LPUART1\_CTS,DEBUG\_SUBGHZSPI\_MISOOUT,TIM16\_CH1,CM4\_EVENTOUT |  |
| 30 | SCK(PA5) | I/O | TIM2\_CH1,TIM2\_ETR,SPI2\_MISO,SPI1\_SCK,DEBUG\_SUBGHZSPI\_SCKOUT,LPTIM2\_ETR,CM4\_EVENTOUT |  |
| 31 | NSS/CS(PA4) | I/O | RTC\_OUT2,LPTIM1\_OUT,SPI1\_NSS,USART2\_CK,DEBUG\_SUBGHZSPI\_NSSOUT,LPTIM2\_OUT,CM4\_EVENTOUT |  |
| 32 | 3V3(VDD) | Supply pin |  |  |
| 33 | RF | ANT |  |  |
| 34 | GND | GND |  |  |

## Case Applications
-----------------

### [**Case 1: Single-channel Application Routines For Single-channel Gateways And Nodes**](../case/Case1_Single-channel_application_routines_for_single-channel_gateways_and_nodes.md)

### [**Case 2: Multi-Channel Application Routine For Single-Channel Gateways And Nodes**](../case/Case2_Multi-Channel_Application_Routine_for_Single-Channel_Gateways_and_Nodes.md)

### [**Case 3: Single-channel Application Routines for Raspberry Pi Gateways and Nodes**](../case/Case3_Single-channel_Application_Routines_for_Raspberry_Pi_Gateways_and_Nodes.md#frequency-selection)

### [**Case 4: Multi-Channel Application Routine for Raspberry Pi Gateways and Nodes**](../case/Case4_Multi-Channel_Application_Routine_for_Raspberry_Pi_Gateways_and_Nodes.md#2-lr1262-node)

### [**Case 5: LR1262 Point-to-Point Communication Application Example**](../case/Case5_LR1262_Point-to-Point_Communication_Application_Example.md)

## AT Command Description
----------------------

### [**LR1262 LoRaWAN AT Command Description**](./LR1262_LoRaWAN_AT_Command_Description.md)