# Employee Attrition Prediction Using Logistic Regression

## Project Overview

This project aims to predict employee attrition in a large company using Logistic Regression. Employee attrition (employees leaving the company) is a critical issue because it impacts project timelines, increases recruiting and training costs, and affects overall company productivity.

The goal is to build a predictive model that estimates the probability of an employee leaving based on various demographic, job, and performance-related features. This helps HR teams identify employees at risk of leaving and take proactive retention measures.

---

## Dataset Description

The dataset contains records for approximately 4,000 employees with the following key features:

| Feature                 | Type       | Description                                             |
|-------------------------|------------|---------------------------------------------------------|
| Age                     | Continuous | Employee’s age                                          |
| Attrition               | Nominal    | Whether the employee left last year (Yes/No)           |
| BusinessTravel          | Nominal    | Frequency of business travel                             |
| Department              | Nominal    | Employee’s department                                   |
| DistanceFromHome        | Continuous | Distance from home (km)                                  |
| Education               | Continuous | Education level                                         |
| EducationField          | Nominal    | Field of education                                      |
| Gender                  | Nominal    | Employee gender                                        |
| JobLevel                | Continuous | Job level within the company (1-5)                      |
| MaritalStatus           | Nominal    | Marital status                                         |
| MonthlyIncome           | Continuous | Monthly income in rupees                                |
| NumCompaniesWorked      | Continuous | Number of previous companies worked at                  |
| PercentSalaryHike       | Continuous | Percent salary hike last year                            |
| PerformanceRating       | Continuous | Performance rating last year                             |
| RelationshipSatisfaction| Continuous | Satisfaction with relationships at work                |
| StockOptionLevel        | Continuous | Level of stock options                                  |
| TotalWorkingYears       | Continuous | Total years of experience                                |
| TrainingTimesLastYear   | Continuous | Number of training sessions last year                    |
| WorkLifeBalance         | Continuous | Work-life balance rating                                |
| YearsAtCompany          | Continuous | Years spent at the company                               |
| YearsSinceLastPromotion | Continuous | Years since last promotion                               |
| YearsWithCurrManager    | Continuous | Years with current manager                               |

---

## Methodology

1. **Data Preprocessing:**  
   - Handle categorical variables using encoding techniques.  
   - Normalize continuous features using StandardScaler.  
   - Split the data into training (80%) and testing (20%) sets.

2. **Modeling:**  
   - Train a Logistic Regression model on the training data.  
   - Evaluate the model on the test data using accuracy, confusion matrix, and classification metrics.

3. **Evaluation:**  
   - The model achieved an accuracy of approximately **85%** on the test set.  
   - However, due to class imbalance (only ~15% employees leave), accuracy alone is not a sufficient metric.  
   - The model's recall for employees who left was low, indicating it missed many true attritions.

---

## Results

| Metric        | Value  |
|---------------|--------|
| Accuracy      | 0.85   |
| Precision (Attrition=1) | Low    |
| Recall (Attrition=1)    | Very Low (misses many actual leavers) |
| F1-Score (Attrition=1)  | Low    |

The confusion matrix showed that the model mostly predicted employees as staying and failed to correctly identify those who left.

---

## Conclusion

- The logistic regression model provides a baseline but struggles with identifying employees likely to leave due to class imbalance.
- Improving recall and balancing precision is critical for this business problem.
- Future work can include:  
  - Handling class imbalance via oversampling/undersampling or class weighting.  
  - Feature engineering for better predictors.  
  - Trying more complex models like Random Forests or Gradient Boosting.  
  - Cross-validation and hyperparameter tuning.

---

## Tools & Libraries

- Python 3  
- Pandas, NumPy  
- Scikit-learn  
- Matplotlib, Seaborn  
- scikit-plot  

---

