`Given TimeSeries Data

![6c291965-05cc-44ea-b7d7-eb0bb751551a](https://user-images.githubusercontent.com/88092644/200171074-b80928b3-e56b-4fdc-9da0-50e3d7afecb1.png)
`



### TIMESERIES DATA ANALYSIS

The data provided consists of 38362 records each having 8 features. Some basic EDA is performed on the data and then the data is grouped by the 
date with aggregate function as sum over 'Movement' feature value. This reduces the shape of the dataframe to (2089, 8).

#### Converting the dataset to a TimeSeries Data. 

Although the dataset contains other dimensions also but for performing forecasting, we need to have a TimeSeries data format. Therefore, we convert the existing dataframe
to a TimeSeries data by selecting 'Delivery Date' and 'Movement' features only. All the further analysis will be performed on this dataset only.

#### Splitting into train and test set, then performing the model fitting

The dataset is then visualised to check for any seasonal pattern. At the next step, data is splitted using TimeSeries Cross Validation with number of folds equals to 5.
Once the data is seperated into train and test set, it is fitted using XGBRegressor model. The loss is measured across 5-folds, and its mean value is stated. 

#### Forecasting the movement value for the next 10 months

Using the same regressor instance used to fit the training set, we now try to predict the future value for 10 months future dates.
The prediction is then plotted and some key observations are made.

`Forecasting the next 10 months data

![9041c22c-4732-4a90-b7f3-9da228a5a150](https://user-images.githubusercontent.com/88092644/200171135-c7da10c4-a2e0-49b7-b615-6c65f8eb59ff.png)
`
