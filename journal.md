## 🗓️ July 7, 2025 — Component Research & Selection

Today, I finalized all the main components for the Aromiq Tag.  
I decided to skip breadboard prototyping and go straight to PCB design to save time.  
Researched part availability, selected sensor modules, microcontroller, and supporting components.  
Also documented key common passives and protections needed for the power and programming circuits.

---

### Core Components Selected

| Component            | Model / Component Name | Purpose                                     | JLCPCB Part #                   |
|----------------------|------------------------|---------------------------------------------|---------------------------------|
| **MCU**              | ATtiny1626             | Main controller, low-power, small footprint | `C5227679`                      |
| **VOC Sensor**       | SGP41                  | Detect spoilage gases (e.g., ethylene)      | `C3659325`                      |
| **Temp/Humidity**    | SHTC3                  | Accurate, compact sensor                    | `C194656`                       |
| **Light Sensor**     | TEPT5700               | Detects exposure to light                   | `C141763`                       |
| **EEPROM**           | 24LC256                | External memory for storing sensor logs     | `C5458`                         |
| **NFC Chip**         | NT3H1101 (NXP)         | Enables phone-based data retrieval          | `C73156`                        |
| **Battery Holder**   | CR2032-BS-6-1          | Coin cell holder                            | `C70377`                        |
| **Battery**          | Panasonic CR2032       | Primary power source                        | [external](https://www.amazon.ca/Panasonic-CR2032-Volt-Lithium-Batteries/dp/B0829PGDQR/)        |
| **Programmer Board** | Elegoo Nano CH340      | Arduino Nano for UPDI programming           | [external](https://www.amazon.ca/ELEGOO-Pre-soldered-ATmega-Compatible-Arduino/dp/B0D5LYFRQP)   |

---

### Common Supporting Components

| Component          | Value      | Purpose                                      | JLCPCB Part #  |
|--------------------|------------|----------------------------------------------|----------------|
| Schottky Diode     | BAT54      | Prevent Nano VCC from back-powering battery  | `C191023`      |
| Capacitor (Bypass) | 100nF      | Decoupling MCU VCC/GND                       | `C14663`       |
| Capacitor (Bulk)   | 10µF       | Power smoothing                              | `C13585`       |
| Pull-up Resistor   | 4.7kΩ      | UPDI & I²C pull-up                           | `C23162`       |
| Series Resistor    | 10Ω        | Limits inrush current (optional)             | `C22962`       |
| TVS Diode          | ESD5V      | ESD protection on VCC or I/O                 | `C85364`       |
| LED (Optional)     | Red 0805   | Debug/status indicator                       | `C84256`       |
| LED Resistor       | 330Ω       | LED current limit                            | `C22984`       |
| Jumper Resistor    | 0Ω         | Optional solder bridge/jumper                | `C17168`       |
| Header (UPDI)      | 2-Pin      | Programming header                           | `C2881948`     |

---

### Programming Resource

- How to program the ATtiny using MegaTinyCore:  
  https://wolles-elektronikkiste.de/en/using-megatinycore

---

Next step: Begin schematic in KiCad and start early layout work for the PCB.
