# Cryo-CMOS Charge-Sensitive Amplifier for Quantum-Sensor Readout

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21064438.svg)](https://doi.org/10.5281/zenodo.21064438)

## Citation
If you use this simulation workspace, schematics, or reference data in your research, please cite the permanent archive as follows:

> Selvakumar, S. (2026). *Cryo-CMOS Charge-Sensitive Amplifier for Quantum-Sensor Readout*. Zenodo. https://doi.org/10.5281/zenodo.21064438

This repository contains the complete open-source simulation workspace and architectural schematics for a cryogenic-CMOS charge-sensitive amplifier (CSA) designed for semiconductor quantum-sensor readout. The project evaluates a compact five-transistor operational transconductance amplifier (OTA) topology under two distinct configurations: an idealized tail current source baseline and a physical, active NMOS current-mirror tail bias.

Both variants are fully characterized across an extreme temperature sweep from room temperature (**27°C**) down to liquid nitrogen (**77 K / -196°C**) and a liquid helium topological stress point (**5 K / -268°C**).

---

## Repository Structure

```text
cryo-csa-readout/
├── README.md                     # Repository orientation and execution instructions
├── LICENSE                       # Open-source distribution permissions (MIT License)
├── schematics/
│   ├── Schematic-CM.drawio       # Draw.io current-mirror system layout
│   └── Schematic-Ideal.drawio    # Draw.io ideal baseline system layout
└── spice/
    ├── csa-frontend-CM.asc       # LTspice active current-mirror tail schematic
    └── csa-frontend-Ideal.asc    # LTspice idealized current source schematic
