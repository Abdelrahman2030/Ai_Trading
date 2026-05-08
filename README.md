# AI-Powered Stock Trading System for the Egyptian Stock Market (EGX)

## Overview

This project aims to build an **AI-powered stock trading system for the Egyptian Stock Exchange (EGX)** using machine learning and quantitative analysis.

The objective is to create a system capable of learning historical market behavior and generating predictions that can support trading decisions in the Egyptian stock market.

The long-term vision is to build an intelligent trading assistant that behaves similarly to a professional trader by analyzing:

- Price behavior
- Volume dynamics
- Technical indicators
- Market momentum
- Statistical patterns

Future phases may include:

- Sentiment analysis from news and social media
- Order book analysis
- Market maker behavior detection
- Reinforcement learning trading agents
- Ensemble AI systems

---

## Project Goal

The current goal of the project is to:

> Predict the **next trading day's closing price** using historical market data and engineered technical features.

This project is being developed incrementally, beginning with classical machine learning models before moving into more advanced AI architectures.

---

## Current Pipeline

The current system follows this workflow:

```text
Historical Market Data
        ↓
Feature Engineering
        ↓
Machine Learning Model
        ↓
Prediction
        ↓
Trading Decision
```

---

## Data Source

Current historical market data is collected using the `yfinance` Python library.

### Available Market Data

The dataset currently includes:

- Open price
- High price
- Low price
- Close price
- Trading volume

### Notes

- Daily historical data works reliably for EGX stocks.
- Hourly/intraday data is currently limited for Egyptian stocks using Yahoo Finance.

Example ticker format for EGX stocks:

```python
"COMI.CA"
"ORWE.CA"
"MCRO.CA"
```

---

## Dataset Structure

Each row in the dataset represents:

> **One trading day for one stock**

The model uses historical observations to predict the following trading day's closing price.

### Dataset Columns

#### Raw Market Data

| Column | Description |
|--------|-------------|
| Close | Closing stock price |
| High | Highest traded price during the session |
| Low | Lowest traded price during the session |
| Open | Opening stock price |
| Volume | Total traded shares during the session |

---

## Engineered Features

| Feature | Description |
|----------|-------------|
| return_1d | Percentage price change from the previous trading day |
| return_5d | Percentage price change over the last 5 trading days |
| return_10d | Percentage price change over the last 10 trading days |
| ma_10 | 10-day moving average representing short-term trend |
| ma_50 | 50-day moving average representing long-term trend |
| ma_ratio_10 | Ratio between close price and 10-day moving average |
| ma_ratio_50 | Ratio between close price and 50-day moving average |
| rsi | Relative Strength Index for momentum analysis |
| macd | Momentum indicator based on exponential moving averages |
| macd_signal | MACD signal line used for trend confirmation |
| macd_hist | Difference between MACD and signal line |
| volatility_10 | 10-day rolling volatility |
| volatility_20 | 20-day rolling volatility |
| volume_avg_10 | 10-day average trading volume |
| volume_ratio | Relative trading activity compared to average volume |
| target | Next trading day's closing price |
