# Customers-Segmentation
STP(Abbreviation for Segmentation,Targeting, Positioning) is a fundamental marketing framework. It can be applied to all areas of business and marketing activities. The process of dividing a population of customers into groups that share similar characteristics. Observations within the same group would have comparable purchasing behavior. Observations within the same group would respond similarly to different marketing activities.

The notebook focuses on how to perform customer segmentation, using a hands-on approach. It involves the application of hierarchical and flat clustering techniques for dividing customers into groups. It also features applying the Principal Components Analysis (PCA) to reduce the dimensionality of the problem, as well as combining PCA and K-means for an even more professional customer segmentation.

The dataset has 2000 obervations and 7 features. We applied some techniques to understand data and checked missing values and data types. The final pre-processing technique we applied to the dataset is standardization.

The number of segments is very challenging in K-means algorithm. The easiest way is the elbow method. I did a loop and run the K-Means algorithm from 1 to 11 clusters. Then, we can plot model results for this range of values and select the elbow of the curve as the number of clusters to use. The “elbow” of this graph is the point of inflection on the curve called inertia. We appended the inertia score or the Within-Cluster-Sum-of-Squares (WCSS), then plot a graph of inertia vs number of clusters. WCSS or inertia is the sum of squares of the distances of each data point in all clusters to their respective centroids.





To evaluate the performance of this model, we will use a metric called the silhouette score. This is a coefficient value that ranges from -1 to +1. A higher silhouette score is indicative of a better model.
```python
print(silhouette_score(scaled_features, kmeans.labels_, metric='euclidean'))
```
The silhouette coefficient of this model is 0.267, indicating reasonable cluster separation.

## K-means: Expectation–Maximization
Expectation–maximization (E–M) is a powerful algorithm that comes up in a variety of contexts within data science. k-means is a particularly simple and easy-to-understand application of the algorithm, and we will walk through it briefly here. In short, the expectation–maximization approach here consists of the following procedure:

1. Guess some cluster centers
2. Repeat until converged
    1.E-Step: assign points to the nearest cluster center
    2. M-Step: set the cluster centers to the mean
Here the "E-step" or "Expectation step" is so-named because it involves updating our expectation of which cluster each point belongs to. The "M-step" or "Maximization step" is so-named because it involves maximizing some fitness function that defines the location of the cluster centers—in this case, that maximization is accomplished by taking a simple mean of the data in each cluster.

![Elbow Method][identifier]

## Setup
1. install Python IDE on your device like Anaconda which includes Jupyter Notebook to easily run the code provided and display visualizations at each step. 
2. Also, make sure to have the following libraries installed — Numpy, Pandas, Matplotlib, Seaborn, Scikit-Learn, Kneed, and Scipy.

[identifier]:https://github.com/Hussein-Mazaar/Customers-Segmentation/blob/main/wcss.jpg
