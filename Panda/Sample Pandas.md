Here’s a sample Python script that demonstrates basic operations with **Pandas** and **NumPy** using a stock dataset in a Jupyter Notebook.

### Sample Stock Dataset (You can use a dataset with columns like Date, Open, High, Low, Close, Volume, etc.)
```python
import pandas as pd
import numpy as np

# Sample Data (or load your own CSV file)
data = {
    'Date': ['2023-01-01', '2023-01-02', '2023-01-03', '2023-01-04', '2023-01-05'],
    'Open': [150, 152, 148, 155, 158],
    'High': [155, 153, 149, 158, 160],
    'Low': [148, 147, 146, 153, 157],
    'Close': [154, 150, 148, 156, 159],
    'Volume': [1000, 1100, 1200, 1300, 1400]
}

# Creating a DataFrame from the data
df = pd.DataFrame(data)
df['Date'] = pd.to_datetime(df['Date'])  # Converting Date to datetime format
df.set_index('Date', inplace=True)  # Setting Date as the index

# Display the DataFrame
df
```

### Basic DataFrame Operations
```python
# Viewing the first few rows of the dataset
print(df.head())

# Summary statistics of the stock data
print(df.describe())

# Checking for missing values
print(df.isnull().sum())

# Calculate percentage change in 'Close' prices
df['Price Change (%)'] = df['Close'].pct_change() * 100
print(df)
```

### Using NumPy for Stock Analysis
```python
# Calculate daily returns using NumPy
daily_returns = np.diff(df['Close'].values) / df['Close'].values[:-1] * 100
print("Daily Returns (%):", daily_returns)

# Adding daily returns to the DataFrame (shifted by 1 to align with dates)
df['Daily Return (%)'] = np.insert(daily_returns, 0, 0)  # Inserting 0 for the first day
df.head()
```

### Visualization of Stock Prices
You can also use **Matplotlib** to visualize the stock data.
```python
import matplotlib.pyplot as plt

# Plotting the stock's closing prices over time
plt.figure(figsize=(10, 5))
plt.plot(df.index, df['Close'], label='Close Price', marker='o')
plt.title('Stock Closing Prices Over Time')
plt.xlabel('Date')
plt.ylabel('Close Price')
plt.grid(True)
plt.legend()
plt.show()
```

### Moving Averages Calculation
```python
# Calculate 3-day and 5-day moving averages
df['3-day MA'] = df['Close'].rolling(window=3).mean()
df['5-day MA'] = df['Close'].rolling(window=5).mean()

# Display the updated DataFrame with moving averages
print(df[['Close', '3-day MA', '5-day MA']])
```

### Saving the Updated DataFrame to a CSV File
```python
# Save the updated DataFrame with moving averages and daily returns
df.to_csv('updated_stock_data.csv')
```

### Complete Workflow
This script covers:
1. Loading a stock dataset.
2. Performing data exploration and cleaning.
3. Using NumPy for financial calculations (daily returns).
4. Calculating moving averages.
5. Plotting the stock prices.
6. Saving the processed data.

