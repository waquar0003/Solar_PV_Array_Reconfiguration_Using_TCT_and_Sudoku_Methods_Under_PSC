# TCT and Sudoku PV Array Reconfiguration Under Partial Shading

## 📌 Project Overview

This project presents a **MATLAB/Simulink simulation of photovoltaic (PV) array reconfiguration techniques for improving power extraction under Partial Shading Conditions (PSC)**.

Two PV array configurations are investigated and compared:

* **Total Cross-Tied (TCT) Configuration**
* **Sudoku-Based PV Array Configuration**

The project analyzes the behavior of the PV array in terms of **current, voltage, and output power** under the same shading conditions.

The main objective is to study how different PV array configurations redistribute the effect of non-uniform irradiance and improve the available power from the PV system.

---

## 🎯 Objectives

The major objectives of this project are:

1. Model a PV array under **Partial Shading Conditions**.
2. Implement the **Total Cross-Tied (TCT)** PV array configuration.
3. Implement a **Sudoku-based PV array reconfiguration**.
4. Apply the same irradiance/shading conditions to both configurations.
5. Compare the resulting:

   * PV array current
   * PV array voltage
   * Output power
6. Investigate the effect of PV array reconfiguration on **power extraction under PSC**.
7. Provide a simulation framework that can be further extended with **MPPT/GPPT algorithms**.

---

## ⚡ What is Partial Shading?

In a conventional PV array, all modules do not always receive the same irradiance.

Partial shading can occur because of:

* Buildings
* Trees
* Clouds
* Dust
* Nearby structures
* Other PV modules
* Irregular environmental conditions

For example, different modules in an array may receive:

```text
1000   800   600   400   1000
1000  1000   500  1000   1000
 700  1000  1000   300   1000
1000   600  1000  1000    500
1000  1000   800  1000   1000
```

where the values represent irradiance in **W/m²**.

Because PV modules connected in an array interact electrically, this non-uniform irradiance can significantly reduce the obtainable power.

---

# 🔌 PV Array Configurations

## 1. Total Cross-Tied (TCT)

In a Total Cross-Tied configuration, PV modules are connected using both:

* Series connections
* Cross-ties between rows

This arrangement provides multiple current paths and can reduce mismatch losses compared with simpler configurations.

Conceptually:

```text
PV ─ PV ─ PV ─ PV ─ PV
│    │    │    │    │
├────┼────┼────┼────┤
│    │    │    │    │
PV ─ PV ─ PV ─ PV ─ PV
│    │    │    │    │
├────┼────┼────┼────┤
```

The cross-connections allow current to redistribute between modules.

---

## 2. Sudoku-Based Reconfiguration

The Sudoku configuration rearranges PV modules according to a **Sudoku-based permutation/reconfiguration pattern**.

The objective is to distribute shaded modules more uniformly throughout the electrical array.

Instead of allowing heavily shaded modules to remain concentrated in one electrical path, the reconfiguration attempts to spread their effect across different rows/columns.

Conceptually:

```text
Original Arrangement

[ A  B  C  D  E ]
[ F  G  H  I  J ]
[ K  L  M  N  O ]
[ P  Q  R  S  T ]
[ U  V  W  X  Y ]


Sudoku-Based Arrangement

[ ...reconfigured... ]
[ ...reconfigured... ]
[ ...reconfigured... ]
[ ...reconfigured... ]
[ ...reconfigured... ]
```

The exact permutation depends on the implemented Sudoku mapping.

---

# 🧩 Simulink Model

The uploaded Simulink model contains separate sections for analyzing the TCT and Sudoku configurations.

The model includes outputs for:

### Current

```text
Current TCT
Current SUDOKU
```

### Voltage

```text
Voltage TCT
Voltage SUDOKU
```

### Power

```text
Power TCT
Power SUDOKU
```

These outputs allow direct comparison of the two PV configurations.

---

# 📊 Performance Comparison

The simulation can be used to compare:

| Parameter                  | TCT | Sudoku |
| -------------------------- | --: | -----: |
| PV Voltage                 |   ✓ |      ✓ |
| PV Current                 |   ✓ |      ✓ |
| PV Power                   |   ✓ |      ✓ |
| Partial Shading Analysis   |   ✓ |      ✓ |
| Array Reconfiguration      |   — |      ✓ |
| Power Improvement Analysis |   ✓ |      ✓ |

