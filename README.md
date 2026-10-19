# Obesity Prevalence Prediction Based on Demographics in Adults and Children

## Overview

This project applies machine learning techniques to analyse and predict obesity prevalence in the United States across adult and childhood populations.

The project consists of two complementary machine learning tasks:

1. **Adult Obesity Prevalence Forecasting** — a regression problem using Random Forest Regressor and XGBoost Regressor.
2. **Childhood Obesity Risk Prediction** — a classification problem using Logistic Regression and CatBoost Classifier.

The analyses use publicly available U.S. health datasets covering demographic, geographic, temporal and survey-related information.

---

## Project Objectives

The main objectives of this project are to:

- Predict state-level adult obesity prevalence using ensemble regression methods.
- Identify important demographic, geographic, temporal and survey-related predictors.
- Classify elevated obesity prevalence among children participating in the WIC programme.
- Compare the performance of different machine learning algorithms.
- Evaluate the impact of feature engineering on predictive performance.
- Provide interpretable insights that could support public-health analysis and targeted intervention strategies.

---

# Project Structure

```text
obesity-prevalence-prediction/
│
├── README.md
├── ML_FINAL_Regression.ipynb
├── ML_FINAL_Classification.ipynb
├── requirements.txt
├── .gitignore
│
├── data/
│   └── README.md
│
└── results/
    └── README.md
```

---

# 1. Adult Obesity Prevalence Forecasting

### Notebook

`ML_FINAL_Regression.ipynb`

The first analysis treats obesity prevalence as a continuous prediction problem.

The analysis uses data from the:

**Nutrition, Physical Activity, and Obesity – Behavioral Risk Factor Surveillance System (BRFSS)**

Dataset source:

https://catalog.data.gov/dataset/nutrition-physical-activity-and-obesity-behavioral-risk-factor-surveillance-system

### Models

Two ensemble regression algorithms are compared:

- Random Forest Regressor
- XGBoost Regressor

These models were selected because they can capture nonlinear relationships and interactions within structured health data.

---

## Adult Data Processing

The analysis includes:

- Data cleaning
- Missing-value handling
- Outlier handling
- Target-variable preparation
- Categorical feature encoding
- Geographic feature extraction
- Temporal feature preparation
- Feature engineering
- Exploratory Data Analysis
- Model training
- Hyperparameter tuning
- Model evaluation
- Feature importance analysis

The modelling process uses an 80/20 training-test split and GridSearchCV for hyperparameter tuning.

---

## Adult Model Evaluation

The regression models are evaluated using:

- **RMSE — Root Mean Squared Error**
- **MAE — Mean Absolute Error**
- **R² — Coefficient of Determination**

Reported results:

| Model | RMSE | MAE | R² |
|---|---:|---:|---:|
| Random Forest | 3.35 | 2.22 | 0.84 |
| XGBoost | 3.88 | 2.84 | 0.79 |

Based on the reported evaluation results, Random Forest achieved the stronger performance, with lower RMSE and MAE and a higher R² score.

Feature-importance analysis identified variables including `QuestionID_encoded` and `Latitude` among the important predictors reported in the study.

---

# 2. Childhood Obesity Risk Prediction

### Notebook

`ML_FINAL_Classification.ipynb`

The second analysis investigates elevated obesity prevalence among children participating in the WIC programme.

The study focuses on children in the following age groups:

- 3–23 months
- 2–4 years

The analysis uses the:

**Nutrition, Physical Activity, and Obesity – Women, Infant, and Child (WIC)** dataset.

Dataset source:

https://catalog.data.gov/dataset/nutrition-physical-activity-and-obesity-women-infant-and-child

---

## Classification Target

The classification task creates a binary target based on obesity prevalence.

```text
Elevated_Obesity = 1
when prevalence > 15%

Elevated_Obesity = 0
when prevalence ≤ 15%
```

The objective is to classify whether the observed prevalence falls into the elevated-obesity category.

---

## Childhood Models

Two classification algorithms are evaluated:

### Logistic Regression

Logistic Regression provides an interpretable baseline for binary classification and allows examination of relationships between predictors and the classification outcome.

### CatBoost Classifier

CatBoost is used as a gradient-boosting classification approach capable of modelling nonlinear relationships and interactions within structured data.

The original study specifically evaluates Logistic Regression and CatBoost for childhood obesity classification.

---

## Feature Engineering

The childhood analysis includes engineered variables designed to capture regional and temporal patterns, including:

- Regional obesity patterns
- Temporal trends
- Year-related information
- Demographic characteristics
- Geographic characteristics

The study reports that `Regional_Obesity` improved predictive performance during feature engineering.

Categorical variables are transformed for modelling, while numerical variables are processed to support the classification algorithms.

---

## Classification Evaluation

The childhood models are evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

