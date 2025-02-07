# Black Friday Sales Prediction

## Description

This project aims to predict sales during Black Friday, a crucial period for retailers, by leveraging historical transaction data.  Accurate sales forecasting during this high-volume period is essential for optimizing inventory management, staffing, and marketing campaigns.  The model will analyze various factors, potentially including past sales figures, product categories, pricing strategies, promotional activities, and external factors like economic indicators or online search trends.  The goal is to develop a robust predictive model that can provide retailers with valuable insights into anticipated sales volumes, enabling them to make data-driven decisions and maximize profitability during Black Friday. This project will explore different machine learning algorithms and feature engineering techniques to achieve the highest possible prediction accuracy.

---

## Table of Contents
- [Project Introduction](#project-introduction)
- [Dataset Description](#dataset-description)
- [Exploratory Data Analysis (EDA)](#eda)
- [Data Preparation](#data-preparation)
- [Modeling Phase](#modeling-phase)
- [Evaluation Metric](#evaluation-metric)
- [Conclusion](#conclusion)
- [Project Structure](#project-structure)

## Project Introduction
Black Friday marks the beginning of the holiday shopping season in the United States. Retail stores and eCommerce businesses need to set product prices strategically to maximize profits. This project predicts product purchase amounts based on historical sales data, helping retailers optimize pricing strategies.

## Dataset Description
The dataset, sourced from an [Analytics Vidhya](https://datahack.analyticsvidhya.com/) hackathon, includes 537,577 records with 12 columns. It contains customer demographics (age, gender, marital status, city type, years in city), product details (product category), and purchase amounts. Our goal is to predict purchase amounts to facilitate personalized offers.

## EDA
Key observations from data visualization:
- **Gender:** ~75% of purchases are made by males, and men tend to spend more than women.
- **Marital Status:** Single men spend the most; married men tend to spend less.
- **Age Group:** 25-40-year-olds spend the most.
- **City Category:** City B contributes the most to total sales, but City C shows higher per-product sales.
- **Stay in Current City:** New residents (1 year) spend more, while settled individuals (4+ years) spend less.
- **Product Category Analysis:** Some product categories dominate sales, while others have higher average purchase values.

## Data Preparation
- Used `LabelEncoder` for categorical variables (Age, Gender, City_Category).
- Applied `get_dummies` from Pandas to encode categorical variables.
- Filled missing values in `Product_Category_2` and `Product_Category_3`.
- Dropped `User_ID` and `Product_ID` as they don't contribute to the prediction model.

## Modeling Phase
Implemented and compared multiple supervised learning models:
- **Linear Regression**
- **Decision Tree Regressor**
- **Random Forest Regressor**
- **XGBoost Regressor** (performed best with lowest RMSE)

## Evaluation Metric
We used **Root Mean Square Error (RMSE)** to measure prediction accuracy. RMSE quantifies the average difference between predicted and actual purchase values.

## Conclusion
The **XGBoost Regressor** outperformed other models with an RMSE of **2879**, making it the best choice for predicting purchase amounts.

## Project Structure
```
.
├── data/                     # Contains raw dataset files
├── notebooks/                # Jupyter notebooks for data exploration and modeling
├── models/                   # Trained machine learning models
├── src/                      # Source code for data processing and model training
│   ├── data_preprocessing.py # Scripts for cleaning and encoding data
│   ├── model_training.py     # Training and evaluation scripts
│   ├── visualization.py      # Data visualization utilities
├── README.md                 # Project documentation (this file)
├── requirements.txt          # Dependencies required to run the project
└── results/                  # Model performance metrics and plots
```
### Notable Techniques Used
- [Label Encoding](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.LabelEncoder.html) for categorical feature transformation.
- [One-Hot Encoding](https://pandas.pydata.org/docs/reference/api/pandas.get_dummies.html) using `pandas.get_dummies`.
- [Random Forest Regressor](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html) and [XGBoost Regressor](https://xgboost.readthedocs.io/en/latest/python/python_api.html) for machine learning.
- Data visualization using [Seaborn](https://seaborn.pydata.org/) and [Matplotlib](https://matplotlib.org/).

### Libraries and Technologies
- **Python** (Primary language)
- **Pandas** (Data processing)
- **NumPy** (Numerical operations)
- **Scikit-Learn** (Machine Learning)
- **XGBoost** (Optimized gradient boosting)
- **Matplotlib & Seaborn** (Data visualization)
- **Jupyter Notebooks** (Interactive data analysis)

### Dataset Source
- [Analytics Vidhya Black Friday Dataset](https://datahack.analyticsvidhya.com/)

---
This project helps retail businesses understand customer purchasing behavior and optimize pricing strategies during Black Friday sales.

