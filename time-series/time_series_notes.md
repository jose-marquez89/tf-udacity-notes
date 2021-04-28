# Time Series
- a time series is an ordered sequence of values, equally spaced over time
- single value at each timestamp is called univariate 
- multivariate is exactly what it seems like
- example
    - if you're looking at birth and death rates in a country as a function of time, you could look at these as two separate univariate time-series
    - to study how the values are related through time, it's better to look at them as a multivariate series
- predicting the past via filling in gaps in a time series is called imputation

### Describing common patterns in time series
- sometimes a time series will drift up or down
    - this is called a trend
- seasonality is when patterns repeat at predictable intervals
- some time series have both trend and seasonality
- sometimes when a time series looks nearly unpredictable, you can at least get the mean, std dev and variance
- you can isolate trends, seasonality and noise

### Forecasting
- a simple approach is to take the last value assume that the next value will be the same
    - this is called naive forecasting
    - naive forecasting can provide a good baseline
    - good idea to measure the performance of this
- to measure performance, you can partition the data into train, test and validation
    - it's a good idea to make sure that enough seasonality is included in the training, validation and tesing partitions
    - this is called fixed partitioning
- time series forecasting may not always be a reliable estimate because things can behave differently in the future
    - may still be a good estimate
- it's a good idea with time-series forecasting to train on the entire set before putting a model into production
    - this is different from the typical machine learning best practice of not training on the test set

### Roll forward partitioning
- you will generally want to retrain your model as you get new data
- roll forward partitioning gradually increases the size of the training partition
- does a better job of mimicing production conditions
- takes more time to train

### Metrics
- most common metric is MSE
- sometimes we use RMSE which has roughly the same scale as the original values
- MAE can be used as well
- good option is mean absolute percentage error (MAPE)
    - mean ratio between the absolute value and the absolute error
- a simple forecasting method is to compute a moving average
    - just the mean of the past `n` values
    - eliminates noise but does not anticipate seasonality or trends
    - doesn't always perform very well due to this
    - you can make this better by removing trend and seasonality from the original data
    - use a technique called differencing
        - instead of studying the time series itself, you study the value at 't' and the value one year (or any fixed period I assume) earlier
        - the 'differenced' time series has no trend or seasonality
        - you can use a moving average to get a forecast for the differenced time series
        - to get a forecast for the original time series, you need to add back the value from the prior period
        - slighty better than naive forecasting
        - final forecast will still be pretty noisy
        - with another moving average you can get a smoother forecast
        - keep this in mind; simple approaches may work just fine
- moving averages using centered windows are more accurate than trailing windows
    - this works best for past values
    - not so good present because you won't know future values

### Machine Learning Approaches
- the simplest approach is to create a model that will learn to forecast a time step given a time window before it
- prepare a dataset of time windows of a fixed size
- window is observation and the resulting time-step value is the target

#### TODO: Finish time windows
