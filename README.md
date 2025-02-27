# README: Crypto Clustering Project

## Overview

This project aims to analyze cryptocurrency market data using K-Means clustering and Principal Component Analysis (PCA) to identify patterns in cryptocurrency performance. The project is structured to follow a step-by-step approach, starting from loading data, normalizing it, finding the optimal number of clusters, and finally visualizing the results.

## Project Workflow

### 1. Preparing the Data

- Loaded **crypto\_market\_data.csv** into a Pandas DataFrame.
- Generated summary statistics and visualized data distribution.
- Standardized the data using `StandardScaler()` from scikit-learn.



### 2. Finding the Best k for K-Means Clustering

- Used the elbow method to determine the best number of clusters (`k`):
  - Created a range of k values from **1 to 11**.
  - Computed inertia for each k and stored the values.
  - Plotted the Elbow Curve to determine the optimal k.



### 3. Clustering Cryptocurrencies Using K-Means

- Initialized the K-Means model with the best `k`.
- Fitted the model to the **scaled DataFrame** and predicted clusters.
- Added the cluster labels to the DataFrame.
- Created a scatter plot using **hvPlot**:
  - **X-axis**: `price_change_percentage_24h`
  - **Y-axis**: `price_change_percentage_7d`



### 4. Optimizing Clusters with PCA

- Applied **Principal Component Analysis (PCA)** to reduce features to **three principal components**.
- Retrieved the explained variance to measure the information captured.
- Created a new DataFrame with the PCA-transformed data, keeping **coin\_id** as the index.

### 5. Finding the Best k for PCA-Reduced Data

- Repeated the **elbow method** using the **PCA DataFrame**.
- Determined the best value for `k` using inertia and visualized the results.

### 6. Clustering Cryptocurrencies Using PCA-Reduced Data

- Initialized K-Means with the best `k` for PCA-reduced data.
- Fitted the model and predicted cluster labels.
- Created a new DataFrame including the predicted clusters.
- Created a scatter plot using **hvPlot**:
  - **X-axis**: `PC1`
  - **Y-axis**: `PC2`
  - Colored by cluster labels and hovered over **coin\_id**.



