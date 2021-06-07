---
title: "Spectral clustering"
excerpt: "The aim of this work is to illustrate the spectral clustering and to see
some applications in the field of bioinformatics.<br/><img src='/images/clusters.png'>"
collection: portfolio
---

I apply this technique to a training set obtained from microarray experiments on oligonucleotides of sick patients of leukemia, in order to group them into the three main categories of the disease. In general, the clustering serves to estimate the classes belonging to the training set with geometric considerations, looking at the distribution and density of data input. The objective of these techniques is therefore to minimize the distance of objects in a group and maximize the distance between different groups. From the moment that the problems of Clustering often have a high number of data there is need of an efficient algorithm. This algorithm is found in algebraic ways and in particular, in spectral clustering, the algorithm is based on the calculation of the second eigenvector of the Laplacian.
Compared to partitional and hierarchical clustering, spectral clustering presents several advantages. First of all the simplicity of implementation, for which a linear algebra library is sufficient, moreover the results overcome numerous difficulties that present themselves with other techniques.
Graph theory is the theory that underlies spectral clustering: the training set comes considered as a weighted graph whose vertices represent training objects set while the arcs correspond to the weights of similarity between the vertices that they connect. The secret of this technique consists in partitioning this graph through the so-called
'cut'. The problem of 'cut' is solved through the Laplacian.
In Fig.1 we can see the behavior of the Fielder vector in grouping the three clusters. We calculated and shown the behavior of the latter with MATLAB. Codes and report are available on [this repository](https://github.com/Gianpe/Spectral_clustering)
<img src='/images/clusters.png'>
