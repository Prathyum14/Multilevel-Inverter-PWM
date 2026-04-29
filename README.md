# Five-Level Multilevel Inverter with PWM Control and Harmonic Reduction

A MATLAB/Simulink simulation of a 5-level Cascaded H-Bridge (CHB) multilevel inverter using Sinusoidal PWM (SPWM) and Level-Shifted PWM techniques, achieving a Total Harmonic Distortion (THD) below 5%.

---

## Overview

Multilevel inverters are a critical technology in modern power electronics — used in renewable energy systems, motor drives, HVDC transmission, and industrial power supplies. This project designs, simulates, and validates a **5-level Cascaded H-Bridge inverter** in MATLAB/Simulink, demonstrating significant harmonic reduction compared to conventional 2-level inverters.

---

## Key Results

| Parameter | Value |
|-----------|-------|
| Topology | 5-Level Cascaded H-Bridge (CHB) |
| PWM Technique | SPWM / Level-Shifted PWM |
| Total Harmonic Distortion (THD) | **< 5%** |
| Output Waveform | Stepped — closely approximates sinusoidal |
| Switching Devices | IGBT / MOSFET |
| Simulation Tool | MATLAB/Simulink |

---

## Features

- ✅ 5-level output voltage waveform (stepped sinusoidal approximation)
- ✅ THD below 5% — significantly better than 2-level inverters (~30–40% THD)
- ✅ SPWM and Level-Shifted PWM switching strategy implemented
- ✅ Gate driver circuitry designed for IGBT/MOSFET switching
- ✅ Performance analyzed under varying load conditions
- ✅ Switching loss and efficiency analysis included

---

## Background

### Why Multilevel Inverters?

A conventional 2-level inverter switches between +Vdc and −Vdc, producing a square wave with high harmonic content. A **5-level inverter** produces five voltage levels: +2Vdc, +Vdc, 0, −Vdc, −2Vdc — creating a stepped waveform that is much closer to a pure sine wave.

**Benefits:**
- Lower THD → less filtering required
- Reduced dv/dt stress on switching devices
- Lower switching losses per device
- Better electromagnetic compatibility (EMC)

### Cascaded H-Bridge Topology

Each H-Bridge cell produces a 3-level output (−V, 0, +V). Two cascaded H-Bridge cells produce a 5-level output. Each cell requires its own isolated DC source, making this topology well-suited for battery-based and solar applications.

---

## PWM Techniques Used

### 1. Sinusoidal PWM (SPWM)
- A sinusoidal reference signal is compared against multiple triangular carrier signals
- For 5-level: 4 carrier signals, phase-shifted or level-shifted
- Switching frequency determines harmonic spectrum

### 2. Level-Shifted PWM
- Carrier signals are stacked vertically (level-shifted) rather than phase-shifted
- Produces naturally balanced power distribution across H-Bridge cells
- Results in lower THD for the same switching frequency

---

## Repository Structure

```
multilevel-inverter-pwm/
│
├── matlab/
│   ├── inverter_5level.m            # Main MATLAB script
│   └── inverter_5level.slx          # Simulink model file
│
├── results/
│   ├── output_waveform.png          # 5-level output voltage waveform
│   ├── thd_analysis.png             # FFT / THD analysis plot
│   ├── load_variation.png           # Performance under load variation
│   └── switching_losses.png         # Switching loss analysis
│
├── docs/
│   ├── circuit_diagram.png          # CHB inverter circuit diagram
│   └── gate_driver_design.png       # Gate driver circuit
│
└── README.md
```

---

## How to Run

### Requirements
- MATLAB R2020a or later
- Simulink
- SimPowerSystems / Simscape Electrical toolbox

### Steps
1. Clone or download this repository
2. Open MATLAB and navigate to the `matlab/` folder
3. Open `inverter_5level.slx` in Simulink
4. Click **Run** to start the simulation
5. View output waveforms in the Scope blocks
6. Run `inverter_5level.m` for THD analysis and FFT plots

---

## Results & Analysis

### Output Waveform
The 5-level output voltage closely approximates a sinusoidal waveform with clearly visible stepped levels at +2Vdc, +Vdc, 0, −Vdc, −2Vdc.

### THD Analysis
- **5-Level CHB Inverter THD: < 5%**
- Conventional 2-level inverter THD: ~30–40% (for reference)
- FFT analysis confirms dominant fundamental frequency with minimal harmonic content

### Load Variation
System maintains stable output voltage and waveform quality under resistive, inductive, and mixed load conditions.

### Switching Losses
Per-device switching frequency is lower in multilevel topology compared to 2-level, resulting in reduced switching losses and improved overall efficiency.

---

## Gate Driver Design

A gate driver circuit was designed to provide:
- Proper voltage levels for IGBT/MOSFET gate triggering
- Electrical isolation between control and power circuits
- Protection against shoot-through conditions

---

## Applications

- Solar PV grid-tied inverters
- Battery energy storage systems (BESS)
- Variable frequency drives (VFD) for motor control
- HVDC transmission systems
- Uninterruptible Power Supplies (UPS)

---

## Tools Used

| Tool | Purpose |
|------|---------|
| MATLAB/Simulink | Simulation and modelling |
| Simscape Electrical | Power electronics component library |
| MATLAB FFT | THD and harmonic analysis |

---

## Author

**Prathyum G**  
B.Tech – Electrical & Electronics Engineering  
University Visvesvaraya College of Engineering (UVCE), Bangalore  
📧 prathyum14@gmail.com
