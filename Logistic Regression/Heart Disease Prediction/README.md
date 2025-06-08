Heart Disease Prediction Using Logistic Regression
Project Overview
This project aims to predict the presence of heart disease in patients using logistic regression. Heart disease is a critical health issue, impacting patient outcomes and healthcare systems. Identifying at-risk individuals early can guide preventive measures and treatment.
The goal is to build a predictive model that estimates the probability of heart disease based on demographic, clinical, and test-related features. This helps medical professionals identify patients at risk and prioritize interventions.

Dataset Description
The dataset is the Heart Disease UCI dataset from Kaggle, containing records for approximately 920 patients (a variant combining multiple sources) with the following key features:



Feature
Type
Description



id
Continuous
Unique identifier


age
Continuous
Patient’s age in years


sex
Nominal
Gender (Male, Female)


dataset
Nominal
Data source (e.g., Cleveland, Hungary)


cp
Nominal
Chest pain type (0-3)


trestbps
Continuous
Resting blood pressure (mm Hg)


chol
Continuous
Serum cholesterol (mg/dl)


fbs
Nominal
Fasting blood sugar > 120 mg/dl (1 = True, 0 = False)


restecg
Nominal
Resting ECG results (0-2)


thalch
Continuous
Maximum heart rate achieved


exang
Nominal
Exercise-induced angina (1 = Yes, 0 = No)


oldpeak
Continuous
ST depression induced by by exercise


slope
Nominal
Slope of peak exercise ST segment (0-2)


ca
Continuous
Number of major vessels (0-3, dropped)


thal
Nominal
Thalassemia (1-3, dropped)


num
Nominal
Target: Heart disease (0 = No, 1+ = Yes)



Methodology

Data Preprocessing:  

Handle categorical variables (sex, dataset, cp, restecg, slope) using encoding techniques.  
Drop features with excessive missing values (ca, thal).  
Use KNN imputation for missing values in trestbps, chol, fbs, thalch, exang, oldpeak, slope.  
Cap outliers in numeric features at 1.5 * IQR.  
Add feature: age_group (Young: 0-40, Middle: 40-60, Senior: 60+).  
Normalize continuous features using StandardScaler.  
Split the data into training (80%) and testing (20%) sets.


Modeling:  

Train a Logistic Regression model on the training data.  
Tune hyperparameters (C, solver) using GridSearchCV with 5-fold cross-validation.  
Evaluate the model on the test data using accuracy, confusion matrix, and classification metrics.


Evaluation:  

The model achieved an accuracy of approximately 80.43% on the test set.  
Due to potential class imbalance, accuracy alone is not sufficient.  
Recall for heart disease cases (Class 1) was moderate, indicating some missed diagnoses.




Results



Metric
Value



Accuracy
0.8043


Precision (Class 1)
0.87


Recall (Class 1)
0.79


F1-Score (Class 1)
0.83


The confusion matrix for the test set (184 samples) is:



Actual \ Predicted
0 (No Disease)
1 (Disease)



0 (No Disease)
62
13


1 (Disease)
23
86



Interpretation:
Correctly predicted 62 no-disease and 86 disease cases.
Missed 23 disease cases (false negatives), a concern for medical applications.
Strong precision (0.87) for disease prediction, but recall (0.79) suggests room to improve detection.




Conclusion

The logistic regression model provides a solid baseline for heart disease prediction, achieving 80.43% accuracy.
High precision for Class 1 (0.87) is promising, but moderate recall (0.79) indicates missed heart disease cases, critical in healthcare.
Future work can include:  
Handling class imbalance via oversampling (e.g., SMOTE) or class weighting.  
Feature engineering for better predictors (e.g., interaction terms).  
Trying more complex models like Random Forests or Gradient Boosting.  
Cross-validation and hyperparameter tuning for robustness.  
Using SHAP for enhanced feature importance interpretation.




Tools & Libraries

Python 3  
Pandas, NumPy  
Scikit-learn  
Matplotlib, Seaborn  
scikit-plot

