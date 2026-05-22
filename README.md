# Open Battery Smart Charger

Smart 2S Li-Ion battery charger designed in KiCad featuring input protection, power-path management, and intelligent charging control.

---

## Overview

This project implements an intelligent battery charging system for **2-cell Li-Ion batteries (8.4V)** with integrated protection and automatic power switching.

The system combines:

- Smart charging control
- Input overvoltage and overcurrent protection
- Automatic source/battery switching
- Auxiliary regulated 3.3V rail
- Battery monitoring interfaces

The design was developed in **KiCad 10** as part of a hardware/electronics engineering portfolio project.

---

## Features

- 2S Li-Ion battery charging (8.4V)
- Constant-current / constant-voltage (CC/CV) charging
- Input surge and fault protection
- Power-path management between external supply and battery
- Reverse current protection
- 3.3V regulated output for embedded systems
- Thermistor input for battery temperature supervision
- System and battery voltage interfaces

---

## System Architecture

### 1. Input Protection Stage

The input stage is protected using the **TPS26600** eFuse, providing:

- Overvoltage protection (OVP)
- Current limiting
- Fault protection
- Hot-plug robustness

This stage protects downstream electronics from abnormal supply conditions.

### 2. Smart Battery Charger

Battery charging is managed using the **LT3650**, configured for:

- 2S Li-Ion battery charging
- Constant-current / constant-voltage charging profile
- Battery temperature monitoring
- Charging status feedback

### 3. Power Path Management

The **LTC4412** controller enables automatic switching between:

- External DC power source
- Battery supply

This ensures uninterrupted system operation while preventing reverse current paths.

### 4. Auxiliary Power Rail

A dedicated **3.3V LDO regulator** powers low-voltage logic and embedded systems.

---

## Main Components

| Component | Function |
|---|---|
| LT3650 | Smart battery charger |
| TPS26600 | Input protection / eFuse |
| LTC4412 | Ideal diode power-path controller |
| LDK320AM33R | 3.3V voltage regulator |

---

## Specifications

| Parameter | Value |
|---|---|
| Battery Type | 2S Li-Ion |
| Charge Voltage | 8.4V |
| Charging Method | CC/CV |
| Logic Rail | 3.3V |
| Input Protection | OVP / current limiting |
| Design Tool | KiCad 10 |

---

## Repository Structure

```text
Open_Battery_Charger/
│
├── hardware/
│   ├── Open_Battery_Charger.kicad_pro
│   ├── Open_Battery_Charger.kicad_sch
│   ├── Open_Battery_Charger.kicad_pcb
│   └── fp-lib-table
│
├── docs/
│   ├── schematic.pdf
│   ├── schematic.png
│   ├── 2D_pcb_top.png
│   ├── 2D_Dpcb_bottom.png
│   ├── 3D_pcb_top.png
│   ├── 3D_Dpcb_bottom.png
│   └── block_diagram.png
│
└── production/
    ├── gerbers/
    └── bom.csv
```

---

## Schematic

![Schematic](Docs/schematic.png)

---

## PCB Design

### Top View

![PCB Top](Docs/2D_pcb_top.png)

### 3D Render

![PCB Render](Docs/3D_pcb_top.png)

---

## Design Considerations

Key engineering decisions considered during development:

- Input fault protection for safer operation
- Efficient battery charging profile implementation
- Automatic power source switching
- Low-voltage regulation for embedded systems
- Modular architecture for maintainability

---

## Tools

- KiCad 10
- Datasheet-driven design methodology
- Electronic circuit validation

---

## Future Improvements

- PCB manufacturing and validation
- Thermal characterization
- Charging efficiency measurements
- Test reports and oscilloscope captures
- Firmware integration for battery monitoring

---

## License

This project is released under the MIT License.
