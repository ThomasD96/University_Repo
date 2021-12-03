Credit Risk Modeling - Prediciting Customer Loan Defaults with Machine Learning Models
======================================================

> Work project submitted at the Credit Risk department at Nova School of Business and Economics (Nova SBE)

[![License MIT](http://img.shields.io/badge/license-MIT-brightgreen.svg)](license.md)

> **Author**: [Thomas Dornigg](https://www.linkedin.com/in/thomas-dornigg/) <br>
> **Supervisor**: Prof. João Pedro Pereira <br>
> **Academic year**: 2021/22

In co-operation with: **`zeb.rolfes.schierenbeck.associates gmbh`**

<p align="center">
  <img alt="Light" src="https://github.com/ThomasD96/University_Repo/blob/master/Nova_SBE/Master_thesis/pictures/zeb_logo.png" width="20%" hspace="25" >
&nbsp; &nbsp; &nbsp;
  <img alt="Dark" src="https://github.com/ThomasD96/University_Repo/blob/master/Nova_SBE/Master_thesis/pictures/nova_logo.png" width="45%">
</p>

## Overview
In today’s financial markets, banks play a crucial role, especially when it comes to the decision on who should be granted a loan and under which market conditions. A major issue which financial institutions have to face in this process is the risk of non-payment of its counterparty, meaning that banks need to pay special attention not to give a loan to risky borrowers. However, since banks have to analyze and process a certain amount of applications every day, this method is time-consuming and the result of the evaluation, when done manually, prone to errors. In this case, the best option for the bank is to evaluate the customer based on its previous credit history in a fully automatic way. To do so, statistical credit scoring algorithms are required to overcome those challenges. These algorithms, which compute probability of defaults for each applicant based on the credit history of its customers, are the main methods which financial institutions nowadays use to determine whether a loan should be granted to a borrower or not.

The objective of this project is to use historical loan application data to predict whether or not an applicant will be able to repay a loan. This is a standard supervised classification task:

- Supervised: The labels are included in the training data and the goal is to train a model to learn to predict the labels from the features

- Classification: The label is a binary variable, 0 (will repay loan on time), 1 (will have difficulty repaying loan)

In this project, the goals achieved are :
- Data Exploration routines are designed and implemented to do standard statistical analysis and visualization.
- Classification models such as Logistic Regression, Random Forest, XGBoost, Decision Tree, AdaBoost and Support Vector Machine are built to predict whether or not an applicant will be able to repay a loan
- Evaluated Classification models by Accuracy, Precision, Recall, True Negative Rate, True Positive Rate, False Negative Rate, False Positive Rate and ROC – AUC chart
- Create a GUI based on the final models 

## Data Sources
The dataset for this project can be found on [Kaggle](https://www.kaggle.com/laotse/credit-risk-dataset/tasks). It was published by Lao Tse under the CC0 public licence (usability 7/10). The data contains basic financial information of about 32,581 borrowers with a total of 12 features related to each of the borrowers. Along with it, there are more specific information provided about every particular borrower. Predicting whether or not a client will repay a loan or have difficulty is a critical business need - thus,  by unlocking the full potential of the data, the goal is to see what sort of machine learning/deep learning models can be developed to achieve this task.
