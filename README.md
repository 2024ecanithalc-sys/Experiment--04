# Experiment--04
Experiment -04

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
## Design Calculations for MOS Differential Amplifier

### Given Specifications
- VDD = +0.9 V  
- VSS = -0.9 V  
- Maximum Power, P ≤ 2 mW  
- VinCM = 0 V  
- VoCM = 0 V  
- PMOS Threshold Voltage, Vtp = -0.7 V  

---

### Step 1: Total Current Calculation

\[
P = (V_{DD} - V_{SS}) \cdot I_{total}
\]

\[
2 \times 10^{-3} = (0.9 - (-0.9)) \cdot I_{total}
\]

\[
2 \times 10^{-3} = 1.8 \cdot I_{total}
\]

\[
I_{total} = \frac{2 \times 10^{-3}}{1.8} = 1.11 \text{ mA}
\]

So, **tail current**:
\[
I_{tail} = 1.11 \text{ mA}
\]

Each transistor carries:
\[
I_D = \frac{I_{tail}}{2} = 0.555 \text{ mA}
\]

---

### Step 2: Overdrive Voltage Selection

Assume a reasonable overdrive voltage:
\[
V_{OV} = V_{GS} - V_T \approx 0.2 \text{ V}
\]

---

### Step 3: Transconductance (gm)

\[
g_m = \frac{2I_D}{V_{OV}}
\]

\[
g_m = \frac{2 \times 0.555 \text{ mA}}{0.2}
= 5.55 \text{ mS}
\]

---

### Step 4: MOSFET Sizing (W/L)

Using:
\[
I_D = \frac{1}{2} k_n \frac{W}{L} V_{OV}^2
\]

Assume:
\[
k_n = 200 \, \mu A/V^2
\]

\[
0.555 \text{ mA} = \frac{1}{2} \cdot 200 \times 10^{-6} \cdot \frac{W}{L} \cdot (0.2)^2
\]

\[
0.555 \times 10^{-3} = 100 \times 10^{-6} \cdot \frac{W}{L} \cdot 0.04
\]

\[
0.555 \times 10^{-3} = 4 \times 10^{-6} \cdot \frac{W}{L}
\]

\[
\frac{W}{L} = \frac{0.555 \times 10^{-3}}{4 \times 10^{-6}} \approx 139
\]

---

### Step 5: Output Resistance

\[
r_o = \frac{1}{\lambda I_D}
\]

Assume:
\[
\lambda = 0.02 \, V^{-1}
\]

\[
r_o = \frac{1}{0.02 \times 0.555 \times 10^{-3}} \approx 90 \, k\Omega
\]

---

### Step 6: Voltage Gain

For differential amplifier:
\[
A_v = g_m \cdot r_o
\]

\[
A_v = 5.55 \times 10^{-3} \cdot 90 \times 10^{3}
\approx 500
\]

---

### Step 7: Output Common Mode Check

\[
V_{oCM} = 0 V \quad (\text{given, satisfied with symmetric design})
\]

---

### Final Design Summary

| Parameter | Value |
|----------|------|
| Tail Current | 1.11 mA |
| Drain Current (each) | 0.555 mA |
| Transconductance (gm) | 5.55 mS |
| W/L Ratio | ≈ 139 |
| Output Resistance | ≈ 90 kΩ |
| Voltage Gain | ≈ 500 |

---

### Conclusion

The designed MOS differential amplifier satisfies:
- Low power constraint (≤ 2 mW)
- Symmetric operation around 0 V
- High gain (~500)

Proper transistor sizing and biasing ensure efficient low-voltage operation.
---
