# Anomaly Detection

## Definition

Anomaly detection (or outlier detection) is **the identification of rare items, events or observations which raise suspicions by differing significantly from the majority of the data.** Typically, anomalous data can be connected to some kind of problem or rare event such as e.g. bank fraud, medical problems, structural defects, malfunctioning equipment etc. This connection makes it very interesting to be able to pick out which data points can be considered anomalies, as identifying these events are typically very interesting from a business perspective.

## Data Visualization

This brings us to one of the key objectives: How do we identify whether data points are normal or anomalous? In some simple cases, as in the example figure below, data visualization can give us important information.

![image](https://user-images.githubusercontent.com/28102493/96762741-bfb3e180-13d9-11eb-8704-65b0488df3e7.png)


In this case of two-dimensional data (X and Y), it becomes quite easy to visually identify anomalies through data points located outside the typical distribution. However, looking at the figures to the right, it is not possible to identify the outlier directly from investigating one variable at the time: It is the combination of the X and Y variable that allows us to easily identify the anomaly. This complicates the matter substantially when we scale up from two variables to 10–100s of variables, which is often the case in practical applications of anomaly detection.

## Machine Learning Solutions

### Supervised Machine Learning for Anomaly Detection

The supervised method requires a labeled training set with normal and anomalous samples for constructing a predictive model. The most common supervised methods include **supervised neural networks, support vector machine, k-nearest neighbors, Bayesian networks and decision trees.**

Probably, the most popular nonparametric technique is **K-nearest neighbor (k-NN)** that calculates the approximate distances between different points on the input vectors and assigns the unlabeled point to the class of its K-nearest neighbors. Another effective model is the **Bayesian network** that encodes probabilistic relationships among variables of interest.
Supervised models are believed to provide a better detection rate than unsupervised methods due to their capability of encoding interdependencies between variables, along with their ability to incorporate both prior knowledge and data and to return a confidence score with the model output.

### Unsupervised Machine Learning for Anomaly Detection

Unsupervised techniques do not require manually labeled training data. They presume that most of the network connections are normal traffic and only a small amount of percentage is abnormal and anticipate that malicious traffic is statistically different from normal traffic. Based on these two assumptions, groups of frequent similar instances are assumed to be normal and the data groups that are infrequent are categorized as malicious.
The most popular unsupervised algorithms include:

1. **K-means,**
1. **Autoencoders:** models that map input data into a hidden representation and then attempt to restore the original input from this internal representation. For regular pieces of data, such reconstruction will be accurate, while in case of anomalies, the decoding result will differ noticeably from the input.
1. **GMMs,**
1. **PCAs,** 
1. and **hypothesis tests-based analysis**

