# **Homework 8**

## Original Plot:

![previous_plot](https://github.com/miles-garcia/DSPS_MGarcia/assets/144054740/e14e20fd-b1c0-42f0-bce7-4ff7bf6a605d)

Figure 1: DBSCAN clustering placed on the TSNE 2-D projection. We see one cluster (c=1 at the bottom) that's really tiny (it contains like 6 points, barely enough to be a cluster since my minimum is 5). The interesting thing here is that the "outlier" points are just inside cluster 0, so something in the TSNE projection is not showing through about those points compared to the DBSCAN. We also get very different clustering to kMeans.

(This was taken from HW7)


## Fixed Plot:
![fixed_plot](https://github.com/miles-garcia/DSPS_MGarcia/assets/144054740/521f878a-b67b-45db-8b95-d9285f9e034e)

Figure 2: This plot shows the results of the DBSCAN clustering on the TSNE 2-D projection of the data. The DBSCAN clustering results in two clusters, with one large cluster (in the dark turquoise color) containing the vast majority of the data, and a smaller cluster 
(in yellow at the lower middle-left) with only a few data points. The outliers, in purple, seem to be in very similar positions to points that were assinged to the clusters, so it is not evvident in the 2-D TSNE projection why these outliers are actually different from 
clustered data. It is also interesting that the small cluster is so small-- again, with the TSNE projection, it's not immediately obvious what separates those points from the rest of the data. 


### Discussion on Changes:
I changed a couple critical components of this plot. The biggest one was the removal of the useless colorbar in favor of labeling the points separately. Since there isn't a continuous distribution for the data (ie., the points can only be in clusters -1 (outlier), 0, or 1)
, a colorbar is adding a lot of useless information in the form of all the in-between colors that don't get used. So instead, I just separate the data into the clusters and label those individually. Definitely a big improvement there for readability, really showing that 
these data are only in 3 clusters and not a continuous set. For example, it could seem like maybe some points are just CLOSE to -1, 0, or 1 and that could add confusion. Especially with the change in the alpha (which I'll talk about later), the colorbar is harder to read 
since overlapping points will mix colors a bit. The other thing I did with the labels is actually label the colors as specific clusters/outlier, whereas before my colorbar was unlabeled, and even if I labeled it, for example, "Cluster Number", it still wouldn't point out 
that one cluster is for outliers, not a cluster itself. That would be confusing, but no label was also bad, obviously.

Then, I decided to change the alpha from 1 to 0.5, so it's easier to see point density. I found that this was really important-- for example in the small yellow cluster, with alpha = 1, you can't easily see that there's a purple outlier point in there. 
With the alpha at 0.5, on the other hand, it's much more visible. Same thing goes for a few of the outliers in the middle of cluster 1. I even thought that the outliers were just generally on the edges of the clusters, but with alpha =0.5 we can see that isn't entirely true,
since there are some outliers in the middle of the cluster. Alpha = 0.5 just generally helps visualize the points, and show the outliers, which were often hidden in the original plot.
