# Prompt II Notebook Documentation

This README summarizes the analysis completed in the Jupyter notebook prompt_II.ipynb. The notebook focuses on two related goals:

1. Understanding which factors drive used car prices.
2. Exploring time-series methods for forecasting price trends for selected vehicle models.

## Project Objective

The notebook uses a used-car dataset to support decision-making for a dealership by:

- predicting vehicle price more accurately,
- identifying important price drivers,
- and exploring forecasting approaches for future price movement.

## Data Preparation

The analysis begins with the dataset file vehicles.csv and includes the following steps:

- loading the data into a pandas DataFrame,
- removing rows with missing year values,
- filtering the dataset to a relevant resale window,
- narrowing the sample to a practical price and mileage range,
- and creating a working dataset with features such as manufacturer, model, fuel, year, price, odometer, and state.

## Exploratory Data Analysis

The notebook performs exploratory data analysis to understand the structure of the data and identify quality issues. This includes:

- inspecting dataset shape and missing values,
- checking the distribution of key variables,
- creating a correlation matrix for numeric features,
- and visualizing price-related patterns for Chevrolet and Ford vehicles.

## Modeling for Price Prediction

The notebook builds several regression models to predict vehicle price.

### Preprocessing

The feature engineering and preprocessing pipeline includes:

- selecting numeric and categorical features,
- scaling numeric features with StandardScaler,
- encoding categorical variables with OrdinalEncoder,
- and applying polynomial feature transformation for nonlinear relationships.

### Regression Models Explored

The notebook evaluates the following models:

- Linear Regression as a baseline model.
- Ridge Regression with GridSearchCV to tune the regularization parameter alpha.
- Lasso Regression for sparse feature selection and simpler interpretation.

### Evaluation Approach

Model quality is assessed using mean squared error (MSE), with comparisons made against a baseline model. The notebook also examines the coefficients of the regularized models to interpret which features influence price.

## Time-Series Analysis

A separate portion of the notebook applies time-series methods to analyze historical price movement.

### Time-Series Preparation

The analysis converts the dataset into a time-based series by resampling annual price data and organizing it by year.

### Methods Used

The notebook explores:

- seasonal decomposition and STL (Seasonal-Trend decomposition using LOESS),
- ACF and PACF plots to inspect autocorrelation structure,
- the Augmented Dickey-Fuller (ADF) test for stationarity,
- and forecasting models such as ARIMA and SARIMAX.

### Forecasting Workflow

The time-series workflow includes:

- visualizing historical price trends,
- separating trend and seasonality components,
- selecting model orders based on autocorrelation diagnostics,
- and comparing forecast values with actual values.

## Key Takeaways

The notebook shows that:

- regularized regression models improve on the simple baseline,
- Ridge Regression performs well after tuning,
- and time-series decomposition plus forecasting methods provide useful insight into price trends over time.

## Files Used

- prompt_II.ipynb
- data/vehicles.csv
- images/ for generated charts and plots
