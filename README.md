# DHC-ID 696
# Telco-Churn-Prediction-End-To-End-Pipeline
A production-ready and reusable machine learning pipeline for predicting customer churn using the Scikit-learn Pipeline API. This project demonstrates automated data preprocessing, model training, hyperparameter tuning, evaluation, and model deployment.

## Objective

The objective of this project is to build an end-to-end machine learning pipeline capable of predicting whether a telecom customer is likely to churn based on customer demographics, account information, and service usage details.

---

## Dataset

**Dataset:** Telco Customer Churn Dataset

**Source:** Kaggle

**Dataset Link:** https://www.kaggle.com/datasets/blastchar/telco-customer-churn

**Target Variable:** Churn (Yes / No)

**Dataset Size:** Approximately 7,000 customer records

---

## Methodology

### 1. Data Loading and Inspection

* Loaded the Telco Customer Churn dataset using Pandas.
* Examined dataset structure, feature types, and missing values.
* Identified numerical and categorical features for preprocessing.

### 2. Data Preprocessing

A Scikit-learn Pipeline was used to automate preprocessing tasks.

#### Numerical Features

* Missing values handled using Median Imputation.
* Features standardized using StandardScaler.

#### Categorical Features

* Missing values handled using Most Frequent Imputation.
* Features encoded using OneHotEncoder.

#### ColumnTransformer

* Combined numerical and categorical preprocessing into a single workflow.
* Ensured that appropriate transformations were applied automatically to each feature type.

### 3. Model Development

Two machine learning classification models were implemented:

#### Logistic Regression

* Used as the baseline classification model.
* Integrated directly into the machine learning pipeline.

#### Random Forest Classifier

* Ensemble learning model based on multiple decision trees.
* Used to capture complex patterns within the dataset.

### 4. Hyperparameter Tuning

GridSearchCV was used with 5-fold cross-validation to identify the optimal hyperparameter combination for each model.

#### Logistic Regression Parameters

* C
* Solver

#### Random Forest Parameters

* Number of Estimators
* Maximum Depth
* Minimum Samples Split

### 5. Model Evaluation

The best-performing model was selected based on cross-validation accuracy.

Evaluation metrics included:

* Accuracy Score
* Precision
* Recall
* F1-Score
* Confusion Matrix
* Classification Report

### 6. Pipeline Export

The complete machine learning pipeline, including preprocessing and the trained model, was exported using Joblib.

This allows the model to be loaded and used for future predictions without retraining.

---

## Results

### Selected Model

**Logistic Regression**

### Best Hyperparameters

```python
{
    'model__C': 0.01,
    'model__solver': 'liblinear'
}
```

### Model Performance

| Metric                    | Value  |
| ------------------------- | ------ |
| Cross Validation Accuracy | 80.48% |
| Test Accuracy             | 79.84% |

### Classification Report

| Class        | Precision | Recall | F1-Score |
| ------------ | --------- | ------ | -------- |
| No Churn (0) | 0.84      | 0.90   | 0.87     |
| Churn (1)    | 0.66      | 0.51   | 0.57     |

### Key Findings

* Logistic Regression achieved the best overall performance during cross-validation.
* GridSearchCV successfully identified the optimal model configuration.
* The pipeline automated preprocessing, training, evaluation, and prediction workflows.
* The exported model can be reused directly in deployment environments without retraining.
* The model achieved approximately 80% accuracy on unseen test data.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Joblib

---

## Installation

Install the required dependencies:

```bash
pip install pandas numpy scikit-learn joblib
```

---

## Usage

### Run the Notebook

Open and execute:

```text
Telco_Churn_prediction_.ipynb
```

### Load the Saved Pipeline

```python
import joblib

pipeline = joblib.load("customer_churn_pipeline.pkl")

predictions = pipeline.predict(new_data)
```

---

## Repository Structure

```text
├── Telco_Churn_prediction_.ipynb
├── customer_churn_pipeline.pkl
├── README.md
```

```
```
