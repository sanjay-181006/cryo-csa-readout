# Cryogenic-CMOS Charge-Sensitive Amplifier (CSA)

<p align="center">
  <a href="https://doi.org/10.5281/zenodo.21256347">
    <img src="https://zenodo.org/badge/DOI/10.5281/zenodo.21256347.svg" alt="DOI">
  </a>
</p>

---

## Overview
This repository provides the complete research workspace for the design and characterization of a high-sensitivity **Charge-Sensitive Amplifier (CSA)** optimized for quantum-sensor readout. 

The design utilizes a **Telescopic Cascode topology** implemented in **130nm CMOS technology**, engineered to operate across extreme thermal gradients from room temperature (+27°C) to deep-cryogenic levels (-268°C).

---

## Design Highlights
* **Technology Node:** 130nm BSIM3v3 (Level 8) physical models for silicon-accurate simulation of short-channel effects, velocity saturation, and parasitic capacitance.
* **Architecture:** Telescopic Cascode OTA, chosen for superior output resistance and high open-loop gain ($A_{VOL}$), essential for maintaining charge collection efficiency.
* **Thermal Characterization:** Evaluated across a wide temperature range (-268°C to +27°C) to document cryogenic gain enhancement.

---

## Core Principles
The CSA converts incident input charge ($Q_{in}$) into a proportional output voltage ($V_{out}$) defined by the feedback network:

$$V_{out} = \frac{Q_{in}}{C_f}$$

Where $C_f$ (100fF) acts as the integration element. In the cryogenic regime, the design leverages the inverse relationship between temperature and carrier mobility to achieve an exponential increase in Open-Loop Gain, effectively approaching ideal charge integration efficiency ($\eta \approx 100\%$) at low temperatures.

---

## Performance Summary

| Temperature (°C) | Max Open-Loop Gain (dB) | -3dB Bandwidth (Hz) |
| :--- | :--- | :--- |
| **27** | 53.46 | 53,051 |
| **-73** | 103.96 | 27.50 |
| **-268** | 143.70 | 3.52 |

---

## Repository Structure
```text
cryo-csa-readout/
├── README.md
├── schematics/             # Architecture diagrams (Draw.io)
└── Spice/
    ├── csa-frontend CM.asc # Optimized Cascode Testbench
    └── 130nm_models.txt    # BSIM3v3 parameter library
