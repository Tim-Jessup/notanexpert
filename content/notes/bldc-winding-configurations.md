---
title: "Delta vs Wye BLDC Motor Windings"
date: 2024-11-30
---

Notes on how delta and wye winding configurations affect BLDC motor performance and ESC design. This came up while working on ESC thermal analysis.

## The basics (as I understand them)

BLDC motors can have their three phase windings connected in two ways: delta (Δ) or wye (Y). The choice affects voltage, current, and torque characteristics.

### Wye (Y) configuration

- All three windings meet at a common neutral point
- Phase voltage is lower than line voltage (V_phase = V_line / √3)
- Used when you need higher voltage operation
- Lower starting current
- Better for high-speed applications

### Delta (Δ) configuration  

- Windings form a triangle, no neutral point
- Phase voltage equals line voltage
- Higher starting torque
- More current draw
- Better for low-speed, high-torque applications

## Impact on ESC design

For ESC design, this matters because:

1. **Current handling**: Delta draws more current for the same power, need beefier FETs
2. **Back-EMF**: Affects how we detect rotor position in sensorless control
3. **Thermal considerations**: Higher currents mean more I²R losses

## What I'm still figuring out

- Optimal winding configurations for different drone applications
- How this interacts with PWM frequency selection
- Trade-offs in efficiency across the operating range

## References

- Motor manufacturer datasheets
- "Brushless DC Motor Control Made Easy" - Microchip AN857
- Various forum discussions (some contradictory)

This is my current understanding. Corrections welcome.
