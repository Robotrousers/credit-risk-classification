# Module 20 Challenge Report 

## Overview of the Analysis

The purpose of this challenge is to see if a machine learning logistic regression model can be used to predict loan status and display them as 
healthy or unhealthy.

The dataset included historical financial data about loans that have been designated healthy or unhealthy (0 or 1) and
presented alongisde other data such as number of accounts, debt to income, derogatory marks etc. These other variables add weight to the model
to help it determine which will likely be healthy or unhealthy.

By using value_counts on both the training and testing data, you can see that only about 3% of the loans are unhealthy. y_test is distributed
as 0: 18759 and 1: 625. y_train is distributed as 0: 56277 and 1: 1875. Even though there is an imbalance, using our classification report, we
can see that there is enough support data to have a high accuracy and recall for both healthy and unhealthy to use this model reliably.

To prep this data, we first separated our target (y) from all the features (x). We split the data into X and y test, X and y train using the
train_test_split function. Using stratify=y we can maintain the class proportions. We used a random_state of 1 so we an reproducse our work.
We used a LogisticRegression model to train the data. We used a confusion matrix to get an overall insight into our classifications for both.
Our predictions on the test data were evaluated with metrics for precision, recall, f1-score and showed the amount of support data for each
group.

## Results

* LogisticRegression:
    * The accuracy of the model is 99%, which means it correctly classified 99% of all loans.
    * Healthy loans can be predicted with a precision and recall of 100% with no false positives and no false negatives!
    * There is a large number to support the healthy loan data.
    * Unhealthy loans have an 87% precision with a few false positives. This means 87% predicted as unhealthy were actually unhealthy.
    * Unhealthy loans recall is 95%, indicating 95% are correctly identified
    * While the support number for the unhealthy loans class is lower at 625, this is still very good, especially given the high precision
        and recall.

## Summary

The LogisticRegression model shows amazing performance at classifying loans. It has a 99% overall accuracy with great precision and recall numbers.
Healthy class has a 100% prediction rate. Unhealthy is lower at 87% precision and 95% recall, but this is still very high. As a bank, it is more
important to correctly identify the 1, or unhealthy class, but given the still high numbers for this, we can conclude that LogisticRegression is
a highly recommended and reliable model for prediction on this dataset. We were only asked to use one model for this challenge, so I cannot 
recommended another against this it, but since this model is so strong, I would not hesitate to recommend it.