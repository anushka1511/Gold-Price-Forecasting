# Gold Price Forecasting using Holt-Winters and Ensemble Learning

This project aims to forecast the USD-denominated gold price using two contrasting methods:  
- A **classical time-series model** (Holt-Winters Exponential Smoothing)  
- An **advanced ensemble machine learning model** (Gradient Boosting Regressor)

By comparing these methods on historical gold data, we evaluate their performance in modeling and predicting financial time series behavior.

---

## Objective

To predict the complex dynamics of gold prices and compare the forecasting accuracy of traditional statistical techniques with modern machine learning models.

---

## Methodologies

### 1. **Holt-Winters Exponential Smoothing**
- Captures trend and seasonality
- Suited for regular, cyclic patterns
- Model trained on 80% of 10 years of daily data

### 2. **Ensemble Learning (Gradient Boosting Regressor)**
- Uses lag features, rolling statistics (mean, std), and time-based patterns
- Trained with engineered features on the same 80% split
- Evaluated with:
  - R² Score
  - Symmetric Mean Absolute Percentage Error (SMAPE)

---

## Dataset

- Source: Yahoo Finance via `yfinance`
- Ticker: `GC=F` (Gold Futures, USD)
- Timeframe: Last 10 years, daily frequency

---

## Results

| Model                     | R² Score | SMAPE (%) |
|--------------------------|----------|------------|
| Holt-Winters             | -5.31    | *NaN*      |
| Ensemble (Gradient Boosting) | -1.11    | **19.82**   |

> **Conclusion**: The Ensemble model demonstrated a more reliable performance based on SMAPE, even in volatile price periods.

---

## Key Features Used (Top 10)
- lag_1
- rolling_mean_21
- lag_2
- lag_10
- rolling_mean_10
- lag_21
- rolling_mean_5
- lag_3
- lag_5
- rolling_std_21

---

## Tech Stack

- Python
- yFinance
- Scikit-learn
- Statsmodels
- Pandas, NumPy, tqdm

---

## How to Run

1. Clone the repository  
2. Install dependencies  
   ```bash
   pip install pandas yfinance scikit-learn statsmodels tqdm
