# ❤️ Heart Disease Prediction Using Logistic Regression

## 📋 Project Overview
Heart disease is a critical global health issue. Early identification of at-risk patients can guide timely preventive measures and treatment.  
This project builds a **Logistic Regression** model that estimates the probability of heart disease using demographic, clinical, and test-related features from the **Heart Disease UCI** dataset.

---

## 🗂️ Dataset Description
The (combined) dataset contains ~920 patient records with the features below.  
Droppable columns `ca` and `thal` are excluded due to excessive missing values.

| Feature   | Type      | Description                                        |
|-----------|-----------|----------------------------------------------------|
| `id`      | Continuous | Unique identifier                                  |
| `age`     | Continuous | Patient age (years)                                |
| `sex`     | Nominal    | Gender (0 = Female, 1 = Male)                      |
| `dataset` | Nominal    | Data source (Cleveland, Hungary, etc.)             |
| `cp`      | Nominal    | Chest-pain type (0 – 3)                            |
| `trestbps`| Continuous | Resting blood pressure (mm Hg)                     |
| `chol`    | Continuous | Serum cholesterol (mg/dl)                          |
| `fbs`     | Nominal    | Fasting blood sugar > 120 mg/dl (1 = True)         |
| `restecg` | Nominal    | Resting ECG results (0 – 2)                        |
| `thalch`  | Continuous | Max heart rate achieved                            |
| `exang`   | Nominal    | Exercise-induced angina (1 = Yes)                 |
| `oldpeak` | Continuous | ST depression induced by exercise                  |
| `slope`   | Nominal    | Slope of peak exercise ST segment (0 – 2)          |
| *(dropped)* `ca` | Continuous | # major vessels (0 – 3)                      |
| *(dropped)* `thal` | Nominal | Thalassemia (1 – 3)                          |
| `num`     | Nominal    | **Target**&nbsp;— Heart disease (0 = No, 1+ = Yes) |

---

## ⚙️ Methodology

1. **Data Preprocessing**  
   - Encode categorical variables (`sex`, `dataset`, `cp`, `restecg`, `slope`).  
   - Drop `ca` and `thal` (excessive missingness).  
   - **KNN Imputer** for `trestbps`, `chol`, `fbs`, `thalch`, `exang`, `oldpeak`, `slope`.  
   - Cap outliers at *1.5 × IQR*.  
   - Add `age_group` feature: *Young* (≤ 40), *Middle* (40–60), *Senior* (> 60).  
   - Standardize numeric features (`StandardScaler`).  
   - Train-test split 80 / 20 (stratified).

2. **Modeling**  
   - Train **LogisticRegression** with hyper-parameter tuning (`C`, `solver`) via `GridSearchCV` (5-fold).  

3. **Evaluation**  
   - Accuracy, precision, recall, F1-score.  
   - Confusion matrix.

---

## 📈 Results

| Metric                | Value |
|-----------------------|-------|
| **Accuracy**          | **0.8043** |
| Precision (Class 1)   | 0.87  |
| Recall (Class 1)      | 0.79  |
| F1-Score (Class 1)    | 0.83  |

**Confusion Matrix (test = 184):**

| Actual \\ Predicted | **0 (No Disease)** | **1 (Disease)** |
|---------------------|--------------------|-----------------|
| **0 (No Disease)** | 62                 | 13              |
| **1 (Disease)**    | 23                 | 86              |

*Interpretation*  
* • Correctly identified 86 heart-disease cases and 62 non-disease cases.  
* • Missed 23 true disease cases (false negatives) — a concern in clinical settings.  

---

## 🔍 Conclusion
- Logistic Regression delivered a solid **80.4 % accuracy** baseline.  
- **High precision (0.87)** indicates reliable positive predictions.  
- **Moderate recall (0.79)** shows some at-risk patients remain undetected.  

### Next Steps
- Address class imbalance (SMOTE, class weighting).  
- Engineer interaction features (e.g., `age × chol`).  
- Evaluate ensemble models (Random Forest, Gradient Boosting, XGBoost).  
- Use SHAP for feature-importance interpretability.  
- Perform nested cross-validation for robust generalization.

---

## 🛠️ Tools & Libraries
- **Python 3**  
- `pandas`, `numpy`  
- `scikit-learn`  
- `matplotlib`, `seaborn`  
- `scikit-plot`

---
