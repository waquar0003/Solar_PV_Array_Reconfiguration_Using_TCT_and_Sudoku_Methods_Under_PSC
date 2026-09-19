# Solar PV Array Reconfiguration Using TCT and Sudoku Methods Under Partial Shading Conditions

##  Project Overview

This project focuses on the MATLAB/Simulink modeling and comparative analysis of **Total Cross-Tied (TCT)** and **Sudoku-based PV array configurations** under Partial Shading Conditions (PSC).

Partial shading occurs when different PV modules receive different levels of solar irradiance due to obstacles, clouds, or other environmental conditions. It can cause mismatch losses and multiple peaks in the Power–Voltage (P–V) characteristics, making maximum power extraction more challenging.

The main objective of this project is to investigate how Sudoku-based shade dispersion affects the power output of a PV array compared with a conventional TCT configuration under different shading patterns.

The simulation is inspired by research on Sudoku-based PV array shade dispersion and evaluates both configurations under four partial shading scenarios.

---

##  Project Objectives

* Develop a 9×9 Solar PV array model in MATLAB/Simulink.
* Implement conventional Total Cross-Tied (TCT) and Sudoku-based PV array configurations.
* Apply different irradiance matrices to simulate partial shading.
* Analyze the current, voltage, and power characteristics of both configurations.
* Compare the P–V characteristics under four shading patterns: Short Wide (SW), Long Wide (LW), Short Narrow (SN), and Long Narrow (LN).
* Investigate the impact of shade dispersion on PV array power generation.

---

##  Tools & Technologies

* MATLAB
* Simulink
* MATLAB Function Block
* Simscape Electrical – PV Array
* XY Graph for characteristic comparison

---

##  PV Array Parameters

The simulation uses a user-defined PV module in the Simulink PV Array block.

| Parameter                      |  Value |
| :----------------------------- | -----: |
| Array Configuration            |  9 × 9 |
| Total PV Modules               |     81 |
| Maximum Power per Module       | 79.2 W |
| Number of Cells per Module     |     60 |
| Open-Circuit Voltage (Voc)     |   22 V |
| Short-Circuit Current (Isc)    |  4.7 A |
| Voltage at Maximum Power (Vmp) |   18 V |
| Current at Maximum Power (Imp) |  4.4 A |

### PV Array Model Parameters

![PV Array Parameters](<01. Solar PV Array parameters .png>)

---

##  System Model & Methodology

The Simulink model accepts irradiance values for the PV modules and evaluates array performance using two configurations: TCT and Sudoku.

A MATLAB Function block defines the irradiance matrices for the four shading cases and separates the 9×9 matrix into nine row-wise signals. These signals are supplied to the corresponding PV array subsystems.

The electrical outputs are processed to obtain current, voltage, and power characteristics, which are displayed using an XY Graph for comparison.

### Overall Simulink Model

![Overall Simulink Model](<02. Model Simulation.png>)

### TCT Configuration

The Total Cross-Tied (TCT) configuration connects PV modules in series within each row, with rows cross-connected in parallel. It serves as the conventional configuration for comparison.

![TCT Subsystem](<03. TCT block.png>)

### Sudoku Configuration

The Sudoku configuration uses a shade-dispersion arrangement to redistribute the physical placement of PV modules exposed to different irradiance levels. The aim is to distribute shading more evenly across the array and reduce the adverse effects of non-uniform irradiance.

![Sudoku Subsystem](<04. SUDOKU block.png>)

### Row-Level Sudoku Model

![Row Model in Sudoku](<05. Mdel of row in SUDOKU.png>)

---

##  Partial Shading Cases

Four irradiance patterns are simulated to examine the behavior of both array configurations under different spatial distributions of shading.

| Case   | Shading Pattern   |
| :----- | :---------------- |
| Case 1 | Short Wide (SW)   |
| Case 2 | Long Wide (LW)    |
| Case 3 | Short Narrow (SN) |
| Case 4 | Long Narrow (LN)  |

