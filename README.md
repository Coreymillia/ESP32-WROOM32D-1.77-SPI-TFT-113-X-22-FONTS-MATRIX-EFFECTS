# ESP32 WROOM-32D Matrix Rain Display

A stunning 113-effect Matrix-style digital rain screensaver running on ESP32 WROOM-32D with ST7735 TFT display and capacitive touch control.

![Matrix Effects Demo](https://img.shields.io/badge/Effects-113-brightgreen) ![Platform](https://img.shields.io/badge/Platform-ESP32-blue) ![Display](https://img.shields.io/badge/Display-ST7735-orange)

## ✨ Features

- **113 Different Matrix Effects** including:
  - Classic Matrix Rain (multiple variants)
  - Digital Waterfalls
  - Code Streams
  - Binary Cascades
  - Glitch Effects
  - 3D Matrix Tunnel
  - And 107+ more stunning effects!

- **Capacitive Touch Control** - TTP223B touch sensor
- **Auto-scroll Mode** - cycles through effects automatically
- **Boot Button Control** - backwards navigation
- **Multiple Font Support** - various cyberpunk-style fonts
- **Optimized Performance** - smooth 160x128 display rendering

## 🔧 Hardware Requirements

### Components
- ESP32 WROOM-32D Development Board
- 1.77" ST7735 TFT Display (128x160)
- TTP223B Capacitive Touch Sensor

### Wiring Diagram

```
ST7735 TFT Display:
┌─────────────────┬─────────────────────┐
│ ST7735 Pin      │ ESP32 WROOM-32D Pin │
├─────────────────┼─────────────────────┤
│ VCC             │ 5V                │
│ GND             │ GND                 │
│ CS              │ GPIO 5              │
│ RST             │ GPIO 4              │
│ DC/A0           │ GPIO 2              │
│ SDA/MOSI        │ GPIO 23 (VSPI_MOSI) │
│ SCK/CLK         │ GPIO 18 (VSPI_SCK)  │
│ LED/BL          │ 3.3V (always on)    │
└─────────────────┴─────────────────────┘

TTP223B Touch Sensor:
┌─────────────────┬─────────────────────┐
│ TTP223B Pin     │ ESP32 Pin           │
├─────────────────┼─────────────────────┤
│ VCC             │ 3.3V                │
│ GND             │ GND                 │
│ I/O             │ GPIO 15             │
└─────────────────┴─────────────────────┘
```

## 🎮 Controls

- **Quick Touch** (< 2 seconds): Cycle through matrix effects
- **Long Touch** (2+ seconds): Toggle auto-scroll mode ON/OFF
- **Boot Button** (GPIO 0): Navigate backwards through effects

## 🚀 Getting Started

### Prerequisites
- [PlatformIO](https://platformio.org/) installed
- ESP32 development environment set up

### Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/esp32-matrix-display.git
cd esp32-matrix-display
```

2. Wire up your hardware according to the wiring diagram above

3. Build and upload:
```bash
pio run --target upload
```

4. Monitor serial output (optional):
```bash
pio device monitor --baud 115200
```

## 📋 Project Structure

```
├── src/
│   └── main.cpp          # Main application code
├── include/              # Header files (if any)
├── lib/                  # Custom libraries
├── platformio.ini        # PlatformIO configuration
├── WIRING_GUIDE.md      # Detailed wiring instructions
└── README.md            # This file
```

## 🎨 Matrix Effects Categories

The 113 effects include:
- **Classic Rain Effects** (0-20): Traditional Matrix digital rain
- **Waterfall Variants** (21-35): Cascading digital streams
- **Binary Displays** (36-50): Binary code rain patterns
- **Glitch Effects** (51-65): Digital corruption visuals
- **3D Tunnel** (66-80): Immersive tunnel effects
- **Code Streams** (81-95): Programming language rain
- **Custom Variants** (96-112): Unique artistic interpretations

## ⚙️ Configuration

### Auto-scroll Timing
Default: 30 seconds per effect. Modify `autoSwitchInterval` in `main.cpp`:
```cpp
const unsigned long autoSwitchInterval = 30000; // 30 seconds
```

### Touch Sensitivity
Adjust long press duration in `main.cpp`:
```cpp
const unsigned long longPressTime = 2000; // 2 seconds
```

## 🔧 Customization

### Adding New Effects
1. Add your effect function to `main.cpp`
2. Update the `EffectMode` enum
3. Add the case to the main switch statement
4. Increment `TOTAL_MODES`

### Changing Colors
Matrix effects use various green shades. Modify color constants:
```cpp
#define MATRIX_GREEN 0x07E0
#define BRIGHT_GREEN 0x07FF
#define DIM_GREEN 0x0340
```

## 📊 Performance

- **RAM Usage**: ~13.7% (44,952 bytes)
- **Flash Usage**: ~31.6% (414,113 bytes)
- **Frame Rate**: Optimized for smooth scrolling
- **Power Consumption**: ~150mA @ 3.3V (display on)

## 🛠️ Troubleshooting

### Display Issues
- Check SPI wiring (SCK=18, MOSI=23)
- Verify display initialization in serial monitor
- Ensure 3.3V power supply is stable

### Touch Sensor Issues
- Verify GPIO 15 connection
- Check for proper grounding
- Monitor serial output for touch events

### No Effects Displaying
- Check display rotation setting
- Verify matrix column calculations
- Monitor serial for initialization messages

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-effect`)
3. Commit your changes (`git commit -m 'Add amazing new matrix effect'`)
4. Push to the branch (`git push origin feature/amazing-effect`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Inspired by the Matrix movie series
- Built with [Adafruit GFX Library](https://github.com/adafruit/Adafruit-GFX-Library)
- Uses [Adafruit ST7735 Library](https://github.com/adafruit/Adafruit-ST7735-Library)
- Matrix rain algorithms inspired by classic screensaver implementations

## 📸 Gallery

*Upload photos/videos of your completed project here!*

---

**Built with ❤️ for the cyberpunk aesthetic**

*"Welcome to the real world."* - Morpheus
