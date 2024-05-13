# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: DHARMALINGAM S
RegisterNumber:  212223040037
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("C:/Users/Aadhi/OneDrive/Documents/Software Engineering/Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="pink",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="black",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:
![K Means Clustering for Customer Segmentation](sam.png)
![image](https://github.com/Dharma23012432/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152275002/f318ed8f-c797-4033-9c91-2a19cb0bc6d3)
![image](https://github.com/Dharma23012432/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152275002/856eaa55-701f-4486-a86e-e0faccafb4b1)
![image](https://github.com/Dharma23012432/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152275002/d448c85d-a00c-43f9-a408-16905587dd14)
![image](https://github.com/Dharma23012432/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152275002/4e8a1434-60c4-4956-8118-f9f9c4dc4754)
![image](https://github.com/Dharma23012432/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152275002/7115f90f-f31d-4eb9-b573-8da63ed0c30c)
![image](https://github.com/Dharma23012432/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152275002/d2df47ee-e520-41f2-9122-69f14e0eed4d)
![image](https://github.com/Dharma23012432/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152275002/7526c06c-cc31-4b55-a0c0-c0b4864e10a6)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
