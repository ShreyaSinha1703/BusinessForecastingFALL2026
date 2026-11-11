# Forecasting Clothing Sales After the COVID Shock

Business Forecasting final project, Fall 2026 (Shreya Sinha).

## What this project does
Forecasts monthly retail clothing sales for the next 2 years (Aug 2026 to Jul 2028, 24 months). The headline recommendation focuses on the first 12 months, because the second year is much less certain. The analysis uses only the recovery period after the COVID low (May 2020 to Jul 2026, 75 months), selected with `window()`.

## Files
| File | What it is |
|---|---|
| `RetailSalesBF.csv` | Data: monthly clothing sales in USD (Date as dd/mm/yy), Jan 1992 to Jul 2026 |
| `Clothing_Sales_Project.Rmd` | Main R code: exploration, decomposition, nine forecasting methods, accuracy comparison, residual analysis, final forecast |
| `Clothing_ARIMA_Assignment.Rmd` | ARIMA assignment: model output explained, residual analysis, 5-month forecast, accuracy |
| Project presentation (`.pptx`) | Slides for classmates: problem, data, method, exploration, model judgement, recommendation, forecast, ideas to improve |
| `Clothing_Sales_Management_Summary.docx` | One-page memo for management with the recommendation |

## How to run
1. Install R and RStudio, then the packages: `install.packages(c("fpp2", "forecast"))`.
2. Put `RetailSalesBF.csv` in a folder and change the `read.csv(...)` path at the top of each `.Rmd` to match.
3. Knit each `.Rmd` (or run the chunks one by one).

## Method in short
- **Window:** recovery period only, May 2020 to Jul 2026.
- **Models compared:** mean, naive, seasonal naive, moving averages, simple smoothing, Holt-Winters, ETS, STL + ETS, ARIMA.
- **Accuracy measure:** MAPE (error as a percentage of sales, fair across small and large months), with RMSE and MAE as a cross-check.
- **Checks:** residual plots, ACF and Ljung-Box test for each model.

## Main results
- Best model: **ARIMA(0,2,2)(0,1,0)[12]**, MAPE 3.50% (Holt-Winters 4.16%, STL + ETS 4.60%, ETS 4.97%).
- Forecast for the first 12 months (Aug 2026 to Jul 2027): about 343,100, which is +4.0% on the last 12 months. Other models give about 333,000 to 336,000.
- Second year (Aug 2027 to Jul 2028): about 352,000, with a much wider range.
- December 2026 peak about 43,100 and January 2027 low about 21,600.

## Notes and limitations
- Only 75 months of data are used, and accuracy is measured on the same data the models were fitted on (no held-out test set).
- The ARIMA model needs three differences in total, so its forecast range is wide.
- COVID months are excluded rather than modelled, and no outside factors (prices, income, promotions) are included.
- The data source and units are used as supplied in the file.
