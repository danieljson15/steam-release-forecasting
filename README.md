# Steam Game Release Forecasting

This project explores time series forecasting models to predict the number of monthly game releases on Steam. Using historical data from 1997 to 2018, I evaluated how well different models could capture industry growth and seasonality in game releases between 2019 and 2024.

## Why Steam?

Steam is one of the largest digital distribution platforms for PC games and represents a huge portion of the gaming industry. I have a lot of games on Steam, I wanted to analyze how game releases have evolved over time and explore whether those trends could be accurately forecasted using time series models.

## Models Used

I tested several forecasting methods:

- **ARIMA** – Simple autoregression; struggled with long-term trend modeling.
- **ETS (Error-Trend-Seasonality)** – Captured seasonality well with monthly data.
- **SARIMA** – Accounted for monthly cycles but was difficult to tune precisely.
- **Prophet** – Performed best overall, handling trend and seasonal components robustly.

## Data Processing

- Used `appid` to count unique games and `release_date` for time-based aggregation.
- Converted all dates to proper `datetime` format.
- Filtered data to only include games released before January 1, 2019 to avoid partial year skewing.
- Aggregated monthly release counts for better pattern visibility and modeling accuracy.

## Key Insights

- Models using **yearly data** underperformed due to low granularity and sparse early years.
- **Monthly aggregation** revealed short-term seasonality and produced much better predictions.
- **Prophet** and **ETS** performed best, with Prophet adapting more naturally to non-linear growth.
