[PCA](https://medium.com/@amulya_k/principal-component-analysis-pca-in-data-analysis-unveiling-the-power-of-dimensionality-065fb35a21e9)
- **Why we don't like high-dimensional data**
1. Computational Complexity
2. Overfitting

- **What is PCA**
PCA is a dimensionality reduction technique that addresses these challenges by transforming the original variables into a new set of variables, known as *principal components*.

These principal components are linear combinations of the original variables and are orthogonal to each other, meaning they are uncorrelated.

- **How PCA works**
1. Centering the data
The first step in PCA is to center the data by subtracting the mean of each variable from the data points. This step ensures that the principal components are centered at the origin.

2. Covariance Matrix
PCA calculates the covariance matrix of the centered data. The covariance matrix measures the relationships between variables.

3. Eigen decomposition
The next step is to perform eigendecomposition on the covariance matrix. This decomposition results in eigenvalues and eigenvectors.

4. Selecting Principal Components
PCA sorts the eigenvalues in decreasing order.
The eigenvalues represent the variance explained by each principal component.
By selecting a subset of the principal components, you can reduce dimensionality while retaining most of the variance in the data.

5. Transform the data
Finally, PCA transforms the original data using the selected principal components. This transformation results in a new dataset with reduced dimensionality.

- **Practical Considerations and Tips**
**1. Standardization:** Before applying PCA, it’s essential to standardize the data to ensure that all variables have the same scale. Standardization prevents variables with larger scales from dominating the principal components.

**2. Choosing the Number of Principal Components:** Selecting the right number of principal components is crucial. You can use metrics like explained variance or scree plots to determine how many components to retain.

- **Applications**