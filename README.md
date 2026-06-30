# Cryo-CMOS Charge-Sensitive Amplifier for Quantum-Sensor Readout

This repository contains the complete open-source simulation workspace and architectural schematics for a cryogenic-CMOS charge-sensitive amplifier (CSA) designed for semiconductor quantum-sensor readout. The project evaluates a compact five-transistor operational transconductance amplifier (OTA) topology under two distinct configurations: an idealized tail current source baseline and a physical, active NMOS current-mirror tail bias.

Both variants are fully characterized across an extreme temperature sweep from room temperature ($27^\circ\text{C}$) down to liquid nitrogen ($77\text{ K} / -196^\circ\text{C}$) and a liquid helium topological stress point ($5\text{ K} / -268^\circ\text{C}$).

---

## Repository Structure

```text
cryo-csa-readout/
├── README.md                     # Repository orientation and execution instructions
├── LICENSE                       # Open-source distribution permissions (MIT License)
├── schematics/
│   ├── Schematic-CM.drawio       # Draw.io current-mirror system layout
│   └── Schematic-Ideal.drawio    # Draw.io ideal baseline system layout[cite: 6]
└── spice/
    ├── csa-frontend-CM.asc       # LTspice active current-mirror tail schematic[cite: 6]
    └── csa-frontend-Ideal.asc    # LTspice idealized current source schematic[cite: 6]