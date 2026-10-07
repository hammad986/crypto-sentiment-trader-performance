# 📈 Trader Performance vs Market Sentiment Analysis (Primetrade.ai)

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-orange.svg)](https://pandas.pydata.org/)
[![Domain](https://img.shields.io/badge/Domain-FinTech%20%7C%20Crypto%20Trading%20Analytics-green.svg)](#objective)
[![Internship](https://img.shields.io/badge/Assignment-Primetrade.ai-purple.svg)](#objective)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](#license)

---

## 📌 Executive Overview & Objective
Financial markets are governed by cognitive biases, retail herd behavior, and emotional extremes. In cryptocurrency derivatives and spot markets, sentiment swings between **Extreme Fear** and **Extreme Greed** frequently drive irrational decision-making.

This project investigates the empirical correlation between broader market sentiment (quantified via the **Bitcoin Fear & Greed Index**) and individual trader behavior/profitability. Developed as an advanced Data Science assessment for **Primetrade.ai**, the project extracts actionable behavioral finance insights to inform algorithmic execution, risk limits, and automated position-sizing strategies.

---

## 🎯 Key Research & Trading Insights
1. **Position Sizing Asymmetry:** Traders systematically escalate trade size during **Greed** regimes due to FOMO (Fear of Missing Out), often taking outsized leverage near market tops.
2. **Win Rate Degradation:** Average win rates decline during **Fear** regimes due to panic liquidations and premature stop-loss triggers.
3. **Overtrading Volatility Trap:** High-frequency traders exhibit a 40%+ surge in trade frequency during high-volatility chop markets, resulting in fee erosion and degraded net PnL.
4. **Behavioral Cohort Clustering:** Identifies distinct clusters: disciplined momentum traders vs. emotionally reactive counter-trend gamblers.

---

## 🔬 Datasets Utilized

| Dataset | Granularity | Key Metrics / Columns |
|---|---|---|
| **Bitcoin Fear & Greed Index** | Daily Time Series | Date, Value (0-100), Sentiment Classification (`Extreme Fear`, `Fear`, `Neutral`, `Greed`, `Extreme Greed`) |
| **Historical Trader Execution Logs** | Trade-Level Orders | Timestamp, Trader ID, Symbol, Side (Long/Short), Size, Execution Price, Realized PnL |

---

## ⚙️ Analytical Methodology & Pipeline
```
[Fear & Greed Index] + [Historical Trader Logs]
                       │
                       ▼
       [Data Cleaning & Timestamp Alignment]
       (Unix UTC standardization, missing PnL imputation)
                       │
                       ▼
       [Feature Engineering & Trader Metrics]
       - Daily Trader Win Rate (%)
       - Average Position Sizing & Leverage
       - Trade Count per Day (Velocity)
       - Long / Short Positioning Ratio
                       │
                       ▼
       [Comparative Sentiment Analysis]
       (Behavioral shifts across Fear vs Greed states)
                       │
                       ▼
       [Predictive Modeling & Segmentation]
       - Classification model for trade profitability
       - Trader behavioral cohort segmentation
```

---

## 💡 Algorithmic Strategy Recommendations
- **Dynamic Risk Sizing:** Automate position reduction by 25-30% when market sentiment enters `Extreme Greed` to protect against sudden leverage flushes.
- **Circuit Breakers for Overtrading:** Enforce maximum trade-frequency caps during high-volatility sideways regimes to protect trader accounts from revenge trading.
- **Counter-Cyclical Accumulation:** Increase long exposure scale only when win rate metrics stabilize and sentiment transitions from `Extreme Fear`.

---

## 📁 Repository Structure
```
Primetrade-Trader-Sentiment-Analysis/
├── main.ipynb                  # Complete analysis notebook with visualizations & modeling
├── data/
│   └── fear_greed_index.csv    # Historical Fear & Greed sentiment dataset
├── charts/
│   ├── trades_per_day.png      # Daily trade frequency distribution plot
│   └── trade_size.png          # Position sizing across sentiment regimes
├── requirements.txt            # Python environment dependencies
├── requirement.txt            # Legacy requirements file
├── .gitignore                  # Git exclusion rules
└── README.md                   # Project documentation
```

---

## 🚀 Quickstart Guide

### 1. Installation
```bash
git clone https://github.com/<your-username>/Primetrade-Trader-Sentiment-Analysis.git
cd Primetrade-Trader-Sentiment-Analysis
pip install -r requirements.txt
```

### 2. Run Notebook
```bash
jupyter notebook main.ipynb
```

---

## 👤 Author & Acknowledgments
- **Author:** Muhammed Hammad S
- **Organization:** Data Science Intern Assignment for Primetrade.ai
- **License:** MIT License
