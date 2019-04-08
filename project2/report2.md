# Time Series Analysis of the S&P 500


Time Series are a sequence of observations taken at discrete intervals in time. Time series are worth investigated due to the powerful insights they provide in forecasting and predicting future observations. This project will employ different statistical tools, such as statsmodels, to forecast the 2018 yearly returns of the S&P 500 Index. Time series analysis has been one of many tools used to analyze stocks and model returns.

The Standard and Poor's 500 Index, commonly known as the S&P 500 Index, is an American Stock Market index based on the market capitalization of the 500 largest publicly traded companies in the US (Investopedia). The breakdown of the index by sector is extremely diverse with bigger weights in sectors such as Information Technology, Communication Services, Health (Dow Jones). The 10 largest companies with highest weights include household names like Apple, Amazon, Berkshire Hathaway, Facebook, and Alphabet(Google). The S&P 500 Index is commonly used by investors as a benchmark for returns since it captures so much of the market returns and therefore can be used examine the health of the United States economy.

Using data collected from Yahoo Finance, I downloaded monthly data from 1/1/1997 - 12/31/2018. The adjusted closing price of the index refers to the closing price of the stock amended to any corporate actions that may have influenced the stock price for that day. 

## Methodologies and Results
Before pursuing a time series analysis, I will perform some exploratory analysis. Here's a breakdown of the procedures for this time series analysis:
1. Exploratory analysis to determine trend, seasonality, and noise
2. Test for stationarity
3. Estimate Model Parameters
4. Use ARIMA model to forecast the monthly returns of 2018

### Exploratory Analysis
Any time series analysis is based on the assumption that the observations have the following three components:

+ Trend - captures long-term changes
+ Seasonality - captures periodic variations in the data
+ Noise - random variation of the trend

The existence of these components determines whether the data is stationary or non-stationary. A data is considered stationary if the observations for all time *t* is from the same distribution. In other words, a time series is stationary if the mean, variance, and correlation are the same for all observations. In order to build a model to predict values of the time series, the data set must be stationary. If it is not, then the model requires that the data be transformed to stationary.

One way to determine trend is to plot the variable and see if decreases or increases in the long run.
[insert plot]

This plot shows that the observations may have an increasing trend. However, there's a lot of variation in the observations. A statisitical tool, known as a *rolling mean* can be used to smoothen out the short-term fluctuations in the data set in order to highlight long-term trends. Here I use a window of 12 months, which means that the function selects on a rolling basis a 12 month interval to calculate the mean. I've also calculated the rolling standard deviation to see if there's any volatility.

[insert rolling plot]

The result of the rolling mean smoothen some of the volatility of the stock market and visibly depict an upward trend that confirms the increasing pattern of the S&P500 Index. Additionally, the rolling standard deviation shows some variation in standard deviation which is a sign that this variable is potentially non-stationary. 

Another elementary way of testing for stationary is to observe whether the mean and variance is constant across all time *t*. This is easily done by partitioning the data into equal parts and calculating the mean and variance of each partition. If there's not a significant difference in the mean and variance of each partition, you can assume that the data is stationary. Otherwise, it's possibly non-stationary. This method is particularly meaningful if your data is from a Gaussian. If not, further testing will be required to determine if the variable is stationary or not.

In terms of looking at the preliminary stages and breaking down the variable into its components, statsmodels provide a method called **seasonal_decompose** which breaks down your time series into its three components.

[insert decompose plot]

This decomposition provides a holistic breakdown of the adjusted closing price over the past 20 years. It is clear that there's an increasing **trend** but it seems like there might also be some **seasonality**. These tools both graphically and statistically provided a preliminary test of stationary using basic tools. However, there is an even more robust test of stationarity called the Augmented Dickey-Fuller Test which can be accessed via statsmodels.


## Testing for Stationarity
### Augmented Dickey-Fuller Test for Stationarity
Simplistically, the Augmented Dickey-Fuller Test for Stationarity is a statistical test known as a unit root test. A unit root test defines how strongly a time series is defined by its trend. The null hypothesis is that a time series can be represented by a unit root, which would imply that the variable is non-stationary. The alternate hypothesis in this case would be the negation - that it is stationary. Therefore, if we find a large p-value from this test, then we can determine that our variable is non-stationary and a smaller p-value would indicate stationary.

Here's a summary of the ADF test:
+ ADF Statistics: 0.8076504166249344
+ p-value: 0.9917586617863505
+ Critical value (1%): -3.4566744514553016
+ Critical value (5%): -2.8731248767783426
+ Critical value (10%): -2.5729436702592023

Given such a high p-value, the result suggest that it is highly likely that this time series does have a unit root which implies that it is indeed non-stationary.

## Estimating Model Parameters
As mentioned earlier, the correlation of the dataset to itself can determine if the data is stationary. In order to build a model to forecast future returns, it is crucial to know how much to transform and adjust our variable in order to make it stationary. This is why we will use the Autocorrelation function (another function of statsmodels) to see how much differencing we need to transform the data to stationary.

### Autocorrelation Function (ACF)
Recall that time Series data have the property that they are ordered which means that past values can help us predict future values based on the correlation between each observations. The Autocorrelation Function (ACF) plots the coefficients of correlation between a time series and lags of itself. In simpler terms, the *ACF* provides insights on how points in the data are correlated separated by a specific lag time. A **lag** is an interval used to calculate the correlation. For example, when lag = 1, we are calculating the correlation between values at *t=0* with *t=1*, *t=1* and *t=2*, *...*, and *t=n-1* and *t=n*.

The statsmodels time series module provides a function called **plot_acf** which plots the autocorrelation function of the data set using lag = 40 and alpha = 0.05, which means that it returns values for the the 95% confidence interval.

[insert acf plot]

As is expected, we see that our correlation is not constant across different lags since we have shown that this variable is non-stationary.

### Transforming Data into Stationary by Taking the Differences
In order to transform the time series to stationary, I employ statsmodels *diff* function using a lag of order 1 (d = 1) by default, which means that it computes the autocorrelation of *t<sub>i</sub>* with *t<sub>i+1</sub>* for *1 ? i ? n* where *n* is the number of observations in the time series.

[insert acf plt for]

The ADF statistics based on this transformation are as followed:
+ ADF Statistics: -15.155031303806982
+ p-value: 6.7134196574358405e-28
+ Critical value (1%): -3.456780859712
+ Critical value (5%): -2.8731715065600003
+ Critical value (10%): -2.572968544

Note that the value of the ADF test is strongly negative and the p-value is significantly smaller than before which means we can assume that our model has been transformed from non-stationary to stationary. Now we will employ the ARIMA model to forecast the next years adjusted return prices.

## Using the ARIMA model to forecast the Monthly Returns of 2018

### What is ARIMA?
[INSERT SPIEL ABOUT THE ARIMA MODEL]

### Result Summary
[EXPORTED MODEL RESULT SUMMARY]

[insert plot]

Based on the Cumulative Distribution Function plot of the residuals, it can be seen that they follow a normal distribution with mean 0, which confirms that our model is a great fit. Now that we have found a fitting model, we can continue to forecast the stock prices of 2018

### Forecast
[insert plot]
[EXPORTED RESULT VS EXPECTED]

## Conclusion
TBD

