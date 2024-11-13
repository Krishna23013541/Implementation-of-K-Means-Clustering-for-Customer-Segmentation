# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required packages.
2. Import the dataset to work on.
3. From sklearn module import kmeans.
4. Define number of clusters to be made.
5. Assign the cluster values.
6. Plot the cluster using matplotlib.pyplot
7. End the program. 

## Program:

Program to implement the K Means Clustering for Customer Segmentation.

Developed by: KRISHNA KUMAR R

RegisterNumber: 212223230107

```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    Kmeans = KMeans(n_clusters = i,init = "k-means++")
    Kmeans.fit(data.iloc[:,3:])
    wcss.append(Kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
Km = KMeans(n_clusters = 5)
Km.fit(data.iloc[:,3:])
y_pred = Km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c = "red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c = "black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c = "blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c = "green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c = "magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
### Data Head
![image](https://github.com/user-attachments/assets/363e0848-08f0-4ac9-8bac-b7173f5ab37f)


### Data Information
![image](https://github.com/user-attachments/assets/ee778c25-e0e9-430e-bd7e-0d997108dcfc)


### Null Data
![image](https://github.com/user-attachments/assets/9fc66185-b38f-4a28-92a9-23f89f80a1a3)

### Graph
![image](https://github.com/user-attachments/assets/7708b5e2-a152-4484-8937-94547e9886a7)


### Prediction
![image](https://github.com/user-attachments/assets/763d9cf3-f45b-4a53-ab23-24818e0ae8c8)


### Customer Graph
![image](https://github.com/user-attachments/assets/2ec805f9-293b-415b-ac3a-a59bdc97dd86)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
