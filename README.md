# MSE-Stock-Market-Prediction
* [Project Intro](#project-intro)
* [Technologies & Setup](#technologies-&-setup)
* [In-details](#in-details)
* [Future Work](#future-work)


## Project Intro

#### Purpose
The purpose of the project is to develop a time series forecasting regression models and classifications model for stocks trading on the Macedonian Stock Exchange (MSE).

#### Dataset
The dataset that we have is containing stock exchange data like open/close price, volume, etc. for each of 22 stocks that had daily trading activity on the exchange for periods between 1997-Jan-09 and 2020-Aug-25. 

![image](https://github.com/FilipAngelov/MSE-Time-Series-Forecasting-Stock-Market/blob/master/data/dataset.png)

The data set contains a time series data that is nonconsecutive, of unequal time length, and has different number of instances based on trading activity for the 22 stocks.

We are converting the time series data to a supervised learning structure to solve the problem as a regression or classification. 
Converting the time series data to a supervised learning structure includes preparing a 40 days look-back sequence of each of the features to predict the price 7 days in the future. 

Dataset was split into train and validation period based on a cutoff date. Various validation periods were tried like leaving the most recent 30, 100, and 300 days for validation and using the rest for train.

A separate Test dataset file containing timeseries data for the same 22 stock starting from 2020-Aug-26 running for 30 days until 2020-Sep-25 was used to test models. 

Train and test datasets can be found in Data folder.

#### Models
For regression we use traditional machine learning and deep neural networks and learning models to predict the stock price 1, 7, or 30 days ahead of time. For classification we use traditional machine learning models to classify stock buying signals as buy/hold/sell based on multiple features.

The deep learning and traditional machine regression learning models are multivariate regression sequence to point prediction models. 
* XGBoost was used for traditional machine learning regression and classification models.
* LSTM layers were used to constract a plain vanila deep neural network to solve a regression problem.

#### Evaluation
We forecasted the price/class 7-days-ahead-of-time over a 30 day testing period. 
Regression models were evaluated based on 'RMSE' and 'RMSE as % of true market price'. The classification error rate metric was used for the classification model evaluation. 

The regression models were also evaluated based on return on investment (ROI) for a trading system that worked as follows:
* Over the 30 days test period we developed 4 predictions - for example: each Monday we predict the price of the next Monday.
* We take market position in each of the stock based on rules: Buy - if predicted price is 2% higher than the current price; Sell - if predicted price is 2% below the current price; and Hold - if predicted price between -2% and 2%.
* We hold the position for 7 days until next Monday and next prediction.
* We evaluate profits/losses for each stock against the total investments.


## Technologies & Setup
**Technologies:**
python, pandas, numpy, tsfresh, xgboost, keras, jupyter

**Setup:**
Please refer to the requirements.txt file in the main repository.


## In-details
```
├──  config
│    └── requirements.txt  - here's the default config file.
│
│
├──  data - folder containing csv datasets 
│    └── data_mse_mse_historic_data_active.csv - is train dataset.
│    └── data_mse_mse_historic_data_active_test.csv  - is test dataset.
│
│
│── notebook with compiled code
│   └── MSE_Time_Series_Regression_and_Classification_Models.ipynb
│
│
└── test results - folder containing test result of models.

```

## Future Work
* ARIMA model
* Make Time Series Forecasting with Convolutional Neural Network Regressor
* Make Time Series Rare Events Regressor
* Facebook Prophet
* Automated Hyper-parameter tunning
* Make Ensemble of the best regressors
* Automate and improve trading system algorithm 
* Implement model explainability
