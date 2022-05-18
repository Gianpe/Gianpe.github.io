---
title: "Bank Loan Status"
excerpt: "The text is about the analysis of the credit situation of a bank, for which we’ll try to
understand the main things.<br/><img src='/images/dm1 (2).png'>"
collection: portfolio
---
Report [here](https://github.com/Gianpe/bank-Loan-Status/blob/master/ProgettoDM1.pdf)

Code [here](https://github.com/Gianpe/bank-Loan-Status)


#### Introduction 

Our goal is to classify the clients, based on their loan status, to understand which are the
features of the clients who already paid the loan and the ones who didn’t finish. To do so, we
have to pass through Data Understanding, Data Cleaning and Data Preparation. Moreover,
we will also clusterize the unlabelled data and finally we will look for association rules.

#### Data Understanding

The dataset is composed by 100514 rows and 19 attributes, that give us information about
the clients of the bank and their loan situation. Particularly, for every client and every
loan there is a ”Client ID” and ”Loan ID”, we have information about the Loan Status
and Term. Moreover, every client has a Credit Score and for everyone of them is given the
Purpose because they made a Loan and if they have a house. Then, we know their Annual
Income , for how long they have worked in the current job, the Year of credit History, the
Number of Open Account, how many credit problems they had and the Bankruptcies, how
much they pay monthly, the current credit balance, maximum open credit and finally if
they have the Tax Liens.

#### Clustering

We tried to clusterize our data with the techniques that we know, namely K-means, DBSCAN and hierarchical clustering. In particular, we tried different approach, proposing
dataset differently prepared: we tested the complete dataset, the complete dataset without
upper outliers, the dataset with only numerical attributes without outliers and finally the
dataset with only categorical attributes.

#### Classification

We tried to classify our data using basic models, such as the Decision Tree classifiers
ans K-NearestNeighbor, and an advanced one, the Random Forest. Training and
testing the classifiers on the dataset created during the cluster section, we noticed that, not
considering the upper outliers the performance get worst, so we applied the classification on
the complete dataset and in the one with only categorical attributes.
In all cases we split the dataset in training and test set(70% e 30%) and used ’Loan Status’
as class. For parameter tuning we used the Grid Search method and Cross Validation, for
which we considered the training composed by validation set and training set.

#### Frequent Pattern Extraction

We computed the frequent item sets with Apriori algohorithm and we ordered them basing
on the support. It can be noticed that the frequent itemset with higher support is [’No
bankruptcies’, ’0.0 tax Liens’] with support = 89,12 %. The second frequent itemset with
respect to support is [’(10802.0, 10009721.7) LoanAmount’, ’0.0 tax Liens’] with support =
88,00 %. So, what we can notice is that when tax liens is 0( so the client has not tax liens),
usually the bankrupt is never declared and the current loan amount is low.



