# Boston-house-price-prediction

**Predicting the median home value using classical and deep learning models on the Boston Housing dataset.**

This project walks through a complete regression pipeline—from data preprocessing to model training and evaluation. It's beginner-friendly, structured for reproducibility, and demonstrates both classical ML (e.g., Linear Regression, XGBoost) and deep learning techniques (via Keras).

---


---

## 🚀 Overview

### 📌 Goal

To predict the `MEDV` (Median value of owner-occupied homes in $1000s) using housing features such as crime rate, number of rooms, tax rate, etc.

### 💡 Highlights

- End-to-end machine learning workflow
- Applied linear and non-linear models
- Feature selection & multicollinearity handling using VIF
- Performance evaluation using RMSE, MAE, R²
- Deep learning regression with Keras for comparative analysis

---

## 🧹 Data Preprocessing

- Loaded `housing.csv` into a Pandas DataFrame
- Checked for missing/null values
- Scaled numeric features using `StandardScaler`
- Split into training (80%) and test (20%) sets

---

## 📊 Exploratory Data Analysis

- Explored relationships using:
  - Correlation heatmaps
  - Boxplots and scatterplots
- Found **LSTAT** (% low-status population) and **RM** (number of rooms) as most influential features
- Used **Variance Inflation Factor (VIF)** to detect multicollinearity
  - Removed `TAX` due to high redundancy

### 📈 Correlation Heatmap  
![Correlation Heatmap](plots/correlation_heatmap.png)

---

## 🔍 Model Training & Comparison

### Classical Models Used:

- Linear Regression
- Ridge & Lasso
- Random Forest
- XGBoost

### Evaluation Metrics:

- **RMSE**
- **MAE**
- **R² score**

🏆 **Best Model**: **XGBoost**  
**RMSE ≈ 2.8**, **R² ≈ 0.83**

### 🔧 Deep Learning Model (Keras)

- Simple MLP: Dense layers with ReLU activations and dropout
- Slightly lower performance than XGBoost but valuable for experimentation

---

## 🧠 Key Insights

- **LSTAT** and **RM** are highly predictive of house prices.
- Handling multicollinearity significantly stabilizes linear models.
- Ensemble methods like XGBoost outperform linear models by capturing non-linearities.
- Deep learning requires more hyperparameter tuning for structured/tabular data.

---

## 🛠️ Setup Instructions

Install required packages:

```bash
pip install -r requirements.txt
