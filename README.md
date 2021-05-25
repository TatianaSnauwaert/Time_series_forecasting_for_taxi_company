# Time_series_forecasting_for_taxi_company
## Time Series Project from Practicum by Yandex

### Goal

Develop a model for the Sweet Lift Taxi company that predicts the amount of taxi orders for the next hour based on the historical data. It will be used to attract more drivers during peak hours.

The RMSE metric on the test set should not be more than 48.

### This project's repo includes the following files:

- The project's jupyter notebook (Time_series_forecasting_for_taxi_company_final.ipynb);
- A pdf format of the notebook (Time_series_forecasting_for_taxi_company_final.pdf);
- Input data (taxi.csv);
- Project description from Practicum (Time_Series_project_description.pdf);

### We have completed the following steps in this project:

1. Descriptive statistics

2. Data preprocessing

We made sure the dates and times were in chronological order, resample data by 1 hour because we needed to predict orders for the next hour and took the sum as an aggregation function since we needed to identify the total number of orders for a particular hour. We also plotted the data and noticed that this set is quite stationary. Finally, we checked the data for duplicates.

3. EDA

We have performed a seasonal decomposition of this dataset to see if there are any trends and seasonality in the data. We noticed the overall trend that the number of orders is growing in this company over the time. We didn't see any clear seasonality in terms of months of the year in this dataset but the data was collected for only 6 months. The level of residuals doesn't change over time, so it shouldn't influence the predictions. The residuals level is mostly around 0, which means that the data was well decomposed.

Finally, we've decided to take a look at the hourly data and noticed a pattern of the number of orders during each day. Based on that we've decided to create a new feature that will help a model better learn this pattern.

4. Splitting the data

Data was split into train and test sets with the ration 1:5.

5. Standard scaling

It was performed to be able to compare feature importances.

6. Model selection

We have compared Linear Regression, Random Forest, XGBoost, LightGBM and CatBoost models. We have also tuned a few hyperparameters for these algorithms. We have chosen the tuned CatBoost model based on RMSE score.

7. Feature importances

Based on the features importances attribute, we found that the hourofday and rolling_mean turned out to be much more important in this model than any other feature.

8. Sanity check

The test score of the Dummy regression model, that we use as a baseline to analyze the model quality, is 30.51% higher than our final chosen model. It means that the modeling was useful.

### Results

The **base CatBoost model** has shown the best results (**test RMSE of 40.57**) in terms of quality. The target metric of 48 or lower has been reached. It showed some degree of overfitting that can be dealt with in the future. Besides, the model with tuned hyperparameters gave slightly worse results than the base model with default parameters, probably other parameters should be adjusted. This can be done in the future.

### Logbook

### The logbook of this project can be found [here](https://docs.google.com/spreadsheets/d/1SrGdReexaSEomJGS6yR6cRwJtHA_XqpprnLaE7B6Ayg/edit#gid=867769669) (Time Series tab).
Total time spent on the project: 9.3 hours with a daily average of 1.86 hours working for 5 days.
