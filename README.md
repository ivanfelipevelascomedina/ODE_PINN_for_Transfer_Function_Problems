# Physics-Informed Neural Networks (PINNs) for Transfer Function Analysis

## Overview

This repository implements **Physics-Informed Neural Networks (PINNs)** for solving transfer function problems and analyzing their behavior in time and frequency domains. PINNs leverage the knowledge of physical laws (such as Ordinary Differential Equations (ODEs) or Partial Differential Equations (PDEs)) to constrain the learning process, making them highly effective for tasks requiring extrapolation, noise tolerance, and optimization in physics-constrained environments.

The focus of this project is on analyzing transfer functions for 3 different configurations using PINNs and comparing their performance against traditional data-driven approaches like LSTMs.

---

## **Files & Folders**
- **`requirements.txt`**: Lists necessary libraries.
- **`Transfer_Function_Problems_PINN.ipynb`**: Main code file.
- **`Datasets folder`**: Contains the datasets (train, validation and test) for the 3 configurations.
- **`Models folder`**: Contains the trained models for the 3 configurations.
- **`Data_Driven_Models folder`**: Contains the different data-driven models codes to compare with the physics-based PINN model.
  
---

## Features

- **High-Frequency Domain Extrapolation**: PINNs utilize physical equations to generalize well to unseen high-frequency data.
- **Noise Tolerance**: Models are constrained by physical laws, providing robustness to noisy datasets.
- **Frequency Domain Optimization**: Loss functions directly optimize gain and phase characteristics of Bode plots.
- **Lightweight Architecture**: The model has significantly fewer parameters compared to purely data-driven approaches, reducing training time and computational cost.

---

## Dataset

- The dataset is split into **training**, **validation**, and **test** sets.
- Includes only sine signals for transfer functions across different configurations.
- The second configuration (config_1) incorporates individual output signals for the transfer function.

---

## Loss Function

The loss function includes:
1. **Data Loss**: Error between predicted and actual outputs for training data.
2. **Physics Loss**: Penalizes predictions that violate the governing equations.
3. **Frequency Domain Constraints**: Optimizes the gain and phase from the Bode plot.

---

## Results

- **Strengths**:
  - Excellent performance on seen data (e.g., sine wave inputs).
  - Acceptable performance on unseen data (e.g., pulse inputs).
  - Lower training time and computational cost compared to data-driven alternatives.

- **Drawbacks**:
  - Performance decreases as the physics of the model becomes more complex.
  - Requires integration with other machine learning techniques for highly complex transfer functions.

