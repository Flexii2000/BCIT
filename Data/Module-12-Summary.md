# Chapter 10 

## Clustering Basics
**Unsupervised task:** 
> - group similar records
> - maximize within-cluster similarity
> - minimize between-cluster similarity 

- Used for segmentation, anomaly detection, dimensionality reduction.  

- Clustering often performed as preliminary step in data mining process

- Clustering results used as input to other data mining techniques


## Measuring Similarity
**Numeric:**
- Euclidean
- Manhattan
- Minkowski distances:
  
  $$
d_{\text{City-Block}}(\mathbf{x}, \mathbf{y}) = \sum_i |x_i - y_i| \quad\quad
d_{\text{Minkowski}}(\mathbf{x}, \mathbf{y}) = \sum_i |x_i - y_i|^{\,q}
$$


**Categorical: different(x,y)**
  
**Normalize before clustering (Min-Max or Z-score)**  

## Clustering Tasks in Business

>Target marketing for niche product, without large marketing budget
>
> Accounting auditing: Segment behavior into benign and suspicious categories
> 
> As a dimension-reduction tool when data set has hundreds of attributes
> 
> Gene expression clustering, where genes exhibit similar characteristic

## Hierarchical Clustering

*Clustering is either Hierarchical or Non-Hierarchical *

### Three Types
- *dendogram* -> Treelike cluster Structure
- **Agglomerative (bottom-up):** each record starts as its own cluster → merge closest pairs -> until only one single cluster left
- **Divisive (top-down):** start with all in one cluster → split most dissimilar -> continue until each record represents a single cluster

**Agglomerative is most common.**  


### Linkage Methods
- **Single linkage:** minimum distance between cluster members → long “chains.”  
- **Complete linkage:** maximum distance → compact, spherical clusters.  

- **Average linkage:** average pairwise distance → stable clusters.  


## k-Means Clustering
### Algorithm
1. Choose k.  
2. Assign k random initial centroids.  
3. Assign each record to closest centroid.  
4. Recompute centroids.  
5. Repeat until convergence (no movement or MSE reduction minimal).  

### Objective
- Minimize within-cluster variation (MSE), maximize between-cluster variation (MSB).  
- $\text{Pseudo-F statistic} = \frac {MSB} {MSE}$ (higher is better).  


### Notes
- k-Means may find **local** optimum → use multiple initializations.  
- Choosing k: use pseudo-F, domain knowledge, or algorithms like BIRCH.  
- Sensitive to scaling; normalize first.  

[^1]

## Cluster Profiling
- Understand meaning of clusters by comparing attribute distributions (e.g., International Plan, Voice Mail Plan).  
- Used for downstream prediction tasks like churn.  

[^1]: **BIRCH (Balanced Iterative Reducing and Clustering using Hierarchies)** is an efficient clustering algorithm that incrementally builds a compact tree structure (CF-tree) to summarize large datasets. It clusters data in a single scan, automatically suggests a good number of clusters, and is designed for very large datasets where k-means would be too slow.
