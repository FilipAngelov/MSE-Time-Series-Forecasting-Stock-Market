# MSE-Stock-Market-Prediction
* [Project Intro](#project-intro)
* [Technologies & Setup](#technologies-&-setup)
* [Dataset](#dataset)
* [In-details](#in-details)
* [Future Work](#future-work)


## Project Intro
The purpose of the project is to develop timeseries forecasting regression models and classifications models for stocks trading on the Macedonian Stock Exchange (MSE).

The dataset that we have is containing stock exchange data like open/close price, volume, etc. for each of 22 stocks that had daily trading activity on the exchange for periods between 1997-Jan-09 and 2020-Aug-25.

We use statistical models, traditional machine learning, and deep neural networks and learning models to predict the stock price 1, 7, or 30 days ahead of time. 

The deep learning and traditional machine learning models are multivariate sequence to point prediction models. We use 40 days look-back sequence of each of the features to predict a point in time (7 days) in the future. 

A standard ARIMA model is univariate to point of time forecasting method.

* Statistical ARIMA model was used to set a baseline RMSE score (in MKD currency units) for each of the stocks of interest. 
* XGBoost was used for regression and classification models.
* Plain vanila LSTM was used for regression model.


## Technologies & Setup
**Technologies:**
python, pandas, numpy, tsfresh, xgboost, keras, jupyter

**Setup:**
Please refer to the requirements.txt file in the main repository.


## Dataset
The data set contains a timeseries data that is nonconsecutive, of unequal time length, and has different number of instances based on trading activity for the 22 stocks.

Dataset was split into train and validation period based on a cutoff date. Various validation periods were tried like leaving the last 30, 100, and 300 days for validation and using the rest for train.

A separate Test dataset file containing timeseries data for the same 22 stock starting from 2020-Aug-26 running for 30 days until 2020-Sep-25 was used to test models. 

We evaluated the models based on 'RMSE as % of true market price', and classification error rate metrics for a 7-days-ahead-of-time predictions over the 30 day testing period. 

Train and test datasets can be found in Data folder.

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
└── test results - foler containing test result of models.

```

## Future Work
* Make Time Series Forecasting with Convolutional Neural Network Regressor
* Make Time Series Rare Events Regressor
* Facebook Prophet
* Automated Hyper-parameter tunning
* Make Ensemble of the best regressors
* Automate trading rule algorithm 
