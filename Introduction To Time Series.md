![image](https://github.com/user-attachments/assets/8ca769c2-a896-498d-bee8-a61803978258)

**Frequency:**
* refers to how often data points are collected in a time series. It specifies the interval between consecutive observations.
![image](https://github.com/user-attachments/assets/b06b901e-76f8-4c49-943b-c20b300cbdaf)

**Horizon:**
* refers to the number of future time steps for which predictions are being made. It defines how far ahead in the future you are forecasting.
![image](https://github.com/user-attachments/assets/e1b02408-5ab3-484e-a7cf-cb1cfabcf895)


# Types of forecasting:
* Qualitative Forecasting: This approach is based on judgment, opinions, and intuition rather than on hard data. It’s often used when there isn’t much historical data available. For example, a 
  company might use expert opinions to predict the success of a new product.

* Quantitative Forecasting: This method relies on numerical data and statistical techniques to make predictions. It’s often used when there’s plenty of historical data available. For instance, 
  a company might use past sales data to forecast future sales.


# Seasonal decomposition
* Trend

* Seasonality

* Noise


Components:
![image](https://github.com/user-attachments/assets/36cb40cd-f35d-4e45-85d1-6a65beb285a2)

* Level: baseline average around which your data fluctuates over time
![image](https://github.com/user-attachments/assets/856eaba7-bd31-4462-9d46-8d67efb25acf)

* Trend: the above time series has an increasing trend.

* Seasonality: Cycle or pattern that repeats over time (periodically)  (e.g., daily, weekly, monthly, yearly)
  Example: Ice cream sales
![image](https://github.com/user-attachments/assets/f79bca7b-0847-427a-bc47-ad2b8a37dd82)

* Cyclicity: refers to patterns that occur over long, irregular intervals. Unlike seasonality, cyclic patterns don't have a fixed or predictable frequency. These cycles are often driven by economic or business conditions and can last for several years.

* Noise: if we subtract trend and seasonality/cyclicity, we get noise (these are random fluctuations)


# Additive And Multiplicative Nature of Time Series:
* In an additive model, the components of the time series (trend, seasonality, and noise) are added together:
* In a multiplicative model, the components of the time series are multiplied:

![image](https://github.com/user-attachments/assets/a378f7b4-d623-42ee-abde-d71b501e8a27)

* If the seasonal patterns or trends are consistent and don’t change with the level of the time series, go with **additive**.

* `In an additive model, the noise (residual) component is typically centered around **zero**.`

* If the seasonal patterns or trends get bigger or smaller depending on the level of the time series, go with **multiplicative**.

* `In a multiplicative model, the noise component is generally assumed to have a mean of **1**.`
![image](https://github.com/user-attachments/assets/66c23db6-e631-4e6b-9fb5-6eb9b85ef33b)

* So yes, if the base level of the series stays the same, additive is usually a good choice. If the base level changes and you see proportional changes in the components, then multiplicative is more appropriate.


**What Happens If the Wrong Model is Used:**
* If you apply an additive model to data that follows a multiplicative pattern, the noise may exhibit some structure or pattern (not just centered around zero). This can be due to the fact that the model fails to capture the proportional change in the seasonal and trend components.

* As you mentioned, in a multiplicative model, the noise typically fluctuates around 1, but if the wrong model is used (like additive for multiplicative data), you'll observe patterns in the residuals that shouldn't be there, as shown in the residual plot. The noise in the residuals will not be purely random anymore, but might show a systematic pattern.


* `if we plot additive TS as multiplicative, there might be a pattern in the noise (As we know, noise can either 0 or 1) but here it has a pattern and values other than 0 and 1`
![image](https://github.com/user-attachments/assets/3b0c3c4d-2559-4f0d-86ea-e841d5d80658)


# Stationarity:  `means that the statistical properties of the series—like the mean, variance, and autocorrelation—remain constant over time. Stationarity means that the series behaves the same way over time, with no trends or seasonal patterns that change the overall structure of the data.`
* `Dickey-Fuller (ADF) test is used to check if its stationary`
  ![image](https://github.com/user-attachments/assets/d597e36c-7ee2-4e8e-a4c9-35ee0643d142)
  ![image](https://github.com/user-attachments/assets/f20c8873-ad12-4cfc-b501-1dfe154da4f5)


* Non-Stationary Series: `The series has trends, seasonality, or other patterns that change over time.`

![image](https://github.com/user-attachments/assets/3f5ea5ff-7081-42b7-a5b6-552c412a118b)

* mean: constant mean over time means, when i move, the mean should remain constant
![image](https://github.com/user-attachments/assets/b000460d-cede-4942-83f9-69a7180dfb66)

* constant variance: In the top plot (stationary series), the ups and downs (fluctuations) are roughly the same size all the way through. This shows constant variance.

* In the bottom plot (non-stationary series), the ups and downs start small but get bigger over time. This shows changing variance.
  
* constant autocorrelation: is about how a current value in the series is related to its past values.

* `JUST LOOK AT THE WIDTH, IF SAME THEN CONSTANT AUTOCORRELATION`

* In the top plot (stationary series), the relationship between the values remains consistent, meaning if there’s a pattern (like a repeat every few points), that pattern doesn’t change over time.

* In the bottom plot (non-stationary series), as the variance changes, the relationships between the data points also start to change, which can disrupt the pattern, meaning autocorrelation is not constant.


# Differencing:  
`technique used in time series analysis to make a time series stationary, which means removing trends or seasonality. The idea is to subtract the previous value in the series from the current value. This helps to remove patterns that make the series non-stationary.`

* First-Order Differencing:

* First-order differencing means subtracting the value of the previous time point from the current time point

* `It removes linear trends. If your data is steadily increasing or decreasing, first-order differencing will often make it stationary.`

* Second-Order Differencing:

* Second-order differencing means taking the first-order differenced series and then differencing it again.

* `It removes quadratic trends or trends that change direction (like a curve). It's useful when the first-order differencing isn’t enough to make the series stationary.`

* `SOME OTHER TECHNIQUES TO MAKE NON-STATIONARY, STATIONARY`
![image](https://github.com/user-attachments/assets/e26c9665-a020-41e6-b38e-ff625de2ec6f)


# lAGS:
![image](https://github.com/user-attachments/assets/2b0aac7f-4399-42be-92b3-d8466b4f9039)

`This is how we do lags, the values says that 40 is influnced by 20(WITH SOME CONSTANT) + 10(WITH SOME CONSTANT)`
![image](https://github.com/user-attachments/assets/ecb97b47-e842-4669-9868-69e804ea265f)



# Auto correlation
`Measures how much the current value in a time series is related to its past values, considering all previous lags`
* The plot here shows a baseline, above this line shows that this lag is statistically significant 
![image](https://github.com/user-attachments/assets/d21d245d-2866-4bff-8064-feac262c78cd)


# Partial Auto Correlation
`Measures the direct relationship between the current value and a specific past value, removing the influence of the values in between.`

 ![image](https://github.com/user-attachments/assets/a431ea19-4b95-45cb-b408-12e4baa44bbd)


![image](https://github.com/user-attachments/assets/2b5ea2aa-7e4d-4847-8d77-b28058dc9ed0)


# AR and MA
![image](https://github.com/user-attachments/assets/3438a84c-7131-4e42-993d-f859e03ea3ce)

* `AR: Relies directly on past values.`

* `but how many past values we need for this, ACF and PACF will tell us`
![image](https://github.com/user-attachments/assets/50d9eb15-5b1d-4697-80d9-5e5f62a03ab9)

* `IF ITS AR:`
![image](https://github.com/user-attachments/assets/592a61b3-4056-4829-8ab8-22aacfeba9a5)

* `Example: “I played well yesterday, so I’ll probably play well today.”`

![image](https://github.com/user-attachments/assets/fe229101-1502-4ee7-9e6c-c6061981a220)
![image](https://github.com/user-attachments/assets/5bcc60f7-23f5-446c-8711-041a5ad9677e)


* `MA: Relies on past prediction errors.`

* `Example: “I guessed my score too low last time, so I’ll guess higher this time.”`

* `but how many past ERROR values we need for this, ACF and PACF will tell us`
![image](https://github.com/user-attachments/assets/4530ff0f-92ef-4bd9-91a0-0e9e043baf07)

* `IF ITS MA:`
![image](https://github.com/user-attachments/assets/8cbe49c6-433c-40c2-a4fb-eddda45b2ad0)

![image](https://github.com/user-attachments/assets/bd7b132f-3d54-42d3-b7bb-08a0ac9e3408)


`if we see k significant lags in both of them, then its ARMA`
![image](https://github.com/user-attachments/assets/698dfb93-1ced-4100-a6a4-a566fe00ccb2)
![image](https://github.com/user-attachments/assets/a83a3831-2a9d-4fbe-b1dc-6313213f6083)

`Equation`
![image](https://github.com/user-attachments/assets/d20db3a1-5271-482c-866d-6339a1ebb544)


 












