---
title: "Sentiment analysis during US election"
excerpt: "We are going to analyse data about the elections in Usa in 2020, to understand the general sentiment
of people around the world through tweets.<br/><img src='/images/trumpbiden.png'>"
collection: portfolio
---

Project made with Monia Bennici and Filip Strzazlka.
#### Introduction
The original dataset is composed by 776k tweets related
to Joe Biden and 970k to Donald Trump. Each tweet is described by its text and 19 additional
attributes: 4 tweet attributes (timestamp, likes, retweets, source: webapp/mobile),8 user attributes
(nickname, screen name, join date),7 location attributes (country, city, state, latitude, longitude).
To train a model we also have a support dataset, that contains sentences and the sentiment of that
sentence labeled as positive, neutral or negative. The main goal of this work is to create a timeline
visualisation of general twitter community attitude to candidates.

#### Data Cleaning
We opened the csv les as dataframes through SparkSession. Both Trump le and Biden le
contains missing values in the columns source, user name, user description, user location, lat, long,
city, country, continent, state and state code. Since we do not need all the 20 attributes for the
analysis, we drop the columns we considered useless. For the purpose of the project we just used
created at and tweet that do not contain missing values, but we also left likes, lat, long and city for
future aims maintaining the missing values. Also, we detected 1251 duplicates rows in Trump le
and 1851 in Biden one. So we deleted them because they are not useful. The last step consists of
removing special chars (as hashtags, url's etc) and we did it with the function clean text, obtaining
rows without text when the tweet is just composed of these chars. This problem will be solved in
the next steps. Finally, we saved the clean dataframes as csv les in HDFS.
Also the support dataset had to be clean. First of all, we had two csv les (train.csv and test.csv)
containing the same information (text, sentiment) plus the column "selected text in train.csv, so we decided to merge them in one, dropping from train the columns "selected test". The dataset contained some missing values, we deleted them and there was not any duplicate row. Also in this
case, we deleted special char with clean text and we saved the obtained dataframe in HDFS.

#### Text Analysis

For the text analysis it was necessary to split the text into words and delete rows with the blank
text created in the previous step and we did it with the function split text. We rst analyse the
support dataset. The analysis is based on the frequency of a word to be in a class of the support
dataset with respect to the frequency to be in the support dataset in general.

#### Classification
In order to classify our dataset, we featured the text data. In particular, we used three vectorization
methods, that are word2vec, bag of words and TF-IDF. Reminding that every line of the dataset is
split into words, the bag of words build a dictionary from the set of these words, returning vectors.
Also word2vec uses the single words and it place every word in a point in the space, where the
more two words are near, the more are similar. Finally, the TF-IDF compute the probability to and a word in the document, giving more importance to rare words (so the words that appear less in lines). Using these three method, we trained two classiers on the support dataset: Naive-Bayes and Multilayer Perceptron.
Despite bag of words does not take semantic meaning in consideration, it brings the best results
with both classifiers. So we choose the Multilayer perceptron as classification method.

#### Visualizations
Finally, applying the classifier to our dataset, we obatined the predicted sentiment on tweets.
Starting from this, we computed a dayly mean of the sentiment, considering positive= 1, neutral=
0 and negative= -1. In this way, we can see the trend of the sentiment about the candidates, shown
in figure . The graphs show a similar sentiment trend for both candidates, until the beginning
of November, where there is an increasing of positive attitude towards Biden, infact the top mean
score for Biden is 0.06, meanwhile for Trump stops at -0.02. Looking for news in newspapers, we
can see what happened the day before the peaks occur, noticing that the 27th of October, the
day near the negative peak for Trump, Twitter censured Trump's twitter post,meanwhile at the
beginning of November both had an increasing in positive sentiment and it can be due to the vote
count in Georgia.
<img src='/images/trumpvsbiden.png'>
