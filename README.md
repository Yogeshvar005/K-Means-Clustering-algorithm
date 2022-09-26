# Implementation of K-Means Clustering Algorithm
## Aim
To write a python program to implement K-Means Clustering Algorithm.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation

## Algorithm:

### Step1
Import the necessary packages using import statement.

### Step2
Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

### Step3
Plot a graph for the applicant income vs loan amount lot using sns.scatterplot.

### Step4
Obtain the kmeam clustering, display the clusters using .cluster_centers_ and the labels using .labels_ .

### Step5
Predict the k means using kmean.predict() method and display the result.

## Program:
```python
import pandas as pd 
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
import seaborn as sns
import warnings
warnings.filterwarnings('ignore')

data=pd.read_csv('clustering.csv')
print(data.head(2))

x1=data.loc[:,['ApplicantIncome','LoanAmount']]
print(x1.head(2))

x=x1.values
sns.scatterplot(x[:,0],x[:,1])
plt.xlabel('Income')
plt.ylabel('Loan')
plt.show()
KMeans = KMeans(n_clusters=4)
kmeans=KMeans.fit(x)

print('Cluster Centers: ',kmeans.cluster_centers_)
print('labels:',kmeans.labels_)

predicted_cluster=kmeans.predict([[9200,110]])
print('The cluster group for the ApplicantIncome 9200 and Loan Amount 110 is ',predicted_cluster)
```
## Output:
![output](k.png)
![output](m.png)

## Result
Thus the K-means clustering algorithm is implemented and predicted the cluster class using python program.