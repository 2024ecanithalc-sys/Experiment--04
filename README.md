# Experiment--04
Experiment -04

##  Differentional Amplifier Analysis 
### Aim : Design and analusis the MOS differential amplifier circuit for the following specifications VDD = 0.9V, VSS = -0.9V, P <=2mW, VinCM =0V, VoCM = 0V, Vp = -0.7V

## MOS Differential Amplifier Analysis

### Aim
Design and analyze a MOS differential amplifier for the following specifications:
- **VDD = 0.9 V**
- **VSS = -0.9 V**
- **Power (P) ≤ 2 mW**
- **Input Common Mode Voltage (VinCM) = 0 V**
- **Output Common Mode Voltage (VoCM) = 0 V**
- **Threshold Voltage (Vp) = -0.7 V**

---

### Introduction

A **MOS Differential Amplifier** is a fundamental building block in analog circuit design. It is widely used in operational amplifiers, comparators, and signal processing circuits.

The main function of a differential amplifier is to amplify the **difference between two input signals** while rejecting any signals that are common to both inputs (common-mode signals). This property is known as **Common-Mode Rejection**.

A typical MOS differential amplifier consists of:
- Two matched MOSFETs (NMOS or PMOS)
- A constant current source for biasing
- Load elements (resistive or active loads)

---

### Key Features

- Amplifies differential input: `Vout ∝ (Vin1 - Vin2)`
- High Common-Mode Rejection Ratio (CMRR)
- Low power consumption (suitable for modern CMOS designs)
- High gain and good linearity

---

### Design Considerations

- **Low Voltage Operation:** With ±0.9 V supply, transistors must operate efficiently in limited headroom.
- **Power Constraint:** Total current must be minimized to keep power ≤ 2 mW.
- **Symmetry:** Ensures proper differential operation and zero output offset.
- **Biasing:** Proper current source design is critical for stability.

---

### Applications

- Operational Amplifiers (Op-Amps)
- Analog Signal Processing
- Data Converters (ADC/DAC)
- Sensor Interfaces

---

### Conclusion

The MOS differential amplifier is essential for precise analog signal amplification. Designing under low voltage and power constraints requires careful transistor sizing and biasing to achieve optimal performance.

---
