# Hardware Specification

## System Overview

The Chibi-ECEN-BLDC is a three-phase motor driver controlled by an STM32F405 ARM Cortex-M4 microcontroller. A three-phase bridge driver ASIC (DRV8302) is employed as a power electronics and analog instrumentation front end. The PCB is intended to be a test platform for developing field-oriented control software for a 480-watt brushless DC motor.

## System Parameters

| Parameter | Specification |
|-----------|--------------|
| Input Voltage (nominal) | 48 VDC |
| Output Current (maximum bus input average) | 10 Amps |
| Switching Frequency (nominal) | 20 kHz |
| Microcontroller | STM32F405RGT6 (ARM Cortex-M4, 168 MHz) |
| Driver IC | DRV8302 (Three-phase pre-driver with buck converter) |
| PCB Layers | 4 layers |


## PCB Specifications

| Parameter | Value |
|-----------|-------|
| Board Thickness | 1.6 mm (0.063") |
| Copper Weight | 1 oz (35 μm) base, 2 oz recommended for power layers |
| Layer Stack | Signal/Power, GND, Power, Signal/Power |
| Minimum Trace Width | 0.006" (0.15 mm) for signals, wider for power |
| Minimum Clearance | 0.006" (0.15 mm) for low voltage, 0.010" for high voltage |
| Via Size | 0.013" drill, 0.024" pad (typical) |
| Solder Mask | Green (or per preference) |
| Silkscreen | White on top, none on bottom |

## Layer Stack-up

1. **Layer 1 (Top):** Signal + Power routing, component side
2. **Layer 2:** Ground plane (GND)
3. **Layer 3:** Power plane (48V, 5V, 3.3V)
4. **Layer 4 (Bottom):** Signal + Power routing


## Power Budget

Estimated power consumption and heat dissipation:

| Subsystem | Typical Power | Notes |
|-----------|--------------|-------|
| Motor (load) | Up to 480W | 48V × 10A |
| Power Stage Loss | ~10-20W | MOSFET conduction and switching losses |
| DRV8302 + Buck | ~2W | Gate drive and control |
| STM32F405 | ~0.5W | MCU and peripherals |
| Linear Regulator | ~0.5W | 3.3V logic supply |

**Total system loss:** Approximately 15-25W (excluding motor)

### Heatsink Mounting

The board includes four mounting holes for attaching a "full brick" standard heatsink. Heat dissipation is primarily through the D2PAK packages to the heatsink, secondarily through PCB copper pours.

- **Heatsink Type:** Flat-based aluminum heatsink
- **Thermal Interface:** Thermal pad or thermal paste between D2PAK packages and heatsink
- **Clearance:** Component heights were specified to ensure no interference

**Important:** Do not use electrically conductive thermal paste unless heatsink is electrically isolated. MOSFET tabs may be at different potentials.

