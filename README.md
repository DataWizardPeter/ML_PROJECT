Project Overview
This project aims to predict house prices in Bengaluru using various features such as location, size (BHK), total square footage, and number of bathrooms. The dataset used for this project contains information about various houses in Bengaluru. The goal is to build a regression model to accurately predict house prices.

Dataset
The dataset used is Bengaluru_House_Data.csv, which contains the following columns:

area_type: Type of area (e.g., Super built-up Area, Plot Area)
availability: Availability status (e.g., Ready to move)
location: Location of the property
size: Number of bedrooms (e.g., 2 BHK, 4 Bedroom)
society: Name of the society
total_sqft: Total area in square feet
bath: Number of bathrooms
balcony: Number of balconies
price: Price of the property in Lakhs
Data Preprocessing
Handling Missing Values:

Dropped columns with a significant number of missing values (society and balcony).
Dropped rows with missing values in location, size, and bath.
Feature Engineering:

Created a new column BHK by extracting the number of bedrooms from the size column.
Converted total_sqft to a numerical value, handling ranges by taking the average.
Created a new column price_per_sqft by dividing the price by the total square footage.
Handling Categorical Data:

Stripped extra spaces in location names and replaced locations with less than 10 data points with 'other'.
Created dummy variables for the location column.
Outlier Removal:

Removed outliers in total_sqft per BHK.
Removed outliers in price_per_sqft based on the mean and standard deviation.
Removed properties with an abnormal number of bathrooms compared to the number of bedrooms.
Model Building
Linear Regression: The primary model used for prediction.
Model Evaluation: Used train_test_split and cross_val_score to evaluate the model's performance.
Hyperparameter Tuning: Used GridSearchCV for hyperparameter tuning of Lasso and Decision Tree Regressor models.
Results
The Linear Regression model achieved a score of 0.845 on the test set.
Cross-validation scores were consistent, indicating a reliable model.
