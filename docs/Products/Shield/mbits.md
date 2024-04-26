---
title: Mbits
---

## **Introduction**
----------------

Mbits is a pocket-sized microcontroller has lots of features the same as Microbit V2. Mbits is an ESP32-WROVER-B based educational hardware suitable for kids to learn how to program and experience hot topics such as IoT and AI.

**Model: [MIB26580B](https://www.elecrow.com/blog/the-best-micro:bit-alternative-mbits.html)**

![Mbits 1.jpg](https://wiki.elecrow.com/images/thumb/c/c7/Mbits_1.jpg/600px-Mbits_1.jpg){ loading=lazy }

## **Features**
------------

- Pocket-sized microcontroller designed
- Wireless connectivity with built-in 2.4GHz micro:bit radio and BLE Bluetooth 4.2
- Onboard MEMS microphone, speaker, 25 RGB LEDs
- Onboard accelerometer for motion sensing applications
- Notched edge connector for easier connections
- Dedicated I2C bus for peripherals
- Two programmable buttons
- Supports graphical programming (Lestscode, based on Scratch3.0), Arduino IDE and Micro Python

## **Pin Map**
-----------

| **Mbits1.1\_ESP32** | **Mbits1.2\_ESP32** |
|:-:|:-:|
| ![Mbits1.1 ESP32.png](https://wiki.elecrow.com/images/thumb/8/8c/Mbits1.1_ESP32.png/600px-Mbits1.1_ESP32.png){ loading=lazy } | ![Mbits1.2 ESP32.png](https://wiki.elecrow.com/images/thumb/b/bc/Mbits1.2_ESP32.png/600px-Mbits1.2_ESP32.png){ loading=lazy } |

| **The Definition Edge Connector V1.1** |
|---|
| ![Edge connector definition.jpg](https://wiki.elecrow.com/images/thumb/7/7a/Edge_connector_definition.jpg/600px-Edge_connector_definition.jpg){ loading=lazy } |



The Definition Edge Connector V1.2  

| **Pin Name** | **Analog Function1** | **Analog Function2** | **Function1** | **Function2** | **Function3** | **Power** |
| ------------ | -------------------- | -------------------- | ------------- | ------------- | ------------- | --------- |
| P3           | ADC2_CH4             |                      | GPIO13        |               | PWM           |           |
| P0           | ADC2_CH9             | DAC_2                | GPIO26        |               | PWM           |           |
| P4           | ADC2_CH7             |                      | GPIO27        |               | PWM           |           |
| P5           | ADC1_CH0             |                      | GPIO36        |               | PWM           |           |
| P6           |                      |                      | GPIO5         |               | PWM           |           |
| P7           | ADC2_CH5             |                      | GPIO12        |               | PWM           |           |
| P1           | ADC1_CH4             |                      | GPIO32        |               | PWM           |           |
| P8           | ADC2_CH0             |                      | GPIO4         |               | PWM           |           |
| P9           | ADC1_CH6             |                      | GPIO34        |               | PWM           |           |
| P10          | ADC2_CH6             |                      | GPIO14        |               | PWM           |           |
| P11          | ADC1_CH3             |                      | GPIO39        |               | PWM           |           |
| P12          | ADC2_CH3             |                      | GPIO15        |               | PWM           |           |
| P2           | ADC2_CH8             | DAC_1                | GPIO25        |               | PWM           |           |
| P13          |                      |                      | GPIO18        | SPI_SCK       | PWM           |           |
| P14          |                      |                      | GPIO19        | SCI_MISO      | PWM           |           |
| P15          |                      |                      | GPIO23        | SPI_MOSI      | PWM           |           |
| P16          | ADC2_CH2             |                      | GPIO2         |               | PWM           |           |
| 3v3          |                      |                      |               |               |               | 3.3V      |
| 3v3          |                      |                      |               |               |               | 3.3V      |
| 3v3          |                      |                      |               |               |               | 3.3V      |
| P19          |                      |                      | GPIO21        | I2C_SCL       | PWM           |           |
| P20          |                      |                      | GPIO22        | I2C_SDA       | PWM           |           |
| GND          |                      |                      |               |               |               | GROUND    |
| GND          |                      |                      |               |               |               | GROUND    |
| GND          |                      |                      |               |               |               | GROUND    |

## **Use on Letscode** 
--------------------

### **Install the Letscode** 

Part 1: Setting up the programming environment

1：Download the [Letscode installation package](https://www.elecrow.com/letscode.html) and install it on your computer.

2：After successful installation, open the Letscode software, click "Add Extension" in the lower left corner, find the "Mbits" board type and select.

![Mbits (5).png](https://wiki.elecrow.com/images/thumb/e/ea/Mbits_%285%29.png/400px-Mbits_%285%29.png){ loading=lazy }
![Mbits (6).png](https://wiki.elecrow.com/images/thumb/d/d5/Mbits_%286%29.png/400px-Mbits_%286%29.png){ loading=lazy }

3：Enter the programming interface, you can drag the programming block to program, when the program is written, click the "port" in the upper left corner to select the port of the Mbits board;

![Mbits (7).png](https://wiki.elecrow.com/images/thumb/7/75/Mbits_%287%29.png/700px-Mbits_%287%29.png){ loading=lazy }

4：Click the "Upload Code" button in the upper right corner, upload the code, and wait for the upload to succeed.

Part 2: Some examples

1.MPU6050 example

The reference code is as follows:

![Mbits (8).png](https://wiki.elecrow.com/images/thumb/a/a6/Mbits_%288%29.png/400px-Mbits_%288%29.png){ loading=lazy }

After the code is uploaded successfully, the coordinate value of X will be displayed on the RGB dot matrix screen;

### **Use with Mbits-3-Axis Digital Accelerometer** 

**Description**

This is a high resolution digital accelerometer on Mbits. The module agile enough to detect single and double taps. It's ideal for motion detection, Gesture detection as well as robotics. Default Address = 0x68。


**Usage**

Here we show how to read the raw data from the accelerometer.

1.Connect the data cable to the communication port of Mbits.

2.Open the software and upload the following program to Mbits.

① Letscode Mode

![Mbits-3-Axis Digital Accelerometer 1.png](https://wiki.elecrow.com/images/b/bb/Mbits-3-Axis_Digital_Accelerometer_1.png){ loading=lazy }

② Code Mode

```
// Language ArduinoC
#include <MPU6050_tockn.h>
#include <Wire.h>

MPU6050 mpu6050(Wire);


void setup() {
  Serial.begin(115200);
  Wire.begin(22,21);
  mpu6050.begin();
  mpu6050.calcGyroOffsets(true);
}

void loop() {
  mpu6050.update();
  Serial.println(String("x的值：") + String((mpu6050.getAccX())));
  Serial.println(String("y的值：") + String((mpu6050.getAccY())));
  Serial.println(String("z的值：") + String((mpu6050.getAccZ())));
  delay(1000);
}
```

3.After the upload is successful,You can observe the data through the serial monitor.

![Mbits-3-Axis Digital Accelerometer 3.png](https://wiki.elecrow.com/images/7/74/Mbits-3-Axis_Digital_Accelerometer_3.png){ loading=lazy }

### **Use with Mbits-Button** 

**Description**  
There are two buttons on the Mbits, called button\_A and button\_B.


**Usage**

The following sketch demonstrates a simple application of the module. 1.Connect the data cable to the communication port of Mbits.

2.Open the software and upload the following program to Mbits.

① Letscode Mode

![Mbits-Button.png](https://wiki.elecrow.com/images/b/ba/Mbits-Button.png){ loading=lazy }

② Code Mode

```
// Language ArduinoC
#include <FastLED.h>
#include "Dots5x5font.h"
#define NUM_ROWS 5
#define NUM_COLUMNS 5
#define NUM_LEDS (NUM_ROWS * NUM_COLUMNS)
#define LED_PIN 13
#define LED_TYPE WS2812B
#define COLOR_ORDER GRB
#include <Button.h>

CRGBArray<NUM_LEDS> leds;
uint8_t max_bright =10;
CRGB myRGBcolor_r32m(255, 0, 0);
const uint8_t maxBitmap_r32m[]= {
  B11111,B11111,B11111,B11111,B11111
};
CRGB myRGBcolor_rzbc(0, 255, 93);
const uint8_t maxBitmap_rzbc[]= {
  B11111,B11111,B11111,B11111,B11111
};

void Display(const byte dat[],CRGB myRGBcolor){
  for (int c = 0; c < 5; c++){
    for (int r = 0; r < 5; r++){
      if (bitRead(dat[c], r)){
        leds[c * 5 + 4-r] = myRGBcolor;
      }
      FastLED.show();
      delay(5);
    }
  }
}

void setup() {
  FastLED.addLeds<LED_TYPE, LED_PIN, COLOR_ORDER>(leds, NUM_LEDS);
  FastLED.setBrightness(max_bright);
}

void loop() {
  if (buttonA.isPressed() && !buttonB.isPressed()) {
    Display(maxBitmap_r32m,myRGBcolor_r32m);
  }
  if (buttonB.isPressed() && !buttonA.isPressed()) {
    Display(maxBitmap_rzbc,myRGBcolor_rzbc);
  }
  if (buttonAB.isPressed()) {
    FastLED.clear();
  }
}
```

3.After the upload is successful, you can see When the button a is pressed, the matrix will be red, when the button B is pressed, the matrix will be green, and when the buttons a and B are pressed at the same time, the matrix will not be displayed.

### **Use with Mbits-Buzzer** 

**Description**  
This is the buzzer module on Mbits, You can use it to play simple tunes. At present, the buzzer can only play one tone.


**Usage**  
The following sketch demonstrates a simple application of the module.

1.Connect the data cable to the communication port of Mbits.

2.Open the software and upload the following program to Mbits.

① Letscode Mode

![Mbits-Buzzer.png](https://wiki.elecrow.com/images/3/3c/Mbits-Buzzer.png){ loading=lazy }

② Code Mode

```
// Language ArduinoC
#include <Tone32.h>
#define BUZZER_PIN 33
#define BUZZER_CHANNEL 0

void setup() {
}

void loop() {
  tone(BUZZER_PIN, NOTE_C4, 500, BUZZER_CHANNEL);
  tone(BUZZER_PIN, NOTE_D4, 500, BUZZER_CHANNEL);
  tone(BUZZER_PIN, NOTE_E4, 500, BUZZER_CHANNEL);
  tone(BUZZER_PIN, NOTE_F4, 500, BUZZER_CHANNEL);
  tone(BUZZER_PIN, NOTE_G4, 500, BUZZER_CHANNEL);
  tone(BUZZER_PIN, NOTE_A4, 500, BUZZER_CHANNEL);
  tone(BUZZER_PIN, NOTE_B4, 500, BUZZER_CHANNEL);
}
```

3.After the upload is successful, you can hear the buzzer on Mbits repeats the sound of seven notes of “Do Re Mi FA So La Si”.

### **Use with Mbits-Microphone** 

**Description**  
This is the microphone module on Mbits, which is a low-power, omnidirectional microphone with an analog output. Normally, the analog value of the microphone varies from 1800 to 1900. When sound is detected, the analog value will decrease.


**Usage**  
Here we show a simple application of the module.

1.Connect the data cable to the communication port of Mbits.

2.Open the software and upload the following program to Mbits.

① Letscode Mode

![Mbits-Microphone.png](https://wiki.elecrow.com/images/c/c7/Mbits-Microphone.png){ loading=lazy }

② Code Mode

```
// Language ArduinoC
#include <FastLED.h>
#include "Dots5x5font.h"
#define NUM_ROWS 5
#define NUM_COLUMNS 5
#define NUM_LEDS (NUM_ROWS * NUM_COLUMNS)
#define LED_PIN 13
#define LED_TYPE WS2812B
#define COLOR_ORDER GRB

CRGBArray<NUM_LEDS> leds;
uint8_t max_bright =10;
CRGB myRGBcolor_zyvx(255, 0, 0);
const uint8_t maxBitmap_zyvx[]= {
  B00000,B11011,B00000,B10001,B01110
};
CRGB myRGBcolor_x6aa(16, 255, 0);
const uint8_t maxBitmap_x6aa[]= {
  B00000,B11011,B00000,B10001,B01110
};

void Display(const byte dat[],CRGB myRGBcolor){
  for (int c = 0; c < 5; c++){
    for (int r = 0; r < 5; r++){
      if (bitRead(dat[c], r)){
        leds[c * 5 + 4-r] = myRGBcolor;
      }
      FastLED.show();
      delay(5);
    }
  }
}

void setup() {
  FastLED.addLeds<LED_TYPE, LED_PIN, COLOR_ORDER>(leds, NUM_LEDS);
  FastLED.setBrightness(max_bright);
}

void loop() {
  if ((analogRead(35)) < 1700) {
    Display(maxBitmap_zyvx,myRGBcolor_zyvx);
  } else {
    Display(maxBitmap_x6aa,myRGBcolor_x6aa);
  }
}
```

3.After the upload is successful, You can see that the matrix is normally green and briefly red after high fives.

### **Use with Mbits-RGB Matrix** 

**Description**  
The RGB Matrix module is an 5\*5 matrix display module composed of 25 rgb led lamp beads. It can respond to changes in input signals in monochrome, full-color, gradual, and horse racing modes, and can also display simple graphics.


**Usage**  
The following sketch demonstrates several simple applications of the module.


**\*Text display**
1.Connect the data cable to the communication port of Mbits.

2.Open the software and upload the following program to Mbits.

① Letscode Mode

![Mbits-RGB Matrix 1.png](https://wiki.elecrow.com/images/b/bf/Mbits-RGB_Matrix_1.png){ loading=lazy }

② Code Mode

```
// Language ArduinoC
#include <FastLED.h>
#include "Dots5x5font.h"
#define NUM_ROWS 5
#define NUM_COLUMNS 5
#define NUM_LEDS (NUM_ROWS * NUM_COLUMNS)
#define LED_PIN 13
#define LED_TYPE WS2812B
#define COLOR_ORDER GRB

CRGBArray<NUM_LEDS> leds;
uint8_t max_bright =10;
CRGB myRGBcolor_adx5(255, 0, 0);

void plotMatrixChar(CRGB (*matrix)[5], CRGB myRGBcolor, int x, char character, int width, int height){
  int y = 0;
  if (width > 0 && height > 0){
    int charIndex = (int)character - 32;
    int xBitsToProcess = width;
    for (int i = 0; i < height; i++){
      byte fontLine = FontData[charIndex][i];
      for (int bitCount = 0; bitCount < xBitsToProcess; bitCount++){
        CRGB pixelColour = CRGB(0, 0, 0);
        if (fontLine & 0b10000000){
          pixelColour = myRGBcolor;
        }
        fontLine = fontLine << 1;
        int xpos = x + bitCount;
        int ypos = y + i;
        if (xpos < 0 || xpos > 10 || ypos < 0 || ypos > 5);
        else{
          matrix[xpos][ypos] = pixelColour;
        }
      }
    }
  }
}
void ShowString(String sMessage){
  CRGB matrixBackColor[10][5];
  int mapLED[] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23,24};
  int messageLength = sMessage.length();
  for (int x = 0; x < messageLength; x++){
    char myChar = sMessage[x];
    plotMatrixChar(matrixBackColor, myRGBcolor_adx5, 0 , myChar, 5, 5);
    for (int sft = 0; sft <= 5; sft++){
      for (int x = 0; x < NUM_COLUMNS; x++){
        for (int y = 0; y < 5; y++){
          int stripIdx = mapLED[y * 5 + x];
          if (x + sft < 5){
            leds[stripIdx] = matrixBackColor[x + sft][y];
          }else{
            leds[stripIdx] = CRGB(0, 0, 0);
          }
        }
      }
      FastLED.show();
      if (sft == 0){
        FastLED.delay(200);
      }else{
        FastLED.delay(30);
      }
    }
  }
}

void setup() {
  FastLED.addLeds<LED_TYPE, LED_PIN, COLOR_ORDER>(leds, NUM_LEDS);
  FastLED.setBrightness(max_bright);
}

void loop() {
  ShowString("Letscode");
}
```

3.After the upload is successful, you can see several letters of “letscode” are displayed quickly.


**\*DIY Images**

1.Connect the data cable to the communication port of Mbits . 2.Open the software and upload the following program to Mbits.

① Letscode Mode

![Mbits-RGB Matrix 2.png](https://wiki.elecrow.com/images/2/21/Mbits-RGB_Matrix_2.png){ loading=lazy }

② Code Mode

```
// Language ArduinoC
#include <FastLED.h>
#include "Dots5x5font.h"
#define NUM_ROWS 5
#define NUM_COLUMNS 5
#define NUM_LEDS (NUM_ROWS * NUM_COLUMNS)
#define LED_PIN 13
#define LED_TYPE WS2812B
#define COLOR_ORDER GRB

CRGBArray<NUM_LEDS> leds;
uint8_t max_bright =10;
CRGB myRGBcolor_uh2h(255, 0, 0);
const uint8_t maxBitmap_uh2h[]= {
  B00100,B01110,B11111,B10001,B11111
};

void Display(const byte dat[],CRGB myRGBcolor){
  for (int c = 0; c < 5; c++){
    for (int r = 0; r < 5; r++){
      if (bitRead(dat[c], r)){
        leds[c * 5 + 4-r] = myRGBcolor;
      }
      FastLED.show();
      delay(5);
    }
  }
}

void setup() {
  FastLED.addLeds<LED_TYPE, LED_PIN, COLOR_ORDER>(leds, NUM_LEDS);
  FastLED.setBrightness(max_bright);
}

void loop() {
  Display(maxBitmap_uh2h,myRGBcolor_uh2h);
}
```

3.After the upload is successful, you can see the red windmill pattern in the center of the matrix.You can also change red to other colors.


**\*Dynamic Image**

1.Connect the data cable to the communication port of Mbits.

2.Open the software and upload the following program to Mbits.

① Letscode Mode

![Mbits-RGB Matrix 3.png](https://wiki.elecrow.com/images/3/38/Mbits-RGB_Matrix_3.png){ loading=lazy }

② Code Mode

```
// Language ArduinoC
#include <FastLED.h>
#include "Dots5x5font.h"
#define NUM_ROWS 5
#define NUM_COLUMNS 5
#define NUM_LEDS (NUM_ROWS * NUM_COLUMNS)
#define LED_PIN 13
#define LED_TYPE WS2812B
#define COLOR_ORDER GRB

CRGBArray<NUM_LEDS> leds;
uint8_t max_bright =10;
CRGB myRGBcolor_g00e(255, 0, 0);
const uint8_t maxBitmap_g00e[]= {
  B10000,B10000,B10000,B10000,B10000
};
CRGB myRGBcolor_4m3g(250, 255, 0);
const uint8_t maxBitmap_4m3g[]= {
  B01000,B01000,B01000,B01000,B01000
};
CRGB myRGBcolor_kqbq(0, 119, 255);
const uint8_t maxBitmap_kqbq[]= {
  B00100,B00100,B00100,B00100,B00100
};
CRGB myRGBcolor_a8c4(0, 255, 119);
const uint8_t maxBitmap_a8c4[]= {
  B00010,B00010,B00010,B00010,B00010
};
CRGB myRGBcolor_e6v8(199, 0, 255);
const uint8_t maxBitmap_e6v8[]= {
  B00001,B00001,B00001,B00001,B00001
};

void Display(const byte dat[],CRGB myRGBcolor){
  for (int c = 0; c < 5; c++){
    for (int r = 0; r < 5; r++){
      if (bitRead(dat[c], r)){
        leds[c * 5 + 4-r] = myRGBcolor;
      }
      FastLED.show();
      delay(5);
    }
  }
}

void setup() {
  FastLED.addLeds<LED_TYPE, LED_PIN, COLOR_ORDER>(leds, NUM_LEDS);
  FastLED.setBrightness(max_bright);
}

void loop() {
  Display(maxBitmap_g00e,myRGBcolor_g00e);
  delay(500);
  Display(maxBitmap_4m3g,myRGBcolor_4m3g);
  delay(500);
  Display(maxBitmap_kqbq,myRGBcolor_kqbq);
  delay(500);
  Display(maxBitmap_a8c4,myRGBcolor_a8c4);
  delay(500);
  Display(maxBitmap_e6v8,myRGBcolor_e6v8);
  delay(500);
  FastLED.clear();
}
```

3.After the upload is successful, you can see the center of the matrix from left to right showing red, yellow, blue, green and purple alternately.

### **Use with Mbits-Temperature Sensor** 

**Description**  
This is the temperature sensor on Mbits, The module can detect the temperature of the surrounding environment in real-time. Normally, the temperature value detected by the temperature sensor is 31 degrees.


**Usage**

Here we show a simple application of the module.

1.Connect the data cable to the communication port of Mbits.

2.Open the software and upload the following program to Mbits.

① Letscode Mode

![Mbits-Temperature Sensor.png](https://wiki.elecrow.com/images/e/e7/Mbits-Temperature_Sensor.png){ loading=lazy }

② Code Mode

```
// Language ArduinoC
#include<Wire.h>
#include <tmp75.h>
#include <Tone32.h>
#define BUZZER_PIN 33
#define BUZZER_CHANNEL 0

TMP75 Tmp75Sensor;

void setup() {
  Wire.begin(22,21);
  Tmp75Sensor.begin();
}

void loop() {
  if ((Tmp75Sensor.readTemperature()) > 35) {
    tone(BUZZER_PIN, NOTE_C4, 500, BUZZER_CHANNEL);
    tone(BUZZER_PIN, NOTE_D4, 500, BUZZER_CHANNEL);
  } else {
    noTone(BUZZER_PIN, BUZZER_CHANNEL);
  }
}
```

3.After the upload is successful,You can try to raise the temperature to 35 degrees, and you'll hear the buzzer making a beeping noise.

## **Use on Arduino**
------------------

- **Part 1. Setting up the programming environment**

1：Download and install the latest version of Arduino IDE, Windows Installer from [https://www.arduino.cc/en/software](https://www.arduino.cc/en/software)

2：Add ESP32 development board data in Arduino IDE

a)ClickFile -&gt;Preferences-&gt;Additional boards manager URLs

b)Add the following URLs:  
[https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package\_esp32\_dev\_index.json](https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_dev_index.json)   
[https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package\_esp32\_index.json](https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json)

c)ClickTools -&gt;Board -&gt;Board Manager. Search for esp,find esp32, and click Install.

d)Click"Tools"-&gt;"Board"-&gt;"ESP32 Arduino", select "**ESP32-Wrover Module**"; Click "Port", select the corresponding com port

![Tools.png](https://wiki.elecrow.com/images/thumb/c/c5/Tools.png/700px-Tools.png){ loading=lazy }

- **Part 2: Some examples**

1.5\*5 RGB dot matrix and buttons

The 5\*5RGB dot matrix is controlled by GPIO13, Button A is controlled by GPIO36, and Button B is controlled by GPIO39.

a)Download [RGB\_Demo](../../files/RGB-Demo-zip.md), firstly unzip RGB\_Demo.zip, then unzip [Button.zip](../../files/Button-zip.md), [FastLED-master.zip](https://wiki.elecrow.com/images/1/13/FastLED-master.zip), [RGB\_Font](https://wiki.elecrow.com/images/c/c0/RGB_Font.zip) and RGB\_Test.zip.  
![20221205151822.png](https://wiki.elecrow.com/images/c/c2/20221205151822.png){ loading=lazy }


b)Copy the following three library files (Button, FastLED-master, RGB\_Font) to the libraries under the Arduino installation directory;
![20221205151135.png](https://wiki.elecrow.com/images/thumb/3/30/20221205151135.png/600px-20221205151135.png){ loading=lazy }


c)Upload the following program (RGB\_Test) to the Mbits board;

```
 #include <FastLED.h>
#include "Dots5x5font.h"
#define NUM_ROWS 5
#define NUM_COLUMNS 5
#define NUM_LEDS (NUM_ROWS * NUM_COLUMNS)
#define LED_PIN 13
#define LED_TYPE WS2812B
#define COLOR_ORDER GRB
#include <Button.h>

CRGBArray<NUM_LEDS> leds;
uint8_t max_bright = 10;
CRGB myRGBcolor_uijf(0, 255, 21);
CRGB myRGBcolor_28dt(34, 0, 255);

void plotMatrixChar(CRGB (*matrix)[5], CRGB myRGBcolor, int x, char character, int width, int height) {
  int y = 0;
  if (width > 0 && height > 0) {
    int charIndex = (int)character - 32;
    int xBitsToProcess = width;
    for (int i = 0; i < height; i++) {
      byte fontLine = FontData[charIndex][i];
      for (int bitCount = 0; bitCount < xBitsToProcess; bitCount++) {
        CRGB pixelColour = CRGB(0, 0, 0);
        if (fontLine & 0b10000000) {
          pixelColour = myRGBcolor;
        }
        fontLine = fontLine << 1;
        int xpos = x + bitCount;
        int ypos = y + i;
        if (xpos < 0 || xpos > 10 || ypos < 0 || ypos > 5);
        else {
          matrix[xpos][ypos] = pixelColour;
        }
      }
    }
  }
}

void ShowString(String sMessage,CRGB myRGBcolor) {
  CRGB matrixBackColor[10][5];
  int mapLED[] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24};
  int messageLength = sMessage.length();
  for (int x = 0; x < messageLength; x++) {
    char myChar = sMessage[x];
    plotMatrixChar(matrixBackColor, myRGBcolor, 0 , myChar, 5, 5);
    for (int sft = 0; sft <= 5; sft++) {
      for (int x = 0; x < NUM_COLUMNS; x++) {
        for (int y = 0; y < 5; y++) {
          int stripIdx = mapLED[y * 5 + x];
          if (x + sft < 5) {
            leds[stripIdx] = matrixBackColor[x + sft][y];
          } else {
            leds[stripIdx] = CRGB(0, 0, 0);
          }
        }
      }
      FastLED.show();
      if (sft == 0) {
        FastLED.delay(200);
      } else {
        FastLED.delay(30);
      }
    }
  }
}


void setup() {
  FastLED.addLeds<LED_TYPE, LED_PIN, COLOR_ORDER>(leds, NUM_LEDS);
  FastLED.setBrightness(max_bright);
}

void loop() {
  if (buttonA.isPressed() && !buttonB.isPressed()) {
    ShowString("welcome",myRGBcolor_uijf);
  }
  if (buttonB.isPressed() && !buttonA.isPressed()) {
    ShowString("elecrow",myRGBcolor_28dt);
  }
}
```


d)After the program is downloaded, press the Button A, the RGB dot matrix will scroll the words "WELCOME", and press the Button B to scroll the words "ELECROW";；

![Mbits (2).png](https://wiki.elecrow.com/images/thumb/3/31/Mbits_%282%29.png/300px-Mbits_%282%29.png){ loading=lazy }
![Mbits (3).png](https://wiki.elecrow.com/images/thumb/6/6f/Mbits_%283%29.png/300px-Mbits_%283%29.png){ loading=lazy }


2.Temperature sensor

d)Copy the library files of [TMP75](https://wiki.elecrow.com/images/d/da/TMP75.zip) to the libraries directory under the Arduino installation directory;

e)Click "File→Examples→TMP75→simpleTMP75.ino" to open the corresponding program file and download it to the Mbits board;

f)The sample code is as follows:：

```
#include<Wire.h>
#include <tmp75.h>

#define T_LOW 24.8
#define T_HIGH 25.0125

TMP75 mySensor; // mySensor at default i2c address

void setup(){
  Wire.begin(22,21); // initialize i2c library
  Serial.begin(9600);
  int error=mySensor.begin();
  if (error) {
    Serial.println("TMP75 not responding...");
    while(1);
  }
 // ALERT pin should be low if temperature is above T_HIGH
 // and should return to high when temperature is below T_LOW
 mySensor.setHighLimit(T_HIGH);
 mySensor.setLowLimit(T_LOW);
  
}

void loop(){
  float temp = mySensor.readTemperature();
  Serial.print("Temp = ");
  Serial.print(temp,4); // 4 decimals to see full 12 bits resolution
  Serial.println(" Celsius");
  delay(500);
  
}
```

g)After the program is downloaded, open the serial port monitor, set the baud rate to 9600, and the serial port will print out the currently detected temperature value estimate, as shown in the figure:

![Mbits (4).png](https://wiki.elecrow.com/images/thumb/6/69/Mbits_%284%29.png/700px-Mbits_%284%29.png){ loading=lazy }

3.Buzzer

The passive buzzer is connected to the GPIO33 pin by default, and we can output PWM waves on this pin to drive the buzzer.

The following code is an example of playing a song:

```
int speakerPin = 33; 

int length = 15; // the number of notes 
char notes[] = "ccggaagffeeddc "; // a space represents a rest 
int beats[] = { 1, 1, 1, 1, 1, 1, 2, 1, 1, 1, 1, 1, 1, 2, 4 }; 
int tempo = 300; 

void playTone(int tone, int duration) { 
  for (long i = 0; i < duration * 1000L; i += tone * 2) { 
    digitalWrite(speakerPin, HIGH); 
    delayMicroseconds(tone); 
    digitalWrite(speakerPin, LOW); 
    delayMicroseconds(tone); 
  } 
} 

void playNote(char note, int duration) { 
  char names[] = { 'c', 'd', 'e', 'f', 'g', 'a', 'b', 'C' }; 
  int tones[] = { 1915, 1700, 1519, 1432, 1275, 1136, 1014, 956 }; 

  // play the tone corresponding to the note name 
  for (int i = 0; i < 8; i++) { 
    if (names[i] == note) { 
      playTone(tones[i], duration); 
    } 
  } 
} 

void setup() { 
  pinMode(speakerPin, OUTPUT); 
} 

void loop() { 
  for (int i = 0; i < length; i++) { 
    if (notes[i] == ' ') { 
      delay(beats[i] * tempo); // rest 
    } else { 
      playNote(notes[i], beats[i] * tempo); 
    } 

    // pause between notes 
    delay(tempo / 2);  
  } 
}
```

g)After the program is downloaded, open the serial port monitor, set the baud rate to 9600, and the serial port will print out the currently detected temperature value estimate, as shown in the figure:

After the program is downloaded successfully, you can hear the beautiful tune.

## **Resources**
-------------

[Arduino program](https://wiki.elecrow.com/images/5/54/Arduino_program.zip)   
[Mbits-V1.1-20210420-01.pdf](https://wiki.elecrow.com/images/f/f4/Mbits-V1.1-20210420-01.pdf)  
[Mbits-V1.2-20210713-01.pdf](https://wiki.elecrow.com/images/d/d7/Mbits-V1.2-20210713-01.pdf)  

Please feel free to ask questions here. [https://forum.elecrow.com/discussions](https://forum.elecrow.com/discussions)