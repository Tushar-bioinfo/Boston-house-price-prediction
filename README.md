#  Boston House Price Prediction

This project presents an end-to-end workflow for understanding and predicting Boston housing prices using multiple linear regression. The dataset originates from the UCI Machine Learning Repository (via CMU), and the analysis is designed to explore data patterns, evaluate predictors, and deploy a custom-built price estimator with confidence intervals.

---

##  Project Objectives

- Conduct in-depth exploratory data analysis (EDA) to understand Boston housing trends.
- Develop and validate linear regression models (standard and log-transformed).
- Evaluate model assumptions using VIF, residual plots, and BIC.
- Create a property price estimator that incorporates today's inflation and user-defined confidence.

---

##  Exploratory Data Analysis

The EDA covered the following key analyses:

- **Distributions**: House prices, number of rooms, LSTAT, access to highways, etc.
- **Correlations**: Heatmaps, pairplots, and jointplots were used to understand relationships.
- **Multicollinearity**: Variance Inflation Factor (VIF) was used to evaluate redundant predictors.
- **Feature Transformations**: Log transformation of prices to normalize skewed distribution.
- **Model Simplification**: Based on BIC and p-values, features like `INDUS` and `AGE` were removed.

---

##  Modeling Workflow

We implemented multivariable regression using both raw and log-transformed price targets. Key steps included:

1. **Model Training**:
    ```python
    regr = LinearRegression()
    regr.fit(x_train, y_train)
    ```

2. **Model Evaluation**:
    ```python
    r2_train = regr.score(x_train, y_train)
    r2_test = regr.score(x_test, y_test)
    ```

3. **Statsmodels for Interpretability**:
    ```python
    model = sm.OLS(y_train, sm.add_constant(x_train)).fit()
    model.summary()
    ```

4. **Prediction Function**:
    Custom estimator using number of rooms, proximity to river, and confidence level:
    ```python
    get_log_estimate(rooms_num=3, next_2_river=True, high_confidence=True)
    ```

5. **Scaling Estimates**:
    Adjusted predictions to reflect current market values using inflation scaling.

---

##  Residual & Diagnostic Testing

tested for:

- Residual skewness and normality
- Homoscedasticity of residuals
- Predicted vs. actual performance
- Prediction intervals using log-scale ± 2×RMSE


