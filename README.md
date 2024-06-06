# Time-Series-Predictions-of-Stock-Trading-Volume

This report investigates methods for predicting the trading volume of a stock (VolStock1(t)) based on historical data.

**Data and Features**

The analysis utilizes several data points to understand factors influencing trading volume:

* Earnings Announcement Day (EADay): Indicates whether there was an earnings announcement on a particular day.
* Trading Day of the Week: Includes separate variables for Monday, Tuesday, Wednesday, Thursday, and Friday.
* Month of the Year: Includes separate variables for each month, potentially capturing seasonal trends related to earnings cycles.
* Past Trading Volume: The volume of the stock traded on the previous day (VolStock1(t-1)) and potentially a few days before (VolStock2(t-1) to VolStock6(t-1)).
* Moving Averages (EMA_2 to EMA_6): Exponential moving averages of the trading volume, which can help smooth out short-term fluctuations.

**Models Evaluated**

The report compares three models for predicting trading volume:
* Basic Model: This initial model uses only EADay and the previous day's trading volume (VolStock1(t-1)) as features. It achieves a moderate R-squared of 0.40, indicating that it explains around 40% of the variation in trading volume.
* Basic Model 2: This variant explores including additional days around the earnings announcement (EADayBefore and EADayAfter) but achieves a lower R-squared of 0.196.
* OLS Model: This more complex model incorporates all the features mentioned earlier (including Day of Week, Month, and Moving Averages) and achieves a significantly higher R-squared of 0.496. This suggests that these additional factors provide valuable insights into predicting trading volume.

A further refinement (OLS Model 2) reduces the number of features but maintains a comparable R-squared of 0.482.

**ARIMA Model**

The report then explores using an ARIMA model, a statistical method for analyzing time series data. This model focuses on past values of the target variable (trading volume) to make predictions. The analysis confirms stationarity of the data (meaning the statistical properties don't change over time) and identifies optimal parameters for the model. However, the ARIMA model achieves a Mean Squared Error (MSE) of 2.02 on validation data, indicating a relatively high average difference between predicted and actual values.

**ARIMAX Model**

To improve prediction accuracy, the report introduces an ARIMAX model. This extends ARIMA by incorporating additional explanatory variables (like EADay, Day of Week, Month) alongside past values. By leveraging this broader range of factors, the ARIMAX model achieves a significantly lower MSE of 1.13, demonstrating a substantial improvement in prediction accuracy.

**Conclusion**

The report highlights the limitations of simpler models and emphasizes the effectiveness of the ARIMAX model in capturing the complexities of stock trading volume data. By incorporating various relevant features and accounting for seasonality, the ARIMAX model provides more accurate predictions compared to other methods explored.
