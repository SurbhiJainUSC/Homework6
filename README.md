# Supervised-Semi-supervised-and-Unsupervised-Learning
The task is compare different machine learning approaches: Supervised Learning, Semi-supervised Learning and Unsupervised
Learning ny monte-carlo simulation.

## Dataset
The Breast Cancer Wisconsin (Diagnostic) dataset contains 10 real-valued features that describe the characteristics of the 
cell nuclei present in the image. There are total 569 observations, each described using 30 features and 1 class label 
(Malignant=M or Benign=B).

## Supervised Learning
An L1-penalized SVM has been trained to classify the normalized data. 5-fold cross-validation has been used to choose 
the penalty parameter. The average accuracy, precision, recall, F-score, AUC, and ROC curve have been computed for both 
training and testing sets over M runs in monte-carlo simulation. 

## Semi-supervised Learning
To perform semi-supervised learning, 50% of the positive class along with 50% of the negative class in the training set have
been selected as labeled data and the rest serve as unlabeled data. An L1-penalized SVM has been then trained to classify 
the labeled data. 5-fold cross-validation has been used to choose the penalty parameter. The unlabeled data point that is 
farthest to the decision boundary of the SVM is then labeled and added to the labeled data set. The SVM is then retrained
on current labeled dataset. The process is continued until all unlabeled data points are added to the labeled set. 
The final SVM is then tested on the test data and the average accuracy, precision, recall, F-score, AUC, and ROC curve have 
been computed for both training and testing sets over M runs in monte-carlo simulation. 

## Unsupervised Learning
K-means clustering algorithm is run on whole training set and majority polling has been used to predict the label for the 
members of each cluster. This algorithm finds an optimal solution that could be either local best solution or global best 
solution. To make sure that the algorithm does not get trapped in local minimum is to repeat the clustering algorithm multiple 
times and take the most optimal solution. In K-means algorithm, every different choice of initial cluster seeds may lead to 
different clusters because the algorithm tries to optimize the cost function. Therefore, it is better to take a stochastic 
approach and run the algorithm many times with different initial cluster seeds. This will lead to mulitple clustering results,
so choose those clusters that give the lowest error.
