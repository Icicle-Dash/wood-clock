# Wood Clock - Custom LED Matrix Alarm Clock

A custom PCB alarm clock with WS2812B LED matrix display, built for Hack Club Stasis.

**Selected Microcontroller:** Seeed Studio XIAO ESP32-C3 (WiFi + Bluetooth, 400KB RAM, 4MB Flash)

## 🎯 Project Overview

Pre-assembled WS2812B LED matrix + custom PCB motherboard = beautiful, functional alarm clock

## 📋 Bill of Materials

### Core Components
- **Seeed Studio XIAO ESP32-C3** - Main microcontroller
- **WS2812B LED Matrix Panel** - Pre-assembled from AliExpress (8x8 or 16x16)
- **DS3231 RTC Module** - High-accuracy real-time clock with battery backup

### Interface Components
- **74AHCT125N Level Shifter** - 3.3V→5V for LED data line
- **470Ω Resistor** - Data line smoothing
- **10kΩ Resistors (3-4)** - Pull-up for buttons
- **Tactile Buttons (3-4)** - Time set, alarm set, toggle, snooze
- **2N2222 Transistor** - Buzzer driver
- **Active Buzzer** - Alarm sound

### Power & Support
- **1000µF Capacitor** - Power filtering for LEDs
- **100nF Capacitors (2-3)** - Decoupling
- **USB-C Connector** - Power and programming
- **3-Pin JST Connector** - LED panel connection
- **CR2032 Battery** - RTC backup

## 🔌 Component Functions

**XIAO ESP32-C3** - Runs code, WiFi time sync, manages everything
**DS3231 RTC** - Keeps perfect time even when power is lost
**Level Shifter** - Boosts 3.3V signal to 5V for reliable LED control
**Buttons + Pull-ups** - User input without electrical noise
**Buzzer + Transistor** - Alarm sound amplifier
**Capacitors** - Power stability for LED current surges

## ⚡ Why ESP32-C3?

✅ **WiFi** - Automatic NTP time sync from internet
✅ **Bluetooth** - Future expansion possibilities  
✅ **More memory** - 400KB RAM for smooth LED animations
✅ **Lower cost** - Generally cheaper than RP2040 boards

## 🛠️ Action Plan

1. **Pin Assignment** - Map XIAO pins to functions
2. **Schematic Design** - Create circuit in KiCad/EasyEDA
3. **PCB Layout** - Design custom motherboard
4. **Order Parts** - LED panel, PCB fabrication, components
5. **Assembly** - Solder and test electronics
6. **Programming** - WiFi time sync, LED control, alarm logic
7. **Enclosure** - 3D print case and final assembly

## 📐 Key Design Notes

- **Power:** 8x8 matrix needs up to 3.84A, design traces accordingly
- **Level Shifter Critical:** 3.3V to 5V data conversion prevents LED flickering
- **Keep Data Line Short:** Between PCB and LED panel
- **WiFi + RTC Hybrid:** WiFi for sync, RTC for backup

## 🚀 Getting Started

1. Choose LED matrix size (8x8 simpler, 16x16 more impressive)
2. Assign XIAO pins to functions
3. Create schematic in KiCad/EasyEDA
4. Order components and PCB fabrication

---

## XIAO Board Comparison (Reference)

| Attribute | XIAO nRF52840 BLE | XIAO ESP32-C3 | XIAO nRF52840 Plus |
|----------|------------------|--------------|-------------------|
| **MCU** | Nordic nRF52840 | Espressif ESP32-C3 (RISC-V) | Nordic nRF52840 |
| **CPU** | ARM Cortex-M4 @ 64 MHz | RISC-V @ 160 MHz | ARM Cortex-M4 @ 64 MHz |
| **Wireless** | BLE 5.4, Mesh, NFC | Wi-Fi (2.4GHz) + BLE 5.0 | BLE 5.4, Mesh, NFC |
| **Wi-Fi** | ❌ | ✅ | ❌ |
| **Bluetooth** | ✅ | ✅ | ✅ |
| **NFC** | ✅ | ❌ | ✅ |
| **RAM** | 256 KB | 400 KB | 256 KB |
| **Flash** | 1 MB | 4 MB | 1 MB |
| **GPIO Pins** | ~11 | ~11 | ~20 |
| **Power Efficiency** | ⭐⭐⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐⭐ |
| **Battery Use** | Excellent | Moderate | Excellent |
| **Best For** | Wearables, BLE devices | IoT + cloud/Wi-Fi | Sensor-heavy builds |
| **Cost** | Higher | Lowest | Mid |

### Quick Takeaway
- **Low power BLE:** nRF52840 BLE  
- **Wi-Fi projects:** ESP32-C3 ✅ **(Our Choice)**
- **More pins:** nRF52840 Plus  
