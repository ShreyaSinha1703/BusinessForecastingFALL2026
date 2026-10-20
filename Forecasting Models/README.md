# Retail Sales Forecasting: Clothing and Clothing Accessory Stores

**Author:** Shreya Sinha  
**Date:** October 2, 2026  
**Language:** R

## Project Overview

This project analyzes monthly U.S. retail sales for clothing and clothing accessory stores using time-series forecasting techniques in R. The goal is to identify trends and seasonal patterns in historical sales data, compare forecasting models, and determine which model performs best based on forecast accuracy.

The analysis explores how retail clothing sales have changed over time, including seasonal fluctuations and the potential impact of the COVID-19 pandemic. Multiple forecasting methods are evaluated to understand how well they capture the patterns in the data and predict future sales.

## Dataset Information

**Data file:** `Retail Sales - Clothing and Clothing Accessory Stores.csv`

**Source:** Federal Reserve Economic Data (FRED), based on data published by the U.S. Census Bureau.

**Series ID:** `MRTSSM448USN`

**Geographic coverage:** United States

**Frequency:** Monthly

**Coverage:** January 1992 – July 2026

**Seasonal adjustment:** Not seasonally adjusted

### Data Dictionary

| Variable | Variable Name | Measurement Unit | Description |
|---|---|---|---|
| Date of Observation | Date | Date (`YYYY-MM-DD`) | The first day of each month represented in the sales data. |
| Retail sales of clothing and clothing accessories stores | `ClothingSalesUSD` | Numeric | Total monthly retail sales at U.S. clothing and clothing accessory stores, as estimated by the U.S. Census Bureau's Monthly Retail Trade Survey and published through FRED. |

The sales variable represents monthly retail sales in U.S. dollars. The data is not seasonally adjusted, so recurring seasonal patterns remain visible in the observations.

## Data Collection Methodology

The data is collected monthly by the U.S. Census Bureau through the **Monthly Retail Trade Survey (MRTS)**.

According to the dataset documentation used for this project:

- The survey uses a mail-out/mail-back collection method.
- The sample consists of approximately 13,000 retail businesses with paid employees.
- Businesses are selected from the Business Register, which contains employer identification numbers and establishment locations.
- The sample is updated quarterly to account for new businesses and businesses that have closed.
- Newly established firms may take approximately nine months to appear in the survey.
- A new sample is selected approximately every five years, with 2018 identified as the latest sample in the provided documentation.
- Larger firms above a sales cutoff are selected with certainty, representing approximately 2,500 businesses, while the remaining firms are selected randomly.

These collection methods provide a recurring source of information about U.S. retail sales activity.

## Why I Chose This Dataset

I chose this dataset because retail clothing sales are influenced by consumer behavior, seasonal trends, and special occasions. I was interested in investigating whether recurring patterns appear around changes in seasons, back-to-school periods, and other shopping occasions.

Clothing sales may also reflect broader economic conditions, including periods of growth and recession. Another motivation was to explore the potential impact of the COVID-19 pandemic on retail clothing stores, including the decline in sales during the disruption and the subsequent recovery.

I was particularly interested in determining how accurately different forecasting models could capture these trends and seasonal patterns. My personal interest in clothing and shopping also made this dataset relatable and engaging to analyze.

## Project Methodology

### 1. Trend and Seasonality Analysis

I converted the monthly sales observations into a time-series object in R using the `ts()` function, beginning in January 1992 with a frequency of 12.

I used a time-series plot and the autocorrelation function (ACF) to investigate trends and recurring seasonal patterns.

The time-series plot showed an overall upward trend, with a dip around 2020 that may be associated with the COVID-19 pandemic. The ACF showed notable values at lags 12 and 24, supporting the presence of an annual seasonal pattern.

### 2. Forecasting Models

I implemented several forecasting methods using the `fpp2` package:

- **Simple Mean:** Forecasts future sales using the historical average.
- **Naive:** Uses the latest observed sales value as the forecast for future periods.
- **Seasonal Naive:** Uses the corresponding value from the previous seasonal cycle.
- **Moving Averages:** Examines 3-, 5-, and 50-period moving averages to compare different levels of smoothing.
- **Holt-Winters Exponential Smoothing:** Models the level, trend, and additive seasonality in the monthly sales data.

I generated forecasts and visualized the results to compare how the different methods represent historical patterns and future sales.

### 3. Forecast Accuracy Evaluation

I compared forecasting performance using several error metrics:

- **ME:** Mean Error
- **RMSE:** Root Mean Squared Error
- **MAE:** Mean Absolute Error
- **MAPE:** Mean Absolute Percentage Error

MAPE was used as the main comparison metric because it expresses forecast errors as percentages, making the results easier to interpret relative to sales levels.

### 4. Forecast Comparison Results

The reported MAPE values from the analysis were:

| Forecasting Model | MAPE |
|---|---:|
| Simple Mean | 33.93% |
| Naive | 21.30% |
| Seasonal Naive | 7.59% |
| Moving Average (3 periods) | 10.81% |
| Moving Average (5 periods) | 14.36% |
| Moving Average (50 periods) | 15.19% |
| Holt-Winters | 4.97% |

*Note: These figures come from the original R output. Holt-Winters and several other results use training-set accuracy, whereas the moving-average results are labeled as test-set accuracy. The values therefore should not be treated as a fully comparable model ranking until all models are evaluated over the same period.*

### Best-Performing Model

Holt-Winters produced the lowest reported MAPE of 4.97%, while the simple mean model produced the highest reported MAPE of 33.93%.

This result suggests that incorporating level, trend, and seasonality can be useful when forecasting retail clothing sales. However, a fair assessment of the best forecasting model requires evaluating each model on the same held-out test period.

## Tools and Technologies

- **R:** Data analysis and forecasting
- **RStudio:** Development environment
- **fpp2:** Time-series forecasting methods
- **forecast:** Forecast generation and accuracy evaluation
- **Base R:** Time-series plots, ACF analysis, and forecast visualizations

## Key Learning Outcomes

Through this project, I practiced:

- Understanding the background, structure, and collection methodology of a real-world economic dataset.
- Identifying trends and seasonal patterns in monthly sales data.
- Using autocorrelation analysis to investigate seasonality.
- Applying and comparing multiple time-series forecasting models.
- Visualizing forecast results and evaluating prediction errors.
- Interpreting model accuracy and considering the importance of consistent evaluation periods.
- Exploring how economic disruptions and consumer behavior may affect retail sales.

## Conclusion

This project applies time-series analysis and forecasting techniques to U.S. clothing and clothing accessory store sales. The historical data provides an opportunity to explore long-term growth, annual seasonality, and possible disruptions associated with major economic events.

Among the models tested, Holt-Winters had the lowest reported MAPE. Its ability to incorporate level, trend, and seasonality makes it a promising approach for this dataset. Evaluating all models on a consistent test period would provide a stronger basis for selecting the final forecasting model.

Overall, the project demonstrates how forecasting methods can be used to explore historical retail sales patterns and support data-driven understanding of future sales behavior.

