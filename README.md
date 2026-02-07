

# 📊 Trader Performance vs. Market Sentiment Analysis

## 📌 Project Overview

This project analyzes the behavioral patterns of crypto-asset traders on the **Hyperliquid** exchange in relation to the **Bitcoin Fear & Greed Index**. By merging execution-level data with daily market sentiment, we identify how different trader archetypes respond to market stress and euphoria, ultimately proposing data-driven strategies for exchange optimization and risk management.

---

## 🛠️ Setup & Requirements

### 1. Prerequisites

* **Python:** 3.9+
* **Environment:** Jupyter Notebook or a standard Python environment.

### 2. Required Libraries

Install the necessary data science stack via pip:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels

```

### 3. Data Files

Ensure the following files are in the root directory:

* `historical_data.csv`: Transaction-level execution data.
* `fear_greed_index.csv`: Daily sentiment scores and classifications.

---

## ⚙️ Implementation Workflow

### Step 1: Data Engineering & Cleaning

* **Alignment:** Standardized timestamps to a `YYYY-MM-DD` grain to synchronize high-frequency trades with daily sentiment indices.
* **Outlier Management:** Utilized **Winsorization (95th percentile)** on PnL and Volume to prevent extreme "Whale" events from skewing general behavioral signals.
* **Feature Extraction:** Engineered metrics for **Win Rate**, **Trade Frequency**, and **Average Daily Exposure**.

### Step 2: Behavioral Clustering (Archetyping)

Used **K-Means Clustering** to segment the user base into three distinct personas:

1. **Whales:** High-volume, low-frequency traders with high capital efficiency.
2. **Scalpers:** High-frequency traders capturing small spreads.
3. **Retail:** Occasional traders with varying win rates and smaller sizes.

### Step 3: Statistical & Predictive Modeling

* **Granger Causality:** Tested if Sentiment (T-1) leads to PnL (T-0).
* **Predictive Modeling:** Trained a **Random Forest Classifier** to predict the next-day profitability "bucket" (Profit vs. Loss) with **~66% accuracy**.

---

## 📈 Key Results & Visualizations

### 1. The "Volatility Opportunity"

* **Finding:** Contrary to intuition, **Fear** cycles show a wider distribution of profit potential. While the "Retail" segment sees higher losses, "Scalpers" see a **15-20% boost** in PnL, likely due to increased market volatility and wider bid-ask spreads.

### 2. Archetype Mapping

* **Finding:** Traders cluster heavily by volume and frequency. Identifying these segments allows for personalized platform incentives (e.g., lower maker fees for Scalpers vs. hedging tools for Whales).

### 3. Sentiment & Profit Momentum

* **Finding:** **Win Rate Momentum** is a stronger predictor of tomorrow's success than the Sentiment Index itself. However, Sentiment acts as a **risk multiplier**, amplifying the losses of struggling traders during "Extreme Greed" due to FOMO entries.

---

## 💡 Strategy Recommendations

Based on the data, the following "Rules of Thumb" are proposed:

1. **The Scalper Incentive (Fear Phase):** During "Extreme Fear" days, the platform should implement a **dynamic fee rebate** for the Scalper segment. This ensures market liquidity remains deep when Whales typically move to the sidelines.
2. **The Retail Guardrail (Greed Phase):**
During "Extreme Greed" (Index > 80), implement automated **Risk Alerts** for the Retail segment. Data suggests these users enter "late" during hype cycles, leading to a 4% drop in average win rates. Pre-emptive alerts to reduce leverage could improve long-term user retention.

---

## 🎯 Conclusion

The analysis reveals that market sentiment is a **coincident indicator** for performance rather than a leading causal driver. However, the *interaction* between sentiment and trader archetype is highly predictive. By segmenting users into behavioral clusters, Primetrade.ai can build a more resilient ecosystem that incentivizes liquidity providers during panic and protects retail users during euphoria.

---

**Author:** [K Abhiram]


**Date:** February 2026

Would you like me to help you format the specific **"Methodology"** section for your notebook to match this README?
