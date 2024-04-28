# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:

To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:

1. Hardware – PCs
   
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:

1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program

## Program:

```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: S Kantha Sishanth
RegisterNumber: 212222100020
```

```py
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
  kmeans = KMeans (n_clusters = i, init ="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("no of cluster")
plt.ylabel("wcss")
plt.title("Elbow Metthod")
km=KMeans(n_clusters=5)
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
plt.title("Customer Segments")
```

## Output:

### Dataset:

![ml8_1](https://github.com/Skanthasishanth/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118298456/2df1e2d8-f78c-459f-a348-8abd1a59c9e5)


### Dataset information:

![ml8_2](https://github.com/Skanthasishanth/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118298456/b49bfe21-c45a-467c-a2c0-cfec9d10e616)


![ml8_3](https://github.com/Skanthasishanth/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118298456/bfe6759c-cc5d-47c8-996e-e300ccdde824)

### Elbow method graph (wcss vs each iteration):

![ml8_4](https://github.com/Skanthasishanth/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118298456/d347bb7b-a61e-4fab-9bcd-7b47bcb06214)


### Cluster representing customer segments-graph:

![ml8_5](https://github.com/Skanthasishanth/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118298456/0ff3219c-4360-4d67-abca-a872c6537c95)

## Result:

Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
