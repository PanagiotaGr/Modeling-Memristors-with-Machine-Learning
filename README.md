# 📘 Modeling Memristors with Machine Learning

## 🌟 Overview
This project focuses on **modeling the behavior of memristors** using simulated datasets and applying **machine learning (ML)** to:
- 🔌 Predict **current (I)** from **voltage (V)** and device parameters  
- 🟩 Classify **High / Low resistance states**  
- ⏳ Analyze **time-dependent behavior** with **LSTM networks**  
- 📊 Visualize **I-V characteristics**, **resistance hysteresis**, and **parameter sensitivity**

Memristors are **non-linear resistive devices with memory**, crucial for **neuromorphic computing** and **next-generation memory systems**.  
Accurate modeling supports the design of **robust circuits** and **intelligent systems**.

---

## 🎯 Objectives
- 🔎 Compare memristor models: **Yakopcic, MMS, stat, VTEAM**  
- 📈 Perform **regression** to predict current *(I)* from voltage *(V)*  
- 🟩 Perform **classification** of resistance states *(High / Low)*  
- ⏳ Model **time-dependent dynamics** with **LSTM**  
- 📊 Visualize **I-V curves**, **R-V hysteresis**, and **parameter sensitivity**

---

## 📂 Dataset
Dataset available on **[Kaggle](https://www.kaggle.com/)** in `.mat` format.

### Included Models
- Yakopcic  
- MMS  
- stat  
- VTEAM  

### Fields per Model
| Model | Main Fields |
|-------|-------------|
| Yakopcic, MMS, VTEAM | `Amp`, `Freq`, `Dop`, `Rs`, `U_m`, `I_m`, `t`, `min_r`, `param`, `X`, `G`, `V`, `I`, `cost_function2compare`, `U_sin` |
| stat | `Amp`, `Freq`, `Dop`, `Rs`, `U_m`, `I_m`, `t`, `std`, `wsk`, `eps`, `I_m_b_interp`, `U_m_b_interp`, `U_sin` |

---

## 🔬 Methodology
### 1️⃣ Regression — Current Prediction
- Predict **I** from **V** and device parameters  
- Models: Linear Regression & Neural Networks  
- Evaluation: Predicted vs. Actual scatter plots  

### 2️⃣ Classification — Resistance States
- Compute resistance:  R = V / I  
- Define **High / Low resistance** (median or percentile thresholds)  
- Model: **Random Forest Classifier**  
- Metrics: Accuracy, Confusion Matrix, Visualizations  

### 3️⃣ Sequential Modeling — LSTM
- Capture **temporal dynamics** of current over time `t`  
- Create **sliding-window sequences** of `V`, `I`, and parameters  
- Train **LSTM** to predict next-step current  
- Visualize predicted vs. actual sequences  

### 4️⃣ Advanced Analysis
- 🔄 **Hysteresis Loops:** R-V curves for each model  
- ⚙️ **Parameter Sensitivity:** Effects of amplitude, frequency, doping  
- 📐 **Feature Engineering:** Derived features such as `dV/dt` and `dI/dt` to improve ML models  

---

## 🚀 How to Run
Follow these steps to set up and run the project.

### 1. Clone the Repository
```bash
git clone https://github.com/Lily-Evan/Modeling-Memristors-with-Machine-Learning.git
cd Modeling-Memristors-with-Machine-Learning

Author: Lily-Evan (original repo) / Adapted by Panagiota G for improved README

Kaggle Notebook: Modeling Memristors with Machine Learning
