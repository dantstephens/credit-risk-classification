# credit-risk-classification
Completed by Daniel Stephens

## Overview of this project

The goal of this analysis is to determine whether customers applying for credit will present a risk based on existing data from loan customers. To do this we'll use labeled data to train and test a machine learning model. The model could then be used to predict credit worthiness of future customers applying for credit when supplied with the appropriate inputs.

The dataset used to train and test the model contains the following datapoints: loan size, interest rate, borrower income, debt to income ratio, number of accounts,derogatory marks on credit report, total debt, loan status with financial institution. The loan status is the labeled data point that the model will be trained to predict. A '0' indicates that the loan is in good standing, and a '1' indicates an unhealthy loan. 

## credit_risk_classification.ipynb

In this notebook, the dataset is loaded from a CSV file into a Pandas data frame. The label column with loan status is seperated into a series labeled y and then droped from the dataframe. The dataframe is then given the variable name X. X and y variables were then split into training and test sets. An instance of the Logistic Regression model is created using the LogisticRegression module from SKLearn, and the training data is fitted to the model. Predictions were then made and saved to a dataframe using the trained model on the test data set. Finally, the accuracy of the predictions is calculated, a confusion matrix is generated, and a classification report is printed to display the results. 

A second model is then created with oversampled data. The trainind data is resampled using the RandomOverSampler module from imbalanced-learn. The resampled data is then used to retrain the model and it is tested again. 

## Results

* Machine Learning Model 1:
  * 99% accuracy
  * 0(healthy loan) predictions: 99% precision, 100% recall, 100% f1-score
  * 1(unhealthy loan) predictions: 91% precision, 85% recall, 88% f1-score


* Machine Learning Model 2(resampled):
  * 99% accuracy
  * 0(healthy loan) predictions: 99% precision, 100% recall, 100% f1-score
  * 1(unhealthy loan) predictions: 99% precision, 84% recall, 91% f1-score

## Summary

Based on the results and the use case, both models performed well. In terms of accuracy, both models performed about the same, with a 99% overall accuracy. There were no changes in the models ability to predict healthy loans, as both models had a 99% precision and 100% recall score. Using resampled data, the model did better at predicting unhealthy loans, with a 99% precision and 84% recall. Though the recall score is a point lower from the model that did not use resampled data, the imporved precision resulted in a 91% f1-score, compared to 85%. 

With all of that said, the model using the resampled data would be the recommended one to use out of the two. However, if the use case of the model is to predict whether or not an applicant will keep a loan in good standing and extend credit, either model would work well, as the most important aspect is it's ability to predict healthy loans. Incorrectly predicting unhealthy loans would be considered a false negative in this use case. The benefit to the model is that it can predict whether the customer will keep the loan in good standing with a high level of accuracy, avoiding unnecessary risk. The downside to the models is that they may occasionally present a false negative, and credit might not be extended to a customer who would actually keep the loan in good standing, resulting in missed business. 

## Running the app

* Download the Credit_Risk folder from this repo
* Maintain the file structure of the folder as static path is used in the program to import the data
