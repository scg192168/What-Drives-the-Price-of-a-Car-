# What-Drives-the-Price-of-a-Car-

## Overview

This project analyzes a large dataset of used car listings to identify the key factors that influence vehicle prices. The dataset is derived from a Kaggle dataset originally containing 3 million records, with a reduced version of approximately 426,000 entries used for this analysis.

The goal is to provide actionable insights for a used car dealership to improve inventory selection and pricing strategy.

## Business Objective

From a business perspective, the objective is to understand which vehicle attributes most strongly influence used car prices.

From a data science perspective, this is a **supervised regression problem**, where:

* Target variable: Price
* Features: Vehicle characteristics such as year, mileage, manufacturer, condition, fuel type, transmission, and vehicle type

## Dataset

The dataset contains:

-> ~426,000 used car listings
-> 18 features including:

  * Year
  * Manufacturer
  * Model
  * Condition
  * Fuel type
  * Odometer
  * Transmission
  * Title status
  * Vehicle type
  * Paint color
  * State

## Data Preparation

Several cleaning and preprocessing steps were performed:

* Removed invalid entries (price = 0 or extreme outliers > $100,000)
* Filtered unrealistic year values
* Cleaned odometer values (removed missing and extreme values)
* Dropped irrelevant columns (ID, VIN)
* Handled missing values using:
* Median imputation (numerical features)
* Most frequent imputation (categorical features)
* Applied **log transformation** to price to reduce skewness
* Encoded categorical variables using **One-Hot Encoding**
* Scaled numerical features

## Modeling Approach

Three regression models were built and compared:

1. Linear Regression**
2. Ridge Regression**
3. Lasso Regression**

A full preprocessing and modeling pipeline was implemented using **scikit-learn**, including:

* ColumnTransformer
* Pipelines
* GridSearchCV for hyperparameter tuning
  
## Model Evaluation

Models were evaluated using:

* RMSE (Root Mean Squared Error)
* MAE (Mean Absolute Error)
* R² Score

# Key Results:

* Linear Regression and Ridge performed similarly
* Linear Regression achieved the highest R²
* Lasso performed slightly worse
* The best model achieved an R² score of approximately 0.34

# Key Findings

* Newer vehicles** tend to have higher prices
* Higher mileage (odometer)** significantly reduces price
* Manufacturer and vehicle type** influence resale value
* Condition and title status** impact pricing
* Certain categories of vehicles consistently retain higher value

# Business Recommendations

Based on the analysis, used car dealerships should:

1. Prioritize **newer vehicles with lower mileage**
2. Focus on **clean-title vehicles in good condition**
3. Stock manufacturers and vehicle types with **strong value retention**
4. Avoid high-mileage, older vehicles unless priced aggressively
5. Ensure listings include **complete and accurate information**

# Limitations

* The model explains only part of price variation (R² ≈ 0.34)
* Important factors not included:

  * Trim level
  * Accident history
  * Market demand variations
  * Seller behavior
* Dataset contains missing and noisy real-world data

# Project Structure

```
used-car-price-analysis/
│
├── data/
│   └── vehicles.csv
├── prompt_II.ipynb
├── README.md
```

# How to Run

1. Clone the repository:

```
git clone https://github.com/YOUR-USERNAME/used-car-price-analysis.git
```

2. Install dependencies:

```
pip install pandas numpy matplotlib seaborn scikit-learn
```

3. Run Jupyter Notebook:

```
jupyter notebook
```
4. Open:

```
prompt_II.ipynb
```
# Summary

This project demonstrates how data cleaning, feature engineering, and regression modeling can be used to extract meaningful insights from real-world data. The results provide practical guidance for improving used car inventory and pricing decisions.

## Notebook

View the full analysis here:
- prompt_II.ipynb
