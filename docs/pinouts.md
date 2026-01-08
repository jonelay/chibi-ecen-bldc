# STM32F405RGT6 Pin Assignments

This document details the pin assignments for the STM32F405RGT6 microcontroller in the Chibi-ECEN-BLDC design.

## Pin Mapping Table

| Pin # | Pin Name | Function | Assignment | ChibiOS Config | Peripheral |
|-------|----------|----------|------------|----------------|------------|
| 1 | VBAT | Power | 3V3 | Power | - |
| 2 | PC13 | GPIO | Not used | - | - |
| 3 | PC14/OSC32_IN | Input | FWD (Forward button) | PAL_MODE_INPUT_ANALOG | - |
| 4 | PC15/OSC32_OUT | Input | REV (Reverse button) | PAL_MODE_INPUT_ANALOG | - |
| 5 | PH0/OSC_IN | Oscillator | OSC (8 MHz crystal) | Oscillator | - |
| 6 | PH1/OSC_OUT | Oscillator | OSC (8 MHz crystal) | Oscillator | - |
| 7 | NRST | Reset | Reset button | Reset | - |
| 8 | PC0 | Analog Input | Temp_Motor | PAL_MODE_INPUT_ANALOG | ADC IN10 |
| 9 | PC1 | Analog Input | Temp_Driver | PAL_MODE_INPUT_ANALOG | ADC IN11 |
| 10 | PC2 | Analog Input | AN_IN (Analog Input) | - | ADC IN12 |
| 11 | PC3 | Analog Input | Wheel_Torque | - | - |
| 12 | VSSA | Power | GND (Analog Ground) | Power | - |
| 13 | VDDA | Power | 3V3 (Analog Supply) | Power | - |
| 14 | PA0/WKUP | Analog Input | SENS3 (Current Sense 3) | PAL_MODE_INPUT_ANALOG | - |
| 15 | PA1 | Analog Input | SENS2 (Current Sense 2) | PAL_MODE_INPUT_ANALOG | - |
| 16 | PA2 | Analog Input | SENS1 (Current Sense 1) | PAL_MODE_INPUT_ANALOG | - |
| 17 | PA3 | Analog Input | Brake | PAL_MODE_INPUT_ANALOG | - |
| 18 | VSS | Power | GND | Power | - |
| 19 | VDD | Power | 3V3 | Power | - |
| 20 | PA4 | Analog Input | Throttle | PAL_MODE_INPUT_ANALOG | - |
| 21 | PA5 | Analog Input | BR_SO2 (Bridge Sensor Output 2) | PAL_MODE_INPUT_ANALOG | - |
| 22 | PA6 | Analog Input | BR_SO1 (Bridge Sensor Output 1) | PAL_MODE_INPUT_ANALOG | - |
| 23 | PA7 | GPIO Output | LED_B (Blue LED) | PAL_MODE_OUTPUT_PUSHPULL | - |
| 24 | PC4 | GPIO Output | LED_R (Red LED) | PAL_MODE_OUTPUT_PUSHPULL | - |
| 25 | PC5 | GPIO Output | LED_G (Green LED) | PAL_MODE_OUTPUT_PUSHPULL | - |
| 26 | PB0 | Analog Input | Pedal_Torque | PAL_MODE_INPUT_ANALOG | - |
| 27 | PB1 | Timer Input | Pedal_Tach | GPIO_EXTI1 | - |
| 28 | PB2/BOOT1 | Timer Input | Wheel_Tach | GPIO_EXTI2 | - |
| 29 | PB10 | UART TX | TX | UART TX | UART4 |
| 30 | PB11 | UART RX | RX | UART RX | UART4 |
| 31 | VCAP_1 | Power | 2.2µF capacitor to GND | Power | - |
| 32 | VDD | Power | 3V3 | Power | - |
| 33-34 | PB12-PB13 | SPI/GPIO | Reserved | - | - |
| 35-38 | PB14-PB15, PD8-PD9 | Timer/GPIO | PWM outputs or control | - | TIM1/TIM8 |
| 39 | PD10 | GPIO | Reserved | - | - |
| 40 | PD11 | GPIO | Reserved | - | - |
| 41 | PD12 | GPIO | Reserved | - | - |
| 42 | PD13 | GPIO | Reserved | - | - |
| 43 | PD14 | GPIO | Reserved | - | - |
| 44 | PD15 | GPIO | Reserved | - | - |
| 45-46 | PC6-PC7 | Timer/UART | Reserved | - | - |
| 47 | PC8 | GPIO | Reserved | - | - |
| 48 | PC9 | GPIO | Reserved | - | - |
| 49 | PA8 | Timer Output | PWM_AH (Phase A High-Side) | - | TIM1_CH1 |
| 50 | PA9 | USB/UART | VBUS detect or UART TX | - | - |
| 51 | PA10 | USB/UART | USB_ID or UART RX | - | - |
| 52 | PA11 | USB | USB_DM (D-) | - | USB OTG FS |
| 53 | PA12 | USB | USB_DP (D+) | - | USB OTG FS |
| 54 | PA13/SWDIO | Debug | SWDIO (SWD Data) | Debug | SWD |
| 55 | VCAP_2 | Power | 2.2µF capacitor to GND | Power | - |
| 56 | VDD | Power | 3V3 | Power | - |
| 57 | PA14/SWCLK | Debug | SWCLK (SWD Clock) | Debug | SWD |
| 58 | PA15 | GPIO/SPI | Reserved (SPI NSS alt function) | - | - |
| 59 | PC10 | SPI/UART | Reserved | - | - |
| 60 | PC11 | SPI/UART | Reserved | - | - |
| 61 | PC12 | SPI/UART | Reserved | - | - |
| 62 | PD0 | GPIO | Reserved | - | - |
| 63 | PD1 | GPIO | Reserved | - | - |
| 64 | PD2 | GPIO | Reserved | - | - |

