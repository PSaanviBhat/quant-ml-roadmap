# Phase 3 – Algorithmic Trading & Deep ML

**Duration:** Months 13–18 (April 2027 – September 2027)

Build real trading systems, implement advanced deep learning models, and explore reinforcement learning for portfolio management.

## Goals

- Build and backtest a complete algorithmic trading strategy
- Implement a Sharpe-ratio-optimized portfolio
- Build LSTM/Transformer models for time series forecasting
- Build a basic RL agent for portfolio allocation
- Write and publish a technical blog post

---

## Module 1: Backtesting Framework (Weeks 1–4)

### What is Backtesting?
Simulating a trading strategy on historical data to estimate its performance before risking real capital.

### Topics
- [ ] Event-driven vs vectorized backtesting
- [ ] OHLCV data handling and resampling
- [ ] Signal generation: entry and exit rules
- [ ] Position sizing and capital allocation
- [ ] Transaction costs: commissions, slippage, market impact
- [ ] Performance metrics: Total Return, Annualized Return, Volatility, Sharpe Ratio, Max Drawdown, Calmar Ratio, Win Rate

### Libraries
| Library | Style | Best For |
|---------|-------|----------|
| backtrader | Event-driven | Beginners, full-featured |
| zipline-reloaded | Event-driven | Institutional-grade |
| vectorbt | Vectorized | Fast research, iteration |

---

## Module 2: Trading Strategies (Weeks 5–8)

### Strategy 1: Momentum
- Buy stocks that have performed well over the past N days
- Sell (or short) stocks that have performed poorly

### Strategy 2: Mean Reversion
- Buy when price drops significantly below rolling average
- Sell when price rises significantly above

### Strategy 3: Pairs Trading
- Find two cointegrated stocks
- Trade the spread when it deviates from mean

### Strategy 4: ML-Driven Signal
- Use Phase 2 prediction model to generate buy/sell signals
- Combine with proper position sizing

**Resource:** *Algorithmic Trading* – Ernest Chan (Chapters 1–7)

---

## Module 3: Portfolio Optimization (Weeks 9–12)

### Topics
- [ ] Modern Portfolio Theory (Markowitz)
- [ ] Mean-Variance Optimization
- [ ] Efficient Frontier
- [ ] Risk Parity
- [ ] Maximum Sharpe Ratio portfolio

```python
from pypfopt import EfficientFrontier, risk_models, expected_returns

mu = expected_returns.mean_historical_return(prices)
S = risk_models.sample_cov(prices)

ef = EfficientFrontier(mu, S)
weights = ef.max_sharpe()
ef.portfolio_performance(verbose=True)
```

---

## Module 4: Deep Learning (Weeks 1–6, parallel)

### Topics
- [ ] Neural networks from scratch
- [ ] RNNs and LSTMs
- [ ] Transformer architecture and attention
- [ ] Training tricks: dropout, batch norm, learning rate schedules
- [ ] Avoiding overfitting on small financial datasets

**Resources:** fast.ai Part 1 + *Deep Learning with Python* – Chollet

---

## Module 5: LSTMs for Time Series (Weeks 9–12)

### Topics
- [ ] Sequence modeling fundamentals
- [ ] Preparing time series data for LSTMs
- [ ] Walk-forward validation for deep learning models
- [ ] Multi-step-ahead forecasting
- [ ] Temporal Fusion Transformer

> **Key insight:** LSTMs are often NOT better than gradient boosting for tabular financial data. Always compare both.

---

## Module 6: Reinforcement Learning (Weeks 13–18)

### Topics
- [ ] MDP: States, Actions, Rewards, Policy
- [ ] Q-Learning and Deep Q-Networks (DQN)
- [ ] Policy Gradient methods (PPO, A2C)
- [ ] Portfolio allocation as RL environment
- [ ] OpenAI Gymnasium for custom environments

```python
class PortfolioEnv:
    def __init__(self, prices):
        self.prices = prices
        self.current_step = 0

    def reset(self):
        self.current_step = 0
        return self._get_observation()

    def step(self, action):
        returns = self._get_returns()
        reward = sum(a * r for a, r in zip(action, returns))
        self.current_step += 1
        done = self.current_step >= len(self.prices) - 1
        return self._get_observation(), reward, done, {}
```

---

## Phase 3 Projects

### Project 1: Momentum Backtesting Framework
- Universe: Top 50 NSE stocks
- Signal: Buy top 10 performers over past 20 days, rebalance weekly
- Include transaction costs
- Report: Sharpe, max drawdown, annual return vs NIFTY benchmark

### Project 2: LSTM Price Forecasting
- 5 years of daily OHLCV data
- Features: OHLCV + technical indicators
- Target: Next 5-day return
- Walk-forward validation
- Compare vs linear regression + XGBoost baseline

### Project 3: RL Portfolio Agent
- Custom Gym environment with 5 stocks
- Train PPO agent using Stable Baselines 3
- Evaluate against equal-weight benchmark

### Project 4: Technical Blog Post
- 500–1000 words on one of your projects
- Include: problem statement, methodology, results, limitations
- Publish on GitHub Pages or Medium

---

## Phase 3 Completion Checklist

- [ ] Built and backtested a complete trading strategy
- [ ] Understand Sharpe Ratio, max drawdown, walk-forward validation
- [ ] Built an LSTM forecasting model with proper validation
- [ ] Trained a basic RL agent for portfolio allocation
- [ ] Published a technical blog post
- [ ] All projects on GitHub with clean notebooks

## Next: [Phase 4 – Specialization](../phase4-specialization/README.md)
