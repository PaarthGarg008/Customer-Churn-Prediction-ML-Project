
# CUSTOMER CHURN PREDICTION & CUSTOMER SEGMENTATION

## Project Overview

This project aims to predict whether a telecom customer is likely to leave the company (churn) and to segment customers into different groups for better business decision-making.

The project uses Machine Learning techniques to analyze customer behavior and identify the factors responsible for customer churn.

---

## Problem Statement

Customer churn is one of the major challenges faced by telecom companies. Losing customers directly impacts revenue and growth.

The objectives of this project are:

1. Predict whether a customer will churn or not.
2. Identify the most important factors affecting churn.
3. Segment customers into groups using K-Means clustering.
4. Provide business insights to improve customer retention.

---

## Dataset

Dataset Used: **Telco Customer Churn Dataset**

The dataset contains information about telecom customers such as:

* Customer demographics
* Account information
* Service subscriptions
* Billing details
* Customer tenure
* Churn status

Target Variable:

* **Churn Value**

  * 1 → Customer churned
  * 0 → Customer retained

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Google Colab

---

## Project Workflow

### 1. Data Loading

The dataset is loaded using Pandas.

```python
pd.read_excel()
```

---

### 2. Data Cleaning

The following preprocessing steps were performed:

* Removed unnecessary columns.
* Converted `Total Charges` to numeric format.
* Handled missing values using median imputation.
* Removed duplicate records.

Columns removed include:

* CustomerID
* Country
* State
* City
* Zip Code
* Latitude
* Longitude
* Churn Reason
* Churn Category

These columns were removed because they either do not contribute to prediction or may cause data leakage.

---

### 3. Data Encoding

Machine Learning algorithms require numerical input.

Categorical columns were converted into numerical form using:

```python
LabelEncoder()
```

This transformed text values into numeric labels.

---

### 4. Exploratory Data Analysis (EDA)

Several visualizations were created to understand customer behavior.

Examples include:

* Churn distribution
* Contract type distribution
* Monthly charges analysis
* Tenure analysis
* Correlation heatmap

These visualizations help identify important churn patterns.

---

### 5. Feature Selection

Feature selection was performed using:

```python
SelectKBest
```

This technique selects the most relevant features for prediction and improves model performance.

---

### 6. Train-Test Split

The dataset was divided into:

* Training Data: 80%
* Testing Data: 20%

```python
train_test_split()
```

Stratified splitting was used to maintain the original churn distribution.

---

### 7. Machine Learning Model

The project uses:

# Random Forest Classifier

Reasons for choosing Random Forest:

* Handles both numerical and categorical features.
* Reduces overfitting.
* Provides feature importance.
* Produces good performance on classification problems.

---

### 8. Hyperparameter Tuning

To improve model performance, Grid Search Cross Validation was used.

```python
GridSearchCV()
```

Parameters tuned:

* Number of trees (`n_estimators`)
* Maximum depth (`max_depth`)
* Minimum samples split
* Minimum samples leaf

The model was optimized based on **Recall Score**.

---

### 9. Cross Validation

Cross-validation was performed to evaluate model stability.

```python
cross_val_score()
```

This ensures that the model performs consistently on different subsets of the dataset.

---

### 10. Model Evaluation Metrics

The following evaluation metrics were used:

* Accuracy Score
* Precision Score
* Recall Score
* F1 Score
* ROC-AUC Score
* Confusion Matrix

Special emphasis was given to **Recall Score** because correctly identifying churn customers is more important than overall accuracy.

---

### 11. ROC Curve

ROC Curve was plotted to evaluate the classification capability of the model.

A higher ROC-AUC score indicates better model performance.

---

### 12. Customer Segmentation

Customer segmentation was performed using:

# K-Means Clustering

Features used:

* Tenure Months
* Monthly Charges
* Total Charges
* CLTV

K-Means groups customers into different segments based on similar characteristics.

This helps businesses create targeted marketing strategies.

---

## Business Insights

Key observations from the analysis:

* Customers with month-to-month contracts are more likely to churn.
* Customers with shorter tenure have higher churn probability.
* Higher monthly charges are associated with increased churn.
* Long-term customers are less likely to leave.
* Customer segmentation helps identify high-value and at-risk customers.

---

## Conclusion

The Random Forest model successfully predicts customer churn and provides valuable insights for customer retention.

Customer segmentation further helps businesses understand customer behavior and design personalized strategies to reduce churn.

---

## Future Improvements

Possible future enhancements include:

* Deploying the model using Streamlit or Flask.
* Comparing multiple ML algorithms.
* Using advanced feature engineering techniques.
* Building a real-time churn prediction dashboard.

---

## Author

**Paarth Garg**
