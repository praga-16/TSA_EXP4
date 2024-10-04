# Ex.No:04   FIT ARMA MODEL FOR TIME SERIES

# Date: 


### AIM:
To implement ARMA model in python.
### ALGORITHM:
1. Import necessary libraries.
2. Set up matplotlib settings for figure size.
3. Define an ARMA(1,1) process with coefficients ar1 and ma1, and generate a sample of 1000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

4. Display the autocorrelation and partial autocorrelation plots for the ARMA(1,1) process using
plot_acf and plot_pacf.
5. Define an ARMA(2,2) process with coefficients ar2 and ma2, and generate a sample of 10000

data points using the ArmaProcess class. Plot the generated time series and set the title and x-
axis limits.

6. Display the autocorrelation and partial autocorrelation plots for the ARMA(2,2) process using
plot_acf and plot_pacf.
### PROGRAM:
```
Name : pragatheesvaran A B
Register number : 212221240039
```
```python

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.arima_process import ArmaProcess
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf
import warnings
warnings.filterwarnings('ignore')

# Load the dataset
data = pd.read_csv('powerconsumption.csv')

# Use the 'Temperature' column (remove the leading space)
close_prices = data['Temperature'].dropna()

plt.rcParams['figure.figsize'] = [10, 7.5]

# Simulate ARMA(1,1) Process
ar1 = np.array([1, 0.33])
ma1 = np.array([1, 0.9])
ARMA_1 = ArmaProcess(ar1, ma1).generate_sample(nsample=len(close_prices))
plt.plot(ARMA_1)
plt.title('Simulated ARMA(1,1) Process')
plt.xlim([0, 200])
plt.show()

# Plot ACF and PACF for ARMA(1,1)
plot_acf(ARMA_1)
plot_pacf(ARMA_1)

# Simulate ARMA(2,2) Process
ar2 = np.array([1, 0.33, 0.5])
ma2 = np.array([1, 0.9, 0.3])
ARMA_2 = ArmaProcess(ar2, ma2).generate_sample(nsample=len(close_prices) * 10)
plt.plot(ARMA_2)
plt.title('Simulated ARMA(2,2) Process')
plt.xlim([0, 200])
plt.show()

# Plot ACF and PACF for ARMA(2,2)
plot_acf(ARMA_2)
plot_pacf(ARMA_2)

```

### OUTPUT:
SIMULATED ARMA(1,1) PROCESS:

![download](https://github.com/user-attachments/assets/440ae1a4-cfb8-4ce8-a920-4478c9df6bca)


Partial Autocorrelation

![download](https://github.com/user-attachments/assets/aef87ab3-4df6-4aad-9c82-701dcfd4a029)



Autocorrelation

![download](https://github.com/user-attachments/assets/027ecf0d-41a8-4a38-b1f7-a9b043e32307)



SIMULATED ARMA(2,2) PROCESS:

![download](https://github.com/user-attachments/assets/53d04690-bf67-4b04-be9e-5146d7f13575)



Partial Autocorrelation

![download](https://github.com/user-attachments/assets/ed81e098-7ed3-4a7b-b5e3-0cb2498d5eba)




Autocorrelation

![download](https://github.com/user-attachments/assets/378b0c9c-b689-4082-a251-56c4715a31ea)




RESULT:
Thus, a python program is created to fir ARMA Model successfully.
