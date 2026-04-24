# Health Insurance Cost Prediction Using Statistical Modeling

## Overview

This project analyzes U.S. health insurance data to identify key drivers of medical insurance charges and build predictive models using multiple linear regression. The goal is to understand how demographic and lifestyle factors influence healthcare costs from an actuarial perspective.

The analysis focuses on interpreting risk factors such as age, BMI, smoking status, and number of children, and evaluates how these variables interact to affect insurance charges.

---

## Dataset

The dataset contains 1,338 observations with the following variables:

- **age**: Age of the primary beneficiary  
- **sex**: Gender of the beneficiary  
- **bmi**: Body mass index  
- **children**: Number of dependents covered  
- **smoker**: Smoking status (yes/no)  
- **region**: Residential region in the U.S.  
- **charges**: Individual medical insurance costs  

---

## Tools & Libraries

- R  
- readxl  
- base R (lm, summary, plots)

---

## Exploratory Data Analysis

Key findings from the exploratory analysis:

- Age ranges from 18 to 64 with an average of ~39 years  
- BMI is centered around 30 (obesity range on average)  
- About 20% of individuals are smokers  
- Medical charges are highly right-skewed with large variation  

---

## Modeling Approach

Multiple linear regression models were built progressively:

### 1. Full Model
Includes all predictors:

```r
charges ~ age + sex + bmi + children + smoker + region
```

### 2. Refined Model

Removes weak predictors (sex and region):

```r
charges ~ age + bmi + children + smoker
```

### 3. Interaction Model (Final Model)
```r
charges ~ age + bmi * smoker + children
```
Model Performance
Model	Adjusted R²
Full Model:	0.7494
Refined Model:	0.7489
Interaction Model: 0.8382

Key Findings
Smoking status is the strongest predictor of medical insurance charges
BMI significantly increases costs, especially for smokers
Age has a consistent positive relationship with charges
The interaction between BMI and smoking status greatly improves model performance

These findings indicate that insurance costs are not purely additive but depend on interactions between key lifestyle risk factors.

## Conclusion

This analysis demonstrates that smoking behavior and BMI are the dominant drivers of medical insurance costs, with age and number of children also contributing to variability. The inclusion of interaction effects significantly improves model performance, aligning with actuarial principles that insurance risk is driven by combined lifestyle factors rather than isolated variables.

### Future Improvements
Explore nonlinear models (random forests, GAMs)
Include additional health-related variables if available
Apply cross-validation to assess out-of-sample performance
Extend to pricing simulation or risk scoring framework
