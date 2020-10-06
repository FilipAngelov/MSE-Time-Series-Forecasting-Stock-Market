# MSE-Stock-Market-Prediction
* [Project Intro](#project-intro)
* [Technologies & Setup](#technologies-&-setup)
* [Dataset](#dataset)
* [In-details](#in-details)


## Project Intro
The purpose of the project is to develop timeseries forecasting regression models and classications models for stocks trading on the Macedonian Stock Exchange (MSE).

We use statistical models, traditional machine learning, and deep learning models to predict the stock price 7 days ahead of time. 

The dataset that we have is containing stock exchange information like open/close price, volume, etc. for each of 22 stocks that had daily trading activety on the exchange for periods between 1997-Jan-09 and 2020-Aug-25.


## Technologies & Setup
**Technologies:**
python, pandas, numpy, tsfresh, xgboost, keras, jupyter

**Setup:**
Please refer to the requirements.txt file in the main repository.


## Dataset
The data set contains timeseries data that is nonconsecutive, of unequal time length, and has different number of instances based on trading activity for the 22 stocks.

Dataset was split into train and validation period based on a cutoff date point in time. Various validation periods were tested like leaving the last 30, 100, and 300 days for validation.

Test dataset was starting from 2020-Aug-26 for one month until 2020-Sep-25. 

## In-details
