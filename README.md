![329870101-8ec7c229-df4f-4482-971c-0171d02bed1c](https://github.com/Gajalakshmivelmurugan/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/144871940/554a7570-b6b4-434d-8a07-a3eda50f054d)# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
Step-1: Import the required libraries .

Step-2: Read the data frame using pandas.

Step-3: Get the information regarding the null values present in the dataframe.

Step-4: Apply label encoder to the non-numerical column inoreder to convert into numerical values.

Step-5: Determine training and test data set.

Step-6: Apply decision tree regression on to the dataframe.

Step-7: Get the values of Mean square error, r2 and data predictio

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: gajalakshmi V
RegisterNumber:  212223040047
*/
import pandas as pd
data=pd.read_csv("/content/Salary.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()

x=data[["Position","Level"]]
y=data["Salary"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_pred)
mse

r2=metrics.r2_score(y_test,y_pred)
r2

dt.predict([[5,6]])

```

## Output:
data.head()

![329870001-06d30639-ce5b-4179-91a2-5fd89b55cc0e](https://github.com/Gajalakshmivelmurugan/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/144871940/80cb9471-1d5e-46f3-9a5a-552ad2a83fc7)


data.info()

![329870027-b7659271-4756-46d1-9c2f-78fec8155e1f](https://github.com/Gajalakshmivelmurugan/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/144871940/dabc5962-e82a-4637-bd0f-c048738fef78)

Isnull() & sum() function
![329870052-d8df742a-98c3-4b70-9c51-bdb594f675b1](https://github.com/Gajalakshmivelmurugan/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/144871940/9b9246e6-811b-44c8-8177-72afae82e435)


data.head() for position
![329870085-eaab359d-2507-4a53-bb4b-03dfb2095926](https://github.com/Gajalakshmivelmurugan/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/144871940/149c346b-842f-4614-be48-676928750554)


MSE value
![329870101-8ec7c229-df4f-4482-971c-0171d02bed1c](https://github.com/Gajalakshmivelmurugan/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/144871940/1a45c0e7-8eac-4ce2-a7d1-327d0c11fbe2)


R2 value
![329870124-a9fa017c-a877-4b49-9b65-06328732ce8c](https://github.com/Gajalakshmivelmurugan/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/144871940/ad405740-2b0f-40cf-ac2b-7fc9f5de72de)


Prediction value
![329870158-89982a65-f91e-4afc-baf4-010de15b946f](https://github.com/Gajalakshmivelmurugan/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/144871940/5a4850fe-747a-44e3-a69c-b19110f85206)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
