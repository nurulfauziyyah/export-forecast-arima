# 📈 Export Forecasting with ARIMA (Yogyakarta City)

This repository contains a time series forecasting project using the **ARIMA** model to forecast export values of Yogyakarta City based on official data from BPS.

---

## 📊 Dataset

The dataset consists of:

- **Export and Import Values**
- Unit: **Million US Dollars (USD)**
- Source: **BPS (Statistics Indonesia) – Yogyakarta City**
- Period: **2020–2023**

The focus of modeling in this project is on the **export value time series**.

---

## 🎯 Objective

To build a reliable time series forecasting model for export values using the **ARIMA (Autoregressive Integrated Moving Average)** approach and determine the best model based on statistical diagnostics.

---

## 🔎 Methodology

The modeling process follows the Box-Jenkins procedure:

### 1️⃣ General Model Formulation
Define the ARIMA model structure:

\[
ARIMA(p, d, q)
\]

Where:
- **p** = order of Autoregressive (AR)
- **d** = order of differencing
- **q** = order of Moving Average (MA)

---

### 2️⃣ Preliminary Model Identification
- Check stationarity (visual inspection & differencing).
- Identify candidate models using ACF and PACF plots.
- Proposed candidate models:
  - ARIMA(2,1,1)
  - ARIMA(2,1,0)
  - ARIMA(3,1,0)

---

### 3️⃣ Parameter Estimation
Estimate parameters of candidate models and evaluate:

- Significance of coefficients
- AIC (Akaike Information Criterion)
- Diagnostic tests (residual assumptions)

Model comparison summary:

| Model        | AIC    | Diagnostics Result |
|-------------|--------|-------------------|
| ARIMA(2,1,1) | 299.6  | Assumptions not satisfied |
| ARIMA(2,1,0) | 297.86 | Assumptions satisfied ✅ |
| ARIMA(3,1,0) | 299.57 | Assumptions not satisfied |

---

### 4️⃣ Model Adequacy Check
- If residuals satisfy white noise assumptions → model is adequate.
- If not → return to Step 2 (re-identification).

---

## 🏆 Best Model

The best model obtained is:

\[
\boxed{ARIMA(2,1,0)}
\]

Reasons:
- All coefficients are statistically significant.
- Lowest AIC value (297.86).
- Diagnostic tests indicate model assumptions are satisfied.

---

## 📈 Forecasting

Using ARIMA(2,1,0), export values are forecasted for future periods based on historical patterns (2020–2023).

---

## 🛠 Tools Used

- RStudio
