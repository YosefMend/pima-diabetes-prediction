# Pima Diabetes Prediction Project

An end-to-end predictive modeling pipeline for the Pima Indians Diabetes dataset. We compare missing-data strategies, train and tune Logistic Regression and Random Forest models, calibrate predicted probabilities, and interpret model outputs with SHAP.
The Dataset can be found here: https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database/data

## 📁 Repository Structure

├── notebooks/             # Analysis notebooks
│   ├── 01_EDA.ipynb       # Data loading & exploration
│   ├── 02_Stats.ipynb     # Correlations & OR/p-value tables
│   ├── 03_CV_Modeling.ipynb   # CV-AUC & hyperparameter tuning
│   ├── 04_Calibration.ipynb   # Calibration curves & threshold analysis
│   └── 05_Interpretation.ipynb# SHAP & confusion matrix
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

* **Imputation strategies compared:** drop-zero vs. median vs. KNN
* **Models trained:** L1-regularized Logistic Regression, Random Forest
* **Discrimination (ROC-AUC)**: Trial A vs. C benchmarks
* **Calibration:** Platt & Isotonic reliability diagrams
* **Interpretation:** SHAP feature impacts & confusion matrix analysis

## Project Summary

**Objective:**  
Predict onset of type-2 diabetes in the Pima Indian cohort using eight clinical features (Pregnancies, Glucose, BloodPressure, SkinThickness, Insulin, BMI, DiabetesPedigreeFunction, Age).

**Key Findings:**

1. **Baseline comparison (Trials A/B/C):**  
   - **Trial A (drop-zeros)** outperforms median and KNN imputation for both Logistic Regression (AUC ≈ 0.85) and Random Forest (AUC ≈ 0.87).  
   - **Trial C (KNN-imputation)** edges out median-fill but remains behind drop-zeros on this small dataset.

2. **Final tuned models:**  
   - **Logistic Regression** on Trial A achieves **AUC = 0.892**, **Accuracy = 0.823**, **Sensitivity = 0.885**, **Specificity = 0.792** at threshold ≈ 0.34.  
   - **Random Forest** on Trial C achieves **AUC = 0.816**, **Accuracy = 0.747**, **Sensitivity = 0.741**, **Specificity = 0.750** at threshold ≈ 0.17.

3. **Calibration & reliability:**  
   - LR on Trial A yields the lowest Brier score (0.120) and most closely follows a perfect reliability curve.  
   - RF on Trial C can be recalibrated (Brier ≈ 0.169) but still shows larger deviations.

4. **Feature importance (SHAP):**  
   - **Glucose** is the single strongest predictor across all models.  
   - **BMI**, **Insulin**, and **Age** consistently drive risk estimates upward.  
   - **BloodPressure** and **SkinThickness** are the least impactful.

**Recommendations:**  
- **Deploy** the **L1-regularized Logistic Regression** on the drop-zeros dataset for the best balance of discrimination, calibration, and interpretability.  
- **Keep** the KNN-imputed Random Forest as a high-sensitivity backup workflow, especially when scaling to larger datasets.

---

## 📦 Dependencies

See `requirements.txt` for exact versions.

---

## 📈 Next Steps

* Integrate feature engineering (interactions, polynomials)
* Explore gradient-boosted trees and stacking ensembles

---
