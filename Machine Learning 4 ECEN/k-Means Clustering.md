[[Clustering]] algorithm with the basic idea: **use distance to group together similar instances**

## Methodology
1. Choose $k$ hyperparameter for number of clusters to create
2. Assign $k$ random points as estimate of center clusters, $c_k$
	1. Here we are randomly initializing $k$ centroids
3. Assign all datapoints to the closest centroid
	1. $a_i=\text{argmin}_k(\text{dist}(x_i,c_k))$
	2. Equation means to choose among $[c_1,\dots,c_k]$ the mean which minimizes the distance between $x_i$ and $c_k$ and assign that value of $[1\dots k]$ to $a_i$
4. Choose a new centroid, which is the mean of all datapoints in each cluster
	1. $c_k=\frac{1}{|i:a_i=k|}\sum\limits_{i:a_i=k}x_i$
	2. This equation means select the points which are assigned to the mean point $c_k$ (i.e. those with $a_i=k$), and average these points and that new value to $c_k$ 
5. Go back to Step 3, and continue until no points' assignments change

## Choosing Correct $k$
- Result depends substantially on $k$ 
- For small datasets, experiment with $k$
- For larger datasets, there are techniques to assist in choosing the best $k$ 

## Initialization
- Using different initializations leads to different solutions 
- Most k-means solvers include initialization heuristics to minimize these issues

## Python Code
```python
from sklearn.cluster import KMeans
import numpy as np
X = np.array(([1,2],[1,4],[1,0],[10,2],[10,4],[10,0]))
kmeans = KMeans(n_clusters=2,random_state=0).fit(X)
k_means.labels_
#>>> array([1,1,1,0,0,0],dtype=int32)
kmeans.predict([[0,0],[12,3]])
#>>> array([1,0])
k_means.cluster_centers_
#>>> array([[10., 2.], [1., 2.]])
```

