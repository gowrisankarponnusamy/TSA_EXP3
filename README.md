### DEVELOPED BY: GOWRISANKAR P
### REGISTER NO: 212222230041
### DATE:
# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
 
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
#Code
```
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
df = pd.read_csv('MentalHealthSurvey.csv')

sales_data = df['age'].values

```
#Mean
```
mean_sales = np.mean(sales_data)
```
#Variance
```
var_sales = np.var(sales_data)
```
#Normalized data
```
normalized_sales = (sales_data - mean_sales) / np.sqrt(var_sales)
```
#Go through lag components one-by-one
```
lags = range(28)
acf_values = [np.corrcoef(normalized_sales[:-lag], normalized_sales[lag:])[0, 1] if lag != 0 else 1 for lag in lags]
```
#display the graph
```
plt.figure(figsize=(10, 6))
plt.stem(lags, acf_values, use_line_collection=True)
plt.title('Autocorrelation Function (ACF) for MentalHealthSurvey')
plt.xlabel('Lag')
plt.ylabel('ACF')
plt.grid(True)
plt.show()
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/c299cf96-414c-4226-8444-54e5c9bc2ae0)

### RESULT:
Thus python code implemented successfully in auto correlation function.
