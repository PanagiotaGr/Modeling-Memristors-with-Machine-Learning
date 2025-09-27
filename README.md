# 📘 Memristor Modeling & Machine Learning

## 🌟 Project Overview
This project explores the **behavior and dynamics of memristors** using simulated datasets and applies **machine learning (ML)** to:

- 🔌 Predict **current (I)** from **voltage (V)** and device parameters  
- 🟩 Classify **High / Low resistance states**  
- ⏳ Analyze **time-dependent behavior** using **LSTM**  
- 📊 Visualize **I-V characteristics**, **hysteresis loops**, and **parameter sensitivity**

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
- Predict **current (I)** from **voltage (V)** and parameters  
- Approaches:
  - Linear Regression  
  - Multi-feature Neural Networks  
- Features include `V`, `Amp`, `Freq`, `Dop`  
- Evaluation: **Predicted vs Actual** scatter plots

---

### 2️⃣ Classification — Resistance States
- Compute resistance:  
  \[
  R = \frac{V}{I}
  \]
- Define **High / Low resistance** via median or percentile thresholds  
- Use **Random Forest Classifier**  
- Evaluate using **accuracy**, **confusion matrix**, and resistance-state visualization

---

### 3️⃣ Sequential Modeling — LSTM
- Capture **temporal evolution** of current over time `t`  
- Create **sliding-window sequences** of `V`, `I`, and model parameters  
- Train **LSTM networks** to predict next-step current  
- Visualize **predicted vs actual** current sequences

---

### 4️⃣ Advanced Analysis
- 🔄 **Hysteresis Loops:** R–V curves for each model  
- ⚙️ **Parameter Sensitivity:** Effects of `Amp`, `Freq`, and `Dop`  
- 📐 **Feature Engineering:** Derived features such as `dV/dt` and `dI/dt` to improve ML models

---

## 🚀 How to Run
Follow these steps to run the project locally or on Kaggle.

---

### 1. Clone the Repository

git clone https://github.com/yourusername/memristor-ml.git
cd memristor-ml

2. Install Dependencies
pip install numpy scipy matplotlib scikit-learn tensorflow


3. Load the Dataset
from scipy.io import loadmat

# Load the .mat file
data = loadmat('memristor_data.mat')

# Example: access Yakopcic model data
yakopcic_V = data['Yakopcic']['V'][0][0]
yakopcic_I = data['Yakopcic']['I'][0][0]


4. Preprocess the Data

Extract V and I for each model

Normalize or standardize features

Create sliding windows for sequential tasks

from sklearn.preprocessing import MinMaxScaler

# Example: normalize
scaler = MinMaxScaler()
V_scaled = scaler.fit_transform(yakopcic_V.reshape(-1, 1))
I_scaled = scaler.fit_transform(yakopcic_I.reshape(-1, 1))

5. Train the Models

Run the Jupyter or Kaggle notebook:

jupyter notebook "Modeling Memristors with Machine Learning.ipynb"


Inside the notebook:

Regression: Linear Regression & Neural Networks

Classification: Random Forest

Sequential: LSTM for time-series current prediction

6. Visualize the Results

Plot I-V curves

Plot R-V hysteresis loops

Compare predicted vs actual currents


---

## 📈 Results
- ✅ LSTM models provided accurate current predictions across all memristor types  
- ✅ Random Forest achieved high accuracy in resistance-state classification  
- ✅ Visualizations revealed distinct hysteresis behavior among models  
- ✅ Multi-feature inputs improved sequential prediction compared to voltage-only inputs

---

## 📦 Dependencies
Core Libraries:
- [NumPy](https://numpy.org/) — numerical computing  
- [SciPy](https://scipy.org/) — `.mat` data handling  
- [Matplotlib](https://matplotlib.org/) — visualization  
- [scikit-learn](https://scikit-learn.org/) — regression & classification  
- [TensorFlow/Keras](https://www.tensorflow.org/) — LSTM modeling

---

## 📁 Project Structure
```bash
memristor-ml/
│
├─ memristor_data.mat                         # Dataset
├─ Modeling Memristors with Machine Learning.ipynb  # Main Notebook
├─ README.md                                  # Documentation
└─

🔮 Future Work

📊 Multi-class resistance classification (Low / Medium / High)

🔧 Integration of additional device parameters for better prediction

🧠 Neuromorphic circuit simulations with memristor arrays

📈 Interactive dashboards (Plotly/Dash) for real-time exploration

👩‍💻 Author / Contact

Author: Panagiota G

Kaggle Notebook: Modeling Memristors with Machine Learning

⭐ This project bridges the gap between the physics of memristors and modern ML techniques, enabling reliable predictions and advancing research in neuromorphic computing and memory technologies.

