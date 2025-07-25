# Boston-house-price-prediction

**Predicting the median home value using classical and deep learning models on the Boston Housing dataset.**

This project walks through a complete regression pipeline—from data preprocessing to model training and evaluation. It's beginner-friendly, structured for reproducibility, and demonstrates both classical ML (e.g., Linear Regression, XGBoost) and deep learning techniques (via Keras).

---


## Overview

### Goal

To predict the `MEDV` (Median value of owner-occupied homes in $1000s) using housing features such as crime rate, number of rooms, tax rate, etc.

## Data Preprocessing

- Loaded `housing.csv` into a Pandas DataFrame
- Checked for missing/null values
- Scaled numeric features using `StandardScaler`
- Split into training (80%) and test (20%) sets

---

## Exploratory Data Analysis

- Explored relationships using:
  - Correlation heatmaps
  - Boxplots and scatterplots
- Found **LSTAT** (% low-status population) and **RM** (number of rooms) as most influential features
- Used **Variance Inflation Factor (VIF)** to detect multicollinearity
  - Removed `TAX` due to high redundancy

## 🔍 Model Training & Comparison

### Classical Model Used:

- Linear Regression

### Evaluation Metrics:

- **RMSE**
- **R² score**


## 🧠 Key Insights

- **LSTAT** and **RM** are highly predictive of house prices.
- Handling multicollinearity significantly stabilizes linear models.


