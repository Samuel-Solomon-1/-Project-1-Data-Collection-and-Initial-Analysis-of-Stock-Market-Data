# Project 1: Data Collection and Initial Analysis of Stock Market Data

## Overview

This project provides a hands-on introduction to real-world financial data analysis using Python.  
We perform exploratory data analysis (EDA) on **daily historical stock prices** from 1970 to 2020 to identify trends, anomalies, and patterns that have shaped the stock market over the decades.

The analysis covers:

- Data loading and preprocessing
- Decade-based segmentation
- Statistical and visual exploration
- Comparative analysis across decades
- Summary of insights and hypothesis generation

---

## Dataset Description

We use two datasets:

1. **`historical_stocks.csv`**  
   Contains metadata for stocks including:
   - `ticker`, `exchange`, `name`, `sector`, and `industry`

2. **`historical_stock_prices.csv`**  
   Contains daily stock price data:
   - `ticker`, `open`, `high`, `low`, `close`, `adj_close`, `volume`, `date`

> Data Source: Provided via course materials or instructor

---

## Project Structure

```

Project 1: Data Collection and Initial Analysis of Stock Market Data/
│
├── Project 1: Data Collection and Initial Analysis of Stock Market Data.ipynb         # Jupyter Notebook with full analysis
│
├── data/
│   ├── historical_stocks.csv
│   └── historical_stock_prices.csv
│
└── README.md

```

---

## Steps Completed

### 1. **Data Collection**
- Loaded the datasets using Pandas
- Examined structure, missing values, and column types

### 2. **Data Cleaning**
- Handled missing values in `sector` and `industry`
- Removed duplicates
- Converted `date` column to datetime and indexed it

### 3. **Data Segmentation by Decade**
- Created a `decade` column (e.g., 1970s, 1980s, ...)
- Split the data into separate decade-based DataFrames for analysis

### 4. **Exploratory Data Analysis (EDA)**
- Generated summary statistics (mean, median, std) for `open`, `high`, `low`, `close`, and `volume`
- Created:
  - Time series plots of monthly average `close` prices
  - Histograms of `volume` (with 99th percentile cap)
  - Boxplots of `low` prices (log-scaled)

### 5. **Comparative Analysis**
- Compared mean, median, and volatility of prices and volumes across decades
- Visualized:
  - Average `close` price by decade
  - Average `volume` by decade
  - Volatility (std dev of `close`) by decade

---

## Insights Gathered and Conclusion

### Key Findings

- **Steady Growth in Stock Prices:**  
  Prices rose from ~$12 (1970s) to ~$122 (2000s), followed by slight decline in the 2010s.
  
- **Volume Expansion:**  
  Average volume doubled between the 1990s and 2000s, indicating rising market activity.

- **Rising Volatility:**  
  Volatility peaked in the 2000s, showing unstable periods likely tied to tech bubbles, financial crises, or deregulation.

- **Outliers and Skewness:**  
  Significant outliers in both `low` price and `volume` data—especially in recent decades—point to high-performing IPOs or algorithmic trading anomalies.

- **Seasonal Patterns (Potential):**  
  Monthly trends show mild periodicity, though more robust seasonal decomposition is needed.

### Hypotheses for Further Study

- Market growth trends are influenced by **macroeconomic indicators** (GDP, inflation, interest rates).
- **Tech and financial sectors** may disproportionately affect prices in 1990s and 2000s.
- The rise of **electronic trading and retail investing** impacts both volume and volatility patterns.

---

## Future Work

- Join `stock_prices` with `stock_metadata` to explore **sector-wise trends**
- Conduct **time series forecasting** (ARIMA, LSTM) for select tickers
- Decompose seasonal trends using `statsmodels`
- Normalize prices by stock splits and inflation for deeper analysis

---

## Skills Applied

- Pandas data wrangling
- Time-based resampling
- Decade-based segmentation
- Matplotlib and Seaborn visualizations
- Statistical summarization
