# 5x6 Othrolinear Column staggered split keyboard

## Schematic & PCB

- Built around a pi pico (future revisions may be downsized to a rp2040-tiny)
- Texas instruments DRV5053VAQDBZR linear hall effect sensors
  - Low pass filter with 330 Ω resistor and a 100 nF capacitor on every sensors' output
  - 100 nF decoupling capacitor for each sensor
- 4x SN74CBTLV3251DR 8x1 multiplexer per half
  - Low pass filter with 330 Ω resistor and a 100 nF capacitor
  - 100 nF decoupling capacitor
  - 2 of these mux-es share the same ADC in on the pi pico
    - pi pico input will be controlled by enable lines
- XINGLIGHT XL-3216UWC-FB white LEDs
  - Reverse mount, shining through a cutout in the PCB at each key
  - 1 kΩ current limiting resistor in series with each LED
  - Brightness control with PWM signal
- Communication to second half via TRRS plug
  - VSYS (not VBUS) to VSYS of the second pi
  - shared GND
  - UART TX to UART RX
  - UART RX to UART TX

## Warning

⚠️⚠️⚠️ THIS IS AN EXPERIMENTAL KEYBOARD, BUILD AT YOUR OWN RISK ⚠️⚠️⚠️

- No sanity checks have been performed.. yet
- Current draw has not been measured, only vague calculations. **MAY FRY YOUR USB PORT**
- PCB shell may not fit

## TODO

- Designing the right side PCB, SHELL
- Code for both halves of the keyboard
- Get the PCBs & shells manufactured for both halves
