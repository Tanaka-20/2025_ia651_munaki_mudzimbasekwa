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

