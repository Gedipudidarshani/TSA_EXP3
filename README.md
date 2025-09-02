# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
Date: 24-8-2025
### NAME: GEDIPUDI DARSHANI
### REGISTER NUMBER: 212223230062
### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
### PROGRAM:
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.graphics.tsaplots import plot_acf

# Load the dataset
data = pd.read_csv("india.csv")

print("Dataset columns:", data.columns)
print(data.head())

# Convert 'date' column to datetime and set as index
if 'date' in data.columns:
    data['date'] = pd.to_datetime(data['date'], errors='coerce')
    data.set_index('date', inplace=True)

# Use 'close' prices for ACF
price_column = 'high'
price_data = data[price_column]

# Plot ACF for first 35 lags
plt.figure(figsize=(10, 6))
plot_acf(price_data, lags=35, alpha=0.05)
plt.title('AutoCorrelation Function (ACF) for Closing Prices')
plt.xlabel('Lags')
plt.ylabel('ACF Value')
plt.grid(True)
plt.show()
```
### OUTPUT:
<img width="926" height="750" alt="image" src="https://github.com/user-attachments/assets/ce293a02-0533-452c-b8ca-b0690ee41bf2" />

### RESULT:
Thus we have successfully implemented the auto correlation function in python.
