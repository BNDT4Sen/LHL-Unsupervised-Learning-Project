# Unsupervised Learning Project

## Part I : EDA - Exploratory Data Analysis & Pre-processing
The data was read from the provided csv and briefly explored. No null values were found, and all data points appeared to be within a reasonable range of one another. Some outliers existed, but without more knowledge about the dataset, they cannot safely be excluded. The Region and Channel columns were quickly identified to be categorical, and were converted from the int64 data type. Some visualizations were then created to get a stronger grasp on the relationships between the features. Before exporting the lightly modified dataset, the categorical columns were dropped.

## Part II - KMeans Clustering
The modified data set was imported into the KMeans notebook and immediately visualized. It was not possible to identify the number of clusters that would best suit the data, and so an Elbow plot was created. The Elbow plot indicated that either 3 or 5 clusters would be most appropriate for the data. Two KMeans models were run, one for each count of clusters. Both models worked well, with the fewer cluster model providing more of a generalization. One of the clusters of the 5 cluster model was seemingly dedicated to outliers, and this could be useful for further analysis of the data.

## Part III - Hierarchical Clustering 
After importing the data set, a dendrogram was plotted to show the hierarchical clusters. I determined 5 clusters to be appropriate for the model, but 3 or 4 would have also been acceptable. Without a more specific goal in mind for the data, it won't make a big difference. The visualization of the clustering model looked quite similar to the KMeans model. Again one of the clusters had been assigned to outlier duty. The distributions of the other 4 clusters on the graph mirrored the KMeans visualization quite well. 

## Part IV - PCA
The first step for PCA was to plot a correlation matrix of the features from the modified data set. This would give a slight indication as to where the PCA would end up, and if something went wrong, it would be made clearer. Then the entire DataFrame was scaled using StandardScaler. PCA was then conducted on the scaled data. Checking the PCA model and plotting it on a graph revealed two very significant features. The Fresh category accounted for 44% of the variance, and Milk accounted for 28.3%. Frozen came in at a distant third place with 12.3%. Delicassen is the least important variable, explaining only ~1% of the variance. 

## Part V - Conclusion
1. The data would have worked well with anywhere from 3 to 5 clusters. Fewer clusters would lead to a more generalized model, and so this would be useful if drilling down into the data was less important. Anymore than 5 clusters would likely lead to messy clustering and arbitrary centroids. 

2. The region column is likely a geographical category, and the channel column probably expresses in what way the goods were sold; possibly inperson vs online. In the initial EDA visualizations there are some stark differences between the two channels. Frozen and Fresh items were much more likely to be categorized under channel 1, and the remaining categories primarily under channel 2.

3. The dendrogram used in the Hierarchical Clustering is indicative that due to the way that the data is layed out, clusters will never be uniform. The red cluster on the right takes up a fraction of the space that the other two do, unless the number of clusters were to increase dramatically. Too many clusters could hurt the usefulness of the data, however.

4. Fresh and Milk were by far the most influential features in terms of variance according to the PCA model. This could be an important indicator to the grocery store in question that their produce and dairy departments are especially vital in getting customers through the door.