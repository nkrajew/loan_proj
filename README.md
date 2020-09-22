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


## EDA
I looked at a few box plots and distributions to understand the data. I also transformed one of my created variables to be more Gaussian.

![alt text](https://github.com/nkrajew/loan_proj/blob/master/images/barplots_resize.PNG "Bar plots")
![alt text](https://github.com/nkrajew/loan_proj/blob/master/images/dist_plot_pre_resize.PNG "Dist plot")
![alt text](https://github.com/nkrajew/loan_proj/blob/master/images/dist_plot_post_resize.PNG "Log Transformed plot")

## Model Building
First, I created dummy variables for the categorical features(Dependents, Propert_Area, Loan_Amount_Term). Next, I scaled the non-binary numerical features (LoanAmount, TotalIncome). Lastly, I split the data into train and test sets with a split of 75/25, respectively. 

For this project, I created 4 different models and evaluated them based on **accuracy**. I chose accuracy as the main metric since I believe the "cost" of misclassification isn't that great. Therefore, just worrying about whether the model generally predicting correctly seemed an appropriate measure of success. There is, however, a slight disadvantage to using accuracy for this dataset. The dataset is slightly imbalanced (2:1), therefore just guessing "Yes" everytime will yield an accuracy of ~67%. I used this knowledge as a bench mark, meaning my model had to beat a 67% accuracy to be considered useful.

### Models:
- **Logistic Regression** – Baseline model
- **Decision Tree Classifier** – It would be easy to interpret due to the smaller data size and *can* perform feature selection
- **Random Forest Classifier** – I wanted to see if it would outperform the other models, however, if it did, I wouldn't select the model to use due to its difficulty to intepret
- **K-Nearest Neighbors** -It's a simple, fast, and versatile classifier. 

## Model Performance
The baseline Logistic Regression model outperformed the other models on the test sets.

![alt text](https://github.com/nkrajew/loan_proj/blob/master/images/results.PNG "Results")

## Potential Next Steps
- Look for more features to engineer
  - Add co-applciant binary for if there was a co-applicant or not
  - Further research the domain
  - Consult with a subject matter expert
- Build a more complex model (e.g. XGB)
- Clean up the data leak that occurs by imputing/scaling before splitting the data
- Balance the dataset
- Productionize model and build a UI so a new client's information can be entered and a prediction can be made easily
