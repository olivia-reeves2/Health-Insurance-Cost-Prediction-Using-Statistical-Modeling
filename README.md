## Project Overview

This project analyzes the Medical Insurance dataset to model and predict individual healthcare charges using statistical learning techniques in R.

The goal is to identify key drivers of insurance costs and evaluate how interactions between variables (especially BMI and smoking status) improve predictive accuracy.

## Methods Used

- Exploratory Data Analysis (EDA)
- Data visualization (histograms, boxplots, scatterplots)
- Correlation analysis
- Multiple Linear Regression
- Interaction modeling (BMI × Smoker)
- Model comparison using Adjusted R²

## Final Model

The best-performing model was:

charges ~ age + bmi * smoker + children

This model achieved:

- Adjusted R² ≈ 0.838
- Strong improvement over baseline linear models
