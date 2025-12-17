# Module 4 Summary and Highlights
Congratulations! You have completed this lesson. At this point in the course, you know: 

- Clustering is a machine learning technique used to group data based on similarity, with applications in customer segmentation and anomaly detection.

- Hierarchical clustering can be 
   - DIVISIVE (TOP-down) or 
   - AGGLOMERATIVE (BOTTOM-up) and produces a dendrogram to visualize the cluster hierarchy.
![Hierarchical clustering](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Hierarchical%20clustering.png)

- K-means clustering partitions data into clusters based on the distance between data points and centroids but struggles with imbalanced or non-convex clusters.

- Heuristic methods such as silhouette analysis, the elbow method, and the Davies-Bouldin Index help assess k-means performance.
![Heuristic methods to determine K-means](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Heuristic%20methods%20to%20determine%20K-means.png)

- What is the purpose of the Elbow Method in K-Means Clustering?<br/>
To gauge performance by plotting the OBJECTIVE FUNCTION for different cluster numbers.

- How does the Davies-Bouldin INDEX evaluate K-Means?<br/>
By measuring each cluster's average similarity RATIO with the most similar cluster.

- What is the goal of K-Means regarding within-cluster variance?<br/>
To MINimize it.

- What does the centroid represent in K-Means Clustering?<br/>
The average position of all points in a cluster.
![Centroid](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/Centroid.png)

- What is the primary function of K-Means Clustering?<br/>
Partitioning a dataset into similar groups based on centroid distance.
![K-Means Clustering](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/K-Means%20Clustering.png)

- What is the initial step in the K-Means Algorithm Process?<br/>
Choosing the number of clusters and selecting starting centroids.

```
k_means = KMeans(init = "k-means++", n_clusters = 4, n_init = 12)
# The KMeans class has many parameters that can be used, but we will be using these three:
# 1.1. init: Initialization method of the centroids.
# 1.2.1 Value will be: k-means++
# 1.2.2 k-means++: Selects initial cluster centres for k-means clustering in a smart way to speed up convergence.
# 2.1 n_clusters: The number of clusters to form as well as the number of centroids to generate.
# 2.2 Value will be: 4 (since we have 4 centres)
# 3.1 n_init: Number of times the k-means algorithm will be run with different centroid seeds. The final results will be the best output of n_init consecutive runs in terms of inertia.
# 3.2 Value will be: 12
```

- Which of the following scenarios is k-means best suited for?<br/>
Segmenting customers based on purchasing behavior


## Density-Based Spatial Clustering of Applications with Noise (DBSCAN) 

- DBSCAN is a density-based algorithm that creates clusters based on density and works well with natural, irregular patterns.
![DBSCAN](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/DBSCAN.png)

- What is a core point in DBSCAN?<br/>
A point with a MINIMUM number of neighbors within its radius.

```
min_samples=3 # minimum number of samples needed to form a neighbourhood
eps=1.0 # neighbourhood search radius
metric='euclidean' # distance measure 

dbscan = DBSCAN(eps=eps, min_samples=min_samples, metric=metric).fit(coords_scaled)
```

- What is the key feature of DBSCAN regarding cluster shapes?<br/>
Can discover clusters of any shape

- What is a border point in DBSCAN?<br/>
A point within a core point's neighborhood but not a core point.

- What is a noise point in DBSCAN?<br/>
A point isolated from core point neighborhoods.

- Which of the following scenarios is Density-Based Spatial Clustering of Applications with Noise (DBSCAN) best suited for?<br/>
Identifying geographic areas with high crime rates


## Hierarchical Density-Based Spatial Clustering of Applications with Noise (HDBSCAN)

- HDBSCAN is a variant of DBSCAN that does NOT require PARAMETERS and uses cluster stability to find clusters.

```
min_samples=None
min_cluster_size=3
hdb = hdbscan.HDBSCAN(min_samples=min_samples, min_cluster_size=min_cluster_size, metric='euclidean')  # You can adjust parameters as needed
```

- How is a hierarchical tree constructed in HDBSCAN?<br/>
By lowering the density threshold to agglomerate clusters.

![HDBSCAN](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/HDBSCAN.png)

![DBSCAN and HDBSCAN](https://github.com/tuethu/IBM-Data-Science-Course/blob/main/Course%209_Machine%20Learning%20with%20Python/Media/DBSCAN%20and%20HDBSCAN.png)


- How does Hierarchical Density-Based Spatial Clustering of Applications with Noise (HDBSCAN) improve upon the DBSCAN algorithm?<br/>
HDBSCAN can cluster data with varying densities.



- Dimension reduction simplifies data structure, improves clustering outcomes, and is useful in tasks such as face recognition (using eigenfaces).

- Clustering and dimension reduction work together to improve model performance by reducing noise and simplifying feature selection.

PCA, a linear dimensionality reduction method, minimizes information loss while reducing dimensionality and noise in data.

- t-SNE and UMAP are other dimensionality reduction techniques that map high-dimensional data into lower-dimensional spaces for visualization and analysis.

