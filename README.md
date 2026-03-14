# Trader Performance vs Market Sentiment
## Primetrade.ai — Data Science Intern Assignment

## Overview
Analysis of how Bitcoin market sentiment (Fear/Greed) relates to 
trader behavior and performance on Hyperliquid.

---

## Datasets
- **Sentiment Data:** 2644 rows, 4 columns — daily Fear/Greed index
- **Trader Data:** 211224 rows, 16 columns — Hyperliquid trade history
- **Overlapping period:** May 2023 to May 2025

---

## Setup
```bash
pip install pandas matplotlib scikit-learn
```
Open `notebook.ipynb` in Jupyter or Google Colab and run all cells.

---

## Methodology
1. Loaded and cleaned both datasets
2. Converted timestamps and aligned by date
3. Simplified sentiment into 3 categories: Fear, Greed, Neutral
4. Computed daily metrics: PnL, win rate, trade count, trade size, long/short ratio
5. Merged datasets and analyzed performance by sentiment
6. Segmented traders into consistent winners, inconsistent, and consistent losers
7. Built a Random Forest model to predict next-day profitability

---

## Key Insights
1. **Fear days outperform:** Fear days outperform Greed days in avg PnL ($5,185 vs $4,144), despite lower win rates (60% vs 64%). Traders make fewer but bigger winning trades during fearful markets.
2. **Segment divergence:** Consistent winners generate 2x more PnL on Fear days ($6,400) compared to Greed days ($2,900). Inconsistent traders show the opposite pattern, performing better on Greed/Neutral days.
3. **Profit taking on Greed:** Traders sell more than they buy on Greed days (53% SELL vs 47% BUY),
suggesting experienced traders use bullish sentiment to take profits rather than open new positions.

---

## Strategy Recommendations
1. **Consistent Winners:** During Fear days, consistent winner traders should increase trade 
frequency and position sizes. Data shows they generate 2x higher 
PnL during Fear markets, suggesting they successfully exploit 
high volatility periods.
2. **Inconsistent Traders:** During Fear days, inconsistent traders should reduce position sizes 
or avoid trading. Their PnL drops significantly during Fear markets 
($3,900 vs $6,400 for consistent winners). They should focus 
activity on Greed/Neutral days where they perform relatively better.

---

## Predictive Model
- **Model:** Random Forest Classifier
- **Accuracy:** 61%
- **Top Feature:** Average trade size
- **Insight:** [fill what trade size being top feature means]

---

## Files
- `analysis.ipynb` — full analysis
- `README.md` 
- `/data` — csv files
- `/charts` — outputs and visualizations
