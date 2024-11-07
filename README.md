# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary python packages using import statements.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Split the dataset using train_test_split.

4.Calculate Y_Pred and accuracy.

5.Print all the outputs.

6.End the Program. 

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: VIMALA SAHANA W
RegisterNumber:212223040241  
*/
import chardet
file='spam.csv'
with open (file,'rb') as rawdata:
    result=chardet.detect(rawdata.read(100000))
result
import pandas as pd
data=pd.read_csv("spam.csv",encoding='Windows-1252')
data.head()
data.info()
data.isnull().sum()
X=data["v1"].values
y=data["v2"].values
from sklearn.model_selection import train_test_split
X_train,X_test,y_train,y_test=train_test_split(X,y,test_size=0.2,random_state=0
from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
X_train=cv.fit_transform(X_train)
X_test=cv.transform(X_test)
from sklearn.svm import SVC
svc=SVC()
svc.fit(X_train,y_train)
y_pred=svc.predict(X_test)
y_pred
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```

## Output:
![Screenshot 2024-11-07 221819](https://github.com/user-attachments/assets/a36fcc3a-7a63-4480-90ea-81be66b84d90)
![Screenshot 2024-11-07 221830](https://github.com/user-attachments/assets/9e05d90e-b37e-4470-ba46-5e993a0683de)
![Screenshot 2024-11-07 222730](https://github.com/user-attachments/assets/406e344c-96e8-46ee-be6a-2d668a30ba7a)
![Screenshot 2024-11-07 221845](https://github.com/user-attachments/assets/ff0b0651-98a7-4a03-9ae6-5457a913fe5d)
![Screenshot 2024-11-07 221855](https://github.com/user-attachments/assets/585ed79b-72d6-4e7f-bd49-2973899c9049)
![Screenshot 2024-11-07 221902](https://github.com/user-attachments/assets/bc150ee8-8768-40de-862a-751ef4b0f9fb)







## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
