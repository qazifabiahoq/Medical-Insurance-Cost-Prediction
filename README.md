# Medical Insurance Cost Prediction

## Project Overview
This project involves analyzing a medical insurance dataset with the goal of predicting insurance charges based on various attributes such as age, gender, body mass index (BMI), number of children, smoker status, region, and others. The dataset was sourced from the "Medical Cost Personal Dataset" on Kaggle and contains information on individuals' medical costs. The aim is to explore the relationships between different variables and their influence on the charges for health insurance. This is a predictive modeling project where multiple machine learning techniques have been applied to analyze and predict the target variable, "charges."

## Dataset Overview:

Source: Kaggle
Dataset Link: Medical Cost Personal Dataset : https://www.kaggle.com/datasets/harishkumardatalab/medical-insurance-price-prediction?resource=download

## Objective
The main objective of this project is to create a model that can predict medical insurance charges using multiple features. Various machine learning models, including linear regression, ridge regression, and polynomial features, have been explored to predict the "charges" column.

## Who Benefits?

Healthcare Providers & Insurance Companies: The insights gained from this model could help in better understanding customer demographics and predicting insurance costs, which can inform pricing strategies.
Customers: By predicting charges based on personal attributes, individuals can get insights into how different factors influence their medical insurance costs.

Data Scientists & Analysts: The project provides an opportunity to apply various data preprocessing, exploratory data analysis (EDA), and machine learning techniques to solve real-world problems in the insurance domain.

## What I Did

### Step 1: Data Collection and Preprocessing
The first step was to import the dataset into a pandas dataframe. The dataset had no headers initially, so appropriate column names were assigned. The dataset was then cleaned, with missing values in the "smoker" and "age" columns being handled:

For categorical columns like "smoker," missing values were replaced with the most frequent value.
For continuous variables like "age," missing values were replaced with the mean.
Additionally, the "charges" column values were rounded to 2 decimal places to maintain consistency.

### Step 2: Exploratory Data Analysis (EDA)
EDA was conducted to explore the relationships between features:

Visualizations: A regression plot was used to explore the relationship between BMI and charges. The plot showed a positive correlation, indicating that higher BMI values tend to correlate with higher insurance charges.

Correlation Matrix: The correlation matrix helped identify strong relationships between features. Notably, "smoker" and "charges" had a high positive correlation (0.79), meaning smokers tend to have significantly higher insurance charges.

### Step 3: Model Development
The goal was to predict the charges value using different models:

Linear Regression: A basic linear regression model was trained using only the "smoker" attribute, which yielded an R² score of 0.62, indicating that "smoker" alone has some predictive power.

Multiple Linear Regression: A more comprehensive model was created using all available features. This model performed better with an R² score of 0.75, indicating that multiple factors contribute to predicting charges.

Pipeline with Polynomial Features and Scaling: A pipeline was built that included StandardScaler, PolynomialFeatures (degree=2), and LinearRegression. This pipeline improved performance further, achieving an R² score of 0.84, suggesting that feature scaling and polynomial transformation helped capture more complex relationships in the data.

### Step 4: Model Refinement
To improve model performance further, a ridge regression model was applied. The data was split into training and testing subsets, and a Ridge regressor with a hyperparameter alpha=0.1 was used:

The R² score for this model on the test set was 0.73, showing moderate performance.
Polynomial transformations were applied to the training data with degree=2, improving the model’s performance with an R² score of 0.82.
Results and Key Findings
Initial Models: Linear regression models initially performed decently with an R² score of around 0.62 (using just "smoker") and 0.75 (using all features).
Polynomial Ridge Regression: The performance improved significantly after applying polynomial transformations, with the model achieving an R² score of 0.82 on the test set.
Ridge Regression: The model using Ridge regression with alpha=0.1 achieved an R² score of 0.73, indicating that regularization helped prevent overfitting but didn’t offer as much improvement as polynomial transformations.
Visualizations
Regression Plot: The regression plot of BMI vs. charges showed a positive trend, suggesting that higher BMI correlates with higher medical costs.
Boxplot: A boxplot revealed that outliers were present in the "charges" column, especially for smokers, which aligns with the correlation findings.
Correlation Heatmap: The heatmap highlighted strong correlations between "smoker" and "charges," showing that smokers tend to have higher insurance charges.

## Conclusion and Model Evaluation
Which Model is the Best?
After testing several models and transformations, the best model for predicting medical insurance charges is the Pipeline with Polynomial Features and Ridge Regression. This model achieved the highest performance, with an R² score of 0.84. The polynomial features allowed the model to capture non-linear relationships between the features and the target variable (charges), leading to better predictive performance.

Here’s a summary of the model performances:

Linear Regression with "Smoker" Feature:

R² score: 0.62
This model was basic, using only one feature (smoker), and showed a moderate correlation between smoking status and insurance charges.
Multiple Linear Regression (All Features):

R² score: 0.75
By incorporating all features, the performance improved, as the model could capture more complex relationships, including the strong correlation between smoking and charges.
Pipeline with Polynomial Features and Linear Regression:

R² score: 0.84
This model benefited from scaling and polynomial transformations, which allowed it to better capture non-linear relationships and interactions between features. It outperformed the previous models significantly.
Ridge Regression (Alpha=0.1):

R² score: 0.73
The Ridge regression model helped reduce overfitting through regularization but did not show a significant improvement over the polynomial regression model.
Polynomial Ridge Regression (Degree=2):

R² score: 0.82
Polynomial transformations with ridge regularization gave a slight performance boost over simple Ridge regression, but not as much as the polynomial features in the linear regression pipeline.
Conclusion:
From the comparison of all models, it is clear that polynomial transformations combined with scaling provided the best results, highlighting the importance of considering higher-degree interactions and non-linear relationships when predicting complex outcomes like medical insurance charges.

## What I Believe After This:

Based on the findings from this project, it is evident that multiple factors contribute to medical insurance charges. While being a smoker has a strong influence on charges, other factors like age, BMI, and region also play a role. This knowledge can be leveraged by insurance companies to better understand the factors driving healthcare costs and create more accurate pricing models. It’s also clear that feature engineering and transformations, such as polynomial features, can significantly improve model performance.

## Further Steps:

Hyperparameter Tuning: Future improvements can be made by tuning the hyperparameters of the Ridge regression model and the degree of polynomial features to achieve even better performance.

Model Comparison: Exploring more complex models such as Random Forests or Gradient Boosting could provide further improvements in prediction accuracy.

Handling Outliers: The boxplot analysis indicated that there are outliers, especially among smokers. It might be worth applying techniques to handle outliers more effectively in future iterations.

Additional Features: Including more granular features, such as medical history, could improve the model even further. Gathering more data or exploring domain-specific features could offer further insights.

Ensemble Models: Combining different machine learning models, such as ensemble learning techniques, could improve the prediction accuracy by leveraging the strengths of multiple algorithms.

## Acknowledgements

This project was completed as part of the IBM Data Science Professional Certificate, specifically in the Data Analytics with Python course. I would like to thank IBM for providing the resources and materials to make this project possible.
