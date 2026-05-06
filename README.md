# 🏠 California Housing Price Prediction

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-2.0+-green.svg)](https://pandas.pydata.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.0+-orange.svg)](https://scikit-learn.org/)
[![MIT License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 📌 Project Overview

This project analyzes the **California Housing dataset (1990)** to predict median house values based on various features such as income, location, property characteristics, and proximity to the ocean. The goal is to build and compare multiple regression models to identify the most accurate predictor.

## 🎯 Key Objectives

- Perform **exploratory data analysis (EDA)** to understand data distributions and correlations
- Engineer new features to improve model performance
- Handle missing values and skewed distributions
- Train and compare **5 regression models**:
  - Linear Regression
  - Ridge Regression
  - Lasso Regression
  - Random Forest Regressor
  - Gradient Boosting Regressor
- Evaluate models using **RMSE, R², and MAE**

## 📊 Dataset

**Source:** California Housing dataset (1990 census)

**Size:** 20,640 records × 10 features

**Features:**
| Feature | Description |
|---------|-------------|
| `longitude` | Geographic coordinate |
| `latitude` | Geographic coordinate |
| `housing_median_age` | Median age of houses in block |
| `total_rooms` | Total rooms per block |
| `total_bedrooms` | Total bedrooms per block |
| `population` | Population per block |
| `households` | Number of households |
| `median_income` | Median income in block (scaled) |
| `median_house_value` | **Target variable** |
| `ocean_proximity` | Proximity to ocean (categorical) |

## 🔧 Feature Engineering

New features created to capture property density patterns:

```python
df['rooms_per_household'] = df['total_rooms'] / df['households']
df['bedrooms_per_room'] = df['total_bedrooms'] / df['total_rooms']
df['population_per_household'] = df['population'] / df['households']
