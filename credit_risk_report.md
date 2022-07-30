# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

Credit Risk Classification

Credit risk poses a classification problem that’s inherently imbalanced. This is because healthy loans easily outnumber risky loans. In this Challenge, I used various techniques to train and evaluate models with imbalanced classes. I used a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

# Actions:

1. Split the Data into Training and Testing Sets

2. Create a Logistic Regression Model with the Original Data

3. Predict a Logistic Regression Model with Resampled Training Data

4. Create this Credit report


## 1. Split the Data into Training and Testing Sets

Open the starter code notebook and then use it to complete the following steps.

Read the lending_data.csv data from the Resources folder into a Pandas DataFrame.

Create the labels set (y) from the “loan_status” column, and then create the features (X) DataFrame from the remaining columns.

Note A value of 0 in the “loan_status” column means that the loan is healthy. A value of 1 means that the loan has a high risk of defaulting.

Check the balance of the labels variable (y) by using the value_counts function.

Split the data into training and testing datasets by using train_test_split.

## 2. Create a Logistic Regression Model with the Original Data

Employ your knowledge of logistic regression to complete the following steps:

Fit a logistic regression model by using the training data (X_train and y_train).

Save the predictions on the testing data labels by using the testing feature data (X_test) and the fitted model.

Evaluate the model’s performance by doing the following:

1. Calculate the accuracy score of the model.

2. Generate a confusion matrix.

3. Print the classification report.

Answer the following question: How well does the logistic regression model predict both the 0 (healthy loan) and 1 (high-risk loan) labels?

## 3. Predict a Logistic Regression Model with Resampled Training Data

# I noticed the small number of high-risk loan labels? So I tried a model that uses resampled data in hopes that it performed better. In the follwoing, I resampled the training data and then reevaluated the model. Specifically, I used RandomOverSampler.

To do so, I completed the following steps:

Use the RandomOverSampler module from the imbalanced-learn library to resample the data. Be sure to confirm that the labels have an equal number of data points.

Use the LogisticRegression classifier and the resampled data to fit the model and make predictions.

Evaluate the model’s performance by doing the following:

1. Calculate the accuracy score of the model.

2. Generate a confusion matrix.

3. Print the classification report.

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * balanced_accuracy_score(y_test, prediction) = 0.9520479254722232
  * confusion_matrix(y_test, prediction) = array([[18663,   102],
       [   56,   563]])
  * print(classification_report_imbalanced(y_test, prediction)) 
      * recall: 0 = .99, 1 = .91
      * precision: 0 = 1, 1 = .85
 
 


* Machine Learning Model 2:
  * balanced_accuracy_score(y_test, prediction) = 0.9936781215845847
  * confusion_matrix(y_test, prediction) = array([[18649,   116],
       [    4,   615]])
  * print(classification_report_imbalanced(y_test, prediction)) 
      * recall: 0 = .99, 1 = .99
      * precision: 0 = 1, 1 = .84
      

## Summary

Question: How well does the logistic regression model predict both the 0 (healthy loan) and 1 (high-risk loan) labels?
Answer: The logistic regression model does well because the pool of low-risk loans is greater than the pool of high-risk loans. The structure of data makes it so. We want the model to be better trained to pick the high-risk loans.

Question: How well does the logistic regression model, fit with oversampled data, predict both the 0 (healthy loan) and 1 (high-risk loan) labels?
Answer: The logistic regression model, fit with oversampled data, was better able to predict high-risk loans as indicated by the improved recall for the high-risk loans.

I would recommend the second model since its recall has improved.


