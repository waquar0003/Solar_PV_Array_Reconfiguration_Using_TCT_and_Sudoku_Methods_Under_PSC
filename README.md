
# TCT and Sudoku PV Array Reconfiguration Under Partial Shading

A MATLAB/Simulink recreation of a research-paper study comparing Total-Cross-Tied (TCT) and Sudoku photovoltaic (PV) array configurations under partial shading conditions (PSC).

The model applies irradiance matrices to both configurations and compares simulated voltage, current, and power characteristics.

## Project Overview

Partial shading creates non-uniform irradiance across PV modules, which can cause mismatch losses and multiple peaks in the P–V curve.

This project models two array configurations under four shading patterns:

1. Case 1 — Short Wide (SW)
2. Case 2 — Long Wide (LW)
3. Case 3 — Short Narrow (SN)
4. Case 4 — Long Narrow (LN)

## Software

- MATLAB / Simulink
- Developed using MATLAB R2025a

## Simulink Model

The top-level model routes irradiance-row signals to the TCT and Sudoku subsystems. Their voltage, current, and power outputs are connected to an XY Graph for comparison.

![Top-level Simulink model](images/top_level_model.png)

## Irradiance Matrix Code

The `Irr_Matrix` MATLAB Function block defines the irradiance matrix for each case and separates it into nine row signals for the array model.

![Irradiance matrix code](images/irradiance_matrix_code.png)

## Array Configurations

### TCT Subsystem

![TCT subsystem](images/tct_subsystem.png)

### Sudoku Subsystem

![Sudoku subsystem](images/sudoku_subsystem.png)

## Simulation Results

### Case 1 — Short Wide (SW)

![Case 1 results](images/case1_short_wide.png)

### Case 2 — Long Wide (LW)

![Case 2 results](images/case2_long_wide.png)

### Case 3 — Short Narrow (SN)

![Case 3 results](images/case3_short_narrow.png)

### Case 4 — Long Narrow (LN)

![Case 4 results](images/case4_long_narrow.png)

## Key Features

- Four partial-shading irradiance cases
- MATLAB Function block for irradiance-matrix definition
- Nine row-wise irradiance signals
- TCT and Sudoku PV array subsystem models
- XY Graph-based comparison of simulated characteristics

## How to Run

1. Download or clone this repository.
2. Open MATLAB and set the repository folder as the current folder.
3. Open the `.slx` Simulink model.
4. Select the required irradiance case in the `Irr_Matrix` MATLAB Function block.
5. Run the simulation.
6. Inspect the XY Graph to compare TCT and Sudoku outputs.

## Reference

Add the full citation of the research paper recreated in this project:

Author(s), "Paper title," Journal/Conference, year, DOI/URL.

## Author

Your Name  
Electrical Engineering | Aligarh Muslim University