Reported results in the study include:

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 0.82 | 0.65 | 0.84 | 0.73 | 0.92 |
| CatBoost | 0.88 | 0.81 | 0.73 | 0.77 | 0.94 |

The reported results indicate that CatBoost achieved higher overall accuracy and ROC-AUC, while Logistic Regression achieved higher recall in the reported evaluation.

---

# Methodology

The project follows the **CRISP-DM (Cross-Industry Standard Process for Data Mining)** framework.

The main stages are:

```text
Business Understanding
        ↓
Data Understanding
        ↓
Data Preparation
        ↓
Modelling
        ↓
Evaluation
        ↓
Deployment Considerations
```

---

# Technology Stack

### Programming Language

- Python

### Development Environment

- Jupyter Notebook

### Data Analysis

- pandas
- NumPy

### Visualisation

- Matplotlib
- Seaborn

### Machine Learning

- scikit-learn
- XGBoost
- CatBoost

### Statistical Analysis

- statsmodels

---

# Installation

Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/obesity-prevalence-prediction.git
```

Navigate to the project directory:

```bash
cd obesity-prevalence-prediction
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

---

# Dataset Setup

The raw datasets are not included in this repository.

Please download the datasets from their original public sources.

## Adult Dataset

Download:

**Nutrition, Physical Activity, and Obesity – Behavioral Risk Factor Surveillance System**

https://catalog.data.gov/dataset/nutrition-physical-activity-and-obesity-behavioral-risk-factor-surveillance-system

Save the dataset as:

```text
Obesity_adult.csv
```

---

## Childhood Dataset

Download:

**Nutrition, Physical Activity, and Obesity – Women, Infant, and Child**

https://catalog.data.gov/dataset/nutrition-physical-activity-and-obesity-women-infant-and-child

Save the dataset as:

```text
Obesity_child.csv
```

Place the datasets in the location expected by the notebooks.

---

# Running the Project

## Adult Analysis

Open:

```text
ML_FINAL_Regression.ipynb
```

Run the cells sequentially.

The notebook covers:

1. Dataset loading
2. Data exploration
3. Data cleaning
4. Missing-value treatment
5. Feature engineering
6. Exploratory analysis
7. Train-test split
8. Model training
9. Hyperparameter tuning
10. Model evaluation
11. Feature importance analysis

---

## Childhood Analysis

Open:

```text
ML_FINAL_Classification.ipynb
```

Run the cells sequentially.

The notebook covers:

1. Dataset loading
2. Data exploration
3. Data cleaning
4. Target-variable creation
5. Feature engineering
6. Data transformation
7. Classification modelling
8. Hyperparameter tuning
9. Model evaluation
10. Model comparison

---

# Key Findings

### Adult Obesity

The Random Forest model achieved the strongest reported regression performance:

- RMSE: **3.35**
- MAE: **2.22**
- R²: **0.84**

The analysis identified geographic and survey-related variables, including `QuestionID_encoded` and `Latitude`, among important predictors.

### Childhood Obesity

The classification analysis found strong predictive performance from both Logistic Regression and CatBoost.

The reported results show:

- CatBoost: higher accuracy and ROC-AUC
- Logistic Regression: higher recall

This demonstrates the importance of evaluating multiple classification metrics rather than relying on accuracy alone.

---

# Potential Applications

The modelling framework could potentially support:

- Public-health surveillance
- Identification of higher-risk geographic areas
- Demographic pattern analysis
- Resource-allocation planning
- Early identification of elevated prevalence patterns
- Further development of public-health decision-support applications

These are potential applications of the research and not clinical or medical recommendations.

---

# Future Work

Potential future improvements include:

- More advanced hyperparameter optimisation
- Improved handling of class imbalance
- Additional feature-selection approaches
- SHAP-based model explainability
- Model calibration
- Validation against additional datasets
- Deployment through a secure application
- Further investigation of temporal and geographic patterns

The original research also identifies techniques such as SMOTE, Bayesian optimisation and SHAP-based explanations as possible future directions.

---

# Data Sources

### Adult / BRFSS

https://catalog.data.gov/dataset/nutrition-physical-activity-and-obesity-behavioral-risk-factor-surveillance-system

### Childhood / WIC

https://catalog.data.gov/dataset/nutrition-physical-activity-and-obesity-women-infant-and-child

---

# Academic Context

**Programme:** MSc in Data Analytics  
**Module:** Data Mining and Machine Learning (H9DMML)  
**Institution:** National College of Ireland  
**Project:** Obesity Prevalence Prediction Based on Demographics in Adults and Children

---

# Disclaimer

This repository is an academic machine learning project developed for educational and research purposes.

The models are not intended to provide medical diagnosis, individual clinical assessment or medical advice. Predictions should not be used as a substitute for professional healthcare assessment.
