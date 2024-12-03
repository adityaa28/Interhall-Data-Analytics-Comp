# Interhall-Data-Analytics-Comp

To enhance forecasting accuracy, advanced time series and machine learning algorithms were explored for predicting sales in June 2021. The training data spanned from April 2018 to May 2021 and included four key features:

Warehouse ID: Identifies four warehouses (1, 2, 3, and 4).

Region: Represents the geographical direction served by each warehouse.

SKU ID: Unique identifier for stock-keeping units associated with specific warehouses.

Monthly Sales: Records the number of fans sold from April 2018 to May 2021.

The model's performance was evaluated using Mean Absolute Percentage Error (MAPE), calculated as:

MAPE = ABS (Actual Sales - Forecasted Sales) / Actual Sales, if Actual Sales > 0

0%, if both Actual Sales and Forecasted Sales are 0

100%, if Actual Sales = 0 and Forecasted Sales ≠ 0

Initially, various models were tested, including Random Forest, XGBoost Regressor, ARIMA, SES, SARIMA, Holt’s Linear Trend, and FB Prophet. However, these complex methods did not outperform a simpler approach.

Analyzing consecutive monthly sales revealed strong correlations, particularly up to the previous two months. Heatmap visualization reinforced this finding, leading us to explore a simpler predictive strategy.

A significant reduction in MAPE was achieved by predicting June’s sales using the previous month's sales as a reference. Comparisons were made between using May's sales, the average of April and May sales, or April's sales alone.

Recognizing that MAPE penalizes over-forecasting more than under-forecasting (percentage error is capped at 100% for low forecasts but unbounded for high forecasts), we adopted a conservative approach:

Predicted June’s Sales = Minimum (April’s Sales, May’s Sales)
This strategy yielded the lowest MAPE, significantly improving performance. For May 2021, the model achieved a MAPE of 46.55%.
