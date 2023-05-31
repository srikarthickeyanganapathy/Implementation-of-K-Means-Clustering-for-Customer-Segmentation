# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas as pd and matplotlib.pyplot as plt
2. Get the info and also obtain the sum of any null values
3. Importing KMeans from sklearn.cluster we group the similar datas
4. Grouping similar datas gives us a elbow shaped graph which is called the Elbow method. 5.Print the number of clusters obtained
5. Giving the clustered data differnet colors and presenting as a scatter plot
6. Print the obtained graph.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SRI KARTHICKEYAN GANAPATHY
RegisterNumber:  212222240102
*/

import pandas as pd
import matplotlib.pyplot as plt
data =pd.read_csv("/content/Mall_Customers (1).csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
print("K-Means")
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
print("Array:")
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="pink",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
print("Customer Segments")
print("Customer Segement")
plt.legend()
plt.title("Customer Segments")
```

## Output:
### data.head():
![241162689-0b8c9403-fb30-4532-a512-04fc87785e81](https://github.com/srikarthickeyanganapathy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393842/96a1894f-9316-4457-b8ed-8873d312168a)
### data.info():
![241163239-e2bedec8-54c9-4817-b446-e8c352df6dc6](https://github.com/srikarthickeyanganapathy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393842/da231af2-1e66-419d-a700-1fc5545c558d)
### data.isnull().sum():
![241163429-bf25fca5-8621-4b90-8e17-ec3503188ea2](https://github.com/srikarthickeyanganapathy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393842/294be9f6-1141-4959-8a63-c774cd0405df)
### Elbow method Graph:
![241165583-8a3551d3-c8e7-42d0-8eeb-bd8d81da0f9e](https://github.com/srikarthickeyanganapathy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393842/ffadebd5-867b-4992-94d5-3ef9f396d8bf)
### K-means Cluster:
![241165989-79b78b50-5c07-404d-b4af-ae5c30f4fed0](https://github.com/srikarthickeyanganapathy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393842/5660085d-d17b-4326-aeb2-ee6bd3c45c3c)
### y_pred:
![241166103-eae6adc9-6d9e-46c3-9483-c802d1c7892c](https://github.com/srikarthickeyanganapathy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393842/5f6b1837-5ee4-4634-bac6-20946ce1e328)
### Customer segments Graph:
![241166539-8fe78e9b-2ee9-4304-8d88-d88c51204b7e](https://github.com/srikarthickeyanganapathy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393842/f8a1c282-8c6a-4f8c-b72d-c8f94f0fe6c4)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
