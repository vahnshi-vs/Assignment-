# Bitcoin Sentiment vs Trader Performance Analysis
### Hyperliquid × Fear & Greed Index — Exploratory Data Analysis

---

## Project Overview

This project investigates whether Bitcoin market sentiment (Fear & Greed Index)
has a measurable impact on trader performance using historical trade data from
Hyperliquid, a decentralized perpetuals exchange.

The analysis uncovers hidden patterns between market psychology and actual
trading outcomes — including contrarian vs momentum behavior, lag effects,
and coin-level sentiment sensitivity.

---

## Datasets Used

| Dataset | Source | Key Columns |
|---|---|---|
| Hyperliquid Historical Trades | Primetrade.ai | account, coin, execution_price, size_usd, side, closed_pnl, timestamp |
| Bitcoin Fear & Greed Index | Alternative.me | date, classification (Extreme Fear → Extreme Greed) |

---

## Key Questions Answered

1. Do traders perform better during Fear or Greed markets?
2. Does sentiment today predict performance tomorrow? (Lag Effect)
3. Who wins more — contrarian traders or momentum traders?
4. Which coins are most sensitive to market sentiment shifts?
5. Is there a statistically significant difference in PnL across sentiment regimes?

---

## Methodology
Raw Trade Data + Fear & Greed Index
↓
Data Cleaning & Type Normalization
↓
Date-level Merge on Sentiment
↓
Exploratory Analysis (6 chart groups)
↓
Behavioral Segmentation (Contrarian vs Momentum)
↓
Lag Effect Analysis (T+1 day)
↓
Statistical Validation (Independent T-test)
↓
Insights & Recommendations

---

## Analysis Modules

### 1. Sentiment Distribution
- Breakdown of market days by sentiment class
- Sentiment timeline visualization

### 2. PnL vs Sentiment
- Total PnL, average PnL per trade, and win rate grouped by sentiment
- Identifies which emotional regime produces the best outcomes

### 3. Long vs Short Breakdown
- How buy/sell behavior changes across sentiment regimes
- Which direction is more profitable under each sentiment class

### 4. Contrarian vs Momentum Behavior
- **Contrarian** — Buying during Fear, Selling during Greed
- **Momentum** — Buying during Greed, Selling during Fear
- Compared on avg PnL and win rate

### 5. Lag Effect (Sentiment → Next Day Performance)
- Tests whether today's Fear/Greed classification predicts tomorrow's trader PnL
- Cumulative PnL chart colored by daily sentiment

### 6. Coin × Sentiment Heatmap
- Top 8 coins compared across all sentiment classes
- Identifies which assets are most sentiment-reactive

---

## Key Findings

> ⚠️ Replace these placeholders with your actual output values after running the notebook.

- 📈 **Best avg PnL sentiment:
  ============================================================
STATISTICAL TEST — Fear vs Greed
============================================================
Fear  | Mean: $110.1343  | N: 16,195
Greed | Mean: $104.4478  | N: 16,913
T-stat: 0.3644  |  P-value: 0.715587
Result: ❌ Not significant at p<0.05

============================================================
KEY FINDINGS
============================================================
📈 Best avg PnL sentiment:     Extreme Greed
📉 Worst avg PnL sentiment:    Extreme Fear
🎯 Highest win-rate sentiment: Extreme Greed

🔄 Contrarian avg PnL: $129.9952
📊 Momentum avg PnL:   $32.3619
👉 CONTRARIAN strategy outperforms on this dataset

✅ ALL CHARTS SAVED IN /content/
    01_sentiment_overview.png
    02_pnl_by_sentiment.png
    03_long_short_by_sentiment.png
    04_contrarian_momentum.png
    05_lag_effect.png
    06_coin_analysis.png
- 📉 **Worst avg PnL sentiment:
  ============================================================
STATISTICAL TEST — Fear vs Greed
============================================================
Fear  | Mean: $110.1343  | N: 16,195
Greed | Mean: $104.4478  | N: 16,913
T-stat: 0.3644  |  P-value: 0.715587
Result: ❌ Not significant at p<0.05

============================================================
KEY FINDINGS
============================================================
📈 Best avg PnL sentiment:     Extreme Greed
📉 Worst avg PnL sentiment:    Extreme Fear
🎯 Highest win-rate sentiment: Extreme Greed

🔄 Contrarian avg PnL: $129.9952
📊 Momentum avg PnL:   $32.3619
👉 CONTRARIAN strategy outperforms on this dataset

✅ ALL CHARTS SAVED IN /content/
    01_sentiment_overview.png
    02_pnl_by_sentiment.png
    03_long_short_by_sentiment.png
    04_contrarian_momentum.png
    05_lag_effect.png
    06_coin_analysis.png
- 🎯 **Highest win-rate sentiment:
  ============================================================
STATISTICAL TEST — Fear vs Greed
============================================================
Fear  | Mean: $110.1343  | N: 16,195
Greed | Mean: $104.4478  | N: 16,913
T-stat: 0.3644  |  P-value: 0.715587
Result: ❌ Not significant at p<0.05

