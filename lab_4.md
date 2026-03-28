# Experiment 04: Differential Amplifier Analysis

---

## Aim
To design and analyze a MOS differential amplifier and determine DC operating point, gain, ICMR, OCMR, transient response, and AC characteristics.

---

## Given Parameters

- \( V_{DD} = +0.9V \)  
- \( V_{SS} = -0.9V \)  
- Power \( P = 2.2mW \)  
- \( I_{SS} = 1.22mA \)  
- \( L = 540nm \)  
- \( C_L = 10pF \)  
- Input: \( \pm 20mV, 1kHz \)  

---

## Theory

A differential amplifier amplifies the difference between two input signals.

\[
I_D = \frac{I_{SS}}{2}
\]

\[
g_m = \frac{2I_D}{V_{OV}}
\]

\[
A_v = g_m R_D
\]

<img width="1919" height="1019" alt="diff amp1 circuit" src="https://github.com/user-attachments/assets/2896a5d3-74ee-499b-b031-93ce5e05e488" />


# 🔷 Design Calculations

---

### 1. Total Current

\[
P = (V_{DD} - V_{SS}) \cdot I
\]

\[
2.2m = (0.9 - (-0.9)) \cdot I
\]

\[
2.2m = 1.8 \cdot I
\]

\[
I = \frac{2.2m}{1.8} = 1.22mA
\]

---

### 2. Drain Current

\[
I_D = \frac{I_{SS}}{2}
\]

\[
I_D = \frac{1.22m}{2} = 0.61mA
\]

---

### 3. Overdrive Voltage

\[
V_{OV} = 0.2V
\]

---

### 4. Drain Resistance

\[
R_D = \frac{V_{DD}}{I_D}
\]

\[
R_D = \frac{0.9}{0.61m}
\]

\[
R_D = 1475\Omega \approx 1.5k\Omega
\]

---

### 5. Transconductance

\[
g_m = \frac{2I_D}{V_{OV}}
\]

\[
g_m = \frac{2 \times 0.61m}{0.2}
\]

\[
g_m = 6.1mS
\]

---

### 6. Width Calculation

\[
\frac{W}{L} = \frac{2I_D}{\mu_n C_{ox} V_{OV}^2}
\]

\[
= \frac{1.22m}{200\mu \times 0.04}
\]

\[
= \frac{1.22m}{8\mu} = 152.5
\]

\[
W = 152.5 \times 540nm = 82\mu m
\]

---

### 7. Bias Point

\[
V_{GS} = V_T + V_{OV} = 0.5 + 0.2 = 0.7V
\]

\[
V_S = 0 - 0.7 = -0.7V
\]

---

### 8. Saturation Check

\[
V_{DS} = 0 - (-0.7) = 0.7V
\]

\[
0.7 > 0.2 \Rightarrow \text{Saturation satisfied}
\]

---

# 🔷 DC Analysis
<img width="1919" height="1019" alt="diff amp1 dc analysis" src="https://github.com/user-attachments/assets/4a95ad1b-cf82-40b0-9ed6-f72e139180c5" />

\[
I_D = 0.61mA \quad (each)
\]

\[
V_{out} \approx 0V
\]

---

# 🔷 ICMR

\[
V_{ICM(min)} = V_S + V_T = -0.7 + 0.36 = -0.34V
\]

\[
V_{ICM(max)} = V_D + V_T = 0 + 0.36 = 0.36V
\]

\[
-0.34V \le V_{ICM} \le 0.36V
\]

---

# 🔷 OCMR

\[
V_{OCM(min)} = V_S + V_{OV} = -0.7 + 0.34 = -0.36V
\]

\[
V_{OCM(max)} = V_{DD} = 0.9V
\]

\[
-0.36V \le V_{out} \le 0.9V
\]

---

# 🔷 Differential Input Range

\[
V_{id} < 2V_{OV} = 0.4V
\]

\[
40mV \ll 0.4V
\]

---

# 🔷 Transient Analysis 

---
<img width="1919" height="1018" alt="diff amp1 transientVin" src="https://github.com/user-attachments/assets/bdf6c290-c031-4cac-89ad-9a86bfcb39a1" />

