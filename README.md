# Macro Factor Risk Attribution Model

## Overview
This project builds a macro-driven factor risk model to explain and decompose multi-asset portfolio returns using U.S. economic indicators. It quantifies systematic vs idiosyncratic risk and evaluates factor exposures across equity, rates, credit, and gold.

---

## Methodology

- Collected macroeconomic data from FRED (CPI, UNRATE, FEDFUNDS, 10Y Treasury Yield)
- Constructed orthogonal macro factors using PCA decomposition
- Modeled ETF returns using multivariate OLS regression
- Estimated factor loadings (betas) and explanatory power (R²)
- Computed systematic vs idiosyncratic risk decomposition
- Evaluated factor tail risk using 5% VaR and volatility

---

## Assets Analyzed

- SPY (Equities)
- TLT (Long-Term Treasuries)
- LQD (Investment Grade Credit)
- GLD (Gold)

---

## Macroeconomic Factors

- F1_Market (Growth / Risk-On)
- F2_Rates (Interest Rate / Duration)
- F3_Risk (Credit / Liquidity / Shock)

---

## Key Results

### 📊 Model Fit (R² / Systematic Risk)

| Asset | R² | Systematic Risk |
|------|------|----------------|
| SPY | 0.8683 | 0.8683 |
| TLT | 0.6800 | 0.6800 |
| LQD | 0.4090 | 0.4090 |
| GLD | 0.2443 | 0.2443 |

---

### 📉 Factor Contribution to Risk (%)

| Asset | F1_Market | F2_Rates | F3_Risk |
|------|----------|----------|---------|
| SPY | 0.9609 | 0.0259 | 0.0132 |
| TLT | 0.3049 | 0.3096 | 0.3855 |
| LQD | 0.0005 | 0.6254 | 0.3741 |
| GLD | 0.0075 | 0.9896 | 0.0029 |

---

### 📈 Factor Risk Statistics

| Factor | Volatility | VaR (5%) |
|--------|------------|----------|
| F1_Market | 1.3792 | -1.9816 |
| F2_Rates | 1.0633 | -1.5929 |
| F3_Risk | 0.8454 | -1.2118 |

---

## Key Insights

- SPY is highly driven by systematic macro risk (~87% explained)
- TLT and LQD are primarily rate-sensitive assets
- GLD shows weak macro linkage (low R² ~0.24), consistent with safe-haven behavior
- Rate factor dominates credit markets (LQD ~62% exposure)
- Market factor dominates equity risk (>96% contribution)

---

## Tech Stack

- Python (pandas, numpy)
- statsmodels (OLS regression)
- scikit-learn (PCA)
- yfinance (market data)
- pandas-datareader (FRED macro data)

---

## Files

- `macro_factor_risk_model.ipynb` → main analysis notebook
- `requirements.txt` → dependencies
- `results/` → visual outputs (VaR, distributions, backtests)

---

## Author
Ranveer Bhalla