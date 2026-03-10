# Phase 1 – Foundations

**Duration:** Months 1–6 (March 2026 – September 2026)

Build the mathematical and programming foundation required for everything that follows.

## Goals

- Be comfortable with linear algebra, probability, and calculus at a college level
- Write clean Python code for data analysis using NumPy, Pandas, and Matplotlib
- Understand basic financial instruments and market mechanics
- Have a public GitHub repo with clean notebooks

---

## Module 1: Linear Algebra (Weeks 1–4)

### Why it matters for Quant ML
Covariance matrices, PCA, portfolio optimization, neural network weights — all linear algebra.

### Topics
- [ ] Vectors and vector spaces
- [ ] Matrix operations (multiplication, transpose, inverse)
- [ ] Eigenvalues and eigenvectors
- [ ] Singular Value Decomposition (SVD)
- [ ] Principal Component Analysis (PCA)

### Resources
- 3Blue1Brown Essence of Linear Algebra (visual intuition first)
- Gilbert Strang MIT 18.06 (rigorous treatment)

### Practice
- Implement matrix operations from scratch in NumPy
- Implement PCA from scratch and apply to stock returns data

---

## Module 2: Probability & Statistics (Weeks 5–8)

### Why it matters for Quant ML
Everything in finance is probabilistic. Returns are random variables. Risk is variance.

### Topics
- [ ] Random variables, distributions (normal, lognormal, t-distribution)
- [ ] Expectation, variance, covariance, correlation
- [ ] Bayes theorem
- [ ] Law of Large Numbers, Central Limit Theorem
- [ ] Hypothesis testing, p-values, confidence intervals
- [ ] Maximum Likelihood Estimation

### Resources
- Harvard STAT 110 (YouTube playlist)
- Introduction to Probability – Blitzstein & Hwang

### Finance Application
- Model daily stock returns as a normal distribution
- Test if returns are actually normally distributed (spoiler: they're not)
- Calculate Value at Risk (VaR) using historical simulation

---

## Module 3: Python for Data Analysis (Weeks 1–8, parallel)

### Topics
- [ ] Python basics: data types, control flow, functions, classes
- [ ] NumPy: arrays, indexing, broadcasting, linear algebra
- [ ] Pandas: Series, DataFrame, indexing, groupby, merge, resample
- [ ] Matplotlib / Seaborn: line charts, histograms, heatmaps
- [ ] yfinance: download OHLCV data
- [ ] Git & GitHub: commit, push, branch, PR

### Mini Projects
1. Download 5 years of NIFTY data, calculate daily returns, plot distribution
2. Build a correlation matrix heatmap for top 10 NSE stocks
3. Compute rolling 30-day volatility and plot it

---

## Module 4: Finance Basics (Weeks 9–12)

### Topics
- [ ] Asset classes: equities, fixed income, derivatives, commodities
- [ ] How stock exchanges work (NSE/BSE, order book, bid-ask spread)
- [ ] Return metrics: simple vs log returns, annualization
- [ ] Risk metrics: volatility, Sharpe Ratio, Value at Risk (VaR)
- [ ] Time value of money
- [ ] Introduction to options: calls, puts, moneyness

### Resources
- *A Random Walk Down Wall Street* – Burton Malkiel
- Investopedia (as a reference)

---

## Phase 1 Projects

### Project 1: EDA on Indian Stock Market
- Download 3 years of data for top 20 NSE stocks using yfinance
- Calculate: daily returns, annualized volatility, Sharpe Ratio (assume 6% risk-free rate)
- Build: correlation heatmap, rolling volatility chart
- Find: which stock had the best risk-adjusted return?

### Project 2: Math Cheat Sheet
- One-page summary of linear algebra, probability, and calculus concepts used in ML
- Format: Markdown or PDF
- Add to this repository

---

## Phase 1 Completion Checklist

- [ ] Finished 3Blue1Brown LA + Strang Lectures 1–10
- [ ] Finished Harvard STAT 110 (first 20 lectures)
- [ ] Comfortable with NumPy, Pandas, Matplotlib
- [ ] Completed Project 1 (EDA on NSE stocks)
- [ ] All work committed to GitHub with clean notebooks

## Next: [Phase 2 – ML for Finance](../phase2-ml-for-finance/README.md)
