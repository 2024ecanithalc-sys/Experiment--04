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

---
v_{a} = - a * q P <= 2m*omega V DD * 0.5 =0.9 gamma s Vin CMOV, V DCM =0 V V_{T} =0.36.N rho=(V 00 -V xz ) Iss = 9 - (0.9) * I rc <=8mw ( - 8x*J_{35} <= 9mW J_{5} = 1.11mA I D1 =I 0.2 = J 11 Delta in0.56 mOA J 4 = 3200*10^ -3 -= 1.11 * 1a ^ - 3 * 4 1*8 V_{f} = - 0.7V

Vout Vop-Jo Ro = 0 = 0.9 - JoRo

J_{D}*R_{D} = 0.9 R_{D} = 0.9 = 66363 * 10 ^ 3 * 55 * 10 ^ - 3 = 16.36 * 0.3 * 0.52 \approx  1636Omega V inc*mu = 0v G V onl =V on2 =oV V_{L} = - 0.7V v OS =V G -V S =0+0.7=0.7v V D =V OL5 - V_{T} = 0.7 - 0.36 = 0.39V V DS =V D -V S =0-(-0.7V)=0.7V

v DS >V 0V Rightarrow0.7*0.39V v_{1} = 0v v_{5} = - 0.7V V_{D} = 0V , v ONS =0.7v.v PS =0.7v

width -

J D = 1 2 ln( 6pi * u/L (V OS -v T )^ 2 = (396 * 10 ^ - 102)/0.266 = 1.4 * 0.81 * 10 ^ - 9 * 10 ^ 4 0.266 =14.87*10^ -6 = 14 * 88.19m w= 9I 0 L mu_{h}*C_{0}*x * (V, v) ^ 2 = (2 * 0.456 * 10 ^ - 3 * 360 * 10 ^ - 9)/(2.306 * 1n ^ - 4 * (0.34) * 2) 8.306 * 10 ^ - 4 * (0.34) ^ 2

ICMR

V G, S >= V t V OS =8V JCM -V S , v fCM * mu ^ 0 =v CS +v T Vs -0.70, W = 0.36V U ICMmio = - 0.7 + 0.36 = - 0.34V


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

#### Step 2: To  Check M3 is in saturation :

VDS3 = Vp -VSS 
VDS3 = -0.7V + 0.9V = 0.2V

VGS3 -Vth <= 0.2
VinCM-max = Vp + VGS1
VGS1 = 0.7V, Vth = 0.7V 
VinCM-max = 0V




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
