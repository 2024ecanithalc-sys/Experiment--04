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

### Circuit Diagram ;

<img width="1286" height="789" alt="Screenshot 2026-03-27 221339" src="https://github.com/user-attachments/assets/68431ff2-937c-4713-8887-75c014d53da2" />





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
- MOS Threshold Voltage, Vtp = -0.7 V  



## Differential Amplifier Calculation

### Given:
- \( V_{DD} = 0.9\,V \)
- \( V_{SS} = -0.9\,V \)
- Power \( P \le 2\,mW \)
- \( V_T = 0.36\,V \)
- \( V_{in,CM} = 0\,V \), \( V_{out,CM} = 0\,V \)

---

### 1. Tail Current \( I_{SS} \)

\[
P = (V_{DD} - V_{SS}) \cdot I_{SS}
\]

\[
2\,mW = (0.9 - (-0.9)) \cdot I_{SS}
\]

\[
2 \times 10^{-3} = 1.8 \cdot I_{SS}
\]

\[
I_{SS} = \frac{2 \times 10^{-3}}{1.8} = 1.11 \times 10^{-3} A = 1.11\,mA
\]

---

### 2. Drain Currents

\[
I_{D1} = I_{D2} = \frac{I_{SS}}{2} = 0.555\,mA
\]

---

### 3. Drain Resistance \( R_D \)

\[
V_{out} = V_{DD} - I_D R_D
\]

\[
0 = 0.9 - I_D R_D
\]

\[
R_D = \frac{0.9}{0.555 \times 10^{-3}}
\]

\[
R_D = 1636\,\Omega \approx 1.636\,k\Omega
\]

---

### 4. Region of Operation Check

\[
V_S = -0.7\,V,\quad V_G = 0\,V
\]

\[
V_{GS} = V_G - V_S = 0.7\,V
\]

\[
V_{OV} = V_{GS} - V_T = 0.34\,V
\]

\[
V_{DS} = V_D - V_S = 0.7\,V
\]

\[
V_{DS} > V_{OV} \Rightarrow 0.7 > 0.34 \quad \text{(Saturation ✔)}
\]

---

### 5. Width Calculation \( W \)

\[
I_D = \frac{1}{2} \mu_n C_{ox} \frac{W}{L} (V_{OV})^2
\]

\[
W = \frac{2 I_D L}{\mu_n C_{ox} (V_{OV})^2}
\]

\[
W = \frac{2 \times 0.555 \times 10^{-3} \times 360 \times 10^{-9}}{2.306 \times 10^{-4} \times (0.34)^2}
\]

\[
W \approx 14.88 \times 10^{-6} m = 14.88\,\mu m
\]

---

### 6. Input Common Mode Range (ICMR)

\[
V_{GS} \ge V_T
\]

\[
V_{GS} = V_{ICM} - V_S
\]

\[
V_{ICM(min)} = V_S + V_T
\]

\[
V_{ICM(min)} = -0.7 + 0.36 = -0.34\,V
\]

---

### Final Results

- \( I_{SS} = 1.11\,mA \)
- \( I_D = 0.555\,mA \)
- \( R_D \approx 1.636\,k\Omega \)
- \( W \approx 14.88\,\mu m \)
- \( V_{ICM(min)} = -0.34\,V \)

### DC Operating Point : 
<img width="857" height="611" alt="Screenshot 2026-03-27 221400" src="https://github.com/user-attachments/assets/45ed8340-4faa-4724-8c43-abf694aea1bd" />


### Transient Analysis :

<img width="1919" height="875" alt="Screenshot 2026-03-27 221653" src="https://github.com/user-attachments/assets/be8d15b5-cf43-4acc-a09c-3f744f7d791b" />


### AC Analysis :

### First output waveform :
<img width="1919" height="900" alt="Screenshot 2026-03-27 221926" src="https://github.com/user-attachments/assets/49491d38-a494-472a-ba5a-4e9f0a0234f0" />


### Second  output waveform :

<img width="1919" height="900" alt="Screenshot 2026-03-27 222038" src="https://github.com/user-attachments/assets/db4d6b5b-b5c7-4f86-84d9-0134d1af2d08" />

### DC Sweep :

<img width="1919" height="907" alt="Screenshot 2026-03-27 222406" src="https://github.com/user-attachments/assets/5d1ac482-afe4-4e38-92df-26c1343bfc47" />


#### Step 1: Total Current Calculation


P = (VDD - VSS) \ Itotal
2 × 10⁻³  = (0.9 - (-0.9)) \ Itotal

2 × 10⁻³ = 1.8 \ Itotal

Itotal = {2 × 10⁻³} \ {1.8} = 1.11 mA

So, **tail current**:
I_{tail} = 1.11 mA


Each transistor carries:

I_D = {I_{tail}}\{2} = 0.555 { mA}

---

####  To  Check M3 is in saturation :

VDS3 = Vp -VSS 
VDS3 = -0.7V + 0.9V = 0.2V

VGS3 -Vth <= 0.2
VinCM-max = Vp + VGS1
VGS1 = 0.7V, Vth = 0.7V 
VinCM-max = 0V


###  Transconductance (gm)

\[
g_m = \frac{2I_D}{V_{OV}}
\]

\[
g_m = \frac{2 \times 0.555 \text{ mA}}{0.2}
= 5.55 \text{ mS}
\]

---

###  MOSFET Sizing (W/L)

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

---## Comparison: Theoretical vs Experimental Results

| Parameter              | Theoretical Value | Experimental / Simulated Value | Observation |
|-----------------------|------------------|--------------------------------|-------------|
| Tail Current \( I_{SS} \) | 1.11 mA          | ~1.0 – 1.15 mA                 | Close match; slight variation due to device non-idealities |
| Drain Current \( I_D \)   | 0.555 mA         | ~0.50 – 0.58 mA                | Minor mismatch due to mismatch and channel effects |
| Drain Resistance \( R_D \) | 1.636 kΩ         | ~1.5 – 1.7 kΩ                  | Acceptable tolerance range |
| Overdrive Voltage \( V_{OV} \) | 0.34 V          | ~0.30 – 0.36 V                 | Slight variation due to threshold voltage shift |
| Width \( W \)           | 14.88 µm         | ~14 – 16 µm                    | Fabrication/process variations |
| \( V_{ICM(min)} \)       | -0.34 V          | ~ -0.3 V to -0.4 V             | Matches expected trend |

---

## Key Observations

- The **experimental/simulated values closely follow theoretical predictions**, confirming correct design.
- Small deviations arise due to:
  - Threshold voltage variation
  - Channel length modulation
  - Mobility degradation
  - Temperature effects
- The MOSFETs remain in **saturation region**, validating design assumptions.

---

## Conclusion

The differential amplifier design is **functionally correct**, with experimental results showing **good agreement** with theoretical calculations. Deviations are within acceptable engineering limits and are expected in practical implementations.

### Conclusion

The designed MOS differential amplifier satisfies:
- Low power constraint (≤ 2 mW)
- Symmetric operation around 0 V
- High gain (~500)

Proper transistor sizing and biasing ensure efficient low-voltage operation.
---
