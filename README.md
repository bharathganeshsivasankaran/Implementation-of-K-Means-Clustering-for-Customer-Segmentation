# EXN0-8 Implementation-of-K-Means-Clustering-for-Customer-Segmentation

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

5.Print the outputs and end the program

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Bharathganesh S
RegisterNumber:  212222230022
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1) (1).csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = [] #Within-Cluster sum of square.
for i in range(1,11):
  kmeans=KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```

## Output:
### Dataset:
![image](https://github.com/bharathganeshsivasankaran/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119478098/64d7dd97-a6c1-4269-bf9c-705ae507cef3)
### Dataset information:
![image](https://github.com/bharathganeshsivasankaran/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119478098/ea118279-2c4f-4ee4-956e-1325a769ffed)



![image](https://github.com/bharathganeshsivasankaran/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119478098/089c4581-44b3-45ac-948b-35035afce654)
### Elbow method graph (wcss vs each iteration):
![image](https://github.com/bharathganeshsivasankaran/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119478098/27b8ff91-0a80-4896-b074-198c272aa4e3)
### Cluster represnting customer segments-graph:
![image](https://github.com/bharathganeshsivasankaran/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119478098/4b7b5439-aaf3-4f6d-af76-f75be48a4618)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
