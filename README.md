# E-Commerce Customer Churn Analysis & Prediction

## Project Overview

This project analyzes customer churn in an e-commerce dataset and builds machine learning models to identify patterns associated with customer churn.

The project follows the business intelligence workflow:

**Data → Information → Insights → Decision → Action**

The analysis focuses on customer tenure, complaints, cashback amount, order behavior, satisfaction, and other customer-related variables.

## Objectives

* Understand the structure and quality of the customer dataset.
* Clean missing and duplicate data.
* Explore factors associated with customer churn.
* Build machine learning models for churn prediction.
* Compare Logistic Regression and Random Forest.
* Identify important predictive features.
* Translate analytical findings into practical customer-retention recommendations.

## Dataset

The project uses the **E-Commerce Customer Churn Analysis and Prediction** dataset.

Dataset file:

`E Commerce Dataset.xlsx`

The workbook contains the customer data and a data dictionary.

## Dataset Summary

* Records: **5,630 customers**
* Variables: **20 columns**
* Target variable: `Churn`
* Identifier: `CustomerID`
* Churned customers: **948**
* Non-churned customers: **4,682**
* Overall observed churn rate: **16.84%**

## Data Cleaning

The following preprocessing steps were performed:

* Checked for duplicate rows.
* Checked for duplicate customer IDs.
* Identified missing values.
* Filled missing numerical values using the median.
* Filled missing categorical values using the mode.
* Retained `CustomerID` as an identifier but excluded it from model features.
* Kept `Churn` as the prediction target.

After cleaning:

* Missing values: **0**
* Duplicate rows: **0**
* Duplicate customer IDs: **0**

## Exploratory Analysis

The analysis examines:

* Overall churn distribution
* Customer tenure
* Satisfaction score
* Complaint status
* Order count
* Days since last order
* Preferred payment mode
* Other customer and order characteristics

Important observed patterns include:

* Churned customers had substantially lower average tenure than non-churned customers.
* Customers who reported complaints had a higher observed churn rate.
* Satisfaction score did not show a simple decreasing relationship with churn.
* Multiple customer-behavior variables are useful for understanding churn.

## Machine Learning

Two classification models were trained:

1. Logistic Regression
2. Random Forest Classifier

The dataset was divided into training and testing sets using a stratified split.

### Model Evaluation

| Model               | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
| ------------------- | -------: | --------: | -----: | -------: | ------: |
| Logistic Regression |   79.04% |    43.72% | 84.21% |   57.55% |  0.8862 |
| Random Forest       |   98.40% |    93.88% | 96.84% |   95.34% |  0.9986 |

Random Forest achieved higher values across the reported evaluation metrics on the held-out test set.

## Important Predictive Features

| Feature                     | Importance |
| --------------------------- | ---------: |
| Tenure                      |     0.2391 |
| CashbackAmount              |     0.0924 |
| Complain                    |     0.0648 |
| WarehouseToHome             |     0.0608 |
| DaySinceLastOrder           |     0.0570 |
| NumberOfAddress             |     0.0501 |
| OrderAmountHikeFromlastYear |     0.0494 |
| SatisfactionScore           |     0.0473 |
| NumberOfDeviceRegistered    |     0.0313 |
| OrderCount                  |     0.0281 |

Feature importance represents model-based predictive association and should not be interpreted as proof of causation.

## Business Recommendations

1. Develop stronger retention and onboarding activities for newer customers.
2. Monitor and resolve customer complaints promptly.
3. Use order recency and customer activity as signals for retention monitoring.
4. Analyze cashback behavior when designing customer-retention strategies.
5. Monitor delivery/location-related customer experience.
6. Use the churn model as a screening tool to identify customers who may require retention attention.

## Project Files

* `AhsanMohamed_EcommerceChurnPrediction.ipynb` — analysis, visualization, preprocessing, and machine learning code.
* `requirements.txt` — Python dependencies.
* `E Commerce Dataset.xlsx` — project dataset.
* `PROJECT_REPORT.md` — project report.

## How to Run

### 1. Create a virtual environment

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 2. Install dependencies

```bash
python3 -m pip install -r requirements.txt
```

### 3. Start Jupyter

```bash
jupyter notebook
```

### 4. Open the notebook

Open:

`AhsanMohamed_EcommerceChurnPrediction.ipynb`

Run the notebook cells from top to bottom.

## Author

**Ahsan Mohamed**
B.E. Computer Science and Engineering (AI & ML)
Loyola Institute of Technology & Science, Anna University
