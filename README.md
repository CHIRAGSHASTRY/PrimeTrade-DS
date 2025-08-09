# Trader Performance vs Market Sentiment

## Project Overview
This project analyzes the relationship between Bitcoin market sentiment (Fear & Greed Index) and trader performance (Hyperliquid historical trades).  
The aim is to identify patterns, correlations, and seasonal trends, and to provide insights that can enhance trading strategies.

## Objectives
1. Examine whether market sentiment (fear or greed) correlates with trader profitability.
2. Identify the top-performing trader accounts and analyze their trading characteristics.
3. Detect seasonal patterns in market sentiment.
4. (Optional) Build a simple predictive model to forecast profitable days using sentiment and trading metrics.

## Data Sources

### Historical Trader Data (Hyperliquid)
- Fields used:
  - `Account` — unique trader identifier
  - `Execution Price` — trade execution price
  - `Size USD` — trade size in USD
  - `Start Position` — leverage/position size
  - `Closed PnL` — profit or loss per trade
  - `Timestamp IST` — trade time
- Coverage: May 2025 – December 2025

### Fear & Greed Index
- Fields used:
  - `date` — daily sentiment date
  - `classification` — market mood (Fear, Greed, Neutral, Extreme Fear, Extreme Greed)
- Sentiment mapping to numeric score:
  - Fear = 0.0  
  - Neutral = 0.5  
  - Greed = 1.0

## Analysis Steps
1. **Data Loading**  
   Imported datasets into Pandas DataFrames.

2. **Data Cleaning**  
   - Converted timestamps to datetime format.
   - Extracted `date` for daily aggregation.
   - Mapped sentiment classifications to numerical scores.

3. **Data Merging**  
   - Aggregated trades per day (`trades_count`, `total_volume`, `avg_leverage`, `net_pnl`).
   - Merged with daily sentiment scores.
   - Forward-filled missing sentiment values.

4. **Exploratory Data Analysis (EDA)**  
   - Correlation between sentiment and net PnL.
   - Scatter and time-series visualizations.
   - Top account performance analysis.
   - Seasonal sentiment trends.

5. **Key Findings**  
   - Pearson correlation coefficient: `X.XXX` (replace with computed value).
   - Patterns in sentiment align with PnL fluctuations.
   - Top traders maintain moderate leverage and consistent win rates.
   - Seasonal sentiment peaks mid-year, dips toward year-end.

**6. Optional Prediction Model
   - RandomForestClassifier to predict profitable days based on sentiment and trading metrics.

## Generated Plots (outputs/)
1. Sentiment vs PnL Scatter
2. Sentiment and PnL Over Time
3. Top Accounts Bar Chart

## Final Report
The `ds_report.pdf` contains:
- Data sources
- Cleaning and processing steps
- Key findings with supporting plots
- Insights and recommendations

## How to Run

### Google Colab
1. Open the main analysis notebook: PrimeTrade.ipynb
2. Upload `historical_data.csv` and `fear_greed_index.csv` to the `csv_files` directory in Colab.
3. Run all cells from top to bottom.
Install required packages:
pandas
numpy
matplotlib
scikit-learn

google drive link for the csv files:
https://drive.google.com/drive/folders/1DpS0iduO4IXg8vRNmLnxHoGQJQwUpXzC?usp=sharing

