# Ex.No: 02 LINEAR AND POLYNOMIAL TREND ESTIMATION
Date: 30:10:2026
### AIM:
To Implement Linear and Polynomial Trend Estiamtion Using Python.

### ALGORITHM:
Import necessary libraries (NumPy, Matplotlib)

Load the dataset

Calculate the linear trend values using least square method

Calculate the polynomial trend values using least square method

End the program
### PROGRAM:
A - LINEAR TREND ESTIMATION
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

# Load dataset
df = pd.read_csv('temperature.csv')

# Remove empty rows
df = df.dropna(how='all')

# Select year and annual temperature
x = df['YEAR'].astype(float)
y = pd.to_numeric(df['ANNUAL'], errors='coerce')

# Remove invalid values
data = pd.DataFrame({'YEAR': x, 'ANNUAL': y}).dropna()
x = data['YEAR']
y = data['ANNUAL']

# Calculate linear trend
m, c = np.polyfit(x, y, 1)
linear_trend = m * x + c

# Plot linear trend
plt.scatter(x, y, label='Actual Temperature')
plt.plot(x, linear_trend, color='red', label='Linear Trend')
plt.title('Linear Trend Estimation')
plt.xlabel('YEAR')
plt.ylabel('TEMPERATURE')
plt.legend()
plt.grid()
plt.show()
```

B- POLYNOMIAL TREND ESTIMATION
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

# Load dataset
df = pd.read_csv('temperature.csv')

# Remove empty rows
df = df.dropna(how='all')

# Select year and annual temperature
x = df['YEAR'].astype(float)
y = pd.to_numeric(df['ANNUAL'], errors='coerce')

# Remove invalid values
data = pd.DataFrame({'YEAR': x, 'ANNUAL': y}).dropna()
x = data['YEAR']
y = data['ANNUAL']

# Calculate polynomial trend
coeff = np.polyfit(x, y, 2)
poly_trend = np.polyval(coeff, x)

# Plot polynomial trend
plt.scatter(x, y, label='Actual Temperature')
plt.plot(x, poly_trend, color='red', label='Polynomial Trend')
plt.title('Polynomial Trend Estimation')
plt.xlabel('YEAR')
plt.ylabel('TEMPERATURE')
plt.legend()
plt.grid()
plt.show()
```

### OUTPUT
A - LINEAR TREND ESTIMATION

<img width="757" height="592" alt="image" src="https://github.com/user-attachments/assets/57818a31-64ec-4238-8c34-bd8f8bdafb57" />


B- POLYNOMIAL TREND ESTIMATION

<img width="781" height="595" alt="image" src="https://github.com/user-attachments/assets/4e82db58-2b2c-4a4f-986c-87964f7a47c3" />


### RESULT:
Thus the python program for linear and Polynomial Trend Estiamtion has been executed successfully.
