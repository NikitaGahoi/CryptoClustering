# CryptoClustering
## Project Outline
This project involves the analysis and clustering of cryptocurrencies using unsupervised machine learning techniques, particularly K-Means clustering. The primary goal is to group cryptocurrencies based on their characteristics and price changes, ultimately creating profitable portfolio recommendations. The project's workflow includes data preprocessing, the determination of the optimal number of clusters (k), and the application of Principal Component Analysis (PCA) for dimensionality reduction.

## Data Preparation
In the initial phase of the project, the cryptocurrency market data is loaded and prepared. Data normalization is conducted using the StandardScaler module from scikit-learn, resulting in a scaled dataset. This scaled data serves as the foundation for subsequent clustering and analysis.

## Cluster the Cryptocurrencies
**-Finding Optimal Number of Clusters:** The elbow method is employed to identify the best k value to determine the optimal number of clusters (k) forthe original scaled dataset. A list of k values ranging from 1 to 11 is created, and inertia values are computed for each k. A line chart is generated to visualize the inertia values and identify the optimal k value.
![image](https://github.com/NikitaGahoi/CryptoClustering/assets/136101293/3fcca74e-ec6b-49a7-bd71-790ea9b139af)
