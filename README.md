# CryptoClustering
## Project Outline
This project involves the analysis and clustering of cryptocurrencies using unsupervised machine learning techniques, particularly K-Means clustering. The primary goal is to group cryptocurrencies based on their characteristics and price changes, ultimately creating profitable portfolio recommendations. The project's workflow includes data preprocessing, the determination of the optimal number of clusters (k), and the application of Principal Component Analysis (PCA) for dimensionality reduction.

## Data Preparation
In the initial phase of the project, the cryptocurrency market data is loaded and prepared. Data normalization is conducted using the StandardScaler module from scikit-learn, resulting in a scaled dataset. This scaled data serves as the foundation for subsequent clustering and analysis.

## Cluster the Cryptocurrencies
- **Finding Optimal Number of Clusters:** The elbow method is employed to identify the best k value to determine the optimal number of clusters (k) forthe original scaled dataset. A list of k values ranging from 1 to 11 is created, and inertia values are computed for each k. A line chart is generated to visualize the inertia values and identify the optimal k value.
![image](https://github.com/NikitaGahoi/CryptoClustering/assets/136101293/3fcca74e-ec6b-49a7-bd71-790ea9b139af)

 **According to the elbow curve the best value for 'k' is 4**
 
 - **Clustering with the optimal value of k:** These steps were followed to perform cryptocurrency clustering with the optimal value of k using the original scaled dataset:
     - Start by initializing the K-Means model with the previously determined best value for k. In this case the best value for k is 4
     - Fit the K-Means model to the original scaled dataset, allowing the algorithm to learn the underlying patterns in the data.
     - Employ the trained K-Means model to predict and assign clusters to individual cryptocurrencies in the original scaled dataset. This step groups cryptocurrencies with similar characteristics together.
     - Create a duplicate of the original dataset, introducing an additional column to store the predicted clusters. This column is crucial for identifying the cluster to which each cryptocurrency belongs.
     - To gain deeper insights and facilitate interpretation, generate a scatter plot using the hvPlot library. Configure the x-axis to represent "price_change_percentage_24h" and the y-axis to represent   "price_change_percentage_7d"
     - Enhance the scatter plot by color-coding the data points based on the cluster labels assigned by K-Means. This color differentiation aids in visually distinguishing between different clusters.
     - Improve the plot's informative value by including the "coin_id" column in the hover_cols parameter. This addition enables the identification of individual cryptocurrencies represented by each data point, making it easier to relate specific cryptocurrencies to their respective clusters.
       
  ![image](https://github.com/NikitaGahoi/CryptoClustering/assets/136101293/a82ecc8f-e7d6-4df4-a61c-dbc932b0d8b1)
  

- **Optimize Clusters with Principal Component Analysis:** To enhance the clustering process and reduce the dimensionality of the data, Principal Component Analysis (PCA) is applied. PCA allows for the creation of primary clusters that capture essential information from the original dataset. The explained variance of the PCA components is examined to understand the contribution of each principal component to the data.
- 
  **The variance explained by three principal components is approximately 89.49%**

  Subsequently, create a fresh DataFrame incorporating the PCA-transformed data. This new DataFrame is structured with the "coin_id" index inherited from the original dataset. This arrangement ensures seamless integration with the existing data, maintaining the connection between cryptocurrencies and their corresponding PCA-derived features. By incorporating PCA and retaining essential information while reducing dimensionality, this stage enhances the accuracy and interpretability of cryptocurrency clustering, ultimately leading to more informed decision-making.

![image](https://github.com/NikitaGahoi/CryptoClustering/assets/136101293/a50040c6-1fcb-48ff-a360-4c484bad8b14)

- **Finding Optimal Number of Clusters Using the PCA Data:** Similar to the previous step, I employed the elbow method, but this time on the PCA data. A range of k values is considered, and the inertia values are computed. The resulting elbow curve helps identify the best k value when using the PCA data, and any differences from the best k value found with the original data are noted.

  ![image](https://github.com/NikitaGahoi/CryptoClustering/assets/136101293/8134d77c-a675-4976-ae9a-2ed850aeb097)

   **According to the elbow curve the best value for 'k' is 4**

- **Clustering PCA Data using optimal value of k:** With the optimal k value determined from the PCA data, the K-Means clustering algorithm is applied to group cryptocurrencies. The PCA-transformed data is used for this clustering process. A copy of the PCA data is created to store the predicted clusters.
  
  ![image](https://github.com/NikitaGahoi/CryptoClustering/assets/136101293/13831b3c-99f8-4327-880b-5fe60257194b)

 - A scatter plot is generated to visualize the clustered data, with the x-axis representing the "PC1" and the y-axis representing the "PC2"  Cryptocurrency labels are added to the plot to identify each data point, and the impact of using fewer features for clustering is analyzed.

![image](https://github.com/NikitaGahoi/CryptoClustering/assets/136101293/dbe01b52-fca9-4bf9-a782-d7bae8cd3d11)

- **Visualize and Compare the Results:** A composite graph was prepared to plot the contrast in the Elbow curves and the K-means clusters and PCA clusters. The elbow graphs completely overlaped, whereas the  K-means clusters and PCA clusters showed some variation:
  
 ![image](https://github.com/NikitaGahoi/CryptoClustering/assets/136101293/93038fa5-3130-441d-9425-19ce59248cce)
  




  




