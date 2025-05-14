# EX-10:Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## AlgorithmImport required libraries and load the dataset.
1. Import required libraries and load the dataset.
2. Explore the dataset structure and contents.
3. Determine optimal number of clusters using the Elbow Method.
4. Apply KMeans clustering to the selected features.
5. Assign cluster labels to the original dataset.
6. Visualize the clusters using a scatter plot.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Ashwin Akash M
RegisterNumber:  212223230024
*/
import pandas as pd
df=pd.read_csv('Mall_Customers.csv')
df
df.head()
df.info()
from  sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
    kmeans=KMeans(n_clusters=i,init="k-means++")
    kmeans.fit(df.iloc[:,3:])
    wcss.append(kmeans.inertia_)
import matplotlib.pyplot as plt
plt.plot(range(1,11),wcss)
plt.title("Elbow method")
plt.xlabel("No. of Cluster")
plt.ylabel("wcss")
plt.show()
km=KMeans(n_clusters=5)
km.fit(df.iloc[:,3:])
km_pre=km.predict(df.iloc[:,3:])
km_pre
df["clusters"]=km_pre
df0=df[df["clusters"]==0]
df1=df[df["clusters"]==1]
df2=df[df["clusters"]==2]
df3=df[df["clusters"]==3]
df4=df[df["clusters"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],color="aqua")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],color="violet")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],color="red")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],color="orange")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],color="purple")
plt.show()
```

## Output:
![image](https://github.com/user-attachments/assets/4fddfaa0-758e-4c63-831c-1ea4505ef0ed)<br>
![image](https://github.com/user-attachments/assets/d94e24b1-6bfc-43ff-86f8-27ccf09bfcf6)<br>
![image](https://github.com/user-attachments/assets/a37e84a9-f321-4486-a0d1-36ac1c886238)<br>
![image](https://github.com/user-attachments/assets/93bea04b-1f3b-4fcd-a7ca-e77c42c4336b)<br>
![image](https://github.com/user-attachments/assets/250db8f0-f19c-49ab-b6c2-fbef3626a1ad)<br>
![image](https://github.com/user-attachments/assets/c5eb9d1a-91cc-4802-9d63-00bbcc64e275)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
