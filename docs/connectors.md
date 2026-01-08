# Connector Pinouts

This document describes all external connectors on the Chibi-ECEN-BLDC board.

## Summary

| Connector | Type | Pin Count | Purpose |
|-----------|------|-----------|---------|
| Motor | 3-pin high current | 6 | Three-phase motor connection |
| Throttle | 3-pin | 3 | Throttle pot input (5V supply + signal) |
| Brake Throttle | 3-pin | 3 | Brake throttle input |
| Auxiliary Pot | 3-pin | 3 | Additional potentiometer input |
| E-Brake | 2-pin | 2 | Emergency brake digital input |
| Torque/PAS | 5-pin | 5 | Torque sensor and pedal assist |
| CA-DIP | 6-pin | 6 | Cycle Analyst interface |
| UART | 3-pin | 3 | Serial communication |
| Thermistor | 2-pin | 2 | External temperature sensor |
| USB | Micro-B | - | USB communication |
| JTAG | 10-pin | - | Programming and debug |

## Detailed Pinouts

### Motor Phase Connector (6-pin)

High-current connector for three-phase motor windings.

| Pin | Signal | Type | Notes |
|-----|--------|------|-------|
| 1 | Phase A | High Power | Motor winding A |
| 2 | Phase B | High Power | Motor winding B |
| 3 | Phase C | High Power | Motor winding C |
| 4 | Hall 5V | Low Power | Hall sensor supply |
| 5 | Hall GND | Low Power | Hall sensor ground |
| 6 | Hall Signals | Digital | Hall A, B, C signals |

**Wire Gauge:** 12-14 AWG for phase wires (capable of 10A continuous)

**Connector Type:** Heavy-duty terminal block or Anderson Powerpole

---

### Throttle Connector (3-pin)

Standard potentiometer throttle input.

| Pin | Signal | Type | Notes |
|-----|--------|------|-------|
| 1 | +5V | Power | 5V supply for potentiometer |
| 2 | GND | Power | Ground reference |
| 3 | Throttle | Analog Input | Wiper output (0-5V) |

**Input Range:** 0-5V analog (scaled to 0-3.3V internally if needed)

**Pull-down:** Internal or external to GND for safety (defaults to zero throttle)

---

### Brake Throttle Connector (3-pin)

Separate throttle input for brake/regen control.

| Pin | Signal | Type | Notes |
|-----|--------|------|-------|
| 1 | +5V | Power | 5V supply |
| 2 | GND | Power | Ground |
| 3 | Brake Throttle | Analog Input | 0-5V signal |

---

### Auxiliary Potentiometer (3-pin)

General-purpose analog input for user-configured sensors.

| Pin | Signal | Type | Notes |
|-----|--------|------|-------|
| 1 | +5V | Power | 5V supply |
| 2 | GND | Power | Ground |
| 3 | Potentiometer | Analog Input | 0-5V signal |

---

### E-Brake (Emergency Brake) Connector (2-pin)

Digital input for emergency stop function.

| Pin | Signal | Type | Notes |
|-----|--------|------|-------|
| 1 | GND | Power | Ground reference |
| 2 | EBRAKE | Digital Input | Active low or active high (configurable) |


---

### Torque / Pedal Assist Sensor (5-pin)

Combined connector for torque sensing and pedal cadence measurement.

| Pin | Signal | Type | Notes |
|-----|--------|------|-------|
| 1 | +10V | Power | Higher voltage for some torque sensors |
| 2 | GND | Power | Ground reference |
| 3 | DIR | Digital Input | Direction signal (forward/reverse) |
| 4 | RPM | Timer Input | Cadence frequency (pedal speed) |
| 5 | Torque | Analog Input | Torque sensor output (0-5V) |

**Torque Sensor:** Typically strain gauge or hall-effect based

**RPM Measurement:** Timer input configured for frequency measurement

**Direction:** Optional direction indication for bidirectional pedaling

---

### Cycle Analyst / Display Interface (6-pin)

Connector for Grin Technologies Cycle Analyst or similar display/controller.

| Pin | Signal | Type | Notes |
|-----|--------|------|-------|
| 1 | V+ | Power | Battery voltage passthrough |
| 2 | GND | Power | Ground |
| 3 | S- | Signal | Negative signal (TBD) |
| 4 | S+ | Signal | Positive signal (TBD) |
| 5 | Sp | Signal | Speed signal |
| 6 | ThO | Signal | Throttle output |

**Note:** This interface was planned but not fully implemented in the original design. Pin functions marked "TBD" would need to be defined based on the specific display protocol.

---

### UART Connector (3-pin)

General-purpose serial communication interface.

| Pin | Signal | Type | Notes |
|-----|--------|------|-------|
| 1 | RX | UART Input | Receive data (3.3V TTL) |
| 2 | TX | UART Output | Transmit data (3.3V TTL) |
| 3 | GND | Power | Ground reference |

**Voltage Levels:** 3.3V TTL logic (not RS-232 levels)

**Baud Rate:** Configurable in firmware (typical: 115200)

**Use Cases:** Debug console, telemetry output, configuration interface

---

### Thermistor Connector (2-pin)

External temperature sensor input (motor or battery temperature).

| Pin | Signal | Type | Notes |
|-----|--------|------|-------|
| 1 | GND | Power | Ground reference |
| 2 | NTC | Analog Input | NTC thermistor connection |

**Sensor Type:** NTC (Negative Temperature Coefficient) thermistor

**Circuit:** Voltage divider with known reference resistor

**Range:** Typically -40°C to +125°C depending on thermistor selection

---

### USB Connector

Standard USB Micro-B connector for communication and debugging.

**Signals:** USB D+, D-, VBUS, GND

**Use Cases:**
- Firmware updates
- Configuration software
- Real-time monitoring and control
- Data logging

**Speed:** USB 2.0 Full Speed (12 Mbps)

---

### JTAG/SWD Debug Connector (10-pin)

Standard ARM 10-pin Cortex Debug connector.

| Pin | Signal | Description |
|-----|--------|-------------|
| 1 | VREF | Target voltage reference (3.3V) |
| 2 | SWDIO | Serial Wire Debug Data I/O |
| 3 | GND | Ground |
| 4 | SWCLK | Serial Wire Debug Clock |
| 5 | GND | Ground |
| 6 | SWO | Serial Wire Output (trace) |
| 7 | KEY | Key (no pin) |
| 8 | NC | Not connected |
| 9 | GND | Ground |
| 10 | NRST | Reset signal |

**Programmer:** Compatible with ST-LINK, J-Link, or similar SWD programmers

**Use:** Firmware programming, debugging, and development

---

## I2C Expansion Header

Generic I2C header for adding sensors or peripherals.

| Pin | Signal | Type |
|-----|--------|------|
| 1 | 3.3V | Power |
| 2 | GND | Ground |
| 3 | SCL | I2C Clock |
| 4 | SDA | I2C Data |

**Voltage:** 3.3V logic levels

**Pull-ups:** On-board pull-up resistors (typically 4.7kΩ)

**Use Cases:** External sensors (IMU, GPS, additional ADC, etc.)

