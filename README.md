# MSE-Stock-Market-Prediction
* [Project Intro](#project-intro)
* [Technologies & Setup](#technologies-&-setup)
* [Dataset](#dataset)
* [In-details](#in-details)
* [Future Work](#future-work)


## Project Intro
The purpose of the project is to develop timeseries forecasting regression models and classifications models for stocks trading on the Macedonian Stock Exchange (MSE).

We use statistical models, traditional machine learning, and deep learning models to predict the stock price 1/7/30 (adjustable) days ahead of time. 

The dataset that we have is containing stock exchange information like open/close price, volume, etc. for each of 22 stocks that had daily trading activity on the exchange for periods between 1997-Jan-09 and 2020-Aug-25.


## Technologies & Setup
**Technologies:**
python, pandas, numpy, tsfresh, xgboost, keras, jupyter

**Setup:**
Please refer to the requirements.txt file in the main repository.


## Dataset
The data set contains a timeseries data that is nonconsecutive, of unequal time length, and has different number of instances based on trading activity for the 22 stocks.

Dataset was split into train and validation period based on a cutoff date. Various validation periods were tried like leaving the last 30, 100, and 300 days for validation and using the rest for test.

A separate Test dataset file containing timeseries data for the same 22 stock starting from 2020-Aug-26 running for 30 days until 2020-Sep-25 was used to test models. 

We evaluated the models based on RMSE as % of true market price, and classification error rate metrics for a 7-days-ahead-of-time predictions over the 30 day testing period. 

## In-details
```
├──  config
│    └── defaults.py  - here's the default config file.
│
│
├──  configs  
│    └── train_mnist_softmax.yml  - here's the specific config file for specific model or dataset.
│ 
│
├──  data  
│    └── datasets  - here's the datasets folder that is responsible for all data handling.
│    └── transforms  - here's the data preprocess folder that is responsible for all data augmentation.
│    └── build.py  		   - here's the file to make dataloader.
│    └── collate_batch.py   - here's the file that is responsible for merges a list of samples to form a mini-batch.
││
└── tests					- this foler contains unit test of your project.
     ├── test_data_sampler.py
```

## Future Work
* Make Time Series Forecasting with Convolutional Neural Network Regressor
* Make Time Series Rare Events Regressor
* Automated Hyper-parameter tunning
* Make Ensemble of the best regressors
