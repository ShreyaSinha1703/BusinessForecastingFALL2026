# Retail Sales Time-Series Decomposition and Forecasting

**Author:** Shreya Sinha  
**Date:** October 9, 2026  
**Language:** R

## Project Overview

This project analyzes monthly U.S. retail sales for clothing and clothing accessory stores using time-series decomposition, seasonal adjustment, and forecasting techniques in R.

Using the `fpp2` package, I examine the underlying trend, recurring seasonal patterns, and irregular fluctuations in historical sales data. I also compare two decomposition methods, STL decomposition and classical decomposition, to understand how the components of the sales time series can be separated and used for forecasting.

The analysis focuses on understanding long-term sales growth, annual seasonal fluctuations, and the unusual disruption around 2020 associated with the COVID-19 pandemic.

## Dataset

The project uses `RetailSalesBF.csv`, containing monthly retail sales data for U.S. clothing and clothing accessory stores.

- **Variable:** `ClothingSalesUSD`
- **Geographic coverage:** United States
- **Frequency:** Monthly
- **Start date:** January 1992
- **Seasonal adjustment:** Not seasonally adjusted

The sales data was converted into a monthly time-series object using R's `ts()` function with a frequency of 12.

## Tools and Technologies

- **R:** Statistical analysis and forecasting
- **RStudio:** Development environment
- **fpp2:** Time-series decomposition and forecasting
- **STL decomposition:** Separating trend, seasonal, and remainder components
- **Classical decomposition:** An alternative method for separating time-series components

## Project Methodology

### 1. Visualizing Historical Sales

I plotted the original sales time series to examine long-term trends and changes in monthly retail sales.

The plot shows an overall upward trend, with a notable decline around 2020. This decline may be associated with the disruption caused by the COVID-19 pandemic.

### 2. STL Decomposition

I applied STL decomposition using the `stl()` function with `s.window = "periodic"`.

This method separates the time series into three components:

- **Trend:** Represents the long-term movement in sales. In my analysis, the trend shows substantial growth over time.
- **Seasonality:** Captures recurring monthly patterns, including a prominent December increase and lower sales in the early part of the year.
- **Remainder:** Represents fluctuations not explained by the estimated trend and seasonal components. This includes irregular movements, such as the unusual decline around 2020.

The decomposition suggests that trend and seasonality are important features of the retail sales data.

### 3. Seasonal Adjustment

I used `seasadj()` on the STL decomposition to remove the estimated seasonal component from the original sales data.

I then plotted the seasonally adjusted series alongside the original sales series.

The adjusted series removes recurring seasonal fluctuations, making the underlying trend easier to examine. The broader upward movement and the unusual decline around 2020 remain visible because they are not simply recurring seasonal effects.

### 4. Forecasting with STL Decomposition

I generated forecasts from the STL decomposition using the `forecast()` function.

Two forecasts were examined:

- The default forecast horizon.
- A forecast covering the next 10 months.

The forecast plots display predicted sales along with uncertainty intervals. Because the series is decomposed, the seasonal pattern is incorporated back into the forecasts.

This approach allows the model to use the estimated trend and recurring seasonal behavior when projecting future sales.

### 5. Classical Time-Series Decomposition

As a second method, I applied classical decomposition using R's `decompose()` function.

This method separates the time series into trend, seasonal, and random components. I plotted the resulting decomposition and examined the seasonally adjusted series using `seasadj()`.

Comparing classical decomposition with STL provides an opportunity to explore alternative ways of separating the underlying components of monthly retail sales.

## Key Learning Outcomes

Through this project, I practiced:

- Creating and visualizing monthly time-series data.
- Decomposing sales into trend, seasonal, and remainder components.
- Using STL decomposition with a periodic seasonal component.
- Removing seasonal fluctuations through seasonal adjustment.
- Generating forecasts from a decomposed time series.
- Creating forecasts for a specified 10-month horizon.
- Applying classical decomposition as an alternative analytical method.
- Interpreting the potential impact of unusual economic events on historical sales patterns.

## Conclusion

This project demonstrates how time-series decomposition can help explain patterns in retail clothing sales. The analysis identifies a long-term upward trend, recurring annual seasonality, and irregular fluctuations that cannot be explained by those components alone.

Seasonal adjustment makes the underlying movement in sales easier to examine, while forecasting extends the analysis to future periods. Applying both STL and classical decomposition provides a foundation for understanding how different decomposition methods represent historical sales behavior.


