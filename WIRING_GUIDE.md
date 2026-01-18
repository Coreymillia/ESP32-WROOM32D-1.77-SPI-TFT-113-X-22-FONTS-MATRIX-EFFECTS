# ESP32 WROOM-32D to ST7735 1.77" TFT Matrix Display - Wiring Guide

## Components:
- ESP32 WROOM-32D Development Board
- 1.77" ST7735 TFT Display (128x160)
- TTP223B Capacitive Touch Sensor
- Breadboard/Proto board for connections

## ST7735 TFT Display Connections:
```
ST7735 Pin  →  ESP32 WROOM-32D Pin
---------------------------------
VCC         →  3.3V
GND         →  GND
CS          →  GPIO 5
RST         →  GPIO 4
DC/A0       →  GPIO 2
SDA/MOSI    →  GPIO 23 (VSPI_MOSI)
SCK/CLK     →  GPIO 18 (VSPI_SCK)
LED/BL      →  3.3V (always on) or GPIO pin for PWM control
```

## TTP223B Touch Sensor Connections:
```
TTP223B Pin  →  ESP32 Pin
-----------------------
VCC          →  3.3V
GND          →  GND
I/O          →  GPIO 15
```

## Built-in Controls:
- **Boot Button**: GPIO 0 (built-in on most ESP32 dev boards)

## Pin Summary:
- **Display CS**: GPIO 5
- **Display RST**: GPIO 4  
- **Display DC**: GPIO 2
- **Display SCK**: GPIO 18 (Hardware SPI)
- **Display MOSI**: GPIO 23 (Hardware SPI)
- **Touch Sensor**: GPIO 15
- **Boot Button**: GPIO 0 (built-in)

## Power Requirements:
- **ESP32**: 5V via USB or 3.3V regulated
- **ST7735**: 3.3V (connected to ESP32 3.3V output)
- **TTP223B**: 3.3V (connected to ESP32 3.3V output)

## Notes:
- The ESP32 WROOM-32D uses VSPI (SPI3) by default on pins 18/23
- GPIO 0 is the built-in boot button on most ESP32 development boards
- GPIO 15 is a good choice for the touch sensor (no conflicts with boot/flash)
- All components can be powered from the ESP32's 3.3V regulator
- The display LED pin can be tied to 3.3V for always-on backlight

## Controls:
- **Short Touch**: Cycle through 113 matrix effects
- **Long Touch (1s+)**: Toggle auto-scroll mode ON/OFF
- **Boot Button**: Navigate backwards through effects

## Matrix Effects Include:
- Classic Matrix Rain (multiple variants)
- Digital Waterfalls
- Code Streams
- Binary Cascades
- Glitch Effects
- 3D Matrix Tunnel
- And 107 more stunning effects!