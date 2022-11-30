# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:

Hardware – PCs
Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:

Step1:
Import the necessary packages using import statement.

Step2:
Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

Step3:
Import KMeans and use for loop to cluster the data.

Step4:
Predict the cluster and plot data graphs.

Step5:
Print the outputs and end the program

## Program:
Developed by: Guhanandan V

Register Number: 212221220014

~~~

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers (1).csv")

data.head()
data.info()
data.isnull()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss= [] 

for i in range(1,11):
  kmeans=KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="black",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="cyan",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="yellow",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="green",label="cluster4")
plt.legend()
plt.title("Customer Segments")

~~~

## Output:
### Data Head:

![o1](https://user-images.githubusercontent.com/100425381/204845732-5a6eef26-5a5e-4022-91d0-83a47b64e27a.jpg)


### Checking For Null Data:

![o3](https://user-images.githubusercontent.com/100425381/204845749-0b5ddab0-a26b-4e07-ba6b-37176a97f7dc.jpg)


### Data Information:

![o7](https://user-images.githubusercontent.com/100425381/204845765-b4d7b5c9-9ee9-4d28-94af-bc8437f4937b.jpg)


### Within Cluster Sum of Square (WCSS):

![o5](https://user-images.githubusercontent.com/100425381/204845775-3c331478-e815-48fb-af48-47294b2a4d57.jpg)


### Elbow Method:

![o4](https://user-images.githubusercontent.com/100425381/204845794-d5c9b9f3-ce16-47f1-abc3-556456f91061.jpg)


### K-means:

![o8](https://user-images.githubusercontent.com/100425381/204845956-4bcda332-f4d1-4a63-8a4b-0ea700d6f721.jpg)


### Cluster:

![o6](https://user-images.githubusercontent.com/100425381/204845941-3fe9cb7e-93f4-4b8a-bb7d-62b0fcf71d94.jpg)


## Result:

Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
