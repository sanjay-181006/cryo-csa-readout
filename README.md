# Cryo-CMOS Charge-Sensitive Amplifier for Quantum-Sensor Readout

<p align="center">
  <a href="https://doi.org/10.5281/zenodo.21134662">
    <img src="https://zenodo.org/badge/DOI/10.5281/zenodo.21134662.svg" alt="DOI">
  </a>
</p>

<p align="center">
  <a href="https://zenodo.org/record/21134662">
    <img src="https://upload.wikimedia.org/wikipedia/commons/7/79/Zenodo-logo.svg" width="140">
  </a>
</p>

---

## Abstract

This repository presents a **cryogenic CMOS charge-sensitive amplifier (CSA)** designed for **quantum-sensor readout**, where extremely small charge signals must be converted into measurable voltages with high fidelity.

A compact **five-transistor operational transconductance amplifier (OTA)** topology is investigated under two biasing regimes:

* **Ideal tail current source (theoretical baseline)**
* **NMOS current-mirror tail (physically realizable bias)**

The system is evaluated across **extreme temperature conditions (300 K → 5 K)** to study how **cryogenic device physics impacts analog front-end behavior**, with emphasis on **bias stability, signal integrity, and topology-dependent performance**.

---

## Why This Work Matters

Cryogenic environments are fundamental to:

* Quantum computing systems
* Semiconductor quantum sensors
* Cryogenic detector instrumentation

However, at low temperatures:

* Carrier mobility increases
* Threshold voltages shift
* Bias currents become unstable
* Small-signal behavior becomes highly sensitive

This creates a gap between:

> **Ideal circuit assumptions** and **physically realizable implementations**

This project directly explores that gap.

---

## Core Principle

The CSA converts input charge into output voltage via a feedback capacitor:

```text
V_out = Q_in / C_f
```

For the MOS-based OTA:

```text
g_m ≈ 2 * I_D / V_ov
```

where:

* `Q_in` — input charge
* `C_f` — feedback capacitance
* `g_m` — transconductance
* `I_D` — drain current
* `V_ov = V_GS - V_TH` — overdrive voltage

At cryogenic temperatures, both `g_m` and `V_ov` become strongly temperature-dependent, directly influencing gain and stability.

---

## System Architecture

<p align="center">
  <img src="schematics/csa-ideal.png" width="700">
</p>

<p align="center">
  <em>Figure 1: CSA with ideal tail current source (baseline configuration).</em>
</p>

<p align="center">
  <img src="schematics/csa-current-mirror.png" width="700">
</p>

<p align="center">
  <em>Figure 2: CSA with NMOS current-mirror tail bias (physically realizable configuration).</em>
</p>

Both implementations use a **five-transistor OTA-based CSA topology**, differing only in the **tail bias realization**.

* The **ideal configuration** isolates intrinsic amplifier behavior
* The **current-mirror configuration** introduces real-world bias dependencies

---

## Key Insight

> **At deep cryogenic temperatures, biasing strategy dominates circuit behavior more than topology itself.**

Specifically:

* Ideal biasing → stable, predictable operation
* Physical biasing → temperature-sensitive, introduces drift and non-idealities

This distinction becomes increasingly pronounced as temperature approaches **5 K**.

---

## Results (High-Level)

* The CSA maintains correct charge-to-voltage conversion behavior
* Gain remains governed by feedback capacitance:

```text
Gain ∝ 1 / C_f
```

* Cryogenic operation introduces:

  * Bias current variation
  * Operating point shifts
  * Reduced predictability in current-mirror configurations

* Performance divergence between ideal and physical biasing increases with decreasing temperature

---

## Repository Structure

```text
cryo-csa-readout/
├── README.md
├── LICENSE
├── schematics/
│   ├── csa-ideal.png
│   └── csa-current-mirror.png
└── spice/
    ├── csa-frontend-Ideal.asc
    └── csa-frontend-CM.asc
```

---

## Reproducibility

All results are reproducible using the provided LTspice files.

To explore the system:

1. Open the `.asc` schematics in LTspice
2. Run operating point (`.op`) and transient (`.tran`) simulations
3. Sweep temperature:

```text
.temp 300 77 5
```

4. Compare:

   * Output response
   * Bias stability
   * Ideal vs current-mirror behavior

---

## Citation

If you use this work, please cite:

> Selvakumar, S. (2026). *Cryo-CMOS Charge-Sensitive Amplifier for Quantum-Sensor Readout*. Zenodo. https://doi.org/10.5281/zenodo.21064438

---

## License

Released under the **MIT License**.

---

## Notes

This repository is intentionally structured to:

* Present **clear system-level understanding**
* Provide **fully reproducible simulation artifacts**
* Avoid over-specification in documentation

Detailed behavior, parameter choices, and circuit nuances are best understood directly through the **LTspice schematics and simulations**.

---

## Author

**Sanjay Selvakumar**
Independent Project

---

## Conclusion

This work demonstrates that while CSA architectures remain effective in cryogenic regimes, **practical biasing mechanisms introduce non-trivial limitations** that are not captured in ideal models.

The project serves as a **minimal, high-signal exploration of cryogenic analog circuit behavior**, bridging theoretical assumptions and physically realizable design.

---
