# 🚀 Algo-Trading System (NSE, Nifty50)  
**ML Automation | Backtesting | No TA-Lib | Google Sheets/Telegram Ready**

A robust, pandas-native algorithmic trading framework for Indian stocks (NSE Nifty50):

- 📈 **Quantitative technical analysis:** All major indicators, no TA-Lib!  
- 🤖 **ML-powered price prediction:** Decision Tree & Logistic Regression  
- 🔗 **Backtest any rule-based strategy**  
- 📢 **Smart alerts via Google Sheets and Telegram (optional)**  
- 📝 **Elegant summaries, logs, trade logs ready for reporting**

##✅ **Algo-Trading System Overview** 
**1)📥 Data Ingestion**
-Fetches stock data (e.g., RELIANCE.NS) from Yahoo Finance
-Adds technical indicators like RSI, MACD, SMA, EMA, Bollinger Bands
**2)📊 Strategy Logic**
-Buy: RSI < 30 and MA_20 > MA_50
-Sell: RSI > 70 or MA_20 < MA_50
-Generates signals and calculates profit/loss using backtesting

**3)🤖 Machine Learning**
-Uses indicators to predict if price will go up/down tomorrow
-Trains Decision Tree / Logistic Regression
-Outputs accuracy and prediction with confidence

**4)📈 Output Summary**
-Total trades, win ratio, returns, model accuracy, current signals
-Can be printed in console or exported to JSON / Google Sheets format

**5)🔔 Alert System**
-Plays a beep sound if:
-Accuracy < 50%, win rate = 0%, negative return, or oversold SELL

**6)🎯 Execution (quick_demo)**
-Runs the full pipeline for a few NIFTY 50 stocks
-Saves results, shows performance, and triggers alerts

---

## 🎯 Features

- **Zero TA-Lib Dependency:** All indicators (RSI, SMA, EMA, MACD, Bollinger Bands, volume, price change) built on pure pandas.  
- **Live NSE Data:** Fetches price/volume for any Nifty stock using [yfinance](https://github.com/ranaroussi/yfinance).  
- **Pluggable Strategies:** Default: RSI + Moving Average crossover, but easily modifiable.  
- **Full Backtesting:** See total return, win/loss, buy & hold versus strategy.  
- **Machine Learning:** Predicts next day up/down, accuracy metrics included.  
- **Automation-Ready:** Results exportable to JSON, ready for Google Sheets. Alerts/logs via Telegram or desktop.  
- **Clear Logging:** Every important step is logged and summarized.  

---

## 🖥️ Quick Demo

Run the demo for 3 Nifty stocks with just:

if name == "main":
quick_demo()

**Sample Output:**

================================================================================

ALGO-TRADING SYSTEM RESULTS SUMMARY

RELIANCE.NS

Total Trades: 1

Win Ratio: 0.00%

Total Return: -1.61%

Buy & Hold Return: -3.52%

Final Portfolio Value: ₹98,391.32

ML Model Accuracy: 0.4255

Next Day Prediction: UP ⬆️ (1.00)

Current RSI: 28.57

Current Signal: SELL 🔴

...

---

## 📁 Project Structure

| File                 | Description                               |
|----------------------|-------------------------------------------|
| `trading-algo.ipynb` | Main code/notebook: all classes & workflow |
| `trading_results.json` | Auto-output: run summary in JSON          |
| `trading_system.log` | Full execution trace and logs             |

All code is modular with the following classes:  
`TechnicalIndicators`, `DataIngestion`, `TradingStrategy`, `MLPredictor`, and `AlgoTradingSystem`.

---

## 🚦 Example Trade Log (Google Sheets Ready)

| Symbol      | Entry_Date | Exit_Date | Entry_Price | Exit_Price | PnL%  |
|-------------|-------------|-----------|-------------|------------|--------|
| RELIANCE.NS | 2025-07-21  | 2025-08-01| ₹1428.60    | ₹1393.70   | -2.44% |
| TCS.NS      | 2024-12-26  | 2025-01-09| ₹4108.60    | ₹3980.24   | -3.12% |
| INFY.NS     | 2025-01-01  | 2025-01-22| ₹1856.38    | ₹1830.69   | -1.38% |

Easily copy/paste or integrate into Google Sheets!

---

## ⚙️ How to Run

1. Clone the repository  
2. Install dependencies:

pip install pandas numpy yfinance scikit-learn

Optional:
pip install gspread google-auth requests

3. Edit and run `trading-algo.ipynb`  
4. Adjust stock list and configurations as needed  

---

## 🧩 Requirements

- Python 3.8+  
- [pandas](https://pandas.pydata.org/)  
- [numpy](https://numpy.org/)  
- [yfinance](https://github.com/ranaroussi/yfinance)  
- [scikit-learn](https://scikit-learn.org/)  
- Optional: [gspread](https://docs.gspread.org/), [requests](https://docs.python-requests.org/)  

---

## 🏗️ Modularity

- All functionality encapsulated in classes for easy extension  
- Trading signals, backtests, and ML models are configurable and reusable  
- Outputs formatted for logs, JSON exports, and spreadsheets  

---

## 📢 Alert & Automation

Python-based alerts optionally notify via sounds or logs when:

- Model accuracy drops below 50%  
- Win ratio falls to zero  
- Total returns turn negative  
- Oversold conditions (SELL signal with low RSI)  

---
