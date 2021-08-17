Objective:

The goal of this project was to make a data generating process that creates a dataframe of dimension d with hidden clusters of radius r and noise n. 

Process:
A dataframe-creating function was developed that took 6 input parameters, namely the dimension of the dataframe, the dimension matrix, the number of clusters in the subspace, the length of the corresponding cluster and also the radius of the corresponding cluster. 
The intuition of the process was to generate a random point in space and then pick out random datapoints around it. The range was determined with the radius while the angle was generated randomly. With that, we were able to extract random datapoints within a certain radius of a centre point. 

Results:
After building the function, we created 5 dataframes. The dimension of the dataframes are 3, 8, 15, 20, and 30, with three clusters in each subspace with lengths of 50, 75 and 100, respectively. The radius of each cluster was set at 3, 2, and 3.
After creating the dataframe, we attempted to visualize it and, as a result, made some interesting observations.  As the dimension of the dataframe kept growing, the clusters became less differentiable. Indeed, the most visibly clustered dataframe was the one with the lowest dimension.
Finally, k-means clustering was applied to the model. In order to find out the most adequate number of cluster, the R function cascadeKM from the vegan package was applied on the datasets. 
As it turned out, the number of clusters found out in the datasets from 3 dimension to 30 were 10, 2, 2, 2, and 2 – this shows that as the dimensions increase, the number of clusters found out was decreased.
After that, the function kmeans() was applied on the dataset with the cluster values set as the ones mentioned above. The dataset with three dimensions had a within-cluster-sum-of-squares at 91.5%, which means that there is a high variability between the clusters.
As the dimensions increase, the WCSS keeps decreasing, with the dataset with 30 dimensions having a WCSS of 4.1%, which suggests that the clusters don’t have much variability between themselves. 
To drive this home point even further, kmeans was once again applied with 3 as the cluster size. Even with that, the WCSS for increasing dimensions kept decreasing from 63.5% for three dimensions to 7.3% in the dataset with 30 dimensions. 
This once again works as a testament to the claim that as the dimensionality of the data increases, the more difficult it is to cluster them properly. 
