# Supervised Regression Project

## Overview

This project was developed as part of the Data Science Program at Datamecum.

The objective is to predict a continuous target variable using supervised machine learning techniques while following a complete end-to-end workflow: data exploration, preprocessing, feature engineering, model selection, hyperparameter tuning and deployment of the final pipeline.

---

## Dataset

* **Type:** Regression
* **Samples:** 436
* **Features:** 10 numerical predictors (`V0` - `V9`)
* **Target:** Continuous numerical variable

The dataset contains missing values and variables with different distributions, requiring careful preprocessing before model training.

---

## Project Workflow

### 1. Exploratory Data Analysis (EDA)

The first stage focused on understanding the dataset through:

* Missing values analysis
* Distribution of numerical variables
* Correlation analysis
* Detection of skewed features
* Outlier inspection

This analysis guided the preprocessing decisions applied later in the project.

---

### 2. Data Preprocessing

Several preprocessing strategies were evaluated.

#### Missing Values

Different imputation methods were compared:

* Median Imputation
* KNN Imputation

#### Feature Engineering

Variable **V3** presented a highly skewed distribution.

A logarithmic transformation was applied after shifting the variable to avoid invalid logarithms for non-positive values.

---

### 3. Model Selection

Several regression algorithms were trained and compared.

Models evaluated:

* Linear Regression
* Ridge Regression
* Lasso Regression
* Decision Tree Regressor
* Random Forest Regressor
* Gradient Boosting Regressor (GBR)
* XGBoost Regressor (XGB)
* Support Vector Regressor (SVR)

Model performance was evaluated using:

* Test Mean Squared Error (MSE)
* Cross-Validation Mean Squared Error

---

### 4. Hyperparameter Tuning

GridSearchCV was performed for the best-performing ensemble models:

* Random Forest
* Gradient Boosting
* XGBoost

The selected models were then retrained using the optimal hyperparameters.

---

### 5. Final Pipeline

The final production pipeline includes:

1. KNN Imputation
2. Log transformation of feature V3
3. Tuned Gradient Boosting Regressor

The complete preprocessing and model are stored together using `joblib`, allowing predictions on new unseen data without repeating preprocessing manually.

---

## Results

The best overall performance was achieved using:

* **Model:** Gradient Boosting Regressor
* **Imputation:** KNN Imputer (`k = 5`)
* **Feature Engineering:** Log transformation of V3

This combination produced the lowest prediction error while maintaining good generalization performance.

---

## Technologies

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* XGBoost
* Joblib

---

## Key Takeaways

This project highlights the importance of:

* Performing a thorough exploratory analysis before modeling.
* Comparing different preprocessing strategies rather than assuming a single approach.
* Evaluating models using both test performance and cross-validation.
* Building reproducible machine learning pipelines suitable for deployment.

---

## Author

**Sandra Gálvez Grau**

Business Intelligence & Data Analyst transitioning into Data Science.
