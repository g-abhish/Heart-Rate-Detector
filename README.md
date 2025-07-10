# Heart-Rate-Detector
Arduino-based Heart Rate &amp; SpO2 Monitor using MAX30102 and SSD1306 OLED. Displays pulse waveform, pulse rate, oxygen saturation (SpO2), and stores user settings in EEPROM. Features waveform filtering, sleep mode, and button-controlled display options.

# 💓 Arduino Heart Rate & SpO2 Monitor

This project implements a **compact heart rate and SpO2 (oxygen saturation) monitor** using an Arduino-compatible board, a **MAX30102** pulse oximeter sensor, and an **SSD1306 OLED** display.

## 🛠️ Features

- 📈 Real-time display of:
  - Heart rate (BPM)
  - Blood oxygen level (SpO2 %)
  - PPG waveform (IR/Red LED)
- 🧠 Signal filtering (DC removal + moving average)
- 💾 EEPROM storage for user preferences
- 💤 Sleep mode after inactivity
- 🔘 Button-controlled display options

## 🖥️ Hardware Required

| Component           | Description                       |
|---------------------|-----------------------------------|
| Arduino (Uno/Nano)  | 8-bit AVR microcontroller         |
| MAX30102 Sensor     | Pulse oximeter & heart-rate sensor |
| SSD1306 OLED Display| 128x64 I2C OLED display            |
| Push Button         | For user input (GPIO 3 used)       |
| Resistors & Wires   | Basic components for connection    |

## 📋 Pin Connections

| Component   | Arduino Pin |
|-------------|-------------|
| MAX30102 SDA | A4          |
| MAX30102 SCL | A5          |
| OLED SDA     | A4          |
| OLED SCL     | A5          |
| Button       | D3          |
| LED Output   | LED_BUILTIN |

> Ensure I2C addresses for MAX30102 and SSD1306 do not conflict.

## 📷 UI Screens

- **Pulse & SpO2 screen**
- **Waveform display**
- **"Place Finger" prompt**
- **Sleep countdown screen**
- **Avg Pulse and SpO2 summary**

## 🔧 Software Overview

- **Signal Processing**:
  - Filters DC offset
  - Detects heartbeat peaks
  - Calculates BPM and SpO2 using signal ratios
- **Display Handling**:
  - OLED refresh every 50ms
  - Graphics include text, waveform, symbols
- **Power Saving**:
  - Goes to sleep after ~10s inactivity

## 🔘 Button Functions

Press the button to cycle through:
1. Unfiltered IR waveform
2. Filtered IR waveform
3. Unfiltered RED waveform
4. Filtered RED waveform

## 💾 EEPROM Usage

| Address | Purpose              |
|---------|----------------------|
| `0x07`  | Filter setting        |
| `0x08`  | Red/IR waveform toggle|

## 💡 Setup Instructions

1. Connect all hardware components.
2. Install Arduino libraries:
   - `Adafruit_GFX`
   - `Adafruit_SSD1306`
   - `Wire.h`
3. Flash the code to your Arduino.
4. Place your finger on the MAX30102 sensor.

### ❤️ Built for learning biomedical signal processing and embedded system development.
