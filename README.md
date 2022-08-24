# VarModel

In this project I will identify the coupled relationship between the West Texas Intermediate Oil prices and the market yields for 10-year US Treasury Bonds. I will investigate this cointegrated relationship using a Vector Auto-Regressive model (VAR). From the model’s impulse response function, Granger Test, and forecasted error variance decomposition output I will show that an asymmetric shock in the price for crude oil will lead to a downstream change in the yield of 10-year US Treasury Bonds. 

I will be looking at data from the Federal Reserve Economic Database in St. Louis (FRED) during January 1991 to March 2022. I gathered monthly data on West Texas Intermediate grade crude oil spot prices (measured in US dollars per barrel). We also gathered date on the monthly market yield on 10-year constant maturity US Treasury Bonds, measured in percentages.

Before I can test for cointegration I will use the KPSS unit root test to check for nonstationarity in the two variables. The untransformed data did not pass the unit root test, and both are integrated of order one. I then transformed oil prices into the natural logarithm of its value. This step allows me to then transform both variables into the percentage change from month to month. After these transformations both the variables are stationary.

To determine the specification for the model I need to determine the number of lagged variables to include in the equation. I will use the Hannan-Quin criteria in the VARselect function output. The number of lags in this model will be one lag, or one month.

I then use the Granger Causality Test to test for “causality”/ directionality. The results from this test allow me to reject the hypothesis that oil prices do not predict a response in future Treasury Bond yields. I can then conclude the alternative hypothesis that oil prices do predict a response in future Treasury Bond yields.

I then use an Impulse Response Function and observe that introducing a shock to oil prices by, about 8.5% or one standard deviation from its steady state value, will result in a 2% increase in market yields for 10-year US Treasury Bonds.

I then use the Forecasting Error Variance Decomposition equation for both variables. This shows the amount of information each variable contributes to each other from the VAR model. This first section shows how much the future variation in oil and is caused by oil itself and Treasury Bonds yields. Practically 100% in the variation in oil prices is due to the variation in oil prices. Treasury Bond yields do not affect how oil prices fluctuate in the future. However, the second graph shows that 15% of the future predicted variation in treasury yields are due to past changes in oil prices.

