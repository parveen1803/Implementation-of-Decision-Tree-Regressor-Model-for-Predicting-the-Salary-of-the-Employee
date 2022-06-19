# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the required libraries.
2. Upload and read the dataset.
3. Gather information and presence of null in the dataset.
4. From sklearn.tree import DecisionTreeRegressor and fir the model. 5.Find the mean square error and r squared score value of the model.
5. Check the trained model.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Parveen Fathima M
RegisterNumber: 212219040103  
*/
import pandas as pd
data = pd.read_csv("Salary.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
x= data[["Position","Level"]]
y=data["Salary"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size = 0.2,random_state = 2)
from sklearn.tree import DecisionTreeRegressor
dt = DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred = dt.predict(x_test)
from sklearn import metrics
mse = metrics.mean_squared_error(y_test,y_pred)
mse
r2= metrics.r2_score(y_test,y_pred)
r2
dt.predict([[5,6]])
```

## Output:
## Initial Dataset:
![initial](https://user-images.githubusercontent.com/87666371/174470862-c0159508-84f5-4e9f-8bc9-79df139f1f3c.png)

## Dataset information:
![datainfo](https://user-images.githubusercontent.com/87666371/174470883-d8e025b1-1da9-4ab1-9c1f-1c6e7cf21374.png)

## Null dataset:
![null](https://user-images.githubusercontent.com/87666371/174470903-a8d9a880-b166-4f4f-a033-79f288b5d9d8.png)

## Encoded Dataset:
![encoded](https://user-images.githubusercontent.com/87666371/174470927-caef0dd8-4fb1-4c24-9774-1a0418ab2155.png)

## Mean Square Error value:
![mean](https://user-images.githubusercontent.com/87666371/174470948-45854e8b-5e56-4da2-866e-e30ee2c270b2.png)

## R squared score:
![rsqua](https://user-images.githubusercontent.com/87666371/174470962-5b7b455d-ef32-43e0-ba2e-9028790dba28.png)

## pedictted value:
![predicted](https://user-images.githubusercontent.com/87666371/174470984-84450a26-abc3-4b96-8652-f165e3c1b08a.png)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