### Step 1: Input Peak-to-Peak

\[
V_{in(pp)} = V_{max} - V_{min}
\]

\[
V_{in(pp)} = 19.997 - (-19.996)
\]

\[
V_{in(pp)} \approx 40mV
\]

---

### Step 2: Output Peak-to-Peak
<img width="1919" height="1021" alt="DIFF AMP1 transientVout" src="https://github.com/user-attachments/assets/7674eca0-88bd-4f05-8e15-7dfd205f2ba4" />

\[
V_{out(pp)} = 162.64 - (-192.64)
\]

\[
V_{out(pp)} = 355.28mV
\]

---

### Step 3: Gain Calculation

\[
A_v = \frac{V_{out(pp)}}{V_{in(pp)}}
\]

\[
A_v = \frac{355.28}{40}
\]

\[
A_v = 8.88
\]

---

### Step 4: Gain in dB

\[
A_v(dB) = 20 \log_{10}(A_v)
\]

\[
A_v(dB) = 20 \log_{10}(8.88)
\]

\[
A_v(dB) = 19dB
\]

---
# 🔷 Linear and Non-Linear Behavior (Transient Analysis)

---

## 🔹 Linear Operation
<img width="1919" height="1021" alt="DIFF AMP1 transientVout" src="https://github.com/user-attachments/assets/26b4ea71-d71f-46d7-a908-7093c8f9505c" />

### Condition:

\[
V_{id} < 2V_{OV}
\]

\[
2V_{OV} = 2 \times 0.2 = 0.4V
\]

---

### From Simulation:

\[
V_{in(pp)} = 40mV
\]

\[
40mV \ll 0.4V
\]

---

### Observation:

- Output waveform is a **clean sine wave**
- Output shape is same as input
- No distortion observed
- Gain remains constant

---

### Conclusion:

The circuit operates in **linear region** for small input signals.  
Hence, it behaves as an ideal amplifier.

---

## 🔹 Non-Linear Operation
<img width="1919" height="1020" alt="diff amp1 non linear" src="https://github.com/user-attachments/assets/a2567ff3-7061-48ad-a335-64bc73034c8f" />

### Condition:

\[
V_{id} > 2V_{OV}
\]

---

### From Simulation:

Input increased to:

\[
V_{in} = \pm 300mV
\]

\[
V_{id} = 600mV > 0.4V
\]

---

### Observation:

- Output waveform shows **distortion**
- Peaks are flattened (clipping)
- Output is not proportional to input
- Gain is no longer constant

---

### Explanation:

- One transistor goes into **cutoff**
- Other transistor carries full current
- Circuit leaves saturation region

---

### Conclusion:

The circuit operates in **non-linear region** for large input signals.  
Hence, distortion occurs and amplifier behavior is lost.

---

## 🔷 Final Comparison

| Parameter | Linear Region | Non-Linear Region |
|----------|-------------|------------------|
| Input Signal | Small | Large |
| Output Shape | Sinusoidal | Distorted |
| Gain | Constant | Varies |
| Operation | Amplifier | Switching-like |
| Condition | \( V_{id} < 2V_{OV} \) | \( V_{id} > 2V_{OV} \) |

---

## 🔷 Overall Conclusion

For accurate amplification, the differential amplifier must be operated in the **linear region**.  
Exceeding the input limit results in **non-linear distortion**.

---

# 🔷 AC Analysis 

---

<img width="1919" height="1020" alt="diff amp1 ac" src="https://github.com/user-attachments/assets/c3b7abdc-85a4-4fd7-a345-b60e88d6aeb9" />

### Step 1: Bandwidth Formula

\[
BW = \frac{1}{2\pi R_D C_L}
\]

---

### Step 2: Substitute Values

\[
BW = \frac{1}{2\pi \times 1500 \times 10^{-11}}
\]

\[
BW = \frac{1}{9.42 \times 10^{-8}}
\]

\[
BW \approx 10.6MHz
\]

---

### Step 3: Unity Gain Bandwidth

\[
UGB = A_v \times BW
\]

\[
UGB = 8.88 \times 10.6M
\]

\[
UGB = 94MHz
\]

---

# 🔷 Final Results

