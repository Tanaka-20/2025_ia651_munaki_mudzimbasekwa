# 2025_ia651_munaki_mudzimbasekwa

# House Price Classification Project
## Project Overview
Accurate prediction of house prices plays a key role in real estate investment, mortgage valuation, and urban planning. Property prices are driven by a range of structural and geographic features, including square footage, the number of rooms, renovation history, and the property's location.

This project aims to develop predictive models to estimate house price categories (Low, Medium, High) using a dataset of residential housing records from the United States. The project began by treating this as a regression problem, using models such as Linear Regression, Random Forest Regressor, and XGBoost Regressor, to predict continuous price values. These models were evaluated both with and without geolocation features (latitude and longitude). Evaluation metrics included RMSE and R^2 scores.  Then reframed the problem into a multiclass classification task, based on price quartiles derived from a boxplot analysis. Random Forest and XGBoost were trained for classification, using both raw and SMOTE-balanced data. Evaluation metrics included accuracy, precision, recall, and F1-score.

Exploratory Data Analysis (EDA) included correlation matrix visualizations, boxplots to detect skewness and outliers, and an attempted PCA (Principal Component Analysis), which was later dropped due to minimal variance contribution. Feature importance and model explainability were further enhanced with LIME visualizations, helping to interpret model predictions at the individual record level.Through this end-to-end analysis,  the predictive power of different feature sets and model types were evaluated, ultimately identifying Linear Regression with geolocation features as the best-performing model for regression and Random Forest with geolocation and SMOTE as the best for classification.

## Dataset Overview

•	Source: Kaggle
•	Observations: Thousands of house records from the US

##Features in the Dataset:

•	price: Target variable representing sale price of the house

•	bedrooms: Number of bedrooms

•	bathrooms: Number of bathrooms

•	sqft_living: Square footage of the interior living space

•	sqft_lot: Square footage of the entire lot

•	floors: Number of floors in the house

•	waterfront: Binary indicator whether the house is waterfront

•	view: Integer rating of property view quality

•	condition: Rating of the house condition (1-5)

•	sqft_above: Square footage above ground

•	sqft_basement: Basement area in square feet

•	yr_built: Year the house was originally built

•	yr_renovated: Year the house was renovated (0 if never)

•	latitude/longitude: Geographic location of the house

•	effective_year: Derived feature using max(yr_built, yr_renovated)

•	was_renovated: Binary derived feature (1 if renovated, 0 otherwise)

Engineered features like effective_year and was_renovated were included to improve the predictive power and interpretability of renovation data. Geolocation features (latitude and longitude) were evaluated separately to assess spatial influence on pricing.

## Process Overview
1.	Data Cleaning: Handling missing values and dropping irrelevant columns (e.g., date, street, etc.)
   
2.	Feature Engineering:
   
o	Created price_class using quartiles (Q1, Q2, Q3) obtained from the boxplot

o	Transformed numerical and categorical features

o	Attempted Principal Component Analysis (PCA) to reduce dimensionality and explore potential feature combinations; however, the variance explained by the first principal components was found to be insignificant, so PCA was not used in the final analysis

o	A comprehensive correlation heatmap revealed high correlations (e.g., sqft_living and bathrooms) and weak correlations (e.g., condition, was_renovated). This helped guide feature selection and engineering.

3.	Modeling (Regression Stage):
   
o	Models were initially trained to predict house price as a continuous variable before converting to classification

o	Trained Linear Regression, Random Forest Regressor, and XGBoost Regressor

o	Each model was trained with and without geolocation features (latitude, longitude)

o	Performance was evaluated using RMSE and R² Score

o	Best overall performance was achieved by Linear Regression with geolocation

o	After this regression stage, the problem was reframed as a multiclass classification task based on Q1–Q3 breakpoints

4.	Modeling (Classification Stage):
	
o	Initially trained Random Forest and XGBoost classifiers before applying SMOTE or scaling

o	Then applied SMOTE to balance class distribution

o	Retrained models after SMOTE and scaling

o	Best-performing classification model (Random Forest) was tested with and without geolocation features

5.	Evaluation: Classification reports and confusion matrices
	
6.	LIME Explanation: Model interpretability using LIME was added to explain the classification decision for individual predictions.


