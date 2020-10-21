# Anomaly Detection

## Definition

Anomaly detection (or outlier detection) is **the identification of rare items, events or observations which raise suspicions by differing significantly from the majority of the data.** Typically, anomalous data can be connected to some kind of problem or rare event such as e.g. bank fraud, medical problems, structural defects, malfunctioning equipment etc. This connection makes it very interesting to be able to pick out which data points can be considered anomalies, as identifying these events are typically very interesting from a business perspective. 

Outlier Detection is an exciting yet challenging field, which aims to identify outlying objects that are deviant from the general data distribution. Outlier detection has been proven critical in many fields, such as **credit card fraud analytics,** **network intrusion detection, and mechanical unit defect detection.**


## Data Visualization

This brings us to one of the key objectives: How do we identify whether data points are normal or anomalous? In some simple cases, as in the example figure below, data visualization can give us important information.

![image](https://user-images.githubusercontent.com/28102493/96762741-bfb3e180-13d9-11eb-8704-65b0488df3e7.png)


In this case of two-dimensional data (X and Y), it becomes quite easy to visually identify anomalies through data points located outside the typical distribution. However, looking at the figures to the right, it is not possible to identify the outlier directly from investigating one variable at the time: It is the combination of the X and Y variable that allows us to easily identify the anomaly. This complicates the matter substantially when we scale up from two variables to 10–100s of variables, which is often the case in practical applications of anomaly detection.

## Multi-variable anomaly detection with Machine Learning Solutions

In many systems, system health is determined by the value of multiple metrics. A straightforward extension of the single-metric anomaly-detection approach is to develop anomaly detectors for each metric independently, but this ignores possible correlations or cause-effect relationships between metrics. For example, we may expect to see a correlation between latency and traffic levels. A spike in network latency alone may appear anomalous but may be expected when viewed within the context of a corresponding spike in network traffic. In other words, high network latency may be anomalous only when traffic is low.


### Supervised Machine Learning for Anomaly Detection

The supervised method requires a labeled training set with normal and anomalous samples for constructing a predictive model. The most common supervised methods include **supervised neural networks, support vector machine, k-nearest neighbors, Bayesian networks and decision trees.**

Probably, the most popular nonparametric technique is **K-nearest neighbor (k-NN)** that calculates the approximate distances between different points on the input vectors and assigns the unlabeled point to the class of its K-nearest neighbors. Another effective model is the **Bayesian network** that encodes probabilistic relationships among variables of interest.
Supervised models are believed to provide a better detection rate than unsupervised methods due to their capability of encoding interdependencies between variables, along with their ability to incorporate both prior knowledge and data and to return a confidence score with the model output.

### Unsupervised Machine Learning for Anomaly Detection

Unsupervised techniques do not require manually labeled training data. They presume that most of the network connections are normal traffic and only a small amount of percentage is abnormal and anticipate that malicious traffic is statistically different from normal traffic. Based on these two assumptions, groups of frequent similar instances are assumed to be normal and the data groups that are infrequent are categorized as malicious.
The most popular unsupervised algorithms include:

1. **K-means,**
1. **Robust Covariance**
1. **One-Class SVM**
1. **Isolation Forests**
1. **Autoencoders:** models that map input data into a hidden representation and then attempt to restore the original input from this internal representation. For regular pieces of data, such reconstruction will be accurate, while in case of anomalies, the decoding result will differ noticeably from the input.
1. **GMMs,**
1. **PCAs,** 
1. and **hypothesis tests-based analysis**

These algorithms essentially work by identifying groups of similar data points and considering the points outside of these groups to be anomalies. The Robust Covariance technique assumes that normal data points have a Gaussian distribution, and accordingly estimates the shape of the joint distribution (i.e., estimates the mean and covariance of the multivariate Gaussian distribution). The One-Class SVM algorithm relaxes the Gaussian assumption; instead, it identifies arbitrarily shaped regions with a high density of normal points. Isolation Forests, on the other hand, don’t make any assumptions about the shape of the distribution: a collection of decision trees is constructed, in which each individual decision tree splits data along a random point. Anomalies are considered to be the most isolated points.

![image](https://user-images.githubusercontent.com/28102493/96768762-803bc400-13de-11eb-98c1-f955db09a429.png)

Neural network-based autoencoders are another increasingly popular tool for multivariate anomaly detection. Autoencoders learn efficient representations of complex datasets by encoding them through an unsupervised training process, in which high-dimensional multivariate datasets are represented in lower dimensions. For example, a dataset of cat pictures may be efficiently

represented by an autoencoder, which learns to reconstruct images based on a smaller set of characteristics (e.g. the cat’s color and pose). When trained on a dataset consisting entirely of cats, the autoencoder will perform well, with low reconstruction error. When the autoencoder is faced with images of dogs, however, we expect higher reconstruction error. In a similar manner, an autoencoder trained on normal network data learns what normal behavior looks like. When normal data points are encountered, the reconstruction error is expected to be low. But when anomalous data points are encountered, the error will be high, and the datapoints will be classified as anomalies.

