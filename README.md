### 1. **NMOS I–V Characteristics (Id vs. Vds Analysis)**

In this experiment, an **NMOS transistor** was simulated by varying the **drain-to-source voltage (Vds)** across multiple fixed values of **gate-to-source voltage (Vgs)**. The resulting **Id–Vds curves** were plotted to understand the **device operation regions**:

* **Linear (Ohmic) Region**: When Vds is small and **Vds < (Vgs − Vth)**, the MOSFET behaves like a **voltage-controlled resistor**, showing a nearly linear increase in current.
* **Saturation Region**: When **Vds ≥ (Vgs − Vth)**, the channel gets pinched off near the drain, and **Id becomes almost constant**, indicating **current saturation**.

This study helps in understanding **how MOS transistors behave under different biasing conditions**, which is crucial for **analog circuits and current mirrors**.

---

### 2. **Threshold Voltage Extraction & Velocity Saturation**

A **Vgs vs. Id sweep** was conducted by gradually increasing the **input gate voltage** while monitoring the drain current. The **threshold voltage (Vth)** was extracted using **linear extrapolation** on the semi-log Id-Vgs plot, estimating the point where the MOSFET begins strong inversion.

Additionally, **short-channel effects** were observed:

* In longer devices, **Id increases quadratically** (as per square-law model).
* In **deep submicron-length MOSFETs**, **carrier velocity saturates** at high electric fields, causing a deviation from quadratic behavior. This effect is known as **velocity saturation**, leading to **lower gain and reduced current drive**.

---

### 3. **CMOS Inverter Static Response – Voltage Transfer Characteristic (VTC)**

A **complementary CMOS inverter** was constructed using one PMOS (connected to Vdd) and one NMOS (connected to ground). By sweeping the input voltage from 0 to Vdd, the **transfer curve (Vout vs. Vin)** was plotted.

Key observations:

* At **low Vin**, NMOS is OFF and PMOS is ON → **Vout ≈ Vdd** (Logic High).
* At **high Vin**, NMOS is ON and PMOS is OFF → **Vout ≈ 0V** (Logic Low).
* The **switching threshold (Vm)** occurs at **Vin ≈ Vout**, indicating the point where both transistors conduct simultaneously.

This midpoint determines the **logic robustness** and **symmetry of inverter performance**.

---

### 4. **Transient Analysis – Propagation Delay Estimation**

A **square pulse input** was applied to the inverter, and the **output response** was monitored. Two important timing parameters were extracted:

* **tpLH (Low-to-High delay)** – Time taken for output to rise from LOW to HIGH when input switches from HIGH to LOW.
* **tpHL (High-to-Low delay)** – Time taken for output to fall from HIGH to LOW when input switches from LOW to HIGH.

Both delays were measured at the **50% Vdd crossing point** to ensure consistency.

Observation: Since **PMOS has lower mobility**, rise delay is usually **greater than fall delay**, unless **PMOS is made wider (Wp > Wn)**.

---

### 5. **Noise Margin Calculation – Signal Integrity Study**

From the VTC curve, the following critical voltage parameters were extracted:

* **VOL**: Maximum output voltage recognized as logic LOW
* **VOH**: Minimum output voltage recognized as logic HIGH
* **VIL**: Maximum input voltage still considered as LOW
* **VIH**: Minimum input voltage still considered as HIGH

Using these values:

* **Noise Margin (Low):**
  `NML = VIL − VOL`
* **Noise Margin (High):**
  `NMH = VOH − VIH`

Higher **noise margins** indicate **better immunity to input fluctuations and interference**, ensuring **reliable digital operation**.

---

### 6. **Device & Supply Variation Analysis**

To study **robustness**, simulations were repeated under **two variation scenarios**:

1. **Supply Voltage Variation**:

   * VTC was re-plotted for **different Vdd values** (e.g., 0.8V, 1V, 1.2V).
   * Observation: **Lower Vdd reduces switching speed** and **shifts Vm**, affecting noise margins.

2. **Transistor Sizing Variation**:

   * PMOS and NMOS **W/L ratios were modified** (e.g., increasing PMOS width).
   * A wider PMOS resulted in **faster rising edges** and **more symmetric VTC curves**, since PMOS compensates for its **lower carrier mobility**.

This analysis reflects **how real-world PVT (Process-Voltage-Temperature) variations influence digital circuits**.

---

### 1. **day1_nfet_idvds_L2_W5.spice**
![WhatsApp Image 2025-10-18 at 19 59 59_7d946dff](https://github.com/user-attachments/assets/841bc98f-7636-43f0-9523-bf865d0e0b27)

---

### 2. **day2_nfet_idvgs_L015_W039.spice**
![WhatsApp Image 2025-10-18 at 19 59 59_c28bfbd1](https://github.com/user-attachments/assets/084537df-963d-4f50-acae-5748c2940178)

---

### 2 (2) **day2_nfet_idvds_L015_W039.spice**
![WhatsApp Image 2025-10-18 at 21 02 00_0154bea4](https://github.com/user-attachments/assets/be619e2f-f943-4293-8988-fd6a0f8aac00)

---

### 3. **day3_inv_vtc_Wp084_Wn036.spice**
![WhatsApp Image 2025-10-18 at 21 08 37_6f29e5d2](https://github.com/user-attachments/assets/4ebda3dd-59c9-4507-9e14-8fbb6a0efd19)

---

### 3(2). **day3_inv_tran_Wp084_Wn036.spice**
![WhatsApp Image 2025-10-18 at 21 13 31_2cf3c616](https://github.com/user-attachments/assets/bbc108d8-8775-457e-8b99-3619aad86bb7)

---

### 4. **day4_inv_noisemargin_wp1_wn036.spice**
![WhatsApp Image 2025-10-18 at 21 19 54_147e2673](https://github.com/user-attachments/assets/a188df3e-370d-4d88-b537-f6e9b102c191)

---

### 5. **day5_inv_supplyvariation_Wp1_Wn036.spice**
<img width="1300" height="854" alt="image" src="https://github.com/user-attachments/assets/4c6fde88-b27f-4afc-9353-a42e3959db6f" />













