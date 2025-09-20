# End-to-End Car Price Prediction

![Project Demo](https://github.com/LearnCode801/Car-Price-Prediction/blob/main/Screenshot%202024-10-30%20142815.png)

A comprehensive machine learning project for predicting used car selling prices using various vehicle attributes. This project implements Random Forest regression with hyperparameter tuning to provide accurate price predictions for the used car market.

## 🎬 Project Demo

[![Project Demo Video](https://img.shields.io/badge/Watch-Demo%20Video-red?style=for-the-badge&logo=youtube)](https://lnkd.in/p/dkvhfwzg)

## 📓 Project Notebook

[![View Notebook](https://img.shields.io/badge/View-Jupyter%20Notebook-orange?style=for-the-badge&logo=jupyter)](https://github.com/LearnCode801/Car-Price-Prediction/blob/main/End%20to%20End%20-%20Car%20Price%20Prediction.ipynb)

## 📊 Project Overview

This project aims to help users estimate the selling price of used cars based on key vehicle characteristics such as year, present price, kilometers driven, fuel type, seller type, transmission, and ownership history. The model serves both buyers and sellers in making informed decisions in the used car market.

## 🎯 Key Features

- **Advanced ML Algorithm**: Random Forest Regression with hyperparameter optimization
- **Feature Engineering**: Created car age features and handled categorical variables
- **Data Preprocessing**: Comprehensive data cleaning and encoding
- **Feature Importance Analysis**: Identified key factors affecting car prices
- **Model Persistence**: Saved model for deployment using pickle
- **Visualization**: Detailed EDA with correlation analysis and distribution plots

## 📈 Dataset Information

**Source**: Used Car Price Dataset  
**Records**: 301 car sales records  
**Features**: 8 key attributes after preprocessing  
**Target Variable**: Selling Price (in lakhs)

### Original Dataset Features:
1. **Car_Name**: Vehicle model name
2. **Year**: Manufacturing year (2003-2018)
3. **Selling_Price**: Actual selling price (target variable)
4. **Present_Price**: Current market price
5. **Kms_Driven**: Total kilometers driven (500 - 500,000 km)
6. **Fuel_Type**: Petrol, Diesel, or CNG
7. **Seller_Type**: Dealer or Individual
8. **Transmission**: Manual or Automatic
9. **Owner**: Number of previous owners (0-3)

### Processed Features:
- **Present_Price**: Current market value
- **Kms_Driven**: Vehicle usage indicator  
- **Owner**: Ownership history
- **no_year**: Car age (2020 - manufacturing year)
- **Fuel_Type_Diesel**: Binary encoding for diesel cars
- **Fuel_Type_Petrol**: Binary encoding for petrol cars
- **Seller_Type_Individual**: Binary encoding for individual sellers
- **Transmission_Manual**: Binary encoding for manual transmission

## 🔧 Data Preprocessing

### Data Quality Assessment:
- **Missing Values**: 0 (complete dataset)
- **Duplicates**: Handled through data validation
- **Outliers**: Analyzed using box plots and statistical methods

### Feature Engineering Steps:
1. **Car Age Calculation**: `no_year = 2020 - Year`
2. **Categorical Encoding**: One-hot encoding for categorical variables
3. **Feature Removal**: Dropped `Car_Name` to avoid overfitting
4. **Data Type Optimization**: Ensured proper data types for all features

### Data Distribution:
- **Price Range**: ₹0.10 - ₹35.00 lakhs
- **Car Age**: 2 - 17 years
- **Fuel Type Distribution**: Petrol (majority), Diesel, CNG
- **Transmission**: Manual (majority), Automatic

## 🤖 Machine Learning Implementation

### Algorithm Selection:
**Random Forest Regressor** was chosen for its:
- Robust performance with mixed data types
- Feature importance capabilities  
- Resistance to overfitting
- Excellent handling of non-linear relationships

### Model Performance:
- **Training Accuracy**: Near perfect fit on training data
- **Feature Importance**: Present_Price (38.2%) as top predictor
- **Cross-Validation**: 5-fold CV with negative MSE scoring
- **Hyperparameter Optimization**: RandomizedSearchCV implementation

### Hyperparameter Tuning Results:
```python
Best Parameters:
{
    'n_estimators': 700,
    'min_samples_split': 15, 
    'min_samples_leaf': 1,
    'max_features': 'auto',
    'max_depth': 20
}
```

## 📊 Feature Importance Analysis

Based on Extra Trees Regressor analysis:

1. **Present_Price** (38.24%) - Current market value
2. **Fuel_Type_Diesel** (22.26%) - Diesel vehicle indicator
3. **Seller_Type_Individual** (13.05%) - Individual seller indicator
4. **Transmission_Manual** (13.18%) - Manual transmission
5. **no_year** (7.86%) - Car age

## 📊 Model Validation

### Performance Metrics:
- **Cross-Validation Score**: Optimized using RandomizedSearchCV
- **Feature Importance**: Validated using Extra Trees Regressor
- **Residual Analysis**: Normal distribution of prediction errors
- **Scatter Plot Analysis**: Good correlation between predicted vs actual values

### Model Insights:
1. **Present Price Impact**: Strongest predictor (38% importance)
2. **Fuel Type Effect**: Diesel cars tend to have higher resale value
3. **Seller Type Influence**: Dealer vs Individual seller pricing patterns
4. **Age Depreciation**: Clear negative correlation with car age
5. **Transmission Preference**: Manual transmission market dynamics

## 📈 Exploratory Data Analysis

### Key Findings:
1. **Price Distribution**: Right-skewed distribution with most cars under ₹10 lakhs
2. **Correlation Analysis**: Strong positive correlation (0.88) between present price and selling price
3. **Fuel Type Patterns**: Diesel cars show higher selling prices on average
4. **Age Impact**: Clear depreciation trend with increasing car age
5. **Seller Type Effect**: Dealer prices generally higher than individual sellers

### Visualizations Include:
- Correlation heatmap showing feature relationships
- Box plots for outlier detection
- Pair plots revealing feature interactions
- Feature importance bar charts
- Residual distribution plots

## 🎯 Business Applications

### For Car Sellers:
- **Price Optimization**: Set competitive selling prices
- **Market Analysis**: Understand factors affecting car value
- **Timing Decisions**: Optimal time to sell based on depreciation

### For Car Buyers:
- **Price Validation**: Verify if asking price is fair
- **Negotiation Tool**: Use predictions for price negotiations
- **Market Insights**: Understand value drivers in used car market

### For Dealers:
- **Inventory Pricing**: Accurate pricing for stock vehicles
- **Purchase Decisions**: Evaluate cars for acquisition
- **Market Trends**: Track pricing patterns across segments

---
