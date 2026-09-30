# Bike Demand Prediction 🚲

An end-to-end machine learning project to predict bike rental demand using time, weather, and calendar-related features.

## Project Overview

Bike rental demand changes depending on factors such as temperature, time of day, weather conditions, and working days.

The goal of this project is to understand these patterns and build a machine learning model that can predict bike rental demand.

This project follows a complete machine learning workflow:

**Data → Exploration → Feature Engineering → Model Training → Evaluation → Error Analysis → Interpretation**

## Dataset

The dataset contains historical bike rental observations with information such as:

* Temperature
* Humidity
* Wind speed
* Rainfall
* Snowfall
* Solar radiation
* Hour
* Day
* Month
* Year
* Day of week
* Season
* Working/functioning day
* Bike rental count

## Exploratory Data Analysis

The analysis explored:

* Distribution of bike demand
* Bike demand across different hours
* Bike demand across days of the week
* Relationship between temperature and demand
* Correlation between numerical features and bike demand
* Prediction errors across different hours and seasons

Some important patterns were observed:

* Bike demand varies significantly throughout the day.
* Temperature has a strong relationship with bike demand.
* Hour of the day is one of the important predictors.
* Demand prediction becomes more difficult during periods of unusually high demand.

## Feature Engineering

The dataset was prepared for machine learning by:

* Extracting time-related information
* Encoding categorical variables
* Separating features and target
* Splitting the data chronologically into training and testing periods

The chronological split was used because this is a time-dependent prediction problem.

### Training Data

**7,008 observations**

Period:

`2017-12-01 → 2018-09-18`

### Testing Data

**1,752 observations**

Period:

`2018-09-19 → 2018-11-30`

## Models

Two regression models were compared:

### 1. Linear Regression

Results:

| Metric |  Score |
| ------ | -----: |
| MAE    | 330.39 |
| RMSE   | 455.07 |
| R²     | 0.4495 |

### 2. Random Forest

Results:

| Metric |  Score |
| ------ | -----: |
| MAE    | 222.20 |
| RMSE   | 315.22 |
| R²     | 0.7359 |

The Random Forest model produced lower prediction errors and explained more of the variation in bike demand than the Linear Regression model on the test period.

## Feature Importance

The Random Forest model identified the following features among the most important predictors:

1. Temperature
2. Hour
3. Solar radiation
4. Humidity
5. Rainfall
6. Day of week
7. Dew point

Temperature and hour were particularly influential in the trained model.

## Error Analysis

The model was also evaluated beyond overall metrics.

Prediction errors were analyzed by:

* Hour
* Season
* Demand level

The model generally followed the overall daily demand pattern, but some high-demand observations were substantially harder to predict.

For high-demand observations:

* Number of observations: **233**
* Average error: **388.43**
* Average absolute error: **436.28**

This shows why looking only at an overall metric can hide where a model struggles.

## Key Takeaways

* Bike demand is strongly influenced by time and weather.
* Temperature and hour were important predictors in the Random Forest model.
* Random Forest captured the nonlinear relationships in the data better than Linear Regression.
* High-demand periods remain more difficult to predict accurately.
* Error analysis provides additional insight beyond simply comparing model scores.

## Project Structure

```text
bike-demand-prediction/
│
├── bike_demand_prediction.ipynb
└── README.md
```

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

## Future Improvements

Possible next steps include:

* Hyperparameter tuning
* Cross-validation designed for time-series data
* Testing additional regression models
* Creating lag and rolling features
* Improving prediction during high-demand periods
* Building a simple prediction application

## Conclusion

This project demonstrates an end-to-end approach to a real-world regression problem.

Rather than stopping at model training, the project also investigates why the model performs the way it does, which features influence predictions, and where prediction errors are concentrated.

The results show that time and weather provide meaningful signals for predicting bike rental demand, while unusually high-demand periods remain more challenging for the model.

The project therefore goes beyond simply building a prediction model — it focuses on understanding the data, evaluating the model, and investigating where and why it makes mistakes.
