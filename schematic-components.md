# KiCad Schematic Components - Wood Clock Project

## 🔧 Components to Place

### Main Controller
- **XIAO ESP32-C3** (Module)
  - Pins needed: GPIO3-10, 3.3V, 5V, GND

### Power Supply
- **USB-C Connector** (USB Type-C receptacle)
- **1000µF Capacitor** (Electrolytic, across 5V/GND)
- **100nF Capacitors** (3x, ceramic, decoupling near ICs)

### Timekeeping
- **DS3231 RTC Chip** (SOIC-8 package)
- **CR2032 Battery Holder** (Coin cell holder)

### LED Interface
- **74AHCT125N Level Shifter** (DIP-14 or SOIC-14)
- **470Ω Resistor** (Through-hole or SMD)
- **3-Pin JST Connector** (JST-XH or similar)

### User Interface
- **Tactile Buttons** (4x, 6mm or 12mm)
- **10kΩ Resistors** (4x, pull-ups for buttons)

### Alarm System
- **Active Buzzer** (12mm or similar)
- **2N2222 Transistor** (TO-92 package)
- **1kΩ Resistor** (Transistor base)

### Connectors
- **Test Points** (Optional, for debugging)

---

## ⚡ Power Symbols

- **VCC** (5V power rail)
- **3.3V** (3.3V power rail)
- **GND** (Ground symbols, place near each component group)

---

## 🏷️ Net Labels/Signal Names

### I2C Bus (DS3231)
- `I2C_SDA`
- `I2C_SCL`

### LED Control
- `LED_DATA_3V3` (From XIAO)
- `LED_DATA_5V` (To LED panel)

### Button Inputs
- `BTN_TIME_SET`
- `BTN_ALARM_SET`
- `BTN_ALARM_TOGGLE`
- `BTN_SNOOZE`

### Buzzer Control
- `BUZZER_CTRL`

### Power
- `5V`
- `3V3`
- `GND`

---

## 🔌 Pin Assignments (XIAO ESP32-C3)

| GPIO | Function | Connection |
|------|----------|------------|
| GPIO3 | I2C SDA | DS3231 SDA |
| GPIO4 | I2C SCL | DS3231 SCL |
| GPIO5 | LED Data | Level shifter input |
| GPIO6 | Button 1 | Time Set button |
| GPIO7 | Button 2 | Alarm Set button |
| GPIO8 | Button 3 | Alarm Toggle button |
| GPIO9 | Button 4 | Snooze button |
| GPIO10 | Buzzer | Transistor base via 1kΩ resistor |

---

## 📐 Notes



### Level Shifter (74AHCT125N)
- Channel 1: LED data line conversion (3.3V → 5V)
- Unused channels: Ground inputs and enable pins

### DS3231 RTC
- SOIC-8 package recommended
- 32.768kHz crystal not needed (built into DS3231)
- Pull-up resistors (4.7kΩ) on SDA/SCL lines

### Power Considerations
- USB-C provides 5V power
- XIAO has built-in 3.3V regulator
- 1000µF capacitor handles LED current surges
- Separate 5V and 3.3V power planes recommended

---

## 🎯 Schematic Order

1. Place XIAO ESP32-C3 module (center)
2. Place power components (USB-C, capacitors)
3. Place DS3231 RTC
4. Place level shifter and LED connector
5. Place buttons and pull-up resistors
6. Place buzzer circuit
7. Add power symbols
8. Make wire connections
9. Add net labels
10. Verify all connections

---

## 📚 Component References

- **XIAO ESP32-C3 Datasheet:** Seeed Studio website
- **DS3231 Datasheet:** Maxim Integrated
- **74AHCT125N Datasheet:** Texas Instruments/NXP
- **WS2812B Datasheet:** WorldSemi

---

## ✅ Completion Checklist

- [ ] All components placed
- [ ] Power symbols added
- [ ] Wire connections made
- [ ] Net labels applied
- [ ] Pin assignments verified
- [ ] Power routing checked
- [ ] No unconnected pins (except intentional)
- [ ] Electrical rules check (ERC) passed
