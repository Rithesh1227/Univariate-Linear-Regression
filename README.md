# Implementation of Univariate Linear Regression
## Aim:
To implement univariate Linear Regression to fit a straight line using least squares.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Get the independent variable X and dependent variable Y.
2.	Calculate the mean of the X -values and the mean of the Y -values.
3.	Find the slope m of the line of best fit using the formula.
 ![eqn1](./eq1.jpg)
4.	Compute the y -intercept of the line by using the formula:
![eqn2](./eq2.jpg)  
5.	Use the slope m and the y -intercept to form the equation of the line.
6.	Obtain the straight line equation Y=mX+b and plot the scatterplot.
## Program
```
import numpy as np
import matplotlib.pyplot as plt
# Preprocessing Input data
X = np.array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
Y = np.array([1, 3, 2, 5, 7, 8, 8, 9, 10, 12])
plt.scatter(X, Y)
plt.show()
# Building the model
X_mean = np.mean(X)
Y_mean = np.mean(Y)
num = 0
den = 0
for i in range(len(X)):
    num += (X[i] - X_mean) * (Y[i] - Y_mean)
    den += (X[i] - X_mean) ** 2
m = num / den
c = Y_mean - m * X_mean
print(m, c)
# Making predictions
Y_pred = m * X + c
print(Y_pred)
plt.scatter(X, Y)  # actual
plt.scatter(X, Y_pred, color='red')  # predicted
plt.plot([min(X), max(X)],
         [m * min(X) + c, m * max(X) + c],
         color='red')
plt.show()
```
## Output
</br>
<img width="1103" height="609" alt="Screenshot 2026-02-26 142741" src="https://github.com/user-attachments/assets/da906f4e-6161-464b-9329-b138919075c6" />

</br>
<img width="1092" height="682" alt="Screenshot 2026-02-26 142810" src="https://github.com/user-attachments/assets/255f0ab6-eb66-41d1-8796-f3c21232d595" />

</br>

## Result
Thus the univariate Linear Regression was implemented to fit a straight line using least squares.
