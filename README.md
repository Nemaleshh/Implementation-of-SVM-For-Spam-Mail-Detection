# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary python packages using import statements.

2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3. Split the dataset using train_test_split.

4. Calculate Y_Pred and accuracy.

5. Print all the outputs.

6. End the Program.


## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: Nemaleshwar H
RegisterNumber:  212223230142
*/
```
```py
import chardet
file='spam.csv'
with open (file,'rb') as rawdata:
    result = chardet.detect(rawdata.read(100000))
result

```
```py

import pandas as pd
data=pd.read_csv("spam.csv",encoding='windows-1252')

data.head()

```
```py

data.info()
```
```py
data.isnull().sum()
```
```py

x=data["v1"].values
y=data["v2"].values
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.3,random_state=0)

from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()

x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)
```
```py

from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred

```
```py

from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```
## Output:
![alt text](image1.png)
![alt text](image2.png)

![alt text](image3.png)
![alt text](image4.png)

![alt text](image5.png)

## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
