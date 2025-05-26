# Medical Insurance Cost Prediction

## Project Overview

This project focuses on predicting individual medical insurance charges using a dataset containing features such as age, gender, body mass index (BMI), number of children, smoking status, and region. The aim is to understand how these factors influence insurance costs and to develop a predictive model that accurately estimates insurance charges.

## Dataset Overview

* Source: Kaggle
* Dataset Link: [Medical Cost Personal Dataset](https://www.kaggle.com/datasets/harishkumardatalab/medical-insurance-price-prediction?resource=download)
* Description: The dataset contains personal demographic and medical cost information used for modeling insurance charges.

## Who Benefits?

* **Healthcare Providers & Insurance Companies:** Can utilize insights to better price insurance policies based on customer demographics and risk factors.
* **Customers:** Gain understanding of how personal factors affect their insurance costs, allowing for informed decisions.
* **Data Scientists & Analysts:** Opportunity to apply and explore data preprocessing, exploratory analysis, and various machine learning techniques in a real-world healthcare context.

## What Was Done

1. **Data Collection and Preprocessing:**
   The dataset was imported and cleaned by addressing missing values in categorical and numerical columns. The "charges" column was standardized by rounding to two decimals.

2. **Exploratory Data Analysis (EDA):**
   Relationships between variables were visualized and quantified. A regression plot showed BMI positively correlates with insurance charges, and correlation analysis revealed smoking status has a strong positive correlation (0.79) with charges.

3. **Model Development:**
   Multiple machine learning models were developed:

   * Linear regression using only "smoker" status (R² = 0.62).
   * Multiple linear regression with all features (R² = 0.75).
   * Pipeline combining feature scaling, polynomial features (degree=2), and linear regression (R² = 0.84).

4. **Model Refinement:**
   Ridge regression with polynomial feature transformation was applied to reduce overfitting and improve generalization. The best test set performance was R² = 0.82 for polynomial ridge regression and R² = 0.73 for ridge regression without polynomial features.

## Key Findings

1. **Does smoking affect insurance charges?**
   Yes, smoking status has a strong positive correlation (0.79) with insurance costs, indicating smokers generally face significantly higher charges.

2. **How well can smoking alone predict charges?**
   A simple linear regression model using only smoking status explains 62% of the variance in insurance charges (R² = 0.62).

3. **Does including more features improve prediction?**
   Yes, adding all features increases predictive power (R² = 0.75), confirming that age, BMI, region, and other factors contribute meaningfully.

4. **What impact do polynomial features have?**
   Polynomial transformations coupled with scaling capture complex, non-linear relationships and interactions, improving the model’s R² score to 0.84.

5. **How does regularization affect the model?**
   Ridge regression with regularization reduces overfitting. Polynomial ridge regression achieved an R² of 0.82, slightly less than the pipeline with polynomial linear regression but better than ridge regression without polynomial features.

6. **Are there outliers affecting the model?**
   Outliers exist, especially among smokers, as revealed by boxplots. These extreme values contribute to higher insurance charges and should be considered in modeling.

## Conclusion

The best performing model combined polynomial feature transformation with scaling and linear regression, achieving an R² score of 0.84. This demonstrates that non-linear relationships and feature interactions are crucial for accurately predicting medical insurance charges. Smoking status remains the strongest single predictor, but multiple factors together offer a more precise estimation. Regularization methods like ridge regression help control overfitting but do not outperform polynomial feature models in this case.

## Recommendations

Future work could focus on hyperparameter tuning, exploring advanced models such as Random Forests or Gradient Boosting, and handling outliers more effectively. Including additional features, such as medical history or lifestyle factors, might further enhance prediction accuracy. Ensemble approaches could leverage strengths across models for improved results.

## Acknowledgements

This project was completed as part of the IBM Data Science Professional Certificate within the Data Analytics with Python course. Appreciation is extended to IBM for providing the educational resources and support.
