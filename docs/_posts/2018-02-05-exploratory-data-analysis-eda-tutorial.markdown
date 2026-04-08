---
layout: post
title: "Exploratory Data Analysis (EDA) Tutorial"
date: 2018-02-05
---
## Summary

This post download data from Yahoo finance and does some basic EDA.

```bash
!conda env list
%matplotlib inline
```

```python
#Importing The Data

from pandas_datareader import data
import pandas as pd

# Define the instruments to download. We would like to see Apple, Microsoft and the S&P500 index.
# tickers = ['W', 'HD', 'AMZN','LOW','LL']
tickers = ['ROIC', 'SKT', 'TCO' ,'SPG' ,'MAC']
# Define which online source one should use
data_source = 'yahoo'

# We would like all available data from 01/01/2000 until 12/31/2016.
start_date = '2016-12-01'
end_date = '2017-12-31'

# User pandas_reader.data.DataReader to load the desired data. As simple as that.
panel_data = data.DataReader(tickers, data_source, start_date, end_date)
panel_data.head()
df = panel_data['Adj Close']
```

```python
# Basic Description of the Data

df.describe()
```

```python
first = df.head()
last = df.tail()
print(first)
print(last)
df.sample(6)
```

```python
# A Closer Look At Your Data: Queries

df.query('MAC == ROIC')
```

```python
#cleaning
print(df.columns[df.isnull().any()])
```

```python
# Getting all weekdays between 01/01/2000 and 12/31/2016
all_weekdays = pd.date_range(start=start_date, end=end_date, freq='B')

# How do we align the existing prices in adj_close with our new set of dates?
# All we need to do is reindex adj_close using all_weekdays as the new index
df = df.reindex(all_weekdays)

# Reindexing will insert missing values (NaN) for the dates that were not present
# in the original set. To cope with this, we can fill the missing by replacing them
# with the latest available price for each instrument.
df = df.fillna(method='ffill')
df.isnull().head()
```

```python
# Define your own bins
mybins = range(int(df.MAC.min()), int(df.MAC.max()), 2)

# Cut the data with the help of the bins
df['MAC_bucket'] = pd.cut(df.MAC, bins=mybins)

# Count the number of values per bucket
df['MAC_bucket'].value_counts()
```
