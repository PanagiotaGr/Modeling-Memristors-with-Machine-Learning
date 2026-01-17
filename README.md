# Modeling Memristors with Machine Learning

## Overview

This project models memristor behavior using simulated datasets and machine learning methods. The main goals are:

* predict current (I) from voltage (V) and device parameters,
* classify high/low resistance states,
* model time-dependent dynamics with LSTM networks,
* visualize I–V characteristics, hysteresis, and parameter sensitivity.

Memristors are nonlinear resistive devices with memory and are relevant to neuromorphic computing and emerging memory technologies. Accurate data-driven models can support circuit design and system-level analysis.

## Objectives

* Compare memristor models: **Yakopcic**, **MMS**, **stat**, **VTEAM**
* Regression: predict (I) from (V) and parameters
* Classification: label resistance states (High/Low)
* Sequential modeling: capture temporal dynamics with LSTMs
* Visualization: I–V curves, R–V hysteresis loops, and parameter sensitivity

## Dataset

The dataset is provided in `.mat` format and is available on Kaggle (see link in the original notebook/repository).

Included models:

* Yakopcic
* MMS
* stat
* VTEAM

Common fields (examples):

* For Yakopcic/MMS/VTEAM: `Amp`, `Freq`, `Dop`, `Rs`, `U_m`, `I_m`, `t`, `V`, `I`, plus additional model-specific variables
* For stat: `Amp`, `Freq`, `Dop`, `Rs`, `U_m`, `I_m`, `t`, and additional statistical/fit variables (e.g., `std`, `wsk`, `eps`)

## Methodology

### 1) Regression (current prediction)

* Inputs: voltage (V) and device/model parameters
* Models: linear regression and simple neural networks (baseline)
* Evaluation: predicted vs. actual plots and standard regression metrics

### 2) Classification (resistance state)

* Compute resistance: (R = \frac{V}{I})
* Define High/Low labels using a median or percentile-based threshold
* Model: Random Forest classifier (baseline)
* Evaluation: accuracy, confusion matrix, and diagnostic plots

### 3) Sequential modeling (LSTM)

* Construct sliding-window sequences over time (t)
* Train an LSTM to predict next-step (or multi-step) current
* Compare predicted vs. ground-truth trajectories

### 4) Additional analysis

* Hysteresis: R–V loops per model and parameter settings
* Sensitivity analysis: amplitude, frequency, doping effects
* Feature engineering: derived features such as (dV/dt) and (dI/dt)

## How to Run

Clone the repository and open the notebook/scripts provided:

```bash
git clone https://github.com/PanagiotaGr-/Modeling-Memristors-with-Machine-Learning.git
cd Modeling-Memristors-with-Machine-Learning
```

Then follow the notebook instructions (Kaggle or local execution) for data loading and model training.

## Credits

