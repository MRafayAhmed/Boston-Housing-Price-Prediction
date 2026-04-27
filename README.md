# Boston-Housing-Price-Prediction
# Project Overview
This project implements a **machine learning regression task** to predict housing prices in Boston. Three models are developed **from scratch** without using libraries like `sklearn` for modeling:
1. **Linear Regression**
2. **Random Forest**
3. **XGBoost**
The models are evaluated using **RMSE** (Root Mean Squared Error) and **R² Score**, and feature importance is visualized for the Random Forest model.
# Project Steps
# 1. Load Dataset
* Loads the `BostonHousing.csv` file using `pandas`.
* Displays column names.
# 2. Preprocess Data
* Splits the dataset into:
  * Features (`X`)
  * Target variable (`y = medv`)
* Standardizes features (zero mean, unit variance).
* Splits the dataset into training and test sets using an 80/20 split.
# 3. Linear Regression (From Scratch)
* Implements the normal equation:
  $$
  \theta = (X^TX)^{-1}X^Ty
  $$
* Adds a bias term manually.
# 4. Random Forest Regressor (From Scratch)
* Implements:
  * A simple **decision tree regressor**
  * A **random forest** by bootstrapping training samples and averaging predictions from multiple trees
* Uses recursive splitting based on variance minimization.
# 5. XGBoost Regressor (From Scratch)
* Builds an ensemble of trees trained on residuals of previous predictions.
* Uses **gradient boosting** principles with a learning rate to improve predictions.
# 6. Evaluation Metrics
* **RMSE**: Measures average prediction error.
* **R² Score**: Measures how well the predictions approximate the actual values.
# 7. Train and Evaluate
* Trains each model and evaluates on the test set.
* Displays RMSE and R² for each model.
# 8. Feature Importance (Random Forest)
* Traverses each decision tree and counts how often each feature is used in splits.
* Visualizes the most influential features using a horizontal bar chart.

# How to Run the Script
1. Dependencies: Install the required Python libraries:
   ```bash
   pip install pandas numpy matplotlib scikit-learn
   ```
2. CSV File:
   * Place `BostonHousing.csv` in the correct path as used in the script:

     ```
     C:/Users/Ansar-PC/Desktop/developerhub-data-analysis/BostonHousing.csv
     ```
   * Ensure the file contains the `medv` column.
3. Run the script:
   * You can run the script in:

     * Jupyter Notebook
     * Google Colab (update the path)
     * Any Python IDE (e.g., VS Code, PyCharm)

# Observations

# Model Performance (example output):
Model Performance Comparison:
Linear Regression: RMSE = 4.72, R² = 0.73
Random Forest:     RMSE = 3.45, R² = 0.85
XGBoost:           RMSE = 3.25, R² = 0.87
#  Key Insights:
* **XGBoost** performs best due to its ability to model complex patterns and correct errors iteratively.
* **Random Forest** also performs well due to its ensemble nature and variance reduction.
* **Linear Regression** is fast but limited due to its assumption of linear relationships.

# Feature Importance:
* The bar chart shows which features are most frequently used in Random Forest splits.
* This helps interpret the model and identify critical factors affecting housing prices, such as:

  * LSTAT (% lower status population)
  * RM (number of rooms)
  * PTRATIO (pupil-teacher ratio)

# Optional Enhancements
You can consider:

* Adding cross-validation
* Hyperparameter tuning (depth, estimators)
* Implementing regularized regression (Lasso/Ridge)
* Comparing with `scikit-learn`'s built-in models
