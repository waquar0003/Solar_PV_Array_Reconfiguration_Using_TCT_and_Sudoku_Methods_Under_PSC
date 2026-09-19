# TCT and Sudoku PV Array Reconfiguration Under Partial Shading

A MATLAB/Simulink recreation of a research-paper study comparing **Total-Cross-Tied (TCT)** and **Sudoku** photovoltaic (PV) array configurations under Partial Shading Conditions (PSC).

The project applies different irradiance matrices to both PV array configurations and compares their simulated voltage, current, and power characteristics.

> **Note:** This is an independent MATLAB/Simulink recreation. The simulation plots represent this implementation's outputs and should not be treated as independently verified reproduction of the paper's results.

## Project Overview

Partial shading creates non-uniform irradiance across PV modules, resulting in mismatch losses and multiple peaks in the P–V curve.

This project models and compares TCT and Sudoku PV array configurations under four partial shading patterns:

1. Case 1 — Short Wide (SW)
2. Case 2 — Long Wide (LW)
3. Case 3 — Short Narrow (SN)
4. Case 4 — Long Narrow (LN)

## Software Requirements

* MATLAB
* Simulink
* MATLAB R2025a (used for development)

Required toolboxes or additional libraries depend on the blocks used in the model.

## Simulink Model

The complete MATLAB Simulink model is included in this repository.

**Model file:** `TCT_and_SUDOKU.slx`

The model contains the irradiance matrix generation block, TCT and Sudoku PV array subsystems, and XY Graphs for comparing the simulation outputs.

![Top-level Simulink model](images/top_level_model.png)

### Download the Simulink Model

You can download the model directly from this repository:

1. Open `TCT_and_SUDOKU.slx` in the repository.
2. Click **Download raw file** (or the download button).
3. Save the `.slx` file to your computer.
4. Open it using MATLAB/Simulink.

> GitHub does not display the interactive Simulink model directly in the browser. The `.slx` file must be downloaded and opened in MATLAB/Simulink.

## How to Run the Simulink Model

Follow these steps to execute the simulation:

### Step 1 — Download the Repository

Download the repository as a ZIP file using GitHub's **Code → Download ZIP** option, or clone it using Git:

```bash
git clone https://github.com/Waquar003/Waquar-demo.git
```

Extract the ZIP file if you downloaded it.

### Step 2 — Open MATLAB

Launch MATLAB and set the extracted repository folder as your current working directory.

### Step 3 — Open the Simulink Model

Open the file `TCT_and_SUDOKU.slx` by double-clicking it or running:

```matlab
open_system('TCT_and_SUDOKU.slx')
```

### Step 4 — Select the Irradiance Case

Inside the Simulink model, locate the `Irr_Matrix` MATLAB Function block.

Select the desired irradiance matrix corresponding to one of the four partial shading cases (SW, LW, SN, or LN).

The block separates the 9×9 irradiance matrix into nine row-wise irradiance signals, which are supplied to the TCT and Sudoku PV array subsystems.

### Step 5 — Run the Simulation

Click the **Run** button in Simulink.

The model simulates the TCT and Sudoku PV array configurations under the selected irradiance distribution.

### Step 6 — Compare the Results

Open the XY Graph blocks to observe and compare the simulated characteristics of both configurations.

Use the graph legends to identify the plotted signals and compare their voltage, current, and power behavior.

## Irradiance Matrix Code

The `Irr_Matrix` MATLAB Function block defines the irradiance matrix for each shading case and separates it into nine row-wise signals for the PV array model.

![Irradiance matrix code](images/irradiance_matrix_code.png)

## PV Array Configurations

### Total-Cross-Tied (TCT) Subsystem

![TCT subsystem](images/tct_subsystem.png)

### Sudoku Subsystem

![Sudoku subsystem](images/sudoku_subsystem.png)

## Simulation Results

The following screenshots show the simulated characteristics obtained for the four partial shading cases.

### Case 1 — Short Wide (SW)

![Case 1 results](images/case1_short_wide.png)

### Case 2 — Long Wide (LW)

![Case 2 results](images/case2_long_wide.png)

### Case 3 — Short Narrow (SN)

![Case 3 results](images/case3_short_narrow.png)

### Case 4 — Long Narrow (LN)

![Case 4 results](images/case4_long_narrow.png)

## Repository Contents

```text
Waquar-demo/
│
├── README.md
├── TCT_and_SUDOKU.slx
│
└── images/
    ├── top_level_model.png
    ├── irradiance_matrix_code.png
    ├── tct_subsystem.png
    ├── sudoku_subsystem.png
    ├── case1_short_wide.png
    ├── case2_long_wide.png
    ├── case3_short_narrow.png
    └── case4_long_narrow.png
```

## Key Features

* 9×9 PV array modeling
* TCT and Sudoku PV array configurations
* Four partial shading irradiance cases
* MATLAB Function block for irradiance matrix generation
* Nine row-wise irradiance signals
* Simulink-based PV array simulation
* XY Graph-based comparison of simulation outputs

## Future Improvements

* Add extracted maximum power values for each shading case.
* Include percentage improvement calculations with a clearly defined baseline.
* Add the complete research paper citation and DOI.
* Include additional MPPT algorithms and performance comparisons.

## Reference

This project is inspired by the research paper:

> Enhanced Power Generation From PV Array Under Partial Shading Conditions by Shade Dispersion Using Su Do Ku Configuration

Please refer to the original publication for the authors, journal/conference details, year, and DOI.

## Author

**Waquar Ahmad**
Electrical Engineering Undergraduate
Aligarh Muslim University
