# Quantum Bath Simulation

This repository contains a Jupyter notebook for simulating structured quantum baths using **QuTiP**. 
It is part of an upcoming arXiv submission titled: "Structured Quantum Baths with Memory: A QuTiP Framework for Spectral Diagnostics and
Machine Learning Inference" (link will be added soon). The notebook offers a simplified framework to study open quantum system dynamics, non-Markovian effects, and memory engineering, with an optional machine learning module for parameter inference based on FFT-based spectral features.

- Open quantum system dynamics
- Non-Markovian effects
- Lindblad master equations
- Coupling topologies and memory transfer

A brief overview of the work can be found in my LinkedIn post:
https://www.linkedin.com/posts/ridwan-sakidja-83984710_baths-with-memory-a-qutip-exploration-activity-7352269774392840192-kPxr/

## Why This Matters

Understanding memory flow in quantum baths is essential for quantum control, error mitigation, and system-environment engineering. This framework offers a hands-on, diagnostic rich approach to explore these dynamics with tools designed to be accessible, extensible, and modular.

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
  Single Run: Define specific parameters in the notebook and execute a single simulation.
  - A ZIP archive is automatically created for this run, containing all outputs (FFT features, parameter logs, plots).

  Multi-Run: Specify a range of parameters in the notebook to perform batch simulations.
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

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.16938479.svg)](https://doi.org/10.5281/zenodo.16938479)

## How to Run

Clone this repository:
```bash
git clone https://github.com/sakidja/quantum_bath.git
cd quantum_bath
```

🚀 Quick Start: Run in Google Colab — No Setup Needed
To run instantly in Google Colab for anyone with a browser and a Google account:
- Click the badge below to launch the notebook in Colab:
  [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sakidja/quantum_bath/blob/main/QuTiP_Quantum_Bath.ipynb)
  
- Click “Connect” (top right) to start the runtime.
- Run the first cell to install QuTiP:
  
```bash
!pip install qutip --quiet


