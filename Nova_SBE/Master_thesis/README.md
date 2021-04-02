# Credit Risk Modeling - Predicting Customer Loan Defaults with Machine Learning Models

### Project File Summary
- <b>README.md</b> - a summary of all contents in this repository.
- <b>/Data Processing</b> - Notebook containing all code used for the data cleaning steps
- <b>/EDA</b> - Notebook containg all exploratory data anlysis and visualizations
- <b>/Preprocessing</b> - Jupyter Notebook containing all code used for data scaling and transformation
- <b>/ML Modelling</b> - Jupyter Notebook containing all code used for Logisitic Regression, RandomForest, GradientBoost, AdaBoost, etc. 
- <b>/Deep-Learning</b> - Notebook containing the neural network (ANN) code
- <b>/Thesis</b> - A pdf of the powerpoint presentation

### Objective:
Since the financial crisis, it has become increasingly common for banks and lending institutions to use machine learning and AI to create complex credit risk models to sort loans or borrowers into "default" and "non-default" classes. This is normally done to calculate the "PD" (probability of default), a single stage within a multi-part process for modelling credit risk. Whilst lenders have found that these models do well in calculating the probability of default, the lack of explainability that these black box models present has become increasingly problematic. With this in mind, it is crucial that methods are established to explain what was previously considered "unexplainable." In light of this "black box problem," there has been rapid advancement in the past few years within academia to develop methods for model explainability. 
It will be the objective of this project to apply the most promising of these methods to several machine learning algorithms that have traditionally been difficult to explain.

### The Data:
The data used in this project comes from a former "Kaggle" competition; the data can be found here. The dataset contains all loans issued by lending club from 2007-2018. The target variable in this data is the "current loan status" (Default, Charged-off, Late, Full-Paid, etc). The data includes 2.6 million observations and 143 features. The feature described key qualities of the loan such as interest-rate, amount, balance, grade etc. As well as qualities of the borrower such as account balance, number of loan inquieries, number of previously deliquent loans etc.

### Data Preparation: 
Many of the features contained null values. Some of these were missing at random, but for the vast majority of the features, the null values were not missing at random. In many cases, the missing values were replaced with zero. In these instances the null values actually represented a quality of the loan (ie. no inquiries made in the last 30 days), rather than the lack of data (ie. not having an interest rate). 

For features with null values that couldn't be imputed with a zero, the columns with more than 80% of missing data were dropped. For the remaining columns with missing data, the rows containing null values for these columns were dropped (more data was preserved this way). 

The cleaned data was then scaled and transformed in preperation for modeling. The data was firts split into numeric and categorical features. The numeric features were highly skewed and contained many outliers, and therefore were scaled using the robust scaler method rather than the standard scaler method (the robust scale is less sensitive to outliers). The categorical features were then either ordinally encoded or onehot encoded depending on the values they contained. 

The data was highly imbalanced due to the fact that most loans do not default. To account for this two balancing methods were tried: Random Undersampling and Synthetic Minority Over-sampling Technique (SMOTE). Despite the literature implying otherwise, the random undersampling method yielded superior modeling results. 

### Modeling:
A RandomForest, GradientBoosting, AdaBoosting, BaggingClassifier, and Sequential Neural Network were used in the modeling stage of the project.

The models were chosen iteratively using the RandomForest as the baseline model:

- The Random Forest fit the training data reasonably well and provided good cross-validation scores. However it demonstrated a moderate degree of bias during the training stage.

- The GradientBoosting and AdaBoosting methods were used to in an attempt to reduce the bias demonstrated by the RandomForest. The GradientBoosting algorithm fit the training data better and produced superior cross-validation scores than those of the RandomForest. The AdaBoosting algorithm overfitted the training data, and produced inferior cross-validation scores than those of the RandomForest and GradientBoosting methods.

- To decrease the bias of the RandomForest further, whilst simultaneously preventing any overfit, the BaggingClassifier method was used with a modified version of the original RandomForest containing an increased max-depth hyperparameter value (10 instead of 6). The BaggingClassifier fit the training data well, but did not produce superior cross-validation results than those of the RandomForest and GradientBoosting methods.

- In an attempt to improve on the scorse of the GradientBoosintg and RandomForest methods, a neural network was constructed using 4 dense layers. There were 89 input nodes (the number of features), followed by 3 dense layers containing 256 nodes with a 30% dropout rate for each. The final dense layer contained one exit node. The neural network produced far superior training and validation scores than the RandomForest and GradientBoosting algorithms. 

In light of the results from the modeling stage, explainability methods were applied to the RandomForest, the GradientBoostingClassifier, and the Sequential Neural Network.

<b>A Note on Validation:</b>
The models were trained on balanced data to eliminate any majority bias. However, in order to accurately evaluate a model's performance on real world data, the models were validated on unbalanced data. 

### Explainability:

- To extract explainability from the three models, "shapely values" were computed from the three models using the SHAP python library. 
- The way shapely values are calculated is complicated but also extremely interesting. They are derived from game theory, in that each feature is a "player" and can form coalitions with other "players" (features) to recieve a payoff. The payoff in this case is the prediction of the model output minus the average prediction of the model (which is simply the mean of the target values). 
- Put succinctly, a shapely value is calculated as the average marginal contribution of a feature value across all possible coalitions with other features.
- The brilliance of shapely values is not only can they explain the contribution of a featue to the overall model prediction, but they can also explain <i>local</i> predictions for a single observation (ie. how did the features of a single observation contribute to the model's prediction for that observation).
- The SHAP library contains great visualizations for shapely value explanations which I have included in the modeling notebook.


   


