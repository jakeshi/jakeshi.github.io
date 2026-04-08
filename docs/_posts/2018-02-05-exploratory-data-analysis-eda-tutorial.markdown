---
layout: post
title: "Exploratory Data Analysis with Python and Yahoo Finance"
date: 2018-02-05
categories: data-analysis
---

Following up on my REIT analysis post, I wanted to go deeper into exploratory data analysis (EDA). Same dataset — ROIC, SKT, TCO, SPG, and MAC — but this time I'm walking through the full EDA workflow: descriptive stats, data quality checks, and visualization prep.

## Load the data

```python
from pandas_datareader import data
import pandas as pd

tickers = ['ROIC', 'SKT', 'TCO', 'SPG', 'MAC']
panel_data = data.DataReader(tickers, 'yahoo', '2016-12-01', '2017-12-31')
df = panel_data['Adj Close']
```

## Descriptive statistics

```python
df.describe()
```

```python
print(df.head())
print(df.tail())
df.sample(6)
```

## Queries and checks

Pandas `.query()` is handy for quick filtering:

```python
df.query('MAC == ROIC')
```

## Data quality

Check for missing values and fill them:

```python
print(df.columns[df.isnull().any()])

all_weekdays = pd.date_range(start='2016-12-01', end='2017-12-31', freq='B')
df = df.reindex(all_weekdays)
df = df.fillna(method='ffill')
```

## Distribution analysis

Bucketing a continuous variable to see how prices are distributed:

```python
mybins = range(int(df.MAC.min()), int(df.MAC.max()), 2)
df['MAC_bucket'] = pd.cut(df.MAC, bins=mybins)
df['MAC_bucket'].value_counts()
```

The EDA workflow is always the same: load, describe, check for nulls, clean, explore. It's not glamorous, but every time I skip it I end up regretting it later. Getting disciplined about this part makes everything downstream — modeling, visualization, conclusions — more trustworthy.
