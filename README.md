**Active Low-Pass Filter (Sallen--Key) Using TLV9061**
=====================================================

### *Designed by Arijit Mandal*

This repository contains the full KiCad project, schematic, PCB design, and supporting documentation for a **2nd-order active low-pass filter** based on the **TLV9061** high-performance CMOS op-amp.\
The filter is implemented in a **unity-gain Sallen--Key topology**, optimized for clean analog signal conditioning.

* * * * *

📘 **Project Overview**
-----------------------

This project implements a precision **Active Low Pass Filter (LPF)** suitable for:

-   Sensor signal conditioning

-   Noise filtering in embedded electronics

-   General analog experimentation

The LPF is centered around the **TLV9061**, a modern rail-to-rail, low-noise, high-bandwidth CMOS operational amplifier from Texas Instruments.
![Image Alt Text](https://github.com/arijitmandal2006/Active-LPF/blob/main/3D%20%20front%20view%20of%20Active%20LPF%20PCB.png?raw=true)


A complete KiCad schematic is shown in **page 1 of the submitted schematic PDF**
**Filter Characteristics**
--------------------------

-   **Topology:**  2nd Order

-   **Configuration:** Unity-gain

-   **Cutoff Frequency (fc):** ~1 kHz (based on selected RC values)

-   **Supply Options:**

    -   **Single-Supply:** +5 V

    -   **Dual-Supply:** +5 V / --5 V

-   **Input Type:** Single-ended AC input

-   **Output Type:** Buffered, low-impedance analog output

* * * * *

📐 **Circuit Diagram**
----------------------
The circuit schematic includes:

<img width="1999" height="1545" alt="image" src="https://github.com/user-attachments/assets/ac23512f-eecd-4c17-b419-717dab845f72" />

-   A AC test source

-   RC network (R1, R2, C1, C2) 

-   TLV9061 op-amp with VCC, VEE, and ground

-   Input/output connectors

-   Proper PWR_FLAG usage for clean KiCad ERC.

| Component | Value | Footprint | Notes |
| --- | --- | --- | --- |
| **R1** | 13 kΩ | Axial | Forms RC time constant |
| **R2** | 9.53 kΩ | Axial | Improves Q factor |
| **C1** | 20.5 nF | Axial / radial  | Feedback capacitor |
| **C2** | 10 nF | Axial  | Shunt-to-ground capacitor |
| **U1** | **TLV9061** | SOT-23-5 | Rail-to-rail precision op-amp |
| **Connectors** | VIN / VCC / VEE / OUT | Pin Header 2.54 mm | For easy prototyping |
---------------------------------
⚡ **TLV9061 --- Key Specifications**
----------------------------------

**General**

-   Single-channel CMOS op-amp

-   Rail-to-rail input and output

-   Supply range: **1.8 V to 5.5 V** (single-supply)

-   Slew rate: **6.5 V/µs**

-   Gain bandwidth (GBW): **10 MHz**

-   Noise: **10.5 nV/√Hz** at 1 kHz

**Electrical**

-   Input offset voltage: **±150 µV (typ.)**

-   Output current: **±75 mA**

-   Input bias current: **±1 pA (typ.)**

-   Quiescent current: **180 µA (typ.)**

**Why TLV9061 is ideal for this LPF:**

-   High-speed and low-noise response improves filter accuracy

-   Rail-to-rail I/O supports low-voltage operation

-   Stable in unity-gain configuration (critical for Sallen--Key)

-   Small SOT-23-5 package suits compact analog boards
-   <img width="1999" height="1545" alt="image" src="https://github.com/user-attachments/assets/9ff153b0-666e-4afd-87cb-82d0230f30a0" />
----------------------------------------
🚀 **How to Use the Board**
---------------------------

### 1\. **Power the Board**

Choose one of:

-   **Single supply:**

    `VCC = +5 V
    VEE = GND`

-   **Dual supply:**

    `VCC = +5 V
    VEE = --5 V`

### 2\. **Connect Input Signal**

Use the VIN header:

`Signal → VIN
Ground → GND`

### 3\. **Read the Filtered Output**

Use the OUT header:

`Filtered signal → OUT
Return → GND`
----------------------
