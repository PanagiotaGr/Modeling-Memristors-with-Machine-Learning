# 📘 Modeling Memristors with Machine Learning

## 🌟 Overview
This project focuses on **modeling the behavior of memristors** using simulated datasets and applying **machine learning (ML)** to:
- 🔌 Predict **current (I)** from **voltage (V)** and device parameters  
- 🟩 Classify **High / Low resistance states**  
- ⏳ Analyze **time-dependent behavior** with **LSTM** networks  
- 📊 Visualize **I-V characteristics**, **resistance hysteresis**, and **parameter sensitivity**

Memristors are **non-linear resistive devices with memory**, crucial for **neuromorphic computing** and **next-generation memory systems**.  
Accurate modeling supports the design of **robust circuits** and **intelligent systems**.

---

## 🎯 Objectives
- 🔎 Compare memristor models: **Yakopcic, MMS, stat, VTEAM**  
- 📈 Perform **regression** to predict current *(I)* from voltage *(V)*  
- 🟩 Perform **classification** of resistance states (High / Low)  
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
- Models used:
  - Linear Regression
  - Neural Networks  
- Evaluation: Predicted vs. Actual scatter plots

### 2️⃣ Classification — Resistance States
- Compute resistance:  
  \[
  R = \frac{V}{I}
  \]
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
- 📐 **Feature Engineering:** Derived features such as `dV/dt`, `dI/dt` to improve ML models

---

## 🚀 How to Run
Follow these steps to set up and run the project.

### 1. Clone the Repository
`bash
git clone https://github.com/Lily-Evan/Modeling-Memristors-with-Machine-Learning.git
cd Modeling-Memristors-with-Machine-Learning




 2. Install Dependencies
pip install numpy scipy matplotlib scikit-learn tensorflow

3. Load the Dataset
from scipy.io import loadmat

# Load the .mat file
data = loadmat('memristor_data.mat')

# Example: Access Yakopcic model data
yakopcic_V = data['Yakopcic']['V'][0][0]
yakopcic_I = data['Yakopcic']['I'][0][0]

4. Preprocess the Data
from sklearn.preprocessing import MinMaxScaler

# Example: normalization
scaler = MinMaxScaler()
V_scaled = scaler.fit_transform(yakopcic_V.reshape(-1, 1))
I_scaled = scaler.fit_transform(yakopcic_I.reshape(-1, 1))

5. Train the Models

Run the Jupyter notebook:

jupyter notebook "Modeling Memristors with Machine Learning.ipynb"


Inside the notebook:

Regression: Linear Regression & Neural Networks

Classification: Random Forest

Sequential: LSTM for time-series prediction

6. Visualize the Results

Plot I-V curves

Plot R-V hysteresis loops

Compare Predicted vs Actual currents

📈 Results

✅ LSTM models achieved high accuracy in predicting current for all memristor types

✅ Random Forest performed well in classifying resistance states

✅ Visualizations highlighted distinct hysteresis behavior of different models

✅ Multi-feature sequences improved sequential predictions vs. using voltage only

📦 Dependencies

NumPy
 — numerical computing

SciPy
 — for .mat data handling

Matplotlib
 — visualization

scikit-learn
 — regression & classification

TensorFlow/Keras
 — LSTM modeling

📁 Project Structure
Modeling-Memristors-with-Machine-Learning/
│
├─ memristor_data.mat                         # Dataset
├─ Modeling Memristors with Machine Learning.ipynb  # Main Notebook
├─ README.md                                  # Documentation
└─ utils.py                                   # Helper functions (optional)

🔮 Future Work

📊 Multi-class resistance classification (Low / Medium / High)

🔧 Integration of more device parameters for better predictions

🧠 Neuromorphic circuit simulations using memristor arrays

📈 Interactive dashboards (Plotly/Dash) for real-time analysis

👩‍💻 Author / Contact

Author: Lily-Evan (original repo) / Adapted by Panagiota G for improved README

Kaggle Notebook: Modeling Memristors with Machine Learning

⭐ This project bridges the gap between memristor physics and modern ML techniques, providing tools for better predictions and advancing research in neuromorphic computing.
