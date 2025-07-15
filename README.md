# Predicting Calorie Expenditure - EDA and Feature Engineering

This repository demonstrates how to perform **exploratory data analysis (EDA)** and **feature engineering** using the dataset from [Kaggle Playground Series - Season 5, Episode 5](https://www.kaggle.com/c/playground-series-s5e5).

## Objective

The goal of this project is not to build the most accurate final model, but rather to showcase a clear and thorough pipeline for:

- Exploring and understanding the data
- Identifying important patterns and relationships
- Designing meaningful derived features to improve model interpretability and performance

## Dataset Overview

The dataset provides physiological and activity-related measurements with the goal of predicting **calorie expenditure** (Calories). It includes variables such as:

- **Age**
- **Height**
- **Weight**
- **Duration** (minutes)
- **Heart Rate** (bpm)
- **Body Temperature** (??C)
- **Calories** (target)

For this competition, the evaluation metric is **Root Mean Squared Logarithmic Error (RMSLE)**, which penalizes large differences on a relative (logarithmic) scale and naturally handles skewness in the target variable.

## Exploratory Data Analysis (EDA)

Key steps and findings from the EDA include:

- No missing values in the dataset
- Calories and some physiological variables (e.g., Age, Body Temperature) are right-skewed
- Strong positive correlations between Calories and Duration, Heart Rate, and Body Temperature
- High correlation between Height and Weight, leading to potential multicollinearity

##  Feature Engineering

Based on EDA insights, new features were created to better capture physiological and activity-related effects:

- **BMI**: To consolidate Height and Weight and reduce multicollinearity
- **Interaction terms**: E.g., HeartRate ?? Duration, capturing combined effects
- **Polynomial terms**: E.g., squared Duration, to account for nonlinear relationships
- **Log transformations**: Evaluated for skewed variables, but Calories were left untransformed since RMSLE inherently handles skewness

