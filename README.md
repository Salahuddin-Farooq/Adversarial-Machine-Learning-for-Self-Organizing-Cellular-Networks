# Adversarial-Machine-Learning-for-Self-Organizing-Cellular-Networks
Fourth International Conference on UK-China Emerging Technologies Conference, 2019 Glasgow, UK.

Deep Neural Networks (DNN) have been widely adopted in self-organizing networks (SON) for automating different networking tasks. Recently, it has been shown that DNNs lack robustness against adversarial examples where an adversary can fool the DNN model into incorrect classification by introducing a small imperceptible perturbation to the original example. SON is expected to use DNN for multiple fundamental cellular tasks and many DNN-based solutions for performing SON tasks have been proposed in the literature have not been tested against adversarial examples. In this paper, we have tested and explained the robustness of SON against adversarial example and investigated the performance of an important SON use case in the face of adversarial attacks. We have also generated explanations of incorrect classifications by utilizing an explainable artificial intelligence (AI) technique.

# Code
Code contains implementation of FGSM attack at dataset of LTE network using CleverHans library. 

# Dataset
The dataset is extracted from live LTE network. Each row contains an hourly record of a specific eNodeB with a sudden increase in E-RAB Drop Rate is labeled as an anomaly. Initial experiments involve total 4464 records of two LTE eNodeBs. 3940 records are labeled as normal and 524 as anomalies based on domain knowledge. 

# Data Preprocessing and EDA 
This dataset has binary and nominal data variables and I have applied one-hot encoding to convert nominal features to numeric features since DNNs cannot operate on nominal data directly. This resulted in the transformation of the 25-feature dataset into a 26-feature dataset after one-hot encoding. After analyzing the data, I have noticed varying distributions of each feature. For example, the mean and standard distribution of some features are larger by seven orders of magnitude from some other features. Without performing normalization, these features would dominate other features. To mitigate this effect, we have used min-max scaling using Scikit-learn library to normalize data.

# DNN Architecture 
For our use case of anomaly detection in the dataset of E-RAB Drop Rate, we have used Multilayer Perceptron (MLP) classifier with the activation function of ReLU using Keras and Tensorflow sequential model. The MLP model is composed of three hidden layers of 256 neural units. The output layer contains two neurons since labels have two normal and abnormal classes. For regularization, dropout with a rate of 0.4 and early-stopping is used.

# Conclusions
In this paper, I have performed FGSM and JSMA attack on DNN-based abnormal KPI detector. Our results indicate more than 60% drop in the performance of DNN-based abnormal KPI detector making it very evident that DNN used for detection does not provide robustness against adversarial perturbation. 

 # Results 
 ![Image description](https://github.com/Salahuddin-Farooq/Adversarial-ML-for-Self-Organizing-Cellular-Networks/blob/master/FGSM.png)
 ![Image description](https://github.com/Salahuddin-Farooq/Adversarial-ML-for-Self-Organizing-Cellular-Networks/blob/master/JSMA1.png)