### Case 1 — Short Wide (SW)

**Irradiance Matrix**

![Case 1 Irradiance](<06. case1 irradiance.png>)

**Simulation Results**

![Case 1 SW Results](<07. case 1 - Short Wide (SW) result.png>)

### Case 2 — Long Wide (LW)

**Irradiance Matrix**

![Case 2 Irradiance](<08. case2 irradiance.png>)

**Simulation Results**

![Case 2 LW Results](<09. case 2 — Long Wide (LW) result.png>)

### Case 3 — Short Narrow (SN)

**Irradiance Matrix**

![Case 3 Irradiance](<10. case3 irradiance.png>)

**Simulation Results**

![Case 3 SN Results](<11. case 3 - Short Narrow (SN) result.png>)

### Case 4 — Long Narrow (LN)

**Irradiance Matrix**

![Case 4 Irradiance](<12. case4 irradiance.png>)

**Simulation Results**

![Case 4 LN Results](<13. case 4 - Long Narrow (LN) result.png>)

---

##  MATLAB/Simulink Model (.slx)

The complete MATLAB/Simulink model is included in this repository.

**Model File:** `TCT_and_SUDOKU.slx`

The `.slx` file contains the PV array simulation model used to compare TCT and Sudoku configurations under different partial shading conditions.

###  How to Open and Run the Model

1. Install MATLAB with Simulink and the required Simscape Electrical components.
2. Download `TCT_and_SUDOKU.slx` from this repository.
3. Open MATLAB and navigate to the folder containing the downloaded model.
4. Double-click `TCT_and_SUDOKU.slx` to open it in Simulink.
5. Review the model and its MATLAB Function block, which defines the irradiance matrices for the different shading cases.
6. Click the **Run** button in Simulink to execute the simulation.
7. Observe the resulting current, voltage, and power characteristics using the XY Graph blocks.

**Recommended MATLAB Version:** R2025a (the version used for model development).

> If the model does not open or simulate correctly, check that the required Simulink libraries are installed and that the model is compatible with your MATLAB version.

---

##  Results & Observations

The simulation results provide a comparison of the TCT and Sudoku configurations under the four partial shading scenarios.

The plotted characteristics allow the following aspects to be investigated:

* Changes in PV array voltage and current under non-uniform irradiance.
* Differences in the P–V characteristics of TCT and Sudoku configurations.
* The effect of shading distribution on the maximum power observed in each case.
* The occurrence of multiple peaks and changes in the power curve under partial shading.

In the displayed simulation results, the Sudoku configuration exhibits a higher peak power than the TCT configuration in the four tested cases. The magnitude of the improvement varies with the shading pattern.

These observations are based on the current simulation model and should not be interpreted as a universal performance guarantee for all PV arrays or shading conditions.

---

##  Research Paper Reference

This project is based on the concepts presented in the following research paper:

B. Indu Rani, G. Saravana Ilango, and C. Nagamani, “Enhanced Power Generation From PV Array Under Partial Shading Conditions by Shade Dispersion Using Su Do Ku Configuration,” *IEEE Transactions on Sustainable Energy*, vol. 4, no. 3, pp. 594–601, July 2013.

**DOI:** [10.1109/TSTE.2012.2230033](https://doi.org/10.1109/TSTE.2012.2230033)

[View Paper on IEEE Xplore](https://ieeexplore.ieee.org/document/6397935)

The referenced work investigates Sudoku-based shade dispersion in a TCT-connected PV array to improve power generation under partial shading. The present project implements a MATLAB/Simulink model to study and compare TCT and Sudoku configurations under four shading patterns.

---

##  Author

**Waquar Ahmad**
Electrical Engineering Student
Aligarh Muslim University (AMU)

GitHub: [@waquar0003](https://github.com/waquar0003)

---

