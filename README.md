# Air Quality Index (AQI) Prediction Using XGBoost
## Project Overview

This project focuses on building a robust and production-ready Air Quality Index (AQI) prediction system using machine learning. The model predicts the numerical AQI value based on multiple air pollutant concentrations and further classifies the AQI into Indian Government (CPCB) defined AQI categories with an associated confidence score.

The solution is designed to reflect real-world air quality monitoring scenarios, combining data preprocessing, exploratory data analysis (EDA), feature engineering, and an optimized XGBoost regression model.

## Problem Statement: 

Air pollution is a major environmental and public health concern. Accurately predicting AQI helps:

- Assess pollution severity

- Enable early warnings

- Support data-driven policy and health decisions

- The objective of this project is to:

- Predict AQI values using pollutant data

- Classify AQI into standard CPCB AQI buckets

- Provide a confidence score for predictions

- Dataset Description

## The dataset contains air quality measurements collected across multiple cities and dates. After preprocessing and cleaning, the dataset includes:

## Input Features (Pollutants)

- PM2.5
- PM10
- NO
- NO2
- NOX
- NH3
- CO
- SO2
- O3
- Benzene
- Toluene
- Xylene

### Target Variable:
- AQI (Air Quality Index) – numerical value

### Derived Output

- AQI Bucket (Good, Satisfactory, Moderate, Poor, Very Poor, Severe)

### Data Preprocessing & Cleaning

- The dataset underwent a comprehensive preprocessing pipeline:

- Converted date columns to proper datetime format

- Handled missing values in all numeric features

- Reconstructed missing AQI buckets using CPCB-defined AQI ranges

- Removed unrealistic AQI values (AQI > 900) while retaining valid extreme pollution cases

- Verified data consistency (no negative or invalid pollutant values)

- Ensured 100% completeness before modeling

## After cleaning:

- All features are numerical and model-ready

- AQI bucket labels are fully consistent and reliable

## Exploratory Data Analysis (EDA)

- EDA was performed to understand:

- Feature distributions

- Correlation between pollutants and AQI

- Outlier behavior

- Feature importance patterns

 ### Key visualizations include:

- Distribution plots for pollutants

- Boxplots for outlier detection

- Correlation heatmap for feature relationships

- AQI trend analysis

- EDA insights guided feature selection and model design decisions.

## Feature Selection

 Instead of modifying the original dataset, a separate modeling dataframe was created containing only the most relevant pollutant features and AQI. This ensures:

- Clean separation between raw data and modeling data

- Better experimentation and reproducibility

- No accidental data leakage

## Model Selection
- Why XGBoost?

XGBoost was chosen because:

- It handles non-linear relationships effectively

- It is robust to multicollinearity

- It performs well with structured tabular data

- It is less sensitive to outliers than linear models

- It is widely used in industry for regression problems

- The model was trained as a regression model to predict AQI values directly.

## Model Training
- Train–test split: 80% training, 20% testing

- Model: XGBRegressor

## Tuned hyperparameters:

  - Number of estimators

  - Max depth

  - Learning rate

  - Subsampling and column sampling

## Model Evaluation

The model was evaluated using standard regression metrics:

- R² Score: ~0.87 (Can be termed as accuracy/variance of the model which is 87% )

- Mean Absolute Error (MAE): ~20

- Root Mean Squared Error (RMSE): ~38

## Interpretation:

- The model explains approximately 87% of the variance in AQI

- Errors are within a reasonable and realistic range for environmental data

- Performance is suitable for real-world AQI estimation tasks

- AQI Classification & Confidence Score

## After predicting AQI:

- AQI values are converted into CPCB AQI categories

- A confidence score is calculated based on prediction error magnitude

## Outputs include:

- Predicted AQI

- AQI category

- Confidence percentage

This makes the model more interpretable and application-ready.

## Manual Input Testing
The project supports manual pollutant input testing, allowing:

## Real-time AQI prediction

- Category classification

- Confidence estimation

- This makes the model suitable for integration into dashboards or APIs.

# Key Highlights

### End-to-end ML pipeline (EDA → preprocessing → modeling → evaluation)

### Government-standard AQI classification

### Regression + classification combined approach

### Realistic outlier handling strategy

### Human-interpretable outputs with confidence score

### Industry-aligned modeling practices

## Tech Stack

- Python

- Pandas, NumPy

- Seaborn, Matplotlib

- Scikit-learn

- XGBoost

## Future Enhancements

- Time-series based AQI forecasting

- City-wise or seasonal models

- Model explainability using SHAP

- Deployment as a REST API or web application

- Real-time data ingestion

# Author

Chaitanya Maskare
Final-year Computer Engineering student with a strong interest in Data Analytics, Machine Learning, and real-world problem solving.