The primary comparison is the **maximum obtainable power under identical partial-shading conditions**.

---

# 🧮 Power Calculation

The PV output power is calculated using:

**P = V × I**

where:

* **P** = PV output power (W)
* **V** = PV array voltage (V)
* **I** = PV array current (A)

The resulting power can be used to generate **P–V characteristics** and identify the available maximum power.

---

# 🛠️ Software Requirements

### Required Software

* **MATLAB**
* **Simulink**
* **Simscape Electrical / Simscape components** as required by the model

### Tested MATLAB Version

The project was developed using:

```text
MATLAB R2025a
```

Newer MATLAB versions may require minor compatibility adjustments.

---

# 📁 Project Structure

```text
TCT-and-SUDOKU/
│
├── TCT_and_SUDOKU(1).slx
│
└── README.md
```

### `TCT_and_SUDOKU(1).slx`

Main MATLAB/Simulink model containing the PV array simulation and comparison between:

* TCT configuration
* Sudoku configuration

---

# 🚀 How to Run

### Step 1 — Clone the Repository

Clone this repository to your computer.

### Step 2 — Open MATLAB

Launch MATLAB and navigate to the project directory.

### Step 3 — Open the Simulink Model

Open:

```text
TCT_and_SUDOKU(1).slx
```

### Step 4 — Configure the Simulation

Set the desired:

* Irradiance values
* PV module parameters
* Simulation time
* Shading pattern

### Step 5 — Run the Simulation

Click:

```text
Run ▶
```

### Step 6 — Analyze Results

Observe the outputs for:

```text
Current TCT
Current SUDOKU

Voltage TCT
Voltage SUDOKU

Power TCT
Power SUDOKU
```

The results can then be compared to evaluate the effect of Sudoku-based reconfiguration.

---

# 🔬 Research Significance

PV arrays operating under PSC can exhibit **multiple peaks in their P–V characteristics** because bypass diodes may become activated as a result of shading.

Therefore, simply using a conventional MPPT algorithm may cause the operating point to converge to a **Local Maximum Power Point (LMPP)** instead of the **Global Maximum Power Point (GMPP)**.

PV array reconfiguration provides another approach to reducing mismatch losses before or along with MPPT.

This project therefore provides a foundation for investigating:

```text
Partial Shading
       ↓
PV Array Mismatch
       ↓
Array Reconfiguration
       ↓
TCT / Sudoku Configuration
       ↓
PV Characteristics
       ↓
Maximum Power Extraction
       ↓
MPPT / GPPT
```

---

# 🔮 Future Work

The current model can be extended in several directions.

### 1. MPPT Integration

Implement MPPT algorithms such as:

* Perturb & Observe (P&O)
* Incremental Conductance
* Particle Swarm Optimization (PSO)
* Grey Wolf Optimization (GWO)
* Genetic Algorithm (GA)

### 2. Global Power Point Tracking

A **GPPT algorithm** can be integrated to identify the global maximum power point under multiple peaks.

### 3. Dynamic Reconfiguration

The array can be automatically reconfigured according to the changing irradiance pattern.

### 4. Advanced Shadow Dispersion

Other dispersion techniques can be investigated, including:

* Arnold's Cat Map (ACM)
* Modified/Enhanced ACM
* Chaotic maps
* Sudoku-based dispersion
* Optimization-based reconfiguration

### 5. Joint Optimization

A future version can combine:

```text
Shadow Dispersion
        +
PV Array Reconfiguration
        +
MPPT / GPPT
```

to maximize PV power extraction under dynamically changing partial-shading conditions.

---

# 📈 Expected Outcome

The project is intended to demonstrate that **PV array configuration and module arrangement can significantly affect the power available from a PV array under non-uniform irradiance**.

The simulation provides a framework for quantitatively comparing TCT and Sudoku configurations using voltage, current, and power characteristics.

---

# 👨‍💻 Project

**Project Area:** Solar Photovoltaic Systems
**Application:** Partial Shading Condition Analysis
**Method:** PV Array Reconfiguration
**Configurations:** TCT and Sudoku
**Platform:** MATLAB/Simulink
**MATLAB Version:** R2025a

---

## 📜 License

This project is intended for **academic and research purposes**.

You are welcome to modify and extend the model for educational and research applications.