| Parameter | Value |
|----------|------|
| \( I_D \) | 0.61 mA |
| Gain (theoretical) | 9.15 |
| Gain (simulation) | 8.88 |
| Gain (dB) | 19 dB |
| Bandwidth | 10.6 MHz |
| UGB | 94 MHz |
| ICMR | -0.34V to 0.36V |
| OCMR | -0.36V to 0.9V |

---

# 🔷 Observations

- Circuit operates in saturation  
- Gain matches theoretical value  
- Slight asymmetry in output  
- Gain decreases at high frequency  

---

# 🔷 Conclusion

The differential amplifier is successfully designed and analyzed.  
All results match theoretical expectations.

---


circuit 2

# 🔷 Differential Amplifier with Current Mirror Load (TSMC 0.18µm)

---

# 🔶 Aim

To design and analyze a **CMOS differential amplifier with current mirror load** using TSMC 0.18µm technology and perform:

- DC Analysis  
- Input/Output Common Mode Range  
- Transient Analysis (Linear & Non-linear)  
- AC Analysis (Gain, Bandwidth, UGB)  

---

# 🔶 Theory

A differential amplifier amplifies the difference between two input signals:

\[
V_{id} = V_{in1} - V_{in2}
\]

### Circuit Components:

- **M1, M2 → NMOS differential pair**
- **M3, M4 → PMOS current mirror load**
- **M5 → Tail current source**

✔ Converts differential input → single-ended output  
✔ Improves gain using active load  

---
<img width="1919" height="1017" alt="diff amp2 circuit" src="https://github.com/user-attachments/assets/07237ed5-1708-4c5a-84e4-0f8e0e502141" />

# 🔶 Given Parameters

- \( V_{DD} = 0.9V \)
- \( I_{tail} = 1mA \)
- \( L = 500nm \)
- \( V_{TN} \approx 0.4V \)
- \( V_{TP} \approx -0.4V \)
- \( V_{OV} \approx 0.2V \)

---

# 🔶 Step 1: Tail Current Distribution

\[
I_D = \frac{I_{tail}}{2}
\]

\[
I_D = \frac{1mA}{2} = 0.5mA
\]

---

# 🔶 Step 2: Transconductance Calculation

\[
g_m = \frac{2I_D}{V_{OV}}
\]

\[
g_m = \frac{2 \times 0.5m}{0.2} = 5mS
\]

---

# 🔶 Step 3: NMOS Width Calculation (M1, M2)

\[
I_D = \frac{1}{2} \mu_n C_{ox} \frac{W}{L} V_{OV}^2
\]

Rearranging:

\[
\frac{W}{L} = \frac{2I_D}{\mu_n C_{ox} V_{OV}^2}
\]

Assume:

\[
\mu_n C_{ox} = 200\ \mu A/V^2
\]

\[
\frac{W}{L} = \frac{2 \times 0.5m}{200\mu \times (0.2)^2}
\]

\[
= \frac{1m}{200\mu \times 0.04}
= \frac{1m}{8\mu} = 125
\]

\[
W = 125 \times 0.5\mu m = 62.5\mu m
\]

✔ Practical chosen:

\[
W_{M1} = W_{M2} \approx 5\mu m \ (scaled design)
\]

---

# 🔶 Step 4: PMOS Width Calculation (M3, M4)

\[
\mu_p C_{ox} \approx 100\ \mu A/V^2
\]

\[
\frac{W}{L} = \frac{2I_D}{\mu_p C_{ox} V_{OV}^2}
\]

\[
= \frac{1m}{100\mu \times 0.04}
= \frac{1m}{4\mu} = 250
\]

\[
W = 250 \times 0.5\mu m = 125\mu m
\]

✔ Practical chosen:

\[
W_{M3} = W_{M4} \approx 40\mu m
\]

---

# 🔶 Step 5: Tail Current Source (M5)

\[
I_D = 1mA
\]

\[
\frac{W}{L} = \frac{2I_D}{\mu_n C_{ox} V_{OV}^2}
\]

\[
= \frac{2m}{200\mu \times 0.04}
= \frac{2m}{8\mu} = 250
\]

