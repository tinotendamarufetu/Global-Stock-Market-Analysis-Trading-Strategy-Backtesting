# 📈 Stock Market Analysis & Strategy Backtesting

## 📝 Project Overview
This project explores **global stock market data** from 1965–2020 to understand historical behavior, assess market risk, and evaluate trading strategies.  
The focus is on **data cleaning**, **exploratory analysis**, **market profiling**, and **strategy backtesting** with **drawdown analysis**.  

**Goal:**  
- Understand how different markets behave over time.  
- Measure and visualize volatility & risk.  
- Backtest a simple trading strategy against Buy & Hold.  
- Evaluate risk using drawdowns.  

---

## 📂 Dataset
- **File:** `stock_data.csv`
- **Shape:** 104,224 rows × 6 columns
- **Tickers:** 13 global indexes, including HSI, NYA, IXIC, GDAXI, N225, NSEI, and more.
- **Date Range:** 1965-01-05 → 2021-06-03

**Data Dictionary:**
| Column  | Description |
|---------|-------------|
| ticker  | Ticker symbol of the index |
| date    | Date of observation |
| open    | Opening price |
| high    | Highest price of the day |
| low     | Lowest price of the day |
| close   | Closing price |

---

## 🔹 Methodology

### 1. Data Cleaning
- Converted date columns to datetime format.
- Checked for missing values and negative prices.
- Ensured OHLC (open-high-low-close) consistency.
- Removed anomalies and verified date ranges.

---

### 2. Exploratory Data Analysis (EDA)
- **Summary statistics** for all tickers.
- **Outlier detection**: returns > ±10%.
- **Event analysis**: impact of major crises (2008 GFC, COVID-19 crash).
- **Correlation heatmaps** to measure relationships between markets.

📊 *Example: Crisis impact plot*
![Crisis Impact]
<img width="923" height="496" alt="image" src="https://github.com/user-attachments/assets/7552863a-609d-4223-b0d0-4b21ad608644" />

📊 *Example: Correlatioon of Stocks Daily Returns*
![Corraltion of Dily Returns](<img width="680" height="612" alt="image" src="https://github.com/user-attachments/assets/a389dc3c-8439-489c-a8ae-e68c1570cd90" />)

---

### 3. Market Profiling (Volatility & Risk)
We profiled each market to understand its **risk-return characteristics**.

**Metrics calculated:**
- **Rolling Volatility (252-day)** → how risk changes over time.
- **Rolling Sharpe Ratio** → return per unit of risk.
- **Tail Risk (VaR & CVaR)** → worst-case losses in the bottom 5% of returns.

📊 *Example: Rolling volatility chart*
![Rolling Volatility](<img width="943" height="380" alt="image" src="https://github.com/user-attachments/assets/1eef6268-490b-4e6a-ab42-a46a898e623b" />)

---

### 4. Strategy Backtesting
We tested a **Golden Cross strategy** vs **Buy & Hold**:
- **Golden Cross**: Buy when 50-day moving average > 200-day moving average, else hold cash.
- **Buy & Hold**: Stay invested at all times.

**Key findings:**
- Golden Cross reduced drawdowns during major crashes.
- Buy & Hold outperformed in strong bull markets.

📊 *Example: Backtest equity curve*
![Golden Cross Backtest](<img width="794" height="431" alt="image" src="https://github.com/user-attachments/assets/1d62ba71-6da8-4004-bf62-8a951798fbe4" />)

---

### 5. Drawdown Analysis
We analyzed portfolio drawdowns to understand risk in real terms:
- **Drawdown**: % decline from the last peak.
- **Max Drawdown**: Largest loss from a peak to a trough.
- **Recovery time**: How long it takes to get back to the peak.

**Observation:**
- Momentum-based strategies recovered faster from crashes.
- Buy & Hold had longer, deeper drawdowns.

📊 *Example: Drawdown chart*
![Drawdowns](<img width="785" height="377" alt="image" src="https://github.com/user-attachments/assets/af544d67-72d3-4450-8b8e-060431e33997" />)

---

## 📌 Key Takeaways
- **Markets are cyclical**: Volatility spikes during crises.
- **Risk management matters**: Strategies that limit drawdowns can improve long-term survivability.
- **Golden Cross is defensive**: Sacrifices some upside in exchange for smaller losses.
- **Buy & Hold wins in bull runs**: But requires strong tolerance for drawdowns.

---

## 🛠️ Tools & Libraries
- **Python**: `pandas`, `numpy`, `matplotlib`, `seaborn`
- **Backtesting**: Custom logic with rolling averages
- **Risk Analysis**: Value-at-Risk (VaR), Conditional VaR
- **Visualization**: Heatmaps, line plots, drawdown charts

---

## 📁 Repository Structure
