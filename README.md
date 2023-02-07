# Customers-Segmentation
STP(Abbreviation for Segmentation,Targeting, Positioning) is a fundamental marketing framework. It can be applied to all areas of business and marketing activities. The process of dividing a population of customers into groups that share similar characteristics. Observations within the same group would have comparable purchasing behavior. Observations within the same group would respond similarly to different marketing activities.

The notebook focuses on how to perform customer segmentation, using a hands-on approach. It involves the application of hierarchical and flat clustering techniques for dividing customers into groups. It also features applying the Principal Components Analysis (PCA) to reduce the dimensionality of the problem, as well as combining PCA and K-means for an even more professional customer segmentation.

The dataset has 2000 obervations and 7 features. We applied some techniques to understand data and checked missing values and data types. The final pre-processing technique we applied to the dataset is standardization.

The number of segments is very challenging in K-means algorithm. The easiest way is the elbow method. I did a loop and run the K-Means algorithm from 1 to 11 clusters. Then, we can plot model results for this range of values and select the elbow of the curve as the number of clusters to use. The “elbow” of this graph is the point of inflection on the curve, and in this case is at the 4-cluster mark. To evaluate the performance of this model, we will use a metric called the silhouette score. This is a coefficient value that ranges from -1 to +1. A higher silhouette score is indicative of a better model.
```python
print(silhouette_score(scaled_features, kmeans.labels_, metric='euclidean'))
```
The silhouette coefficient of this model is 0.44, indicating reasonable cluster separation.0.26879180394522123

![Elbow Method][identifier]

## Setup
1. install Python IDE on your device like Anaconda which includes Jupyter Notebook to easily run the code provided and display visualizations at each step. 
2. Also, make sure to have the following libraries installed — Numpy, Pandas, Matplotlib, Seaborn, Scikit-Learn, Kneed, and Scipy.

[identifier]:https://github.com/Hussein-Mazaar/Customers-Segmentation/blob/main/wcss.jpg
