# Traffic-Prediction-Final-Project

## Project Overview

This project was developed as part of the *Applications of Artificial Intelligence in Project Management* course.

The objective is to predict traffic volume at different road junctions using historical traffic data and machine learning techniques. In addition to traffic forecasting, the project introduces a congestion classification framework that converts numerical traffic predictions into interpretable traffic states.

The dataset contains timestamped traffic observations collected from four road junctions. The target variable is the number of vehicles observed at a given date and time.

The dataset was initially coming from Kaggle : https://www.kaggle.com/datasets/fedesoriano/traffic-prediction-dataset?resource=download

## Project Workflow

The notebook follows a complete machine learning pipeline:

1. Data loading and preprocessing
2. Exploratory Data Analysis (EDA)
3. Feature engineering
4. Traffic congestion definition
5. Train / validation / test split
6. Baseline model development
7. Improved baseline development
8. Model evaluation
9. Congestion classification
10. Feature importance analysis

## Models Evaluated

Three regression algorithms were compared:

- Linear Regression
- Random Forest Regressor
- XGBoost Regressor

XGBoost achieved the best overall regression performance and was selected as the final model.

## Feature Engineering

### Baseline Features

- Junction identifier
- Hour of day
- Day of week
- Month
- Year
- Weekend indicator
- Period of day
- Lag features
- Rolling averages

### Improved Features

Additional features were introduced to improve prediction accuracy:

- Weekly lag feature (168 hours)
- Cyclical encoding using sine and cosine transformations
- Additional rolling averages
- Rolling standard deviations

## Congestion Classification

Instead of relying on arbitrary traffic thresholds, congestion levels are defined using junction-specific percentiles:

- Below the 50th percentile → Fluid
- Between the 50th and 90th percentile → Moderate
- Above the 90th percentile → Congested

This approach adapts congestion definitions to the traffic characteristics of each junction.

## Evaluation Metrics

Model performance is evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

Congestion classification performance is evaluated using confusion matrices and classification reports.

## Results

The improved XGBoost model achieved the best regression performance by reducing RMSE and increasing R² compared to the baseline model.

Feature engineering proved to be a major contributor to performance improvements, highlighting the importance of temporal and historical traffic patterns in traffic forecasting.

## Repository Content

- `traffic_congestion_prediction_notebook.ipynb` : Complete project notebook
- Figures and visualizations generated during analysis
- Model evaluation results
- Traffic congestion classification framework

## Author

**Titouan Gagneux**  
JUNIA ISEN Lille – Big Data & Artificial Intelligence
