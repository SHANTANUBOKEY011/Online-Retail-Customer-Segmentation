# Online-Retail-Customer-Segmentation
## Unsupervised Machine Learning on Online Retail Customer Segmentation

To Identify Major Customer Segments On Transnational Dataset Using Unsupervised ML Clustering Algorithms. In this project, our task is to identify major customer segments on a transnational dataset which contains all the transactions occurring between 01/12/2010 and 09/12/2011for a UK-based and registered non-store online retail. The company mainly sells unique all-occasion gifts. Many customers of the company are wholesalers. The dataset provided contains information about Invoice No, Stock Code, Description, Quantity, Invoice Date, Unit Price, Customer ID and Country for each transaction.

## To achieve our goal of segmentation, we followed the following sequence of steps.

* Understanding the dataset, doing some basic inspection on the raw data to check the number of columns, understanding distribution of data and checking statistics of the data in each variable. Checking for and handling missing values, Cleaning the data.
* Feature engineering: After getting some insights from the dataset we created some new features, altered the existing features to understand the hidden patterns in the data.
* EDA & Data insight on original data: we put out interesting inferences from the data to derive some meaningful results by visualizing some plots and distributions.
* After having understood the original data, we moved ahead to generate a new dataset based on Recency, Frequency and Monetary values of all the unique customers in order to do a behavioral customer segmentation. We did some feature engineering and EDA on this new dataset as well. We also made some transformations in this dataset to make it ready to be passed to different clustering algorithms.
* We started with a simple binning and quantile based simple segmentation model first then moved to more complex models because simple implementation helps having a first glance at the data and know where/how to exploit it better.
* Then we moved to k-means clustering and visualized the results with different number of clusters. As we know there is no assurance that k-means will lead to the global best solution. We moved forward and tried Hierarchical Clustering and DBSCAN clusterer as well.
* Obtained the optimal number of clusters using silhouette analysis, Elbow method and dendrogram to majorly identify 4 segments for marketing, churn prediction, to define their value, loyalty, profitability etc for the business on the basis of their behavioral attributes. 

### DESCRIPTION OF OBTAINED CLUSTERS

| CLUSTERER             | CRITERION         | LOST POOR | LOST LOYAL | RECENTLY VISITED AVERAGE | AVERAGE | GOOD | BEST |
| ----------------------|-------------------|-----------|------------|--------------------------|---------|------|------|
| BINNING RFM SCORES    | QUANTILE          | YES       | ---        | ---                      | YES     | YES  | YES  |
| RFM QUANTILE CUT      | QUANTILE          | YES       | YES        | ---                      | ---     | YES  | YES  |
| K-MEANS               | SILHOUETTE ONLY   | YES       | ---        | ---                      | ---     | ---  | YES  |
| K-MEANS               | ELBOW ONLY        | YES       | YES        | YES                      | YES     | ---  | YES  |
| K-MEANS               | SILHOUETTE & ELBOW| YES       | YES        | YES                      | ---     | ---  | YES  |
| AGGLOMERATIVE         | DENDOGRAM (Y = 70)| ---       | ---        | ---                      | YES     | ---  | YES  |
| AGGLOMERATIVE         | DENDOGRAM (Y = 50)| YES       | YES        | ---                      | ---     | ---  | YES  |
| DBSCAN                | EPSILON = 0.2     | YES       | YES        | ---                      | YES     | YES  | ---  |
