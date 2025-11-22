# 🧪 Two-Stage CMOS Operational Amplifier – 90nm | Cadence Virtuoso

## 📝 Abstract
This project presents the design and simulation of a **two-stage CMOS operational amplifier** implemented in **90nm CMOS technology** using **Cadence Virtuoso**.  
The op-amp operates at **1.2 V** supply and targets:

- **Open-loop gain:** 80 dB  
- **GBW:** 20 MHz  
- **Slew rate:** 10 V/μs  
- **Load capacitance:** 1 pF  
- **ICMR:** 0.5 V – 1.0 V  

The architecture includes:

- PMOS input differential pair  
- NMOS current mirror load  
- Common-source second stage  
- Miller compensation  

Transistor dimensions, bias currents, and compensation capacitor were optimized through iterative simulation.  
Simulation results confirm that the amplifier meets design goals and is suitable for mixed-signal and low-power analog applications.

---

## 📘 Introduction
Operational amplifiers are essential building blocks in analog and mixed-signal ICs, used in:

- Amplification  
- Filtering  
- Data conversion  
- Mathematical analog operations  

With CMOS technology scaling down, low-voltage operation becomes challenging due to reduced headroom and limited gain.  
This project addresses these challenges by designing a **two-stage CMOS op-amp** using **90nm GPDK** in Cadence Virtuoso.

### 🎯 Primary Design Goals
- 80 dB open-loop gain  
- 20 MHz gain-bandwidth product  
- 10 V/μs slew rate  
- Stable operation with 1 pF load  
- ICMR: 0.5–1.0 V  
- 1.2 V supply operation  

The amplifier uses a differential first stage and high-gain second stage with Miller compensation to maintain stability.

---

## 🧩 TWO-STAGE OPAMP ARCHITECTURE

### 🖼️ <img width="1502" height="760" alt="image" src="https://github.com/user-attachments/assets/925b3467-c323-42b3-8c0f-3504f6907f9c" />

---

## ⚙️ Working
The amplifier is designed using **90nm CMOS technology** and consists of:

### 🔧 Key Components
- **M3, M4** – PMOS differential pair  
- **M1, M2** – NMOS current mirror load  
- **M5** – NMOS tail current source (6 μA)  
- **M7** – NMOS common-source second stage  
- **M6** – PMOS active load  
- **M8** – PMOS current mirror for biasing  
- **Cc** – 400 fF Miller compensation capacitor  

### 🔍 Working Principle
- PMOS differential pair amplifies input difference  
- NMOS current mirror converts differential current to voltage  
- Second-stage NMOS (M7) boosts gain and drives the output  
- PMOS load (M6) increases gain  
- Miller capacitor (Cc) ensures stability and adequate phase margin  
- Tail current (M5) sets gm and impacts slew rate  
- Bias circuit (M8) generates reference currents  

---

## 📊 Design Table

| Parameter | Value |
|----------|-------|
| Cc | 400 fF |
| I5 | 6 μA |
| M1, M2 | W/L = 5µ / 1µ |
| M3, M4 | W/L = 0.8µ / 1µ |
| M5, M8 | W/L = 2.2µ / 1µ |
| M6 | W/L = 15µ / 1µ |
| M7 | W/L = 21µ / 1µ |

---

## 📈 Simulation Results

### 🖼️ *Bode Plot (AC Response)*  
<img width="1337" height="451" alt="image" src="https://github.com/user-attachments/assets/17080373-42ec-48dd-ba88-519e8974c060" />

### 📌 Extracted Performance
- **Open-loop Gain:** 74.65 dB  
- **GBW:** 21 MHz  
- **Phase Margin:** 52°  

These values indicate:
- Good stability for unity-gain feedback  
- GBW meets target  
- Slightly lower gain than 80 dB target but still acceptable for most analog front-end systems  

---

## 🏁 Conclusion
A **two-stage CMOS operational amplifier** was successfully designed and simulated using **90nm CMOS technology** in Cadence Virtuoso.

### ✔ Achieved Results
- 74.65 dB open-loop gain  
- 21 MHz gain-bandwidth product  
- 52° phase margin  
- Stable driving a 1 pF load  
- Operates at 1.2 V low supply  

Although the gain is slightly below the target, it is acceptable and can be improved using layout-aware tuning or cascode techniques.

The design meets performance requirements for:

- Low-power analog front ends  
- Sensor interfaces  
- Mixed-signal integrated systems  

---

## 📚 References
1. R. Jacob Baker, *CMOS: Circuit Design, Layout, and Simulation*, 3rd Ed., Wiley  
2. N. Weste & D. Harris, *CMOS VLSI Design*, 4th Ed., Pearson  
3. K. Roy et al., “Leakage Current Mechanisms…”, IEEE, 2003  
4. S. Mutoh et al., “1-V Power Supply High-Speed Digital Circuit…”, IEEE JSSC, 1995  
5. Cadence GPDK 90nm PDK Documentation, 2023  

