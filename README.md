# Quantum Bath Simulation

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.16938479.svg)](https://doi.org/10.5281/zenodo.16938479)

This repository contains a Jupyter notebook for simulating structured quantum baths using **QuTiP**. 
It is part of an upcoming paper submission titled: "Structured Quantum Baths with Memory: A QuTiP Framework for Spectral Diagnostics and
Machine Learning Inference" (https://www.arxiv.org/abs/2508.17514). The notebook offers a simplified framework to study open quantum system dynamics, non-Markovian effects, and memory engineering, with an optional machine learning module for parameter inference based on FFT-based spectral features.

- Open quantum system dynamics
- Non-Markovian effects
- Lindblad master equations
- Coupling topologies and memory transfer

A brief overview of the work can be found in my LinkedIn post:

https://www.linkedin.com/feed/update/urn:li:activity:7365924335208890368/

## Why This Matters

Understanding memory flow in quantum baths is essential for quantum control, error mitigation, and system-environment engineering. This framework offers a hands-on, diagnostic rich approach to explore these dynamics with tools designed to be accessible, extensible, and modular.

## Two-Tier Strategy

In this model, we employ a two-tier representation of the environment. The far field is treated _conventionally as a continuum_ within the Lindblad master equation using standard Markovian dissipators, while the near field is represented explicitly as a _structured cluster of 2 to 5 qubits coupled to the central qubit_ (i.e 3 or 6 qubit system as illustrated below). By embedding these near-field degrees of freedom directly into the Hamiltonian, information can flow coherently between system and environment, enabling the study of memory effects and fidelity contributions while remaining fully consistent with the master equation formalism.

<p align="center">
 <img width="300" height="260" alt="image" src="https://github.com/user-attachments/assets/56b7f2ba-59e3-4902-bdff-33b7f8fc92a4" />
 <img width="300" height="260" alt="image" src="https://github.com/user-attachments/assets/81c890eb-cd3d-4033-bbce-06ca327b6343" />
</p>




## Features
- Multi-qubit structured bath modeling
- Thermal Lindblad dissipation and entropy tracking
- Diagnostic plots: entropy, fidelity, populations, entanglement, and trace distance
- FFT-based spectral analysis for memory and coherence signatures
- Optional ML workflow for parameter inference using normalized FFT features

## Requirements
- Python 3.9+
- [QuTiP](https://qutip.org)
- NumPy, Matplotlib

## Simulation Modes
  **Single Run**: Define specific parameters in the notebook and execute a single simulation.
  - A ZIP archive is automatically created for this run, containing all outputs (FFT features, parameter logs, plots).
    
  **Multi-Run**: Specify a range of parameters in the notebook to perform batch simulations.
  - Each completed run generates its own ZIP archive, uniquely tagged for easy identification.
    
   Both modes are fully customizable by editing the parameter cells in the notebook.

## Machine Learning Analysis 
- Normalized FFT-based features are stored in *_input_vectors.csv.
- Simulation parameters and targets (e.g., J_source, backflow, etc) are stored in *_targets.txt.

To prepare data for ML: Combine the two file types into one dataset.
You can also add additional input parameters/targets (e.g., logarithm of custom metrics) by modifying the notebook.
Recommended ML stack:
PCA for feature reduction
XGBoost for regression or classification.


## How to Run

🚀 Quick Start: Run in Google Colab — No Setup Needed

**To run instantly in Google Colab for anyone with a browser and a Google account:**
- Click the badge below to launch the notebook in Colab:
  
  [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sakidja/quantum_bath/blob/main/QuTiP_Quantum_Bath.ipynb)
  
- Click “Connect” (top right) to start the runtime.
- Run the first cell to install QuTiP:
  
```bash
!pip install qutip --quiet
```
- Run the rest of the cells.
---
**To clone this repository:**
```bash
git clone https://github.com/sakidja/quantum_bath.git
cd quantum_bath
```