## Functional Groups

### Motor Control PWM Outputs
High-side and low-side PWM signals for three-phase motor drive:
- **Phase A:** PA8 (AH), TIM1_CH1N (AL)
- **Phase B:** TIM1_CH2 (BH), TIM1_CH2N (BL)
- **Phase C:** TIM1_CH3 (CH), TIM1_CH3N (CL)

### Current Sensing (Analog Inputs)
- **PA0:** SENS3 - Phase C current sense
- **PA1:** SENS2 - Phase B current sense
- **PA2:** SENS1 - Phase A current sense
- **PA5:** BR_SO2 - Additional bridge sensor
- **PA6:** BR_SO1 - Additional bridge sensor

### Temperature Monitoring
- **PC0:** Temp_Motor - Motor temperature (NTC thermistor)
- **PC1:** Temp_Driver - Driver IC temperature

### User Interface
- **PC14:** Forward button input
- **PC15:** Reverse button input
- **PA7:** Blue LED output
- **PC4:** Red LED output
- **PC5:** Green LED output

### Throttle and Brake
- **PA4:** Throttle analog input
- **PA3:** Brake digital input

### Hall Sensors (Optional)
Hall effect sensor inputs for rotor position feedback can be configured on timer capture inputs or GPIO with external interrupts (exact pins TBD based on firmware).

### Communication Interfaces
- **USB:** PA11 (D-), PA12 (D+)
- **UART:** PB10 (TX), PB11 (RX)
- **SWD Debug:** PA13 (SWDIO), PA14 (SWCLK)

### Pedal Sensors
- **PB0:** Pedal_Torque (analog)
- **PB1:** Pedal_Tach (timer input with interrupt)
- **PB2:** Wheel_Tach (timer input with interrupt)

## Notes

1. **ADC Channels:** Most analog inputs use the ADC1 peripheral. ADC2 and ADC3 can be configured for simultaneous sampling if needed.

2. **Timer Configuration:** TIM1 is the primary timer for six-step or FOC motor control, providing complementary PWM outputs with programmable dead-time insertion.

3. **Alternate Functions:** Many pins have multiple possible functions. The table shows the intended assignment for this design.

4. **Reserved Pins:** Pins marked as "Reserved" may be used for future expansion or alternate configurations.

5. **ChibiOS:** The "ChibiOS Config" column shows the intended configuration if using the ChibiOS RTOS, which was being considered for the firmware.

## References

- [STM32F405 Datasheet](../datasheets/STM32F405_DM00037051-2.pdf)
- [STM32F4 Reference Manual](https://www.st.com/resource/en/reference_manual/dm00031020.pdf) (online)
- STM32CubeMX configuration: `design-source/cubemx/chibibldc_v01.ioc`
