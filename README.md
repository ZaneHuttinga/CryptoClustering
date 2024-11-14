# Crypto Clustering
Data Visualization and Analytics Boot Camp Challenge 19

This project uses machine learning (in particular, unsupervised learning) to predict whether various cryptocurrencies are affected by 24-hour or 7-day price changes.

## Predictions using unsupervised learning
The main file (Crypto_Clustering.ipynb) first reads in data from the CSV file Resources/crypto_market_data.csv and loads it into a DataFrame. To prepare the data, we first use the StandardScaler() module from the scikit-learn Python library to normalize the data. From this we create a new DataFrame, which we will refer to as the 'Scaled DataFrame'. Later, we run a Principle Component Analysis (PCA) on this DataFrame to reduce the number of features to 3. We refer to the resulting DataFrame as the 'PCA DataFrame'. The latter step requires the PCA module from scikit-learn.

We perform the following sequence on both the Scaled and PCA DataFrames:
1. Use the elbow method to find the ideal value of k for a K-means model. This involves creating a line chart of inertia versus the value of k.
2. Fit the K-means model (using the KMeans module from scikit-learn) to the DataFrame for the chosen value of k.
3. Predict the clusters to group the cryptocurrencies in the DataFrame.
4. Create a scatter plot showing the clusters. For this we use the Python library hvplot.

## Final comparison
After analyzing the two DataFrames individually, we create two composite plots: one for the inertia plots and one for the scatter plots. We use the latter to assess the impact of using fewer features when using K-Means.