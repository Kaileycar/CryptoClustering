# Crypto Clustering

This assignment works with Unsupervised Learning, specifically the K-Means Algorithm and PCA. You will start  
by findingthe best number of clusters by using K-means and the original dataset and then making a scatter plot  
of those results. The second part is to incorporate PCA and use the K-Means algorithm on the dataset converted  
to PCA and then make a scater plot of those results. At the end, you will compare each plot with one another  
and analyze your findings.

The data we will be using is `Crypto Currency` data  

---

## About

This assignment is broken up into three parts. The first part will be to determine the best value for k using  
the **original** dataset. Make sure to create an elbow chart and use the optimal value of k for the number of  
clusters. Afterwards, cluster your predictions and plot them in a scatter plot using `hvplot`.  The second  
part of this assignment is to find the best value for k using the **PCA** data. Create an elbow chart and use  
the optimal value for k for the number of clusters. Cluster your predictions, aswell, and create another   
scatter plot using `hvplot`. Finally, the last part is to compare each of the visuals to one another. After  
you have done so, analyze and answer the questions being asked.  

---

## Getting Started

  1. Import the [Starter Code](https://github.com/Kaileycar/CryptoClustering/files/12655037/Starter_Code.zip) for this assignment.
  2. Rename the `Crypto_Clustering_starter_code.ipynb` file as `Crypto_Clustering.ipynb`.  
  3. Load the c`rypto_market_data.csv` into a DataFrame.
  4. Get the summary statistics and plot the data.

### Prepare the Data

  1. Standardize the data using `StandardScaler()`.
  2. Create a new DataFrame with the standardized data
     * Set the index to the `coin_id` of the original dataset.

---

## Usage

### Part 1: Find the Best Value for k Using the Original Scaled DataFrame

Use the elbow method to find the best value for `k` using the following steps:  
  * Create a list with the number of k values from 1 to 11.
  * Create an empty list to store the inertia values.
  * Create a `for` loop to compute the inertia with each possible value of `k`.
  * Create a dictionary with the data to plot the elbow curve.
  * Plot a line chart with all the inertia values computed with the different values of `k` to visually identify
    the optimal value for `k`.

*Answer the following question*: What is the best value for `k`?  

**The Elbow Chart should look like this:**    
![Screenshot 2023-09-18 at 7 00 31 PM](https://github.com/Kaileycar/CryptoClustering/assets/130424499/e1171f8b-235c-42f4-b39b-71da18795c47)  

### Cluster Cryptocurrencies with K-Means using the Original Scaled Data

Use the following steps to cluster the cryptocurrencies for the best value for `k` on the original scaled data:  
  * `Initialize` the K-means model with the best value for `k`.
  * `Fit` the K-means model using the original scaled DataFrame.
  * `Predict` the clusters to group the cryptocurrencies using the original scaled DataFrame.
  * Create a `copy` of the original data and add a new column with the predicted clusters.
  * Create a `scatter` plot using hvPlot as follows:
      * Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".  
      * Color the graph points with the labels found using K-means.  
      * Add the "coin_id" column in the `hover_cols` parameter to identify the cryptocurrency represented by each data point.  

**The Scatter Chart should look like this:**  
![Screenshot 2023-09-18 at 7 00 48 PM](https://github.com/Kaileycar/CryptoClustering/assets/130424499/823f76fc-bd35-489f-9b9d-2ab16a4c1af2)  

### Part 2: Optimize Clusters with PCA

  * Using the **original** scaled DataFrame, perform a `PCA` and reduce the features to *three* principal components.
  * Retrieve the `explained variance`.
  * Create a new DataFrame with the PCA data and set the `"coin_id"` index from the original DataFrame as the
     index for the new DataFrame.

### Find the Best Value for k Using the PCA Data

  * Use the same steps as above, but use the new PCA DataFrame to `initialize`, `fit`, and `predict`.
  * Plot a line chart with all the inertia values computed with the different values of `k` to visually identify
    the optimal value for `k`.

*Answer the following question*: What is the best value for `k`?  

**The Elbow Chart should look like this:**  
![Screenshot 2023-09-18 at 7 01 06 PM](https://github.com/Kaileycar/CryptoClustering/assets/130424499/9ef0ca91-06aa-4933-9ddd-fc1969d7edeb)  

### Cluster Cryptocurrencies with K-Means using the PCA Data  

  * Use the same steps as above to create a scatter chart for the cluster group.
  * Set the x-axis as "PC1" and the y-axis as "PC2".

**The Scatter Chart should look like this:**  
![Screenshot 2023-09-18 at 7 01 17 PM](https://github.com/Kaileycar/CryptoClustering/assets/130424499/a8f5da59-c4d2-43c5-9943-c7c4ed627203)  

### Part 3: Visualize and Compare Results  

  * Visually analyze the cluster analysis results by `contrasting` the outcome.
      * Composite a plot to contrast the `Elbow Curves`.
      * Composite a plot to contrast the `Clusters`.
   
**Elbow Curve Plot**:  
![Screenshot 2023-09-18 at 7 01 29 PM](https://github.com/Kaileycar/CryptoClustering/assets/130424499/38b26c14-3182-40cb-b6f9-27673921b129)  

**Cluster Plot**:  
![Screenshot 2023-09-18 at 7 01 55 PM](https://github.com/Kaileycar/CryptoClustering/assets/130424499/792b0617-d8ee-41c1-a13a-256bc696fd4d)  

---

## Links

[Composing Plots](https://holoviz.org/tutorial/Composing_Plots.html)
