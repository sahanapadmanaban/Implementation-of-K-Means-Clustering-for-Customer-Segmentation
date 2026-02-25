# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:

1.Load the dataset and select the required features (Annual Income and Spending Score).


2.Choose the number of clusters (K) using the Elbow Method.

3.Initialize centroids and assign data points to the nearest centroid based on minimum distance.

4.Update the centroids by calculating the mean of each cluster and repeat the process until the centroids stop changing.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: P.SAHANA
RegisterNumber:  212225040355

import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("C:/Users/acer/Downloads/Mall_Customers.csv")

print(data.head())

print(data.info())

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No of Cluster")
plt.ylabel("wcss")
plt.title("Elbow Method")
plt.figure()

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

KMeans(n_clusters=5)

y_pred = km.predict(data.iloc[:,3:])
print("Predicted values: \n",y_pred)

data["cluster"]=y_pred
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
plt.show()

*/
```

## Output:

<img width="818" height="458" alt="image" src="https://github.com/user-attachments/assets/28526f0c-b2cc-49e4-8afd-35341538b556" />

<img width="797" height="702" alt="image" src="https://github.com/user-attachments/assets/04d7a865-dc0d-4c75-8ab8-a2ba4dc207dd" />


<img width="873" height="626" alt="image" src="https://github.com/user-attachments/assets/a4de23e6-6667-4995-8ae9-22e126839603" />

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
