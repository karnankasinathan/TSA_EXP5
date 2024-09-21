### Developed by : Karnan K
### Reg no : 212222230062
### Date: 

# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION


### AIM:
To Illustrates how to perform time series analysis and decomposition on the year average of the complaints and for airline baggage complaints.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```
# Import required packages
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose
df = pd.read_csv('/content/baggagecomplaints.csv', parse_dates=['Date'], index_col='Date')
print("First Five Rows:")
print(df.head())
decomposition = seasonal_decompose(df['Baggage'], model='additive', period=12)
plt.figure(figsize=(12, 8))
plt.subplot(411)
plt.plot(df['Baggage'], label='Observed')
plt.legend(loc='upper left')
plt.title('Observed Data')
# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Trend Plot')
# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonal Plot')
# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residuals', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')
plt.tight_layout()
plt.show()
# Print the overall decomposition results
print("Seasonal Decomposition Components:")
print("Trend:\n", decomposition.trend.dropna().head())
print("Seasonal:\n", decomposition.seasonal.dropna().head())
print("Residual:\n", decomposition.resid.dropna().head())
```


### OUTPUT:
FIRST FIVE ROWS:
![Screenshot 2024-09-21 084743](https://github.com/user-attachments/assets/f5137bda-820f-48ab-bae6-415f3cb866cd)



PLOTTING THE DATA:

SEASONAL PLOT REPRESENTATION :

![Screenshot 2024-09-21 084802](https://github.com/user-attachments/assets/c4cdc95f-4300-4c47-afcc-eef70e3207c4)


TREND PLOT  REPRESENTATION :

![Screenshot 2024-09-21 084810](https://github.com/user-attachments/assets/6cc779fb-a400-4bc0-9929-95169b5a3011)
 

OVERAL REPRESENTATION:

![Screenshot 2024-09-21 084838](https://github.com/user-attachments/assets/7f87292b-f0e7-4950-8a63-a44e366f294b)


### RESULT:
Thus the python code was successfullly created for the time series analysis and decomposition.
