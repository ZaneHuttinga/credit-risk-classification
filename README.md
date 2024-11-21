# credit-risk-classification
Data Visualization and Analytics Boot Camp Challenge 20

## Overview of the Analysis

In this challenge, we delve into a set of loan data to determine how well a model assesses risk. Specifically, we would like to know how well the model can predict healthy and high-risk loans. This is of course relevant when determining whether to give out a loan, as it is very important to understand the level of risk involved before agreeing to pay out money. Any firm would want a clear idea of the recipient's likelihood of repaying the loan.

The model in question is the LogisticRegression class from the linear_model module of the Python library sklearn. This is a machine learning algorithm that runs a regularized logistic regression on a dataset; this is a common statistical method used to predict binary outcomes. In this project, the inputs are individual loans, and the two possible outcomes are the labels 'healthy' and 'high risk'.

The dataset can be found in "Resources/lending_data" and imported into "credit_risk_classification.ipynb" as the DataFrame 'lending_data_df'. Each row represents a loan, and the outcomes are encoded in the column 'loan_status' (a value of 0 means the loan is healthy, and a value of 1 means that the loan is high-risk). The other columns give important information about the borrower and loan (the size of the loan,	the interest rate, the borrower's income, the ratio of debt to income, the number of accounts, the number of derogatory marks, and the borrower's total debt).

The machine learning process involves the following steps:
* Select the labels (y) and the features (X). These are given by the 'loan_status' column and the remaining columns, respectively.
* Split the data into a training set and a test set. This is done using the 'train_test_split' function from the sklearn module 'model_selection'.
* Using the LogisticRegression class, create a model by fitting it to the training data.
* Use the model to make predictions based on the test data.
* Evaluate the model's ability to predict the outcomes by constructing the confusion matrix and the classification report. These are done using the 'confusion_matrix' and 'classification_report' functions from the sklearn module 'metrics', respectively.

## Results

Using bulleted lists, describe the accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
    * Description of Model 1 Accuracy, Precision, and Recall scores.

## Summary

