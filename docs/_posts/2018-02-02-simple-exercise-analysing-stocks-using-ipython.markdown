---
layout: post
title: "Analysing REIT Stocks with Python"
date: 2018-02-02
---

I've been looking at real estate investment trusts (REITs) lately and wanted to do some basic analysis on a few tickers. The goal: pull stock data from Yahoo Finance, look at adjusted closing prices, and start getting comfortable with pandas DataFrames.

The REITs I'm comparing: ROIC, SKT, TCO, SPG, and MAC — a mix of retail and shopping center REITs.

## Pulling the data

```python
from pandas_datareader import data
import pandas as pd

tickers = ['ROIC', 'SKT', 'TCO', 'SPG', 'MAC']
data_source = 'yahoo'
start_date = '2016-12-01'
end_date = '2017-12-31'

panel_data = data.DataReader(tickers, data_source, start_date, end_date)
```

## Working with closing prices

```python
close = panel_data['Close']

# Fill in missing weekday data
all_weekdays = pd.date_range(start=start_date, end=end_date, freq='B')
close = close.reindex(all_weekdays)
```

## Adjusted close and forward fill

```python
adj_close = panel_data['Adj Close']
adj_close = adj_close.reindex(all_weekdays)
adj_close = adj_close.fillna(method='ffill')
adj_close.describe()
```

## Bucketing prices

```python
mybins = range(int(adj_close.MAC.min()), int(adj_close.MAC.max()), 10)
adj_close['MAC_bucket'] = pd.cut(adj_close.MAC, bins=mybins)
adj_close['MAC_bucket'].value_counts()
```

Nothing groundbreaking here — just getting comfortable pulling financial data and working with it in pandas. The `reindex` and `fillna` pattern for handling missing trading days is something I'll reuse a lot. Next step: calculating returns and correlations between these tickers.
