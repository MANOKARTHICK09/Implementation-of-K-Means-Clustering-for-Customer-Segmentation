# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.

2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3. Import KMeans and use for loop to cluster the data.

4. Predict the cluster and plot data graphs.

5. Print the outputs and end the program
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: MANO KARTHICK S
RegisterNumber:212222230077
*/
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []  #Within-Cluster sum of square.
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
plt.title("Customer Segments")
```

## Output:
### DATA.HEAD():
![image](https://github.com/MANOKARTHICK09/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121785458/863499a7-7269-49f4-a028-6d93cf9dfdf8)


### DATA.INF0():
![image](https://github.com/MANOKARTHICK09/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121785458/d071035c-253d-4f79-8aa6-ab17ff600f04)


### DATA.ISNULL().SUM():
![image](https://github.com/MANOKARTHICK09/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121785458/87c370ba-9ce4-4d7b-8fa1-b258ebc845ec)


### PLOT USING ELBOW METHOD:
![image](https://github.com/MANOKARTHICK09/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121785458/28b67b16-25c0-48d7-82d9-0a4a2dc1a320)


### K-MEANS CLUSTERING:
![image](https://github.com/MANOKARTHICK09/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121785458/2f6d2f0b-b1ae-4cbb-a1f6-d31294b705ee)


### Y_PRED ARRAY:
![image](https://github.com/MANOKARTHICK09/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121785458/28c3fa2e-71a8-4660-8c15-a41f7fe8325c)


### CUSTOMER SEGMENT
![image](https://github.com/MANOKARTHICK09/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121785458/003ee4c8-341a-409f-938a-4c5ed5b5caf3)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
