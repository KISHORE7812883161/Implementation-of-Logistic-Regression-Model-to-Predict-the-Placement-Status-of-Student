# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. import pandas module.

2. Read the required csv file using pandas . 

3. Import LabEncoder module.

4. From sklearn import logistic regression.

5. Predict the values of array.

6. Calculate the accuracy, confusion and classification report by importing the required modules from sklearn.

7. print the required values.

8. End the program.

## Program:
```py
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: KISHORE M
RegisterNumber:  212221043003
*/
```
```py
import pandas as pd
data = pd.read_csv("Placement_Data.csv")
print(data.head())
data1 = data.copy()
data1= data1.drop(["sl_no","salary"],axis=1)
print(data1.head())
data1.isnull().sum()
data1.duplicated().sum()
from sklearn.preprocessing import LabelEncoder
lc = LabelEncoder()
data1["gender"] = lc.fit_transform(data1["gender"])
data1["ssc_b"] = lc.fit_transform(data1["ssc_b"])
data1["hsc_b"] = lc.fit_transform(data1["hsc_b"])
data1["hsc_s"] = lc.fit_transform(data1["hsc_s"])
data1["degree_t"]=lc.fit_transform(data["degree_t"])
data1["workex"] = lc.fit_transform(data1["workex"])
data1["specialisation"] = lc.fit_transform(data1["specialisation"])
data1["status"]=lc.fit_transform(data1["status"])
print(data1)
x = data1.iloc[:,:-1]
print(x)
y = data1["status"]
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(x,y,test_size=0.2,random_state=0)
from sklearn.linear_model import LogisticRegression
lr = LogisticRegression(solver="liblinear")
print(lr.fit(x_train,y_train))
y_pred = lr.predict(x_test)
print(y_pred)
from sklearn.metrics import accuracy_score
accuracy = accuracy_score(y_test,y_pred)
print(accuracy)
from sklearn.metrics import confusion_matrix
confusion = confusion_matrix(y_test,y_pred)
print(confusion)
from sklearn.metrics import classification_report
classification_report1 = classification_report(y_test,y_pred)
print(classification_report1)
print(lr.predict([[8,60,1,20,2,2,9,7,0,75,1,65]]))
```
## Output:
![1](https://github.com/KISHORE7812883161/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/142528124/fd30235e-c282-4afb-8cb5-0189850d39bc)
![2](https://github.com/KISHORE7812883161/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/142528124/2a1b293f-6add-4d21-a06b-69e6bfa80850)
![3](https://github.com/KISHORE7812883161/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/142528124/d070b4f7-ecfd-4fc7-8b72-b0c8fc73f467)
![4](https://github.com/KISHORE7812883161/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/142528124/bcd31a96-6a9d-4444-99e3-4ad2e15dd3bf)

## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
