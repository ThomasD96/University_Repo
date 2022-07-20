Cryptocurrency Fraud Detection: Supervised Machine Learning for Illicit Ethereum Transactions
======================================================

> Master thesis submitted at the Faculty of Economics and Business (Sectie Finance) at Universiteit van Amsterdam (UvA)

[![License MIT](http://img.shields.io/badge/license-MIT-brightgreen.svg)](license.md)

> **Author**: [Thomas Dornigg](https://www.linkedin.com/in/thomas-dornigg/) <br>
> **Supervisor**: Prof. Torsten Jochem <br>
> **Academic year**: 2021/22

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

<p align="center">
  <img alt="Dark" src="https://github.com/ThomasD96/University_Repo/blob/master/University_of_Amsterdam/Master_thesis/Pictures/UVA-amsterdam-business-school.png" width="60%">
</p>

## Overview
By definition, fraud is described as the intentional deception of a person or an organization, to gain personally or financially. In particular, the more complex the environment, the more difficult it becomes to detect fraudulent activities. Traditionally, this is performed by employing rule-based, behavioral, or manual techniques. With the increase in popularity of cryptocurrencies, Bitcoin, Ethereum, and other tokens are becoming more and more prevalent as an alternative source of payment, which however has also led to a spike in market manipulation. Thus, more advanced statistical models need to be utilized to spot bogus transactions. This paper investigates the possibilities of using supervised machine learning models to detect frauds in the Ethereum blockchain, while at the same time, also looking into the model's feature explainability. Results indicate that Random Forest and XGBoost are particularly capable of detecting frauds; outperforming traditional methods on a broad scale, measured by several key metrics. In addition, this thesis also shows potential implications of the developed model on security-related aspects of cryptocurrencies, in particular, that authorities and other related parties need to take to tackle future hurdles.

The objective of this project is to use historical Ethereum transactional data to predict whether or not a transaction is fraudulent. This is a standard supervised classification task:

- Supervised: The labels are included in the training data and the goal is to train a model to learn to predict the labels from the features

- Classification: The label is a binary variable, 0 (non-fraudulent), 1 (fraudulent)

In this project, the goals achieved are :
- Data Exploration routines are designed and implemented to do standard statistical analysis and visualization.
- Classification models such as Logistic Regression, Random Forest, XGBoost, Decision Tree, AdaBoost and Support Vector Machine
- Evaluated Classification models by Accuracy, Precision, Recall, True Negative Rate, True Positive Rate, False Negative Rate, False Positive Rate and ROC – AUC chart

## Data Sources
The dataset for this project can be found on [Kaggle](https://www.kaggle.com/laotse/credit-risk-dataset/tasks). It was published by Lao Tse under the CC0 public licence (usability 7/10). The data contains basic financial information of about 32,581 borrowers with a total of 12 features related to each of the borrowers. Along with it, there are more specific information provided about every particular borrower. Predicting whether or not a client will repay a loan or have difficulty is a critical business need - thus,  by unlocking the full potential of the data, the goal is to see what sort of machine learning/deep learning models can be developed to achieve this task.
