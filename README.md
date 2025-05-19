# 🚗 Used Car Price Prediction - Machine Learning Regression Project

This project aims to predict the **selling price** of used cars based on various features such as brand, kilometers driven, fuel type, and more. The dataset was processed, cleaned, and modeled using various regression techniques to improve accuracy.

## 📁 Project Structure

├── Second_at.ipynb # Main Jupyter Notebook with all code
├── final_poly_model.joblib # Trained Polynomial Regression model
├── final_converter.joblib # Polynomial feature transformer
├── CAR DETAILS FROM CAR DEKHO.csv # (If included) The raw data file
├── README.md # Project documentation
├── requirements.txt # Requirements to use


## 🧠 Features Used

- Car brand (extracted from name)
- Year of manufacturing
- Kilometers driven
- Fuel type
- Transmission
- Owner type
- ...and more categorical features converted via one-hot encoding

## 🧹 Data Preprocessing

- Removed null values
- Extracted brand name from full car name
- Converted categorical variables using `pd.get_dummies()`
- Removed outliers using visualization (boxplots, etc.)
- Applied logarithmic transformation to `selling_price` for normalization

## ⚙️ Models Applied

- **Linear Regression**
- **Polynomial Regression** (best performance)
- **Ridge, Lasso, ElasticNet** (with GridSearchCV)
- R² score: **~0.72**

## 🔍 Model Deployment Files

- The trained model and feature transformer were saved using `joblib`:
  ```python
  from joblib import dump, load
  dump(model, 'final_poly_model.joblib')
  dump(poly_converter, 'final_converter.joblib')

  # Load when needed
  model = load('final_poly_model.joblib')
  converter = load('final_converter.joblib')

  
