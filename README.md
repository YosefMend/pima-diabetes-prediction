# Pima Diabetes Prediction Project

An end-to-end predictive modeling pipeline for the Pima Indians Diabetes dataset. We compare missing-data strategies, train and tune Logistic Regression and Random Forest models, calibrate predicted probabilities, and interpret model outputs with SHAP.

## 📁 Repository Structure

```
pima-diabetes-prediction/
├── data/                   # Processed datasets
│   ├── dfA.csv            # Drop-zero version
│   ├── dfB_filled.csv     # Median-imputed version
│   └── dfC_filled.csv     # KNN-imputed version
│
├── notebooks/             # Analysis notebooks
│   ├── 01_EDA.ipynb       # Data loading & exploration
│   ├── 02_Stats.ipynb     # Correlations & OR/p-value tables
│   ├── 03_CV_Modeling.ipynb   # CV-AUC & hyperparameter tuning
│   ├── 04_Calibration.ipynb   # Calibration curves & threshold analysis
│   └── 05_Interpretation.ipynb# SHAP & confusion matrix
│
├── scripts/               # Deployment demos
│
├── requirements.txt       # Python dependencies
└── README.md              # This file
```

---

## 🚀 Installation

1. **Clone the repo**

   ```bash
   git clone https://github.com/YosefMend/pima-diabetes-prediction.git
   cd pima-diabetes-prediction
   ```
2. **Create virtualenv & install dependencies**

   ```bash
   python -m venv venv
   source venv/bin/activate    # macOS/Linux
   .\venv\Scripts\activate   # Windows
   pip install -r requirements.txt
   ```

---

## 📖 Workflow & Usage

1. **Notebooks**: Run sequentially in Jupyter:

   1. `01_EDA.ipynb`
   2. `02_Stats.ipynb`
   3. `03_CV_Modeling.ipynb`
   4. `04_Calibration.ipynb`
   5. `05_Interpretation.ipynb`

## 📊 Key Results & Metrics

> *To be updated as final results are confirmed.*

* **Imputation strategies compared:** drop-zero vs. median vs. KNN
* **Models trained:** L1-regularized Logistic Regression, Random Forest
* **Discrimination (ROC-AUC)**: Trial A vs. C benchmarks
* **Calibration:** Platt & Isotonic reliability diagrams
* **Interpretation:** SHAP feature impacts & confusion matrix analysis

---

## 📦 Dependencies

See `requirements.txt` for exact versions.

---

## 📈 Next Steps

* Integrate feature engineering (interactions, polynomials)
* Explore gradient-boosted trees and stacking ensembles

---
