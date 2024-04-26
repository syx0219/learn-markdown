---
title: LED matrix kit
---

## Introduction
------------

This product is a serially driven 8x8 LED Matrix kit powered by MAX7219.

It only needs three data lines and two power lines.

The 8x8 LED Matrix is easy to use and compatible with Arduino, and its LED brightness adjustment can be implemented in software.

8x8 LED Matrix kit has many applications in real life, such as various types of electronic display panels. If the LED matrix is not driven by any peripherals, it’ll waste the interface of devices, and the LED brightness will be impaired due to insufficient power, so that we cannot get ideal display effect.

The LED matrix can be driven in two ways: parallel or serial. We usually drive it in the serial manner in order to save interface. The serial-driven LED matrix actually dynamically displays the LEDs, i.e., displays the LEDs row-by-row or column-by-column. The persistence of vision for humans is about 0.1s, so as long as we can serially display all 8 rows/columns within 0.1s, we’ll see a complete character or pattern.  
**Model: [DLM72192R](http://www.elecrow.com/max7219-8x8-matrix-display-module-kit-red-dot-p-434.html)**   
![MAX7219 8x8 Matrix Kit - Red Dot11.jpg](https://wiki.elecrow.com/images/thumb/1/18/MAX7219_8x8_Matrix_Kit_-_Red_Dot11.jpg/400px-MAX7219_8x8_Matrix_Kit_-_Red_Dot11.jpg){ loading=lazy }

This product comes in the form of a [kit](http://www.elecrow.com/display-c-77/led-matrix-c-77_100/max7219-8x8-matrix-kit-red-dot-p-434.html) or module. The kit includes the following components:

- MAX7219

- Electrolytic cpaacitor：10uF/25V

- Resistor：10K

- Capacitance：0.1uF

- Headers and receptacles.

After assembling, The [Led matrix module](http://www.elecrow.com/display-c-77/led-matrix-c-77_100/max7219-8x8-matrix-display-module-red-dot-p-433.html) will look as:

![MAX7219 8x8 Matrix Display Module - Red Dot1 01.jpg](https://wiki.elecrow.com/images/thumb/8/8d/MAX7219_8x8_Matrix_Display_Module_-_Red_Dot1_01.jpg/400px-MAX7219_8x8_Matrix_Display_Module_-_Red_Dot1_01.jpg){ loading=lazy }

## Specification of LED Matrix
---------------------------

- Operating Voltage: DC 4.7V – 5.3V

Typical Voltage: 5V

- Operating Current: 320mA

Max Operating Current: 2A

- Operating Temperature: 0 ℃ – 50 ℃

Typical Temperature: 25 ℃

## Assembly Instruction
--------------------

This is a great beginner kit, easy to make even if you are have never soldered before. Please download this [step by step Assembly tutorials](http://www.elecrow.com/wiki/index.php?title=File:Installation_steps.pdf) and then follow it to solder it.

Please pay attention that if it doesn't show as you wanted. it isn't that you soldered wrong. you need to change the direction then assemble it.

## Usage
-----

### **Hardware Installation**

**Connection Wires**

The schematics of the LED matrix is attached below.

Please follow the following instructions to connect hardwares.

1. The 8x8 LED Matrix must be common-grounded with the Arduino module;
2. Connect Arduino pin 8 to DIN on the LED Matrix;
3. Connect Arduino pin 9 to CS on the LED Matrix;
4. Connect Arduino pin 10 to CLK on the LED Matrix;
5. Use independent power supply for the 8x8 LED Matrix Shield, and the supply voltage is 5V/2A.

![LED8X8Kit.jpg](https://wiki.elecrow.com/images/1/19/LED8X8Kit.jpg){ loading=lazy }

*Schematics of the 8x8 LED Matrix*

**Testing Steps**

1.Wiring Instructions

- Connect Arduino pin8 to DIN on 8x8 LED Matrix
- Connect Arduino pin9 to CS of 8x8 LED Matrix
- Connect Arduino pin10 to CLK of 8x8 LED Matrix
- Connect Arduino 5V to VCC of 8x8 LED Matrix
- Connect Arduino GND to GND of 8x8 LED Matrix

*Attention：8\*8LED Matrix must be common-grounded with Arduino module.*

![MAX7219 8x8 Matrix Display Module - Red Dot9.gif](https://wiki.elecrow.com/images/thumb/2/24/MAX7219_8x8_Matrix_Display_Module_-_Red_Dot9.gif/400px-MAX7219_8x8_Matrix_Display_Module_-_Red_Dot9.gif){ loading=lazy }

2.Check the corresponding interfaces are properly connected.

3.You'd better powering up the Arduino/Crowduino with AC adapter.

4.Observation：The LED matrix should circularly display the digits 0 to 9 on LED screen first, then the characters A to Z, as shown in the above figure.

### **Software Programming**

You can download the Max7219 drive library [LedControl,zip](https://wiki.elecrow.com/images/2/26/LedControl.zip) or program the Arduino/Crowduino with the following Example code.

**Example code**

```
 unsigned char i;
 unsigned char j; 
/*Port Definitions*/
int Max7219_pinCLK = 10;
int Max7219_pinCS = 9;
int Max7219_pinDIN = 8;

unsigned char disp1[38][8]={
{0x3C,0x42,0x42,0x42,0x42,0x42,0x42,0x3C},//0 
{0x10,0x18,0x14,0x10,0x10,0x10,0x10,0x10},//1 
{0x7E,0x2,0x2,0x7E,0x40,0x40,0x40,0x7E},//2 
{0x3E,0x2,0x2,0x3E,0x2,0x2,0x3E,0x0},//3  
{0x8,0x18,0x28,0x48,0xFE,0x8,0x8,0x8},//4 
{0x3C,0x20,0x20,0x3C,0x4,0x4,0x3C,0x0},//5 
{0x3C,0x20,0x20,0x3C,0x24,0x24,0x3C,0x0},//6 
{0x3E,0x22,0x4,0x8,0x8,0x8,0x8,0x8},//7  
{0x0,0x3E,0x22,0x22,0x3E,0x22,0x22,0x3E},//8 
{0x3E,0x22,0x22,0x3E,0x2,0x2,0x2,0x3E},//9 
{0x8,0x14,0x22,0x3E,0x22,0x22,0x22,0x22},//A 
{0x3C,0x22,0x22,0x3E,0x22,0x22,0x3C,0x0},//B 
{0x3C,0x40,0x40,0x40,0x40,0x40,0x3C,0x0},//C 
{0x7C,0x42,0x42,0x42,0x42,0x42,0x7C,0x0},//D 
{0x7C,0x40,0x40,0x7C,0x40,0x40,0x40,0x7C},//E 
{0x7C,0x40,0x40,0x7C,0x40,0x40,0x40,0x40},//F 
{0x3C,0x40,0x40,0x40,0x40,0x44,0x44,0x3C},//G
{0x44,0x44,0x44,0x7C,0x44,0x44,0x44,0x44},//H
{0x7C,0x10,0x10,0x10,0x10,0x10,0x10,0x7C},//I
{0x3C,0x8,0x8,0x8,0x8,0x8,0x48,0x30},//J
{0x0,0x24,0x28,0x30,0x20,0x30,0x28,0x24},//K
{0x40,0x40,0x40,0x40,0x40,0x40,0x40,0x7C},//L
{0x81,0xC3,0xA5,0x99,0x81,0x81,0x81,0x81},//M
{0x0,0x42,0x62,0x52,0x4A,0x46,0x42,0x0},//N
{0x3C,0x42,0x42,0x42,0x42,0x42,0x42,0x3C},//O
{0x3C,0x22,0x22,0x22,0x3C,0x20,0x20,0x20},//P
{0x1C,0x22,0x22,0x22,0x22,0x26,0x22,0x1D},//Q
{0x3C,0x22,0x22,0x22,0x3C,0x24,0x22,0x21},//R
{0x0,0x1E,0x20,0x20,0x3E,0x2,0x2,0x3C},//S
{0x0,0x3E,0x8,0x8,0x8,0x8,0x8,0x8},//T
{0x42,0x42,0x42,0x42,0x42,0x42,0x22,0x1C},//U
{0x42,0x42,0x42,0x42,0x42,0x42,0x24,0x18},//V
{0x0,0x49,0x49,0x49,0x49,0x2A,0x1C,0x0},//W
{0x0,0x41,0x22,0x14,0x8,0x14,0x22,0x41},//X
{0x41,0x22,0x14,0x8,0x8,0x8,0x8,0x8},//Y
{0x0,0x7F,0x2,0x4,0x8,0x10,0x20,0x7F},//Z
};

void Write_Max7219_byte(unsigned char DATA) 
{   
            unsigned char i;
	    digitalWrite(Max7219_pinCS,LOW);		
	    for(i=8;i>=1;i--)
          {		  
             digitalWrite(Max7219_pinCLK,LOW);
             digitalWrite(Max7219_pinDIN,DATA&0x80);// Extracting a bit data
             DATA = DATA<<1;
             digitalWrite(Max7219_pinCLK,HIGH);
           }                                 
}

void Write_Max7219(unsigned char address,unsigned char dat)
{
        digitalWrite(Max7219_pinCS,LOW);
        Write_Max7219_byte(address);           //address，code of LED
        Write_Max7219_byte(dat);               //data，figure on LED 
        digitalWrite(Max7219_pinCS,HIGH);
}

void Init_MAX7219(void)
{
 Write_Max7219(0x09, 0x00);       //decoding ：BCD
 Write_Max7219(0x0a, 0x03);       //brightness 
 Write_Max7219(0x0b, 0x07);       //scanlimit；8 LEDs
 Write_Max7219(0x0c, 0x01);       //power-down mode：0，normal mode：1
 Write_Max7219(0x0f, 0x00);       //test display：1；EOT，display：0
}

void setup()
{
  
  pinMode(Max7219_pinCLK,OUTPUT);
  pinMode(Max7219_pinCS,OUTPUT);
  pinMode(Max7219_pinDIN,OUTPUT);
  delay(50);
  Init_MAX7219();
}

void loop()
{ 
   for(j=0;j<38;j++)
  {
   for(i=1;i<9;i++)
    Write_Max7219(i,disp1[j][i-1]);
   delay(500);
  } 		
}
```

## Resources
---------

- step by step Assembly tutorials
- [Arduino playground](http://playground.arduino.cc/Main/LEDMatrix)
- [Led Matrix Arduino library](https://wiki.elecrow.com/images/2/26/LedControl.zip)