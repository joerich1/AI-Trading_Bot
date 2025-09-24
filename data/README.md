# S&P 500 Data

**File:** `sp500_1990_2018.csv`  
**Source:** Yahoo Finance (`^GSPC`)  
**Downloaded:** Sept 23, 2025  
**Range:** Jan 2, 1990 – Dec 31, 2018 (daily)

**Columns:**
- `Date` — trading day
- `Close`, `High`, `Low`, `Open` — prices
- `Volume` — trading volume

**Notes:**
- Raw data as downloaded; two metadata rows at top should be dropped before use.
- Used to compute close-to-close returns and 3-class labels (Down / Flat / Up).
- Preprocessing scripts will add lagged returns, rolling mean/volatility, and split into train/test sets.

**Reproduce download:**
```python
import yfinance as yf
sp500 = yf.download("^GSPC", start="1990-01-01", end="2018-12-31", interval="1d")
sp500.to_csv("sp500_1990_2018.csv")
