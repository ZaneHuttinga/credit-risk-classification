# Credit Risk Classification
Data Visualization and Analytics Boot Camp Challenge 20

## Overview of the Analysis

In this challenge, we delve into a set of loan data to determine how well a model assesses risk. Specifically, we would like to know how well the model can predict healthy and high-risk loans. This is of course relevant when determining whether to give out a loan, as it is very important to understand the level of risk involved before agreeing to pay out money. Any firm would want a clear idea of the recipient's likelihood of repaying the loan.

The model in question is the LogisticRegression class from the linear_model module of the Python library sklearn. This is a machine learning algorithm that runs a regularized logistic regression on a dataset; this is a common statistical method used to predict binary outcomes. In this project, the inputs are individual loans, and the two possible outcomes are the labels 'healthy' and 'high-risk'.

The dataset can be found in "Resources/lending_data" and imported into "credit_risk_classification.ipynb" as the DataFrame 'lending_data_df'. Each row represents a loan, and the outcomes are encoded in the column 'loan_status' (a value of 0 means the loan is healthy, and a value of 1 means that the loan is high-risk). The other columns give important information about the borrower and loan (the size of the loan,	the interest rate, the borrower's income, the ratio of debt to income, the number of accounts, the number of derogatory marks, and the borrower's total debt).

The machine learning process involves the following steps:
* Select the labels (y) and the features (X). These are given by the 'loan_status' column and the remaining columns, respectively.
* Split the data into a training set and a test set. This is done using the 'train_test_split' function from the sklearn module 'model_selection'.
* Using the LogisticRegression class, create a model by fitting it to the training data.
* Use the model to make predictions based on the test data.
* Evaluate the model's ability to predict the outcomes by constructing the confusion matrix and the classification report. These are created using the 'confusion_matrix' and 'classification_report' functions from the sklearn module 'metrics', respectively.

## Results

The confusion matrix for the model is
[[18673,    86],
[   32,   593]]
meaning that there are
* 18673 loans correctly predicted to be healthy;
* 32 falsely predicted to be healthy;
* 593 correctly predicted to be high-risk;
* 86 falsely predicted to be high-risk.

Using these numbers, the classification report contains the following figures:
* accuracy: 0.99
* for healthy loans:
  * precision: 1.00
  * recall: 1.00
  * F_1 score: 1.00
* for high-risk loans:
  * precision: 0.87
  * recall: 0.95
  * F_1 score: 0.91
* macro averages:
  * precision: 0.94
  * recall: 0.97
  * F_1 score: 0.95
* weighted averages:
  * precision: 0.99
  * recall: 0.99
  * F_1 score: 0.99

## Summary

While the accuracy, macro averages and weighted averages all look good, they are not the most informative statistics in this context. This is for two reasons:
* While it is best to correctly predict both healthy and high-risk loans, it is generally more important to predict high-risk loans correctly, since a falsely labeling a high-risk loan could cause a firm to take on more risk than intended, but falsely labeling a healthy loan would not.
* From the confusion matrix it is clear that the vast majority of loans in the test data are healthy, and the vast majority of those are correctly predicted to be healthy. In particular, this is inflating the weighted average.

We will turn instead to the individual labels.

Again, as the classification report indicates, the model is excellent at predicting healthy loans. Specifically, with a precision of 1.00, we know that if the model predicts that a loan is healthy, it is virtually guaranteed to be healthy. Furthermore, a recall value of 1.00 indicates that if a loan is actually healthy, it is virtually guaranteed that the model will predict that it is healthy.

However, as noted above, one would generally expect a firm to care more about correctly predicting high-risk loans. We can see clearly that the model is not quite as good at this, though still reasonably good. The precision tells us that if the model predicts that a loan is high-risk, there is an 87% chance that it actually is high-risk. Perhaps more importantly, the recall tells us that if a loan actually is high-risk, there is a 95% chance that the model will predict that it is high-risk. This means that 5% of high-risk loans will be mislabeled as healthy. Whether this is an acceptable level of risk will depend on a particular firm's specific situation; however, in general this low percentage of missed high-risk loans is a good reason to recommend this model.