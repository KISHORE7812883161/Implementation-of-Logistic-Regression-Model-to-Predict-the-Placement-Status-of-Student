# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
# Step 1 :

Import the standard libraries such as pandas module to read the corresponding csv file.
# Step 2 :

Upload the dataset values and check for any null or duplicated values using .isnull() and .duplicated() function respectively.
# Step 3 :

Import LabelEncoder and encode the corresponding dataset values.
# Step 4 :

Import LogisticRegression from sklearn and apply the model on the dataset using train and test values of x and y.
# Step 5 :

Predict the values of array using the variable y_pred.
# Step 6 :

Calculate the accuracy, confusion and the classification report by importing the required modules such as accuracy_score, confusion_matrix and the classification_report from sklearn.metrics module.
# Step 7 :

Apply new unknown values and print all the acqirred values for accuracy, confusion and the classification report.
# Step 8:
End the program. 

## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: KISHORE M 
RegisterNumber:2122210443003  
*/


import pandas as pd
data = pd.read_csv("Placement_Data.csv")
data.head()

data1 = data.copy()
data1 = data1.drop(["sl_no","salary"],axis = 1)
data1.head()

data1.isnull().sum()

data1.duplicated().sum()

from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()

data1["gender"] = le.fit_transform(data1["gender"])
data1["ssc_b"] = le.fit_transform(data1["ssc_b"])
data1["hsc_b"] = le.fit_transform(data1["hsc_b"])
data1["hsc_s"] = le.fit_transform(data1["hsc_s"])
data1["degree_t"] = le.fit_transform(data1["degree_t"])
data1["workex"] = le.fit_transform(data1["workex"])
data1["specialisation"] = le.fit_transform(data1["specialisation"])
data1["status"] = le.fit_transform(data1["status"])
data1

x = data1.iloc[:,:-1]
x

y = data1["status"]
y

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size = 0.2,random_state = 0)

from sklearn.linear_model import LogisticRegression
lr = LogisticRegression(solver = "liblinear")
lr.fit(x_train,y_train)
y_pred = lr.predict(x_test)
y_pred

from sklearn.metrics import accuracy_score
accuracy = accuracy_score(y_test,y_pred)
accuracy

from sklearn.metrics import confusion_matrix
confusion = confusion_matrix(y_test,y_pred)
confusion

from sklearn.metrics import classification_report
classification_report1 = classification_report(y_test,y_pred)
classification_report1

lr.predict([[1,80,1,90,1,1,90,1,0,85,1,85]])

```
## Output:
# HEAD OF THE DATA :
![image](https://github.com/Yogabharathi3/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/118899387/6ce7e0b0-8f6a-4ff8-b65c-b4c86e1701c5)

# COPY HEAD OF THE DATA :
![image](https://github.com/Yogabharathi3/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/118899387/fd14ef98-ca02-4971-9bd4-5d57b0ef3b4d)

# NULL AND SUM :
![image](https://github.com/Yogabharathi3/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/118899387/59676f83-b804-411a-87e7-25f83ae796d2)

# DUPLICATED :
![image](https://github.com/Yogabharathi3/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/118899387/e4be843f-0f1b-43cf-a990-a1c57e981245)

# X VALUE :
![image](https://github.com/Yogabharathi3/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/118899387/a815f9ef-1e3f-4fbc-a8e8-d220e5e20f74)


# Y VALUE :
![image](https://github.com/Yogabharathi3/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/118899387/5b4617cb-f596-4027-b4ca-86a04716c7db)
# PREDICTED VALUES :
![image](https://github.com/Yogabharathi3/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/118899387/96c43a4d-30b8-4fd3-8d86-5494235375db)


# ACCURACY :
![image](https://github.com/Yogabharathi3/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/118899387/4c057d40-d639-4d9f-8876-7f8a56452eeb)


# CONFUSION MATRIX :
![image](https://github.com/Yogabharathi3/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/118899387/2648598a-f8a2-4816-a33d-93294112a208)


# CLASSIFICATION REPORT :
![image](https://github.com/Yogabharathi3/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/118899387/566d6eb0-605c-46f2-973d-16c6fc7401a1)

## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
