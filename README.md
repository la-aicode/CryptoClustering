# Cryptocurrency Clustering using K-Means and PCA

This project demonstrates how to cluster cryptocurrencies based on their market data using the K-Means clustering algorithm and Principal Component Analysis (PCA) for dimensionality reduction.

## Overview

The code performs the following steps:

1. **Data Loading and Preprocessing:**
   - Loads cryptocurrency market data from a CSV file.
   - Sets the 'coin_id' column as the index of the DataFrame.
   - Scales the data using `StandardScaler` to ensure features with different scales do not disproportionately influence the clustering.

2. **Elbow Method for Optimal k:**
   - Creates a for loop to compute the inertia (within-cluster sum of squares) for different values of `k` (number of clusters) using the KMeans algorithm.
   - Generates an elbow curve plot to visually identify the optimal `k` value that balances cluster compactness and model complexity.

3. **K-Means Clustering:**
   - Initializes a KMeans model with the determined optimal `k` value.
   - Fits the model to the scaled data.
   - Predicts cluster assignments for each cryptocurrency.
   - Adds a new column to the DataFrame to store the predicted clusters.

4. **Principal Component Analysis (PCA):**
   - Creates a PCA model instance with `n_components=3` to reduce the data to three principal components.
   - Applies the PCA model using `fit_transform` on the scaled data.
   - Creates a new DataFrame with the PCA data.
   - Determines the explained variance of each principal component.

5. **Clustering with PCA Data:**
   - Repeats steps 2 and 3 using the PCA data to find the optimal `k` value and perform clustering in the reduced-dimensional space.
   - Adds a new column to the PCA DataFrame to store the predicted clusters.

6. **Visualization:**
   - Generates scatter plots to visualize the clusters in both the original feature space and the reduced PCA space.
   - Identifies the features with the strongest influence on each principal component by examining the component loadings.

## Dependencies

- pandas
- scikit-learn
- matplotlib
- hvplot

## Usage

1. Ensure you have the necessary dependencies installed.
2. Replace `/resources/crypto_market_data.csv` with the actual path to your data file.
3. Execute the code cells in the notebook sequentially.
4. Analyze the results, including the elbow curves, cluster assignments, and visualizations, to gain insights into the cryptocurrency clusters.

## Observations and Insights

- The elbow method helps in finding an appropriate value for `k`, the number of clusters.
- PCA reduces the dimensionality of the data while preserving important information.
- Clustering using PCA data might result in slightly different cluster assignments compared to using the original data.
- Examining component loadings reveals the features that have the strongest influence on each principal component.

## Future Enhancements

- Explore different clustering algorithms, such as hierarchical clustering or DBSCAN.
- Experiment with alternative dimensionality reduction techniques.
- Evaluate cluster quality using metrics like silhouette score.
- Develop interactive visualizations for exploring the clusters in more detail.

## Disclaimer

This project is for educational purposes and should not be considered financial advice. Cryptocurrency investments are speculative and involve risk.