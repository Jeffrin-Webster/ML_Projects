# 🧠📊 Machine Learning Projects Portfolio

This repository contains three fundamental machine learning projects covering:

- 🔢 Linear Regression: Brain Mass Prediction
- ❤️ Logistic Regression: Heart Disease Prediction
- 🛍️ K-Means Clustering: Mall Customers Segmentation

Each project demonstrates data preprocessing, modeling, evaluation, and insights tailored for real-world applications.

---

## 🔢 Brain Weight Prediction using Linear Regression

### 📋 Project Overview

This project uses Linear Regression to predict brain mass based on head size, age, and gender. It serves as an introduction to regression modeling, exploring how physiological features relate to brain weight.

### 🗂️ Dataset Description

The dataset is compiled from a medical study with the following features:

| Feature     | Type       | Description                           |
|-------------|------------|---------------------------------------|
| Gender      | Categorical| Male / Female                         |
| AgeGroup    | Categorical| Age category (e.g., 20–30, 30–40)     |
| Head Size   | Continuous | Head circumference (cm³)              |
| Brain Weight| Continuous | Brain mass (grams)                    |

### ⚙️ Methodology

- Encoded categorical variables (Gender, AgeGroup)
- Performed correlation analysis
- Built a Linear Regression model
- Evaluated with MAE, MSE, RMSE, and R²

### 📈 Results

| Metric        | Value       |
|---------------|-------------|
| MAE           | ~30 g       |
| MSE           | ~1700       |
| RMSE          | ~41.23 g    |
| R² Score      | ~0.85       |

### 🔍 Insights

- Head size had a strong positive correlation with brain weight.
- Age group showed moderate influence.
- The model explains ~85% of variance.

---

## ❤️ Heart Disease Prediction using Logistic Regression

### 📋 Project Overview

Early prediction of heart disease saves lives. This project uses logistic regression to identify patients at risk using demographic and clinical indicators from the UCI Heart Disease dataset.

### 🗂️ Dataset Description

| Feature     | Type       | Description                                     |
|-------------|------------|-------------------------------------------------|
| id          | Continuous | Unique identifier                               |
| age         | Continuous | Age of the patient                              |
| sex         | Nominal    | 0 = Female, 1 = Male                            |
| dataset     | Nominal    | Source (Cleveland, Hungary, etc.)              |
| cp          | Nominal    | Chest pain type (0–3)                           |
| trestbps    | Continuous | Resting blood pressure (mm Hg)                 |
| chol        | Continuous | Serum cholesterol (mg/dl)                      |
| fbs         | Nominal    | Fasting blood sugar > 120 mg/dl (1 = True)     |
| restecg     | Nominal    | Resting ECG results (0–2)                      |
| thalch      | Continuous | Max heart rate achieved                        |
| exang       | Nominal    | Exercise-induced angina (1 = Yes)             |
| oldpeak     | Continuous | ST depression by exercise                      |
| slope       | Nominal    | Slope of peak ST segment (0–2)                 |
| num         | Nominal    | Target (0 = No Disease, 1+ = Disease)          |

Dropped features: `ca`, `thal` (due to missing data)

### ⚙️ Methodology

- Encoded categorical variables
- Handled missing values using KNN imputation
- Capped outliers using 1.5×IQR
- Created `age_group` feature (Young/Middle/Senior)
- Standardized numeric features
- Split data (80% train, 20% test)
- Applied GridSearchCV for Logistic Regression

### 📈 Results

| Metric         | Value     |
|----------------|-----------|
| Accuracy       | 0.8043    |
| Precision (1)  | 0.87      |
| Recall (1)     | 0.79      |
| F1-Score (1)   | 0.83      |

**Confusion Matrix (test set of 184 samples):**

| Actual \ Pred | 0 | 1 |
|---------------|---|---|
| 0             | 62| 13|
| 1             | 23| 86|

### 🔍 Conclusion

- Solid baseline with 80% accuracy.
- Precision is high, but some positive cases missed (false negatives).
- Next steps: handle class imbalance, use ensembles, add SHAP analysis.

---

## 🛍️ Customer Segmentation using K-Means Clustering

### 📋 Project Overview

K-Means clustering is applied to identify customer segments based on Annual Income and Spending Score. Useful for targeted marketing strategies.

### 🗂️ Dataset Description

**File:** `Mall_Customers.csv`  
**Size:** 200 records  
**Source:** Kaggle

| Column               | Type      | Description                                  |
|----------------------|-----------|----------------------------------------------|
| CustomerID           | Integer   | Unique customer ID                           |
| Gender               | Categorical | Male/Female                               |
| Age                  | Integer   | Age of customer                              |
| Annual Income (k$)   | Integer   | Annual income in $1000s                      |
| Spending Score (1–100)| Integer  | Mall-assigned spending score                 |

### ⚙️ Methodology

- Selected features: `Annual Income` and `Spending Score`
- Scaled features using StandardScaler
- Used the elbow method to determine optimal `k=5`
- Applied K-Means clustering
- Interpreted clusters by centers

### 📊 Cluster Centers (k=5)

| Cluster | Income (k$) | Spending Score |
|---------|-------------|----------------|
| 0       | 55.30       | 49.52          |
| 1       | 86.54       | 82.13          |
| 2       | 25.73       | 79.36          |
| 3       | 88.20       | 17.11          |
| 4       | 26.30       | 20.91          |

### 🔍 Interpretation

- **Cluster 1**: High income & high spending → Premium segment
- **Cluster 2**: Low income & high spending → Impulse buyers
- **Cluster 3**: High income & low spending → Frugal rich
- **Cluster 4**: Low income & low spending → Budget group
- **Cluster 0**: Average income & spending → Regulars

### 📈 Evaluation

- Used Elbow Method and Silhouette Score (~0.56) for quality
- Clusters are interpretable and useful for campaign targeting

---

## 🛠️ Tools & Libraries

- Python 3.x
- pandas, numpy
- scikit-learn
- matplotlib, seaborn
- scikit-plot

---
