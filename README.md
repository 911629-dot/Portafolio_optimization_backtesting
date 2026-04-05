# Portafolio_optimization_backtesting
# Portfolio Optimization

A quantitative portfolio for student purposes, using Monte Carlo and 
Scipy mean-variance optimization to find optimal asset allocations 
and applying backtesting.

---

## What it does

1. Downloads adjusted price data from the Tiingo API for any set of assets and date range
2. Runs Monte Carlo simulations to explore the portfolio frontier
3. Uses SLSQP optimization to find the portfolio with maximum Sharpe Ratio and minimum volatility
4. Backtests both portfolios on a user-defined out-of-sample test period
5. Reports returns, volatility, Sharpe ratio, max drawdown, and final capital

---

## How to use

### 1. Install dependencies
```bash
pip install pandas numpy scipy requests tabulate matplotlib
```

### 2. Set your Tiingo API key

Get a free key at [tiingo.com](https://www.tiingo.com) and set it in the notebook:
```python
API_KEY = "your_api_key_here"
```

### 3. Define your assets and date ranges
```python
assets = ["AAPL", "MSFT", "GOOGL", "TLT", "GLD", ...]

price_data_frame = price_data_frame_full.loc["2010-09-09":"2023-12-31"].dropna().copy()  # Train
price_test       = price_data_frame_full.loc["2024-01-01":"2026-01-01"].dropna().copy()  # Test
```

### 4. Run the notebook

The notebook will automatically download and cache the data locally,
then run Monte Carlo, optimize, backtest, and display results.

---

##  Important!

The API can return both `close` and `adjClose`. It's important to use `adjClose` 
to prevent the use of extreme returns on stock split dates.
```python
all_data[asset] = df["adjClose"]
```

---

## Author

If you want a more detailed mathematical explanation of the code, 
check my repository [Portfolio-Optimization-Basic-Functionality](https://github.com/911629-dot/Portfolio-Optimization-Basic-Functionality) — Monte Carlo simulation for portfolio optimization using Sharpe ratio.
