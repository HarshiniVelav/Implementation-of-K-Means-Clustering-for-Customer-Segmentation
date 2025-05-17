# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplotlib.pyplot
2. Read the dataset and transform it
3. Import KMeans and fit the data in the model
4. Plot the Cluster graph

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: HARSHINI.V
RegisterNumber:  212224040109
*/

import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv(r"C:\Users\admin\Downloads\Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
    kmeans = KMeans(n_clusters=i, init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")

km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred

df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster 0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster 1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster 2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster 3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster 4")

plt.legend()
plt.title("customer segmentation")

```

## Output:

![Screenshot 2025-05-17 120724](https://github.com/user-attachments/assets/2f3736ab-bfbd-49ea-bce9-9f591a9288d9)

![Screenshot 2025-05-17 120732](https://github.com/user-attachments/assets/b2af5d37-450b-4623-abdb-3dfa17072be6)

![Screenshot 2025-05-17 120738](https://github.com/user-attachments/assets/91d0b557-8ad7-48aa-8cdd-cffbf842f6e9)

![Screenshot 2025-05-17 120817](https://github.com/user-attachments/assets/61fc79ed-9331-4b58-b3a6-9878c686c24c)

![Screenshot 2025-05-17 120824](https://github.com/user-attachments/assets/8435bd5b-c822-4dfc-96f1-28c9f2a88d6b)


![Screenshot 2025-05-17 120829](https://github.com/user-attachments/assets/d985771c-0638-4cb6-874b-8369b43e893d)


![Screenshot 2025-05-17 120839](https://github.com/user-attachments/assets/8a0cfaa9-ff6c-4b0f-b669-dc9142340ddd)










## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
