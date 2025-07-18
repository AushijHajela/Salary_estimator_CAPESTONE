#  Salary Prediction Capstone Project

This machine learning project predicts the **Expected CTC (Cost to Company)** of job applicants based on their experience, education, role, certifications, and more. It is built using multiple regression models and involves comprehensive preprocessing, feature engineering, model evaluation, and hyperparameter tuning.

---

##  Project Structure
- `salary.ipynb`: Main notebook containing all code
- `expected_ctc.csv`: Dataset with applicant details and expected CTC
- `README.md`: Summary of project
- `report.docx`: Formal project summary

---

## Problem Statement
Build a model to predict **Expected CTC (₹)** using applicant-related data. The model should perform well across different job roles, industries, and education levels.

---

##  EDA & Preprocessing
- Visualized skewness, distribution, and missing data
- Handled categorical and numerical missing values
- Applied log transformation to `Expected_CTC`
- Used mutual information for feature selection
- One-hot encoded relevant features
- Outliers removed using IQR on `Expected_CTC_log`
- Scaled numerical features using `StandardScaler`

---

##  Models Used
| Model                | MAE (₹)     | RMSE (₹)    | R² Score |
|---------------------|-------------|-------------|----------|
| Linear Regression    | 261,948.35  | 411,619.32  | 0.8747   |
| Ridge Regression     | 261,531.98  | 412,338.45  | 0.8743   |
| Lasso Regression     | 266,201.69  | 321,488.82  | 0.9236   |
| Random Forest        | **11,234.78** | **31,825.62** | **0.9993** |
| XGBoost              | 16,044.57   | 32,957.19   | 0.9992   |

---

##  Final Model (Random Forest after outlier removal)
- MAE: ₹10,657.43  
- RMSE: ₹28,427.79  
- R² Score: **0.9994**

---

##  Hyperparameter Tuning
Performed GridSearchCV on RandomForest.  
Best Parameters:
  'n_estimators': 200,
  'max_depth': 50,
  'min_samples_split': 2,
  'min_samples_leaf': 1,
  'max_features': 'sqrt'

