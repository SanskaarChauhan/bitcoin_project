# Bitcoin Sentiment & Trader Performance Analysis

## Project Overview

This project explores the relationship between Bitcoin market sentiment (Fear & Greed Index) and trader performance on Hyperliquid. The analysis uncovers hidden patterns between market psychology and trading outcomes to deliver actionable insights for smarter trading strategies.

---

## Table of Contents

1. [Objectives](#objectives)
2. [Datasets](#datasets)
3. [Project Structure](#project-structure)
4. [Installation & Setup](#installation--setup)
5. [Workflow](#workflow)
6. [Key Findings](#key-findings)
7. [Deliverables](#deliverables)
8. [Technologies Used](#technologies-used)
9. [Future Work](#future-work)

---

## Objectives

The primary objectives of this analysis are:

1. **Explore the relationship** between market sentiment and trader performance
2. **Identify patterns** in trading behavior during different sentiment periods
3. **Uncover insights** that can drive smarter trading strategies
4. **Develop actionable recommendations** based on data-driven analysis

---

## Datasets

### 1. Bitcoin Market Sentiment Dataset
- **Source**: Fear & Greed Index
- **Records**: 2,644 daily observations
- **Date Range**: February 2018 - May 2025
- **Columns**:
  - `timestamp`: Unix timestamp
  - `value`: Sentiment score (0-100)
  - `classification`: Categorical sentiment (Extreme Fear, Fear, Neutral, Greed, Extreme Greed)
  - `date`: Date in YYYY-MM-DD format

### 2. Historical Trader Data from Hyperliquid
- **Source**: Hyperliquid trading platform
- **Records**: 211,224 trades
- **Unique Traders**: 32 accounts
- **Unique Assets**: 246 coins
- **Columns**:
  - `Account`: Trader wallet address
  - `Coin`: Trading symbol
  - `Execution Price`: Trade execution price
  - `Size Tokens`: Position size in tokens
  - `Size USD`: Position size in USD
  - `Side`: BUY or SELL
  - `Timestamp IST`: Trade timestamp
  - `Start Position`: Position before trade
  - `Direction`: Trade direction (Long/Short/Close)
  - `Closed PnL`: Profit/Loss when position closed
  - `Transaction Hash`: Blockchain transaction ID
  - `Order ID`: Unique order identifier
  - `Crossed`: Boolean for market orders
  - `Fee`: Trading fees
  - `Trade ID`: Unique trade identifier
  - `Timestamp`: Unix timestamp

---

## Project Structure

```
project/
│
├── data/
│   ├── fear_greed_index.csv                 # Original sentiment data
│   ├── historical_data.csv                  # Original trading data
│   ├── cleaned_sentiment.csv                # Processed sentiment data
│   ├── cleaned_merged_trades.csv            # Merged trading + sentiment data
│   ├── daily_trader_stats.csv               # Daily aggregated metrics
│   ├── trader_performance_summary.csv       # Trader-level statistics
│   ├── powerbi_sentiment.csv                # Power BI export
│   ├── powerbi_trades.csv                   # Power BI export
│   ├── powerbi_daily_stats.csv              # Power BI export
│   └── powerbi_trader_stats.csv             # Power BI export
│
├── notebooks/
│   ├── 01_data_loading_and_cleaning.ipynb   # Data preparation
│   ├── 02_exploratory_data_analysis.ipynb   # EDA and visualizations
│   ├── 03_sentiment_performance_analysis.ipynb # Sentiment analysis
│   ├── 04_insights_and_strategy.ipynb       # Final insights
│   └── 05_powerbi_export.ipynb              # Power BI data export
│
├── visualizations/
│   ├── sentiment_timeseries.png
│   ├── trading_timeseries.png
│   ├── distributions.png
│   ├── correlation_matrix.png
│   ├── trader_performance.png
│   ├── temporal_patterns.png
│   ├── performance_by_sentiment.png
│   ├── performance_by_sentiment_range.png
│   ├── position_direction_sentiment.png
│   └── executive_dashboard.png
│
├── reports/
│   └── final_report.txt                     # Text summary of findings
│
├── powerbi/
│   └── Trading_Performance_Dashboard.pbix   # Interactive dashboard
│
└── README.md                                # This file
```

---

## Installation & Setup

### Prerequisites

- Python 3.8 or higher
- Jupyter Notebook
- Power BI Desktop (for dashboard)

### Required Python Libraries

```bash
pip install pandas numpy matplotlib seaborn scipy
```

### Setup Steps

1. Clone or download this repository
2. Place the datasets in the `data/` folder
3. Open Jupyter Notebook
4. Run notebooks in order (01 → 02 → 03 → 04 → 05)

---

## Workflow

### Phase 1: Data Preparation (Notebook 01)

**Input**: Raw CSV files
**Output**: Cleaned datasets

**Steps**:
1. Load sentiment and trading data
2. Clean and standardize column names
3. Convert dates to datetime format
4. Create derived features:
   - Time-based features (year, month, hour, day of week)
   - Sentiment encoding (numeric and binary)
   - Trade metrics (profitability, returns, size categories)
5. Merge sentiment with trading data by date
6. Create aggregated datasets:
   - Daily trader statistics
   - Trader performance summaries
7. Export cleaned data

### Phase 2: Exploratory Data Analysis (Notebook 02)

**Input**: Cleaned datasets
**Output**: Visualizations and statistical summaries

**Analysis**:
1. **Basic Statistics**: Overall metrics and distributions
2. **Time Series Analysis**: Trends over time
3. **Distribution Analysis**: PnL, trade sizes, returns
4. **Correlation Analysis**: Relationships between variables
5. **Trader Performance**: Top/bottom performers
6. **Temporal Patterns**: Trading by hour and day of week

**Visualizations**:
- Sentiment trends over time
- Trading volume and PnL trends
- Distribution histograms
- Correlation heatmap
- Trader performance charts
- Temporal activity patterns

### Phase 3: Sentiment-Performance Analysis (Notebook 03)

**Input**: Merged dataset with sentiment
**Output**: Sentiment-specific insights

**Analysis**:
1. Performance metrics by sentiment category
2. Fear vs Greed comparison
3. Performance by sentiment value ranges
4. Trader behavior patterns by sentiment
5. Trade timing analysis
6. Position direction (Long/Short) by sentiment

**Key Metrics**:
- Average PnL per sentiment
- Win rate per sentiment
- Trading volume per sentiment
- Best hours to trade during different sentiments
- Long vs Short performance

### Phase 4: Insights & Strategy (Notebook 04)

**Input**: All analysis results
**Output**: Actionable recommendations

**Deliverables**:
1. **10 Key Findings**: Data-driven discoveries
2. **5 Trading Strategies**: Actionable recommendations
3. **Risk Assessment**: Comprehensive risk metrics
4. **Executive Dashboard**: Visual summary
5. **Final Report**: Text document with all findings

### Phase 5: Power BI Export (Notebook 05)

**Input**: Cleaned datasets
**Output**: Power BI-ready CSV files

**Purpose**: Prepare data for interactive dashboard creation

---

## Key Findings

### Top 10 Insights

1. **Market Sentiment Distribution**: Fear is the most common sentiment (29.5% of days)
2. **Overall Performance**: 211K+ trades executed with 83.20% win rate and $10.30M total PnL
3. **Best Sentiment**: [Varies by data] - certain sentiment periods show higher profitability
4. **Fear vs Greed**: Analysis reveals which market psychology yields better returns
5. **Top Performers**: Small number of traders drive majority of profits
6. **Position Direction**: Long or short positions perform differently by sentiment
7. **Most Traded Assets**: Top 3 coins account for significant trading volume
8. **Trading Volume Patterns**: Volume distribution across sentiment periods
9. **Optimal Timing**: Specific hours show consistently better performance
10. **Behavioral Patterns**: Traders adjust strategies based on market sentiment

---

## Deliverables

### 1. Jupyter Notebooks (5 files)
Complete analysis pipeline with code, visualizations, and explanations

### 2. Cleaned Datasets (8 CSV files)
Ready-to-use data for further analysis or modeling

### 3. Visualizations (10+ PNG files)
Publication-ready charts and graphs

### 4. Final Report (TXT file)
Comprehensive summary of findings, strategies, and risk metrics

### 5. Power BI Dashboard
Interactive dashboard with 5 pages:
- **Page 1**: Trading Performance Overview
- **Page 2**: Sentiment Analysis
- **Page 3**: Trader Performance
- **Page 4**: Trading Patterns
- **Page 5**: Position Analysis

---

## Technologies Used

### Data Analysis
- **Python 3.8+**: Primary programming language
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computations
- **SciPy**: Statistical testing

### Visualization
- **Matplotlib**: Static visualizations
- **Seaborn**: Statistical graphics
- **Power BI Desktop**: Interactive dashboards

### Development Environment
- **Jupyter Notebook**: Interactive development
- **Git**: Version control (optional)

---

## Power BI Dashboard

### Setup Instructions

1. Open Power BI Desktop
2. Import the 4 Power BI CSV files from `data/` folder
3. Create relationships:
   - `powerbi_sentiment[date]` → `powerbi_trades[trade_date]`
   - `powerbi_sentiment[date]` → `powerbi_daily_stats[date]`
   - `powerbi_daily_stats[Account]` → `powerbi_trader_stats[Account]`

### DAX Measures

```dax
Total PnL = SUM(powerbi_trades[Closed_PnL])

Win Rate = 
DIVIDE(
    COUNTROWS(FILTER(powerbi_trades, powerbi_trades[is_profitable] = TRUE)),
    COUNTROWS(FILTER(powerbi_trades, powerbi_trades[is_closed] = TRUE))
) * 100

Cumulative PnL = 
CALCULATE(
    SUM(powerbi_trades[Closed_PnL]),
    FILTER(
        ALL(powerbi_trades[trade_date]),
        powerbi_trades[trade_date] <= MAX(powerbi_trades[trade_date])
    )
)

Profit Factor = 
DIVIDE(
    SUMX(FILTER(powerbi_trades, powerbi_trades[Closed_PnL] > 0), powerbi_trades[Closed_PnL]),
    ABS(SUMX(FILTER(powerbi_trades, powerbi_trades[Closed_PnL] < 0), powerbi_trades[Closed_PnL]))
)
```

### Dashboard Pages

**Page 1: Overview**
- Total PnL, Unique Traders, Win Rate, Trading Volume
- Cumulative PnL line chart
- Market sentiment distribution pie chart

**Page 2: Sentiment Analysis**
- Average PnL by sentiment (bar chart)
- Win rate by sentiment (bar chart)
- Fear & Greed Index timeline
- Performance metrics table

**Page 3: Trader Performance**
- Top 10 traders table
- PnL distribution
- Volume vs PnL scatter plot
- Account filter slicer

**Page 4: Trading Patterns**
- Hourly trading activity
- Day of week activity
- Volume trends
- Time-based filters

**Page 5: Position Analysis**
- Long vs Short performance by sentiment
- Direction-specific win rates
- Position type comparisons

---

## Key Recommendations

### Trading Strategies

1. **Sentiment-Based Entry**: Adjust position sizing based on Fear & Greed Index
2. **Position Direction Strategy**: Optimize Long/Short decisions by sentiment
3. **Optimal Time Windows**: Focus trading during high-performance hours
4. **Volatility-Adjusted Sizing**: Scale positions based on sentiment volatility
5. **High Probability Trading**: Increase frequency during favorable sentiment periods

### Risk Management

- Monitor win rate across different sentiment periods
- Set position size limits based on sentiment volatility
- Track profit factor and risk-reward ratios
- Diversify across multiple sentiment conditions
- Use stop-losses adjusted for market psychology

---

## Future Work

### Potential Enhancements

1. **Machine Learning Models**:
   - Predict profitable trades based on sentiment
   - Classification models for win/loss prediction
   - Time series forecasting for PnL

2. **Advanced Analysis**:
   - Sentiment lag analysis (how past sentiment affects current trades)
   - Coin-specific sentiment relationships
   - Trader clustering and segmentation
   - Market regime detection

3. **Real-Time Integration**:
   - Live sentiment feed integration
   - Automated trade alerts based on sentiment
   - Real-time dashboard updates

4. **Expanded Data**:
   - Include more traders and longer history
   - Add market indicators (BTC price, volume, volatility)
   - Social media sentiment integration

5. **Portfolio Optimization**:
   - Multi-trader portfolio construction
   - Risk-adjusted return maximization
   - Sentiment-based rebalancing strategies

---

## Contributors

- **Project Author**: [Sanskaar Chauhan]
- **Dataset Sources**: 
  - Fear & Greed Index
  - Hyperliquid Trading Platform

---

## License

This project is for educational and analytical purposes.

---

## Contact

For questions or collaboration opportunities, please reach out via [sanskaar.17chauhan@gmail.com].

---

## Acknowledgments

- Fear & Greed Index data providers
- Hyperliquid platform for trading data
- Python data science community
- Power BI community resources

---

**Last Updated**: November 2025
