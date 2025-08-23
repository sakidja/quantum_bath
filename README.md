# Quantum Bath Simulation

This repository contains scripts and notebooks for simulating structured quantum baths using **QuTiP**. 
It is part of an upcoming arXiv submission (link will be added soon). The notebook offers a simplified framework to study open quantum system dynamics, non-Markovian effects, and memory engineering, with an optional machine learning module for parameter inference based on FFT-based spectral features.

- Open quantum system dynamics
- Non-Markovian effects
- Lindblad master equations
- Coupling topologies and memory transfer

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

## Machine Learning Analysis 
Normalized FFT-based features are stored in *_fft_targets.csv.
Simulation parameters (e.g., J12, backflow, etc) are stored in *_param.txt.

To prepare data for ML:
Combine features and parameters into one dataset.
You can also add additional input parameters (e.g., logarithm of custom metrics) by modifying the notebook.
Recommended ML stack:
PCA for feature reduction
XGBoost for regression or classification

## How to Run
Clone this repository:
```bash
git clone https://github.com/sakidja/quantum_bath.git
cd quantum_bath



