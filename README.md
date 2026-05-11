# Ex.No: 02 LINEAR AND POLYNOMIAL TREND ESTIMATION
Date:25.04.2026
## NAME:ABINAYA A
## REG NO : 212224230004
### AIM:
To Implement Linear and Polynomial Trend Estiamtion Using Python.

### ALGORITHM:
Import necessary libraries (NumPy, Matplotlib)

Load the dataset

Calculate the linear trend values using least square method

Calculate the polynomial trend values using least square method

End the program
### PROGRAM:



```

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

# Load the dataset
file_path = 'Gold Price Prediction.csv'  # Replace with your actual file path
data = pd.read_csv(file_path)

# Convert 'Date' column to datetime format and specify the correct format
data['Date'] = pd.to_datetime(data['Date'], format='%m/%d/%y')

# Set the 'Date' column as the index
data.set_index('Date', inplace=True)

# Extract the time (x values) and 'Price Today' (y values)
data['Time'] = np.arange(len(data))
x = data['Time'].values
y = data['Price Today'].values

# Linear trend calculation (degree 1 polynomial)
linear_coefficients = np.polyfit(x, y, 1)
linear_trend = np.polyval(linear_coefficients, x)

# Polynomial trend calculation (degree 2 polynomial)
polynomial_coefficients = np.polyfit(x, y, 2)
polynomial_trend = np.polyval(polynomial_coefficients, x)

# Create subplots: one for the linear trend, one for the polynomial trend
plt.figure(figsize=(12, 10))

# Plot for linear trend
plt.subplot(2, 1, 1)
plt.plot(data.index, y, label='Gold Price Today', color='blue')
plt.plot(data.index, linear_trend, label='Linear Trend', color='red')
plt.title('Gold Price with Linear Trend')
plt.xlabel('Date')
plt.ylabel('Gold Price')
plt.legend()
plt.grid(True)

# Plot for polynomial trend
plt.subplot(2, 1, 2)
plt.plot(data.index, y, label='Gold Price Today', color='blue')
plt.plot(data.index, polynomial_trend, label='Polynomial Trend (Degree 2)', color='green')
plt.title('Gold Price with Polynomial Trend')
plt.xlabel('Date')
plt.ylabel('Gold Price')
plt.legend()
plt.grid(True)

# Adjust layout to avoid overlap
plt.tight_layout()

# Show the plots
plt.show()

# End the program (no further actions required)


```
### OUTPUT
A - LINEAR TREND ESTIMATION
<img width="1373" height="551" alt="image" src="https://github.com/user-attachments/assets/7b0a65e1-d9fd-44b7-832b-89aafd0149ae" />

B- POLYNOMIAL TREND ESTIMATION
<img width="1369" height="572" alt="image" src="https://github.com/user-attachments/assets/e1a33f08-7aae-49dc-b63d-d38046200199" />

### RESULT:
Thus the python program for linear and Polynomial Trend Estiamtion has been executed successfully.
