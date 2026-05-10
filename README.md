# 🏡 House Prices Prediction — Regression Project

This project is based on the Kaggle **House Prices: Advanced Regression Techniques** dataset.  
The goal is to predict house prices using a complete machine learning pipeline, including data preprocessing, feature engineering, and model comparison.

---

## 📌 Problem Statement

Predict the `SalePrice` of residential homes using structured tabular data containing numerical, categorical, and ordinal features.

---

## 📊 Dataset

- Source: Kaggle House Prices Competition  
- Samples: ~1460  
- Features: 70+  

Feature types include:
- Numerical (e.g., area, number of rooms)
- Categorical (e.g., neighborhood, house style)
- Ordinal (e.g., quality ratings like Ex, Gd, TA)

---

## 🔍 Exploratory Data Analysis (EDA)

Performed detailed analysis to understand the data:

- Distribution analysis for numerical and categorical features  
- Correlation analysis to identify important variables  
- Scatter plots and bar plots to study relationships with `SalePrice`  
- Outlier detection using boxplots  
- Missing value analysis  

### Key Insights:
- Strong correlation with `SalePrice`:
  - `GrLivArea`, `OverallQual`, `TotalBsmtSF`
- Many numerical features are highly skewed  
- Presence of extreme outliers affecting model performance  

---

## 🧹 Data Cleaning

- Removed unrealistic outliers (e.g., large area with low price)  
- Handled missing values by:
  - Assigning meaningful categories (`NoGarage`, `NoBsmt`)  
  - Creating binary indicators where appropriate  

---

## ⚙️ Feature Engineering

### ✔️ Log Transformation
- Applied `log1p` to skewed numerical features  
- Transformed `SalePrice` for linear models  

---

### ✔️ Binary Features
Created presence/absence indicators:
- `HasGarage`
- `HasPool`
- `HasFireplace`
- `HasPorch`

---

### ✔️ Feature Aggregation
- `TotalBath`
- `TotalPorch`

---

### ✔️ Ordinal Encoding
Converted ordered categorical features into numeric scale:
- Example: `Ex > Gd > TA > Fa > Po`

---

### ✔️ Feature Reduction
- Dropped redundant and low-information features  
- Removed `Id` column  

---

## 🧠 Modeling

Two main approaches were used:

### 🔹 Linear Models
- Linear Regression  
- Ridge Regression  
- Lasso Regression  

Preprocessing:
- Log transformation  
- Feature scaling  

---

### 🔹 Tree-Based Models
- Decision Tree  
- Random Forest  
- Gradient Boosting  
- XGBoost  
- LightGBM  
- CatBoost  

These models handle non-linearity and do not require scaling.

---

## 🏗️ Pipeline Design

Used **Scikit-learn Pipelines** with:
- `ColumnTransformer`
- One-hot encoding for categorical features  
- Selective scaling  

Benefits:
- Clean workflow  
- Prevents data leakage  
- Easy experimentation  

---

## 🔧 Hyperparameter Tuning

Used **GridSearchCV** with cross-validation to tune:
- Regularization strength  
- Tree depth  
- Number of estimators  
- Learning rate  

---

## 📈 Evaluation Metrics

- RMSE (Root Mean Squared Error)  
- MAE (Mean Absolute Error)  
- R² Score  

For linear models:
- Predictions were transformed back using `expm1`  

---

## 🏆 Results

- Log transformation significantly improved linear models  
- Tree-based models performed well on raw features  
- Boosting models achieved the best overall performance  

---

## 🛠️ Tech Stack

- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn  
- XGBoost, LightGBM, CatBoost  

---

## 🚀 How to Run

```bash
git clone <your-repo-link>
cd <repo-name>

pip install -r requirements.txt

jupyter notebook 
