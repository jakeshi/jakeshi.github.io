---
layout: post
title: "Lump Sum vs. Dollar Cost Averaging: An Apple Stock Analysis"
date: 2017-09-13
---

I've been curious about a classic investing question: is it better to invest a lump sum all at once, or spread it out over time (dollar cost averaging)? Instead of reading more opinions about it, I decided to just look at the data using Python.

I'm using Apple (AAPL) stock as the example — pulling historical prices from Yahoo Finance and simulating both strategies with a $10,000 investment.

## Pulling the data

```python
import pandas as pd
import pandas_datareader.data as web
import datetime

start = datetime.datetime(2017, 9, 1)
end = datetime.datetime(2018, 2, 3)

spy = web.DataReader("AAPL", "yahoo", start, end)
print(spy.head())
```

## Plotting the stock price

```python
%matplotlib inline
import matplotlib.pyplot as plt
from matplotlib.ticker import FuncFormatter
from matplotlib import style
style.use('fivethirtyeight')

spy['Adj Close'].plot(figsize=(20,10))
ax = plt.subplot()
ax.yaxis.set_major_formatter(FuncFormatter(lambda x, pos: '${:,.0f}'.format(x)))
plt.title('AAPL Historical Price on Close')
plt.ylabel('Stock Price ($)')
```

## Lump sum simulation

If you invested $10,000 on any given date, what would it be worth at the end of the period?

```python
value_price = spy['Adj Close'][-1]
initial_investment = 10000

num_stocks_bought = initial_investment / spy['Adj Close']
lumpsum = num_stocks_bought * value_price
lumpsum.name = 'Lump Sum'

lumpsum.plot(figsize=(20,10))
ax = plt.subplot()
ax.yaxis.set_major_formatter(FuncFormatter(lambda x, pos: '${:,.0f}'.format(x)))
plt.title('Lump Sum - Value of $10,000 invested on date')
plt.ylabel('Investment Value ($)')
```

## Dollar cost averaging simulation

Instead of investing all at once, spread the $10,000 over 12 weekly purchases:

```python
def doDCA(investment, start_date):
    investment_dates_all = pd.date_range(start_date, periods=12, freq='7D')
    investment_dates = investment_dates_all[investment_dates_all < spy.index[-1]]
    closest_investment_dates = spy.index.searchsorted(investment_dates)
    portion = investment / 12.0
    stocks_invested = sum(portion / spy['Adj Close'][closest_investment_dates])
    uninvested_dollars = portion * sum(investment_dates_all >= spy.index[-1])
    total_value = value_price * stocks_invested + uninvested_dollars
    return total_value

dca = pd.Series(spy.index.map(lambda x: doDCA(initial_investment, x)),
                index=spy.index, name='Dollar Cost Averaging')
```

The results are interesting. For a stock that's generally trending up like Apple, lump sum tends to win — you benefit from being in the market sooner. DCA smooths out the risk but leaves some upside on the table.

This is a small sample and a single stock, so I wouldn't draw sweeping conclusions. But it's a fun exercise, and writing the DCA simulation from scratch taught me more than reading any article about it.
