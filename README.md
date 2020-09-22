# Loan Prediction: Project Overview
- Created a machine learning model (accuracy = 75%) to predict if a loan applicant will have their application approved.
- Used loan data provided from Kaggle (link below).
- Engineered features from the data to identify families with single earners.
- Performed value imputation for entries with missing data.
- Optimized Logistic Regression, Decision Tree, Random Forest, K-Nearest Neighbors models using GridSearchCV.

## Code and Resources Used
**Python Version:** 3.7\
**Packages:** pandas, numpy, sklearn, seaborn, matplotlib\
**Project Inspiration:** https://towardsdatascience.com/14-data-science-projects-to-do-during-your-14-day-quarantine-8bd60d1e55e1 (Terrence S)

## Data Sources
Loan Data (Kaggle) - https://www.kaggle.com/altruistdelhite04/loan-prediction-problem-dataset

## Data Cleaning
After loading the data, I needed to clean it up in order to build a model. I have listed the changes below:

Imputed values for missing entries of Self_Employed, Dependents, Credit_History, Loan_Amount_Term\
Dropped records that were missing Gender, Married, or LoanAmount\
Made a new column that combined Applicant and Coapplicant Income (named TotalIncome)\
Added a column for if an applicant had more than one dependent and no coapplicant income (named SingleIncome)\
Created dummy variables for:\
 -Dependents\
 -Property_area\
 -Loan_Amount_Term

## EDA
