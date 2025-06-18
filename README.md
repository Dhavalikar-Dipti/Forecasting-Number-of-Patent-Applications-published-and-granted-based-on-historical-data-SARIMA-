# Forecasting-Number-of-Patent-Applications-published-and-granted-based-on-historical-data-SARIMA-


This project performs time series analysis and forecasting on patent data — comparing **Published** and **Granted** patent counts on a weekly basis using SARIMA models.

## Overview

- Data includes weekly patent publication and grant records.
- Goal: Understand seasonal trends, forecast future counts, and compare publishing-to-granting efficiency.

## Tools & Libraries

- Python, Pandas, NumPy, Matplotlib
- `statsmodels` (SARIMA, ADF Test, Decomposition)
- `sklearn.metrics` (MAE, MSE)
- Google Colab + Drive

## Key Steps

### Data Preprocessing
- Converted `PUBLICATION_DATE` to datetime.
- Resampled to weekly frequency.
- Merged datasets for comparative analysis.

### Time Series Decomposition
- Used additive decomposition to isolate **trend**, **seasonality**, and **residuals**.
- Found strong yearly seasonality in both published and granted patents.

### SARIMA Forecasting
- Granted Model: `SARIMA(1, 0, 1)(1, 1, 1, 52)`
- Published Model: `SARIMA(2, 1, 2)(1, 1, 1, 52)`
- Forecasted next **52 weeks** for both series.

### Outlier Detection
- Used IQR method to detect and replace outliers with the **median**.
- Improved model accuracy significantly.

## Model Performance

| Data Type | MAE (Before) | MSE (Before) | MAE (After) | MSE (After) |
|-----------|--------------|--------------|-------------|-------------|
| Granted   | 784.39       | 909,029.10   | 140.58      | 35,118.02   |
| Published | 368.92       | 195,254.68   | 347.83      | 161,069.00  |

## Comparative Insights

- **Trend Gap**: Published > Granted consistently.
- **Ratio Analysis**:
  - Avg. weekly **Published-to-Granted ratio** ≈ **1.6**
  - Forecasted **Grant-to-Publish ratio** ≈ **0.62** (on avg)
- Seasonal patterns repeat annually (52-week cycle).
- Publishing shows more volatility; granted patents exhibit stable trends.

## Forecast Output (Next 52 Weeks)

- Clear seasonal oscillations.
- Reliable predictions for patent activity planning.

## Files

- `Time Series.ipynb`: Complete analysis and code.
- `patent_published.csv`, `patent_granted.csv`: Input datasets.
- `README.md`: This file!

## Conclusion

This analysis helps in:

- Understanding the patent pipeline (submission to approval).
- Estimating backlog and processing efficiency.
- Planning policy decisions or operational capacities based on data-driven forecasts.

---

# Forecasted Grant-to-Publish Ratio (Next 52 Weeks)

![SARIMA Forecast ](Published.png)
