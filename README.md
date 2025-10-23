# Time Series Modelling and Forecasting of Daily Oil Prices  

This repository contains my MSc coursework project for **Advanced Research Methods in Data Science**.  
The project focuses on **time series modelling and forecasting daily crude oil (WTI) prices** using two classical approaches:  
- **ARIMA (Autoregressive Integrated Moving Average)**  
- **ETS (Exponential Smoothing)**  

The work includes data preprocessing, exploratory analysis, model tuning, forecasting, and critical evaluation.  

---

## 📂 Repository Structure
- `Time_Series_Modelling_and_Forecasting.ipynb` – Main Jupyter/Colab notebook with all code (data preprocessing, EDA, ARIMA, ETS, evaluation).  
- `oil_price.csv` – Input dataset of daily oil prices (business-day frequency).  
- `ets_24m_forecast.csv` – Exported 24-month ETS forecast results.  
- `ets_vs_actuals.csv` – Comparison of ETS forecasts with realised prices after 2022.  
- `Time Series Modelling and Forecasting of Daily Oil Prices.pdf` – Final report (6–8 pages).  

---

## ⚙️ Methods
1. **Data Preprocessing**
   - Converted raw price data to business-day frequency.
   - Forward-filled missing values.
   - Split into **train (2020–2021)** and **test (2022)** for validation.

2. **Exploratory Data Analysis**
   - Plotted daily oil prices.  
   - Conducted **stationarity tests** (ADF, KPSS).  
   - Examined **ACF and PACF** to guide ARIMA model selection.  

3. **ARIMA Modelling**
   - Grid search across p=0–8, d=0–2, q=0–8 (243 models).  
   - Best model: **ARIMA(3,1,8)** with lowest AIC.  
   - Refit on full data and forecasted 24 months ahead with 95% confidence intervals.  

4. **ETS Modelling**
   - Grid search across trend, damping, seasonality, and seasonal periods (None, 5, 21).  
   - Best model: **Level-only ETS** (no trend/seasonality).  
   - Refit on full data and forecasted 24 months ahead with confidence intervals.  

5. **Evaluation**
   - Metrics: RMSE, MAE, MAPE.  
   - Compared models on **2022 holdout** and **post-2022 realised data**.  
   - ARIMA adapted better to short-term shocks; ETS smoothed towards long-run mean.  

---

## 📊 Key Results
- **ARIMA(3,1,8):** Captured short-term dynamics, produced tighter forecasts.  
- **ETS (Level-only):** Simpler, but forecasts were overly smooth with wide confidence bands.  
- Both methods provided useful insights, but ARIMA showed better accuracy on holdout and post-2022 data.  

---

## 🖼️ Visuals
Figures included in the notebook and report:
- Daily oil prices (2020–2022)  
- ACF and PACF (first difference)  
- ARIMA 24-month forecast with CI  
- ETS 24-month forecast with CI  
- ETS forecast vs actual post-2022  

---

## 🚀 How to Run
1. Clone the repo:
   ```bash
   git clone https://github.com/yourusername/oil-price-forecasting.git
   cd oil-price-forecasting