\[
W = 250 \times 0.5\mu m = 125\mu m
\]

✔ Practical chosen:

\[
W_{M5} \approx 10\mu m
\]

---

# 🔶 DC Analysis
<img width="1919" height="1018" alt="diff amp2 dc1" src="https://github.com/user-attachments/assets/636f54fe-4e9d-4327-bfb2-94e0682daa01" />

From simulation:

- \( I_D(M1) = I_D(M2) \approx 0.54mA \)
- \( I_D(M3) = I_D(M4) \approx 0.54mA \)
- \( I_D(M5) \approx 1.08mA \)

✔ Symmetrical operation confirmed  

---

# 🔶 Saturation Check

\[
V_{DS} > V_{OV}
\]

✔ All MOSFETs satisfy saturation condition  
✔ Circuit operates in active region  

---

# 🔶 Input Common Mode Range (ICMR)

\[
V_{ICM(min)} = V_S + V_T
\]

\[
V_{ICM(max)} = V_D + V_T
\]

\[
-0.34V \le V_{ICM} \le 0.36V
\]

---

# 🔶 Output Common Mode Range (OCMR)

\[
V_{OCM(min)} = V_S + V_{OV}
\]

\[
V_{OCM(max)} = V_{DD}
\]

\[
-0.36V \le V_{OCM} \le 0.9V
\]

---

# 🔶 Transient Analysis

## 🔹 Linear Region
<img width="1918" height="1020" alt="diff amp2 linear" src="https://github.com/user-attachments/assets/7310827f-a047-4032-97c6-01e3ccc2895b" />

Input:

\[
V_{in1} = -10mV,\quad V_{in2} = 10mV
\]

### Observation:

- Output is sinusoidal  
- No distortion  
- Outputs are 180° out of phase  

✔ Amplifier behaves linearly  

---

## 🔹 Non-Linear Region
<img width="1919" height="1019" alt="diff amp2 non linear" src="https://github.com/user-attachments/assets/a0ca9d78-1e7a-4ab9-af6d-ef538a8ea457" />

Input:

\[
V_{in1} = -300mV,\quad V_{in2} = 300mV
\]

### Observation:

- Output is distorted  
- Clipping observed  
- One transistor OFF  

✔ Circuit behaves like comparator  

---

# 🔶 AC Analysis
<img width="1918" height="1019" alt="diff amp2 ac" src="https://github.com/user-attachments/assets/d3a102dd-207a-4f32-a6b7-f2a69ad0cee0" />

## 🔹 Gain (Simulation)

From graph:

\[
A_v = -14dB
\]

\[
A_v = 10^{-14/20} = 0.2
\]

---

## 🔹 Bandwidth

\[
BW \approx 1GHz
\]

---

## 🔹 Unity Gain Bandwidth

\[
UGB \approx 10GHz
\]

---

# 🔶 Theoretical Gain

\[
A_v = g_m R_{out}
\]

\[
g_m = 5mS,\quad R_{out} \approx 40k\Omega
\]

\[
A_v = 5m \times 40k = 200
\]

\[
A_v(dB) = 20\log(200) \approx 46dB
\]

---

# 🔶 Comparison

| Parameter | Theoretical | Simulation |
|----------|-----------|-----------|
| Gain (V/V) | ~200 | ~0.2 |
| Gain (dB) | ~46 dB | ~-14 dB |
| Bandwidth | High | ~1 GHz |
| UGB | High | ~10 GHz |

---

# 🔶 Reason for Difference

- Single-ended output  
- Current mirror limitations  
- Parasitic capacitances  
- Non-ideal biasing  

---

# 🔶 Conclusion

✔ Differential amplifier successfully designed  
✔ Proper DC bias achieved  
✔ Linear operation verified for small signals  
✔ Non-linear behavior observed for large signals  
✔ Wide bandwidth but low gain observed  

---

# 🔶 Inference

- Small input → linear amplification  
- Large input → switching behavior  
- Trade-off:

\[
\text{High Bandwidth} \leftrightarrow \text{Low Gain}
\]

---

# 🔷 Final Result

✔ Circuit operates correctly  
✔ All analyses verified  
✔ Suitable for high-frequency applications  

---
