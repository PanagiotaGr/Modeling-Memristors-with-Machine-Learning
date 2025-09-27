# 📘 Memristor Modeling & Machine Learning

## 🌟 Project Overview
This project explores the **behavior and dynamics of memristors** using simulated datasets and applies **machine learning (ML)** to:
- Predict current from voltage and device parameters.
- Classify **high / low resistance states**.
- Analyze **time-dependent behavior** via LSTM.
- Visualize **I-V characteristics, hysteresis loops, and parameter sensitivity**.

Memristors are **non-linear resistive devices with memory**, widely used in **neuromorphic computing** and **emerging memory technologies**.  
Accurate modeling is crucial for designing **robust circuits** and **intelligent systems**.

---

## 🎯 Objectives
- 🔎 Compare memristor models: **Yakopcic, MMS, stat, VTEAM**  
- 📈 Perform **regression** to predict current *(I)* from voltage *(V)*  
- 🟩 Classify **resistance states** (High / Low)  
- ⏳ Capture **time-dependent dynamics** using **LSTM**  
- 📊 Visualize **I-V curves**, **R-V hysteresis**, and **parameter sensitivity**

---

## 📂 Dataset
The dataset is available on **[Kaggle](https://www.kaggle.com/)** in `.mat` format.

### Models Included
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
- Predict **current (I)** from **voltage (V)** and parameters.
- Approaches:
  - Linear Regression
  - Multi-feature Neural Networks
- Features include `V`, `Amp`, `Freq`, `Dop`.
- Evaluation: **Predicted vs Actual** scatter plots.

---

### 2️⃣ Classification — Resistance States
- Compute resistance:  
  \[
  R = \frac{V}{I}
  \]
- Define **High / Low** resistance via median or percentile thresholds.
- Use **Random Forest Classifier**.
- Evaluate using **accuracy, confusion matrix**, and state visualization.

---

### 3️⃣ Sequential Modeling — LSTM
- Capture **temporal evolution** of current over time `t`.
- Create **sliding-window sequences** of `V`, `I`, and model parameters.
- Train **LSTM networks** to predict next-step current.
- Visualize **predicted vs actual current** sequences.

---

### 4️⃣ Advanced Analysis
- 🔄 **Hysteresis Loops:** R–V curves for each model.  
- ⚙️ **Parameter Sensitivity:** Effects of `Amp`, `Freq`, and `Dop`.  
- 📐 **Feature Engineering:** Derived features such as `dV/dt` and `dI/dt` to improve ML models.

---

## 🚀 How to Run

### 1. Load Dataset
```python
from scipy.io import loadmat
data = loadmat('memristor_data.mat')
2. Preprocess
Extract V and I for each model.

Flatten and normalize features.

Create sliding windows for sequential tasks.

3. Train Models
Regression → Linear & Neural Networks

Classification → Random Forest

Sequential → LSTM for time-series current prediction

4. Visualize
Plot I-V curves, R-V hysteresis, and Predicted vs Actual results.

📈 Results
✅ LSTM models provided accurate current predictions across all memristor types.

✅ Random Forest achieved high accuracy in resistance-state classification.

✅ Visualizations revealed distinct hysteresis behavior among models.

✅ Multi-feature inputs improved sequential prediction compared to voltage-only inputs.

📦 Dependencies
Install dependencies:

bash
Αντιγραφή κώδικα
pip install numpy scipy matplotlib scikit-learn tensorflow
Core Libraries

NumPy — numerical computing

SciPy — .mat data handling

Matplotlib — visualization

scikit-learn — regression & classification

TensorFlow/Keras — LSTM modeling

📁 Project Structure
bash
Αντιγραφή κώδικα
memristor-ml/
│
├─ memristor_data.mat       # Dataset
├─Modeling Memristors with Machine Learning.ipynb       # Kaggle Notebook
├─ README.md                # Project Documentation
└─
🔮 Future Work
📊 Multi-class resistance classification (Low / Medium / High)

🔧 Integration of additional device parameters for better prediction

🧠 Neuromorphic circuit simulations with memristor arrays

📈 Interactive dashboards (Plotly/Dash) for real-time exploration

👩‍💻 Author / Contact
Author: Panagiota G

Email: 

Kaggle Notebook: https://www.kaggle.com/code/panagiotagrosdouli1/modeling-memristors-with-machine-learning/edit

⭐ This project bridges the gap between the physics of memristors and modern ML techniques, enabling reliable predictions and advancing research in neuromorphic computing and memory technologies.
