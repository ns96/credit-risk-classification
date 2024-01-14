# Credit Risk Classification

Using various Logistic Regression models to identify high-risk loans

## Overview of the Analysis

A major challenge of lending institutions is to keep track of which loans are healthy and will be repaid, and which loans are at a high-risk of defaulting. As such, having a machine learning model which can differentiate (i.e. classify) high-risk from the healthy loans will bring meanfingful value to the lender. 

To build the model, a dataset consiting of 77.5K records with 7 indepent variables (i.e features) which track loan size, interest rate, borrower income, debt to income ratio,   number of accounts, derogatory marks, and total debt. Those variable where are used by the model to predict the loan status which can be either healthy, or high-risk.  A major challenge with predicting the loan status is that the dataset is significantly unbalanced with 96.8% of the loans being healthy, with only 3.2% being flaged as high-risk. Given that, a model that simple looked to maximize accuracy would not be very useful, and would likely miss the critcial high-risk cases.

The data processing steps involved loading a csv file into a dataframe then do some basic data exploration. This was followed by seperating the 7 indepent variables into a new dataframe, and the target variable, "loan status" into it's own series. These datasets where then split into training and testing datasets, making sure to use stratification to compensate for the imbalance nature of the target variable. Additionally, the StandardScalar was used to normalize the train/test datasets.

 Two Logistic Regression models were evaluated. The first model (Model 1) was trained on the normalized, stratified dataset, while the second model (Model 2) was trained using random over sampleing to create a balanced training dataset.

## Results

- Logistic Regression Model 1:
  
  - Accuracy: 98.8% 
  - Precision:  High-Risk 87%, Health 100%
  - Recall: High-Risk 98%, Health 100%
  - F1-Score: High-Risk 92%, Health 100%

- Logistic Regression Model 2:
  
  - Accuracy: 99.6%
  - Precision: High-Risk 87%, Health 100%
  - Recall: High-Risk 100%, Health 99%
  - F1-Score: High-Risk 93%, Health 100%

## Summary

Based on the above results, **Model 2** performs better at find the high-risk loans (higher recall), as such it's recommended for deployment. From a business stand point, it's much better to correctly identify the high-risk loans at the expense of falsely identifing a few healthy loans as high-risk. Once identified as high-risk, additional resources can be used to prevent these accounts from defaulting, or correctly identify them as healthy, since a loan default would be the most costly outcome to lender.  
