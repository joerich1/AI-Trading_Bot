# Dataset: Multinomial Stock Return Forecasting (1990–2018)

This dataset contains the train/test splits used for forecasting multinomial stock returns following *"Forecasting Multinomial Stock Returns Using Machine Learning Methods"*.

---

## Files
- **X_train.csv** – Training features (1990-01-02 to 2006-12-29)
- **y_train.csv** – Training labels (-1, 0, +1)
- **X_test.csv** – Testing features (2007-01-02 to 2018-12-28)
- **y_test.csv** – Testing labels (-1, 0, +1)

---

## Labels (`y_train`, `y_test`)
- `-1` → Return ≤ Q1 (bottom quartile)
- `0`  → Q1 < Return < Q3 (middle 50%)
- `+1` → Return ≥ Q3 (top quartile)

Thresholds (computed from training only):
- Q1 = -0.00465  
- Q3 = 0.00551  

---

## Features (`X_train`, `X_test`)
Columns:

1. **VIX_Close** – CBOE Volatility Index (daily close)
2. **ADS_Index** – Business conditions index
3. **RECBARS** – NBER recession indicator (0/1)
4. **fft** – Foreign exchange factor (broad dollar index return)
5. **3mth** – 3-month Treasury yield
6. **10yr** – 10-year Treasury yield
7. **30yr** – 30-year Treasury yield
8. **Aaa** – Moody’s Aaa corporate bond yield
9. **Baa** – Moody’s Baa corporate bond yield
10. **term_spread** – 10yr – 3mth
11. **long_spread** – 30yr – 10yr
12. **corp_spread** – Baa – Aaa
13. **Aaa_minus_10Y** – Aaa – 10yr
14. **TED** – 3mth LIBOR – 3mth Treasury
15. **majcurr_ret** – Major currency exchange rate return
16. **DAX** – German DAX index return
17. **rdax** – DAX return (daily %)
18. **FTSE** – UK FTSE index return
19. **oil** – WTI crude oil log return
20. **copper_ret** – Copper price log return
21. **gold_ret** – Gold price log return
22. **silver_ret** – Silver price log return
23. **MA10** – 10-day moving average of S&P
24. **MOM10** – 10-day momentum
25. **StochK** – Stochastic oscillator %K
26. **StochD** – Stochastic oscillator %D
27. **RSI** – Relative Strength Index (10-day)
28. **Rperc** – Williams %R
29. **MACD** – Moving Average Convergence Divergence (12–26 EMA)
30. **MACDsig** – MACD signal line (9-day EMA)

---

## Notes
- All features aligned to **S&P 500 trading days** (1990-01-02 → 2018-12-28).  
- Returns are log-differences (`np.log(P_t) - np.log(P_{t-1})`).  
- Technical indicators follow Kara et al. (2011).  