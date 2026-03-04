# 🏠 Real Estate Price Prediction with Machine Learning

## Overview
This project uses machine learning to predict real estate sale prices using historical property transaction data from Connecticut (2001–2023). The goal is to understand how different property characteristics influence sale prices and to compare the performance of multiple predictive models.

📓 **View the full analysis notebook:**  
👉 **[Open the Notebook](./OMIS116%20Final%20Project-vFinal%20(1).ipynb)**

## Dataset
The dataset contains real estate transaction records across Connecticut, including information about property characteristics and sale prices.

Key variables used in this project:
- Assessed Value – property value determined for tax purposes
- Town – location of the property
- Property Type – residential, commercial, industrial, etc.
- Residential Type – type of residential building (single family, condo, etc.)
- List Year – year the property was listed
- Sale Amount – final sale price (target variable)

## Data Preprocessing
Several preprocessing steps were required to prepare the data for modeling:

- Removed columns with very high missing values
- Cleaned column names and standardized formatting
- Removed extreme sale price outliers using percentile trimming
- Split the dataset into training and test sets using a time-based split
- Applied preprocessing pipelines including median imputation, one-hot encoding for categorical variables, and feature scaling

## Models Implemented
Three models were trained and evaluated:

Baseline Model (Median Predictor)  
A simple model that predicts the median sale price for all observations.

Linear Regression  
A basic regression model used as a benchmark for comparison.

Random Forest Regressor  
A tree-based ensemble model capable of capturing more complex relationships between variables.

## Model Performance

| Model | RMSE | MAE | R² |
|------|------|------|------|
| Baseline (Median) | 507,636 | 253,682 | -0.19 |
| Linear Regression | 372,504 | 185,664 | 0.36 |
| Random Forest | 313,688 | 160,109 | 0.54 |

The Random Forest model achieved the best performance, indicating that real estate prices depend on complex interactions between multiple variables rather than simple linear relationships.

## Key Insights
- Random Forest significantly outperforms Linear Regression
- Residential properties are easier to predict than commercial or industrial properties
- Luxury towns tend to have larger prediction errors due to higher price variability
- Removing extreme outliers was essential for obtaining stable model performance

## Limitations
This project uses a limited set of features. Important characteristics such as square footage, number of bedrooms, lot size, property age, and condition were not available in the dataset. Including these features would likely improve prediction accuracy.

## Future Improvements
Future work could improve the model by:

- Training separate models for different property types
- Incorporating more detailed property characteristics
- Adding geographic or spatial features
- Performing more advanced hyperparameter tuning

## Technologies Used
Python  
Pandas  
NumPy  
Scikit-learn  
Matplotlib  
Jupyter Notebook
