# Phase 2 – ML for Finance

**Duration:** Months 7–12 (October 2026 – March 2027)

Apply classical machine learning to financial data. Build intuition for what works and what doesn't in practice.

## Goals

- Understand and implement core ML algorithms from scratch and with scikit-learn
- Engineer meaningful financial features from raw OHLCV data
- Build a full ML pipeline: data → features → model → evaluation → signal
- Understand why most ML models fail on financial data (and how to reduce this)

---

## Module 1: Core ML Algorithms (Weeks 1–4)

### Topics
- [ ] Linear Regression and Regularization (Ridge, Lasso)
- [ ] Logistic Regression
- [ ] Decision Trees
- [ ] Random Forests
- [ ] Gradient Boosting (XGBoost, LightGBM)
- [ ] k-Nearest Neighbors
- [ ] Support Vector Machines

### Key Concepts
- [ ] Bias-variance tradeoff
- [ ] Cross-validation (k-fold, time series split)
- [ ] Hyperparameter tuning (GridSearch, RandomSearch, Optuna)
- [ ] Feature importance and SHAP values
- [ ] Train / validation / test split (no look-ahead!)

### Resources
- *Hands-On Machine Learning* – Aurélien Géron (Chapters 1–7)
- scikit-learn documentation

---

## Module 2: Feature Engineering for Finance (Weeks 5–8)

### Raw Features from OHLCV
- Open, High, Low, Close, Volume
- Log returns: `log(Close_t / Close_{t-1})`
- Rolling statistics: mean, std, min, max over N-day windows

### Technical Indicators
- [ ] SMA and EMA (trend)
- [ ] RSI – Relative Strength Index (momentum)
- [ ] MACD – Moving Average Convergence Divergence (trend + momentum)
- [ ] Bollinger Bands (volatility)
- [ ] ATR – Average True Range (volatility)
- [ ] OBV – On-Balance Volume (volume)

### Advanced Features
- [ ] Lagged returns (t-1, t-2, t-5, t-10, t-20)
- [ ] Day of week, month encoding
- [ ] Sector/industry dummies
- [ ] Volatility regimes

### Critical Warning
**Look-ahead bias:** Never use future information to compute a feature at time t.
Always shift features by at least 1 period before using as input.

```python
# WRONG - look-ahead bias
df['feature'] = df['close'].rolling(20).mean()

# CORRECT - shift by 1 to avoid look-ahead
df['feature'] = df['close'].rolling(20).mean().shift(1)
```

---

## Module 3: Validation for Financial Data (Weeks 7–8)

### Why standard cross-validation fails in finance
- Time series data is NOT i.i.d.
- Standard k-fold uses future data to predict the past → overfitting

### Walk-Forward Validation
```
Train:  [t0 ──────── t1]
Test:                   [t1 ── t2]

Train:  [t0 ──────────── t2]
Test:                       [t2 ── t3]
```

### Purging and Embargo
- Purge: remove training samples that overlap with test period
- Embargo: add a gap between train and test to avoid leakage

---

## Module 4: Time Series Analysis (Weeks 9–12)

### Topics
- [ ] Stationarity and the Augmented Dickey-Fuller test
- [ ] Autocorrelation (ACF) and Partial Autocorrelation (PACF)
- [ ] ARIMA models
- [ ] GARCH models for volatility forecasting
- [ ] Cointegration and pairs selection

---

## Phase 2 Projects

### Project 1: Return Prediction (Regression)
- Predict next-day return for 10 NSE stocks
- Features: technical indicators + lagged returns
- Models: Linear Regression, Random Forest, XGBoost
- Validation: Walk-forward with 252-day train, 21-day test windows
- Metric: IC (Information Coefficient), MSE

### Project 2: Trend Classification (Binary)
- Predict: will the stock be up or down in 5 days?
- Features: same as above
- Models: Logistic Regression, Random Forest, XGBoost
- Metric: Accuracy, Precision, Recall, AUC-ROC

### Project 3: Volatility Forecasting
- Predict next-week realized volatility
- Use GARCH as baseline
- Compare vs ML model

---

## Phase 2 Completion Checklist

- [ ] Understand overfitting and walk-forward validation
- [ ] Built and evaluated a return prediction model
- [ ] Built and evaluated a trend classification model
- [ ] Understand and can explain SHAP feature importance
- [ ] All projects committed to GitHub

## Next: [Phase 3 – Algo Trading & Deep ML](../phase3-algo-trading/README.md)
