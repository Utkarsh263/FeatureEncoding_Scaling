# Feature Encoding, Scaling & Missing Value Handling
## Adult Income Dataset (Sklearn Pipeline)

## Project Overview
This project focuses on data preprocessing and feature engineering for the Adult Income (Census Income) dataset. The goal is to prepare raw data so it can be directly used by machine learning models through proper cleaning, encoding, and scaling.

All transformations are implemented using scikit-learn pipelines to ensure reproducibility and industry-standard practices.

---

## Dataset Description
The Adult Income dataset contains demographic and employment-related information used to predict whether an individual earns more than $50K per year.

- Target Variable: income  
- Task Type: Binary Classification  
- Dataset Source: Kaggle (UCIML Adult Census Income)

---

## Data Cleaning
The following cleaning steps are applied:

- Removed extra spaces from column names and string values  
- Replaced "?" entries with NaN  
- Checked missing values across all columns  

Missing values were found only in categorical features:
- workclass  
- occupation  
- native.country  

No numerical features contained missing values.

---

## Missing Value Handling
- Categorical Features: Filled using most frequent (mode) value  
- Numerical Features: No imputation required  

This approach preserves the original data distribution while ensuring completeness.

---

## Feature Classification

### Numerical Features
- age  
- fnlwgt  
- education.num  
- capital.gain  
- capital.loss  
- hours.per.week  

### Categorical Features
- workclass  
- marital.status  
- occupation  
- relationship  
- race  
- sex  
- native.country  

---

## Feature Encoding
- Target Variable (income) is encoded using LabelEncoder  
  - <=50K → 0  
  - >50K → 1  

- Categorical features are encoded using OneHotEncoder with:
  - handle_unknown = "ignore"
  - Dummy variable trap handled automatically

---

## Feature Scaling
StandardScaler is applied to all numerical features to normalize them to:

- Mean = 0  
- Standard Deviation = 1  

This improves model performance and convergence for algorithms such as Logistic Regression, SVM, and KNN.

---

## Preprocessing Pipeline
The preprocessing workflow is implemented using:

- Pipeline  
- ColumnTransformer  

This ensures a clean, modular, and reusable preprocessing structure.

---

## Exploratory Data Analysis (EDA)
Basic insights are generated using:
- Income distribution visualization  
- Correlation heatmap for numerical features  

Visualization libraries used:
- Matplotlib  
- Seaborn  

---

## Output
After preprocessing, the final model-ready dataset is saved as:

adult_processed_sklearn.csv

---

## Libraries Used
- pandas  
- numpy  
- scikit-learn  
- matplotlib  
- seaborn  

---

## Key Learning Outcomes
- Handling missing categorical values effectively  
- Applying correct encoding strategies  
- Understanding the importance of feature scaling  
- Building reproducible preprocessing pipelines using scikit-learn  

---