============================================================
KEY FINDINGS
============================================================
📈 Best avg PnL sentiment:     Extreme Greed
📉 Worst avg PnL sentiment:    Extreme Fear
🎯 Highest win-rate sentiment: Extreme Greed

🔄 Contrarian avg PnL: $129.9952
📊 Momentum avg PnL:   $32.3619
👉 CONTRARIAN strategy outperforms on this dataset

✅ ALL CHARTS SAVED IN /content/
    01_sentiment_overview.png
    02_pnl_by_sentiment.png
    03_long_short_by_sentiment.png
    04_contrarian_momentum.png
    05_lag_effect.png
    06_coin_analysis.png
- 🔄 **Contrarian vs Momentum winner:
============================================================
STATISTICAL TEST — Fear vs Greed
============================================================
Fear  | Mean: $110.1343  | N: 16,195
Greed | Mean: $104.4478  | N: 16,913
T-stat: 0.3644  |  P-value: 0.715587
Result: ❌ Not significant at p<0.05

============================================================
KEY FINDINGS
============================================================
📈 Best avg PnL sentiment:     Extreme Greed
📉 Worst avg PnL sentiment:    Extreme Fear
🎯 Highest win-rate sentiment: Extreme Greed

🔄 Contrarian avg PnL: $129.9952
📊 Momentum avg PnL:   $32.3619
👉 CONTRARIAN strategy outperforms on this dataset

✅ ALL CHARTS SAVED IN /content/
    01_sentiment_overview.png
    02_pnl_by_sentiment.png
    03_long_short_by_sentiment.png
    04_contrarian_momentum.png
    05_lag_effect.png
    06_coin_analysis.png

---

## Limitations

- `closed_pnl` only captures **realized** gains/losses. Open positions with
  unrealized losses are excluded, which may overstate performance.
- Fear & Greed Index is a **daily** metric merged onto intraday trades —
  intra-day sentiment shifts are not captured.
- Hyperliquid data may contain wash trades or bot activity that inflates
  trade counts without reflecting genuine human sentiment response.
- Sample period and date overlap between datasets affects the robustness
  of lag effect conclusions.

---

## How to Run

### Option 1 — Google Colab (Recommended)
1. Open [Google Colab](https://colab.research.google.com)
2. Upload `analysis.ipynb` or paste the script directly
3. Run cells sequentially — Steps 1 through 13
4. Charts auto-save to `/content/`

### Option 2 — Local
```bash
git clone https://github.com/YOUR_USERNAME/bitcoin-sentiment-trader-analysis
cd bitcoin-sentiment-trader-analysis
pip install -r requirements.txt
jupyter notebook analysis.ipynb
```

---

## Requirements
pandas
numpy
matplotlib
seaborn
scipy
gdown
jupyter

Install all at once:
```bash
pip install -r requirements.txt
```

---

## Output Charts

| File | Description |
|---|---|
| `01_sentiment_overview.png` | Sentiment distribution pie + timeline |
| `02_pnl_by_sentiment.png` | Total PnL, Avg PnL, Win Rate by sentiment |
| `03_long_short_by_sentiment.png` | Long vs Short breakdown by sentiment |
| `04_contrarian_momentum.png` | Contrarian vs Momentum strategy comparison |
| `05_lag_effect.png` | Next-day PnL by today's sentiment + cumulative PnL |
| `06_coin_analysis.png` | Top coins by PnL + Coin × Sentiment heatmap |

---

## Project Structure
bitcoin-sentiment-trader-analysis/
│
├── analysis.ipynb            # Main Jupyter notebook (all 13 steps)
├── analysis.py               # Same code as plain Python script
├── requirements.txt          # Dependencies
├── README.md                 # This file
│
├── data/
│   ├── trades.csv            # Hyperliquid historical trade data
│   └── fear_greed.csv        # Bitcoin Fear & Greed Index
│
└── charts/
├── 01_sentiment_overview.png
├── 02_pnl_by_sentiment.png
├── 03_long_short_by_sentiment.png
├── 04_contrarian_momentum.png
├── 05_lag_effect.png
└── 06_coin_analysis.png

---

## Tools & Libraries

| Tool | Purpose |
|---|---|
| Python 3.x | Core language |
| Pandas | Data wrangling and merging |
| NumPy | Numerical operations |
| Matplotlib | Base visualizations |
| Seaborn | Heatmaps and styled charts |
| SciPy | Statistical testing (T-test) |
| gdown | Google Drive dataset download |

---

## Author

**Vanshika**
MBA — Data Science & Finance | Manipal University Jaipur
Data Analyst | Early Career

📧 vahnshi@gmail.com
🔗 www.linkedin.com/in/vahnshi

---

## Context

Built as part of the **Primetrade.ai Data Science Internship Assessment**.
Objective: Explore the relationship between Bitcoin market sentiment and
trader performance on Hyperliquid to surface actionable trading strategy insights.

---

*Analysis conducted entirely in Python. All charts generated programmatically and reproducible.*
