# Sparkify Project


#### Table of Contents
1. [Motivation](#motivation)
2. [Libraries](#libraries)
3. [Files](#files)
4. [Summary](#summary)
5. [Acknouledgements](#acknowledgements)


### Motivation

In this project we will analyze data from sparkify, a digital music service similar to spotify. The data generated by the service contains timestamped actions of a user such as listening to a song, giving it a thumbs up, logging in, hearing an ad, upgrading or downgrading a subscription, cancelling a subscription and etc. These actions hold the key to understanding user satisfaction and the goal of the project is to uncover these insights and predict whether a user is likely to churn.

Predicting customer churn is a common business problem. Understanding customer satisfaction can get businesses raise revenue by helping them target marketing campaigns to relevant customer groups, for example, offer disstisfied users memebership discounts or other incentves. One of the challenging parts of this problem is to engineer essentail features from the data that affect customer satisfaction. Another challenge is to process massive amounts of data in an efficient and timely manner.

Indeed, such a dataset can be very large, containing all actions for all users in a given period of time: the full sparkify dataset is 12GB. We will use Spark, a distributed framework with python interface, that would allow us to address both challenges. Pyspark has a rich collection of tools that would allow us to engineer relevant features and, even though here we will only work with a tiny portion of the data that is only 128MB, we could readily scale our processes to the full dataset if we ever decided to deploy a cluster on the cloud (we will not do it here).


### Libraries

We have used `pyspark`, `pandas`, `numpy`, `matplotlib.pyplot` and `seaborn` with `python 3.6`. 


### Files
The repository contains the following files:

* Sparkify.ipynb - the notebook where we analyse the data and build a model. 

* Sparkify.html - html for the above notebook.


### Summary

In this project we analyzed a dataset for a digital music service that contains data on user actions. Our aim was to understand user satisfaction and predict churn. We cleaned the data to eliminate points that would not add value to our analysis. We defined churn as a user canceling the account and compared and contrasted the features of groups of users who churned versus users did not. This exploration process helped us mine for insights for what affects churn and as a result we engineered 17 features to use in our model. Next we tried out several models and after choosing the best one, a random forest classifier, we further refined it by using grid search with 3-fold cross-validation (which is a more robust method then just train-validation split as it leaves less up to chance of getting a good split) to find the best parameters. It turned out that the best results were given by using 10 trees, maximum tree depth of 5 and minumum instances per node of 3. We used the F1 score to choose the best model, since the label was skewed. As a result we built a well-balanced model that gave us F1 score of about 70.7% and accuracy score of 70.3%.


### Acknowledgements

For this project we used [spark ml guide](https://spark.apache.org/docs/latest/ml-guide.html), [documentation for spark.sql.functions](https://spark.apache.org/docs/latest/api/scala/index.html#org.apache.spark.sql.functions$) and [pyspark documentation](https://spark.apache.org/docs/latest/api/python/pyspark.ml.html#pyspark.ml.tuning.CrossValidator).
