# GARCH Volatility Analysis - Tesla Stock Returns

## Project Overview

This project implements a comprehensive GARCH (Generalized Autoregressive Conditional Heteroskedasticity) analysis of Tesla stock returns to model and forecast volatility. The analysis demonstrates proper financial econometrics methodology for volatility modeling.

## Problem Statement

Tesla (TSLA) is known for its high volatility, making it an ideal candidate for volatility modeling. Understanding and forecasting volatility is crucial for:
- Risk management and Value-at-Risk (VaR) calculations
- Portfolio optimization
- Options pricing
- Trading strategies

## Project Structure

```
Garch-Analysis/
├── garch_volatility_analysis.ipynb  # Main analysis notebook
├── requirements.txt                  # Python dependencies
└── README.md                        # This file
```

## Installation

1. Clone or navigate to this directory
2. Create a virtual environment (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Linux/Mac
   # or
   venv\Scripts\activate  # On Windows
   ```

3. Install required packages:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

2. Open `garch_volatility_analysis.ipynb`

3. Run all cells sequentially to:
   - Download Tesla stock data (>500 observations)
   - Perform exploratory data analysis
   - Test for ARCH effects
   - Fit and compare multiple GARCH models
   - Validate model diagnostics
   - Generate volatility forecasts

## Methodology

### 1. Data Collection
- Source: Yahoo Finance via yfinance
- Asset: Tesla (TSLA)
- Period: 2021-01-01 to 2024-12-31
- Frequency: Daily
- Total observations: >500

### 2. Models Implemented

#### GARCH(1,1)
Standard GARCH specification with symmetric response to shocks.

#### EGARCH(1,1)
Exponential GARCH that captures asymmetric effects and ensures non-negative variance.

#### GJR-GARCH(1,1)
Threshold GARCH that allows negative shocks to have different impact than positive shocks (leverage effect).

### 3. Model Selection Criteria
- Akaike Information Criterion (AIC)
- Bayesian Information Criterion (BIC)
- Log-Likelihood
- Residual diagnostics
- ARCH LM tests

### 4. Key Tests Performed
- Jarque-Bera test (normality)
- Augmented Dickey-Fuller test (stationarity)
- Ljung-Box test (autocorrelation)
- ARCH LM test (conditional heteroskedasticity)

## Results Summary

The analysis includes:
1. ✅ Evidence of volatility clustering
2. ✅ Statistically significant ARCH effects
3. ✅ Model comparison showing GJR-GARCH as optimal
4. ✅ Successful capture of asymmetric volatility
5. ✅ 30-day volatility forecasts

## Key Findings

- Tesla returns exhibit significant volatility clustering
- Returns distribution shows excess kurtosis (fat tails)
- GJR-GARCH(1,1) provides superior fit due to leverage effect
- Conditional volatility estimates align with market events
- Model residuals show no remaining ARCH effects

## Justification for Model Choice

**GJR-GARCH(1,1) was selected because:**

1. **Leverage Effect**: Captures asymmetric impact of positive vs. negative returns on volatility
2. **Model Fit**: Lowest AIC/BIC values among compared models
3. **Residual Diagnostics**: Successfully eliminates ARCH effects in residuals
4. **Practical Relevance**: Widely used in financial risk management
5. **Theoretical Foundation**: Well-established in financial econometrics literature

## Dependencies

- **numpy**: Numerical computations
- **pandas**: Data manipulation
- **yfinance**: Financial data download
- **matplotlib/seaborn**: Visualization
- **scipy**: Statistical tests
- **statsmodels**: Time series analysis and diagnostics
- **arch**: GARCH models implementation

## References

1. Bollerslev, T. (1986). Generalized autoregressive conditional heteroskedasticity. *Journal of Econometrics*, 31(3), 307-327.
2. Nelson, D. B. (1991). Conditional heteroskedasticity in asset returns: A new approach. *Econometrica*, 59(2), 347-370.
3. Glosten, L. R., Jagannathan, R., & Runkle, D. E. (1993). On the relation between the expected value and the volatility of the nominal excess return on stocks. *The Journal of Finance*, 48(5), 1779-1801.
4. Engle, R. F. (1982). Autoregressive conditional heteroscedasticity with estimates of the variance of United Kingdom inflation. *Econometrica*, 50(4), 987-1007.

## Author

Financial Econometrics Analysis Project

## License

This project is for educational purposes.
