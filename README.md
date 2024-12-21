# Renewable Energy Project (WIP)


## Project Goal
- This goal of this project is to predict renewable energy output by analyzing the relationship between weather and past energy generation.
- Possible methods: ARIMA time series analysis model, machine learning models (linear regression, random forest), deep learning model (neural network model)

## Dataset Description
- This renewable power generation and weather conditions dataset is from [Kaggle](https://www.kaggle.com/datasets/pythonafroz/renewable-power-generation-and-weather-conditions?resource=download) and it ontains 196,776 rows x 17 columns of data (over 3.3 millions of data points).
- Here are some explanation to specific columns in the dataset
  - Energy delta - The difference in energy consumption in Watt-hours (Wh) from the previous timestamp to the current timestamp.
  - GHI - Global Horizontal Irradiance in Watts per square meter (W/m²) measured by a pyranometer
  - rain_1h - The amount of precipitation in millimeters (mm) measured over the past hour.
  - snow_1h - The amount of snowfall in millimeters

## Data analysis steps breakdown
- Perform EDA on the dataset and visualize the relationships between dependent variables and independent variable (Energy delta)
- Created correlation matrix to see the coefficient between each variable
- Performed ARIMA Time Series Analysis for forecasting energy output demand based on DHI

### ARIMA Analysis
- First, performed a Dickey-Fuller test, which is a statistical test used to determine if a time series is stationary.
- Null hypothesis: this time series is not stationary
- Test Statistic: This is the actual value calculated by the test, which is approximately -13.95326 in this case. This value is used to reject or fail to reject the null hypothesis of the test.
- p-value: This tells us the probability of finding the observed, or more extreme, results when the null hypothesis (H0) of a study question is true. The null hypothesis in the context of the Dickey-Fuller test is that the time series has a unit root (i.e., it is non-stationary). Here, your p-value is extremely low (4.660561e-26), which effectively means there is virtually no chance that the time series possesses a unit root according to the test.
- #Lags Used: The number of lags used in the regression when performing the Dickey-Fuller test. In this case, 43 lags were used. The selection of lags can affect the test results; too few may not capture the autocorrelation properly, and too many may introduce noise.
- Number of Observations Used: This is the number of points used in the analysis after adjusting for lags. Here, it's 16,538. This number, combined with the number of lags, tells you how much of your original data was actually used for the testing after accounting for the lags.
- Critical Values: These values correspond to the thresholds that the Test Statistic must cross to reject the null hypothesis at certain confidence levels. The critical values provided are for the 1%, 5%, and 10% levels. These indicate the cutoff points needed to reject the hypothesis of a unit root with corresponding probabilities:
-     Critical Value (1%): -3.430745. The test statistic is far below this value, suggesting you can reject the null hypothesis with more than 99% confidence
-     Critical Value (5%): -2.861715. Similar to the 1% level, the test statistic is well below this, indicating rejection of the null hypothesis with at least 95% confidence.
-     Critical Value (10%): -2.566863. Again, your test statistic is lower, allowing rejection of the null hypothesis with at least 90% confidence.
- Conclusion: Given that the test statistic is far below the critical values at all conventional significance levels and the p-value is exceedingly low, you can confidently reject the null hypothesis. This means that the time series data is stationary, and it does not have a unit root present.









