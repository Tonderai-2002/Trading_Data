# 📊 Personal Forex Trade Performance Analyzer & Strategy Optimizer

This is a hands-on, personalized data project that analyzes my actual trading history exported from MT5/Deriv. It is designed to help me understand my trading behavior, measure performance, and lay the foundation for building data-driven strategy optimizations. Thi work is aimed at showcasing end-to-end data analysis using real-world data.

---

## 🚀 Project Objectives

* Understand historical trade performance using real data
* Identify trends and inefficiencies in time-based and symbol-based performance
* Apply data wrangling, cleaning, and analysis techniques to a real dataset
* Showcase practical, personalized data analysis skills to potential employers

---

## 📁 Dataset Overview

Data was exported from **MetaTrader 5 (MT5)** / **Deriv** in `.xlsx` format and includes:

* **Deals.csv** - Executed trades (closed positions)
* **Orders.csv** - Order history (includes Volume in `x / y` format)
* **Positions.csv** - Open positions (had mixed data types)

Each sheet was saved individually as a `.csv` for structured analysis.

---

## 🔧 Step 1: Data Extraction

* Exported all relevant trading history from MT5.
* Saved each sheet to `.csv` format to prepare for analysis in Python.

---

## 💩 Step 2: Data Cleaning

### Deals

* Removed rows where `Type == "balance"` to keep only real trades.
* Converted `Time` columns to datetime format.

### Orders

* Parsed `Volume` column from format like `"1.00 / 0.00"` to extract numeric value.

### Positions

* Several numeric columns (e.g., `Profit`, `Volume`, `Price`) contained text strings due to export inconsistencies.
* **Converted** `Profit` and `Volume` columns to numeric values.
* **Replaced** textual or non-usable values in `Price` with `NaN` to avoid skewing statistical results. Zero was avoided to preserve integrity.

---

## 📊 Step 3: Basic Trade Performance Analysis

```python
Total Trades: 7360
Win Rate: 15.19%
Average P/L per Trade: -0.51
Total P/L: -3726.51
```

> Insight: A low win rate combined with a negative average profit highlights opportunities for deeper strategy assessment.

---

## 📈 Step 4: Grouped Performance Insights

### 🌎 By Currency Pair (Symbol)

Top instruments by total profit/loss:

| Symbol           | Trades | Total P/L | Avg P/L |
| ---------------- | ------ | --------- | ------- |
| Boom 300 Index   | 612    | +86.00    | +0.14   |
| Jump 50 Index    | 48     | +1.78     | +0.04   |
| Crash 1000 Index | 1806   | -1230.49  | -0.68   |
| Boom 500 Index   | 144    | -359.94   | -2.50   |

> Insight: Boom 300 Index was most profitable. Crash 1000 and Boom 500 led to significant losses.

### ⏰ By Hour of Day

Analyzed average profit per hour:

```python
03:00 → +10.63
01:00 → +3.38
02:00 → +1.48
23:00 → +2.41
...
```

> Some early-morning hours had higher profitability, while midday and evening hours showed more losses.

### 🗓️ By Day of Week

```python
Monday    → -0.27
Tuesday   → -1.15
Wednesday → -0.20
Thursday  → -0.21
Friday    → -0.29
```

> Tuesday showed the lowest average profit, indicating potential overtrading or poor strategy effectiveness on that day.


