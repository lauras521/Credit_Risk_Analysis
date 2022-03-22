# Credit Card Risk Analysis

## Overview

### Purpose
Fast Learning wants to use machine learning to predict credit risk.  Management feels this will provide a quicker and more reliable loan experience.  The company feels machine learning will better predict good candidates for loans which will lead to lower default risk.  Several models to predict credit risk were completed and performance was evaluated.  

## Analysis and Results

### Analysis
The following models were ran for this analysis
1. Logistic Regression - Random Oversampling 
2. Logistic Regression - SMOTE Oversampling
3. Logistic Regression - Undersamping
4. Logistic Regression - SMOTEEN Combination Over and Undersampling
5. Balanced Random Forest Classifer
6. Easy Ensemble Classifer

The following model outputs were analyzed for all 6 models. 

* accuracy score
     *  measures how many observations in the testing set were correctly predicted by the model
* precision (i.e. positive predictive value)
     * mesaure of how reliable a positive classification is
     * Precision = TP / (TP + FP)
* recall/sensitivity (i.e. true positive rate)
     * ability of the classifier to find all the positive samples 
     * recall = TP / (TP + FN)
* F1
     * weighted average of the true postitive rate (recall) and precision  
     * F1 = 2 ( precision * sensitivity ) / (precision + sensitivity)
     * a pronounced imbalance between sensitivity and precision will yield a low F1 score
* support (total number of actual occurences in the dataset)


|                  | Predicted Positive  |  Predicted Negative |
| -------------    | -------------       | -------------       |
| Actual Positive  | True Positive (TP)  |  False Negative (FN)|
| Actual Negative  | False Positive (FP) | True Negative (TN)|

### Results

See image below for a summary of the results above:
<p align="center">
  <img src = https://github.com/lauras521/Credit_Risk_Analysis/blob/fa76f574ebb08d0bea05947ef6cd228d3d143fd7/summary_of_all_tests.PNG>
</p>

### Summary
The company wants to make sure 


## Resources
[link to code for over and undersampling models](https://github.com/lauras521/Credit_Risk_Analysis/blob/13d83effd92bd616b97250ea51257ed6a42cd04d/credit_risk_resampling.ipynb)

[link to code for BalancedRandomForestClassifier and EasyEnsembleClassifier models](https://github.com/lauras521/Credit_Risk_Analysis/blob/13d83effd92bd616b97250ea51257ed6a42cd04d/credit_risk_ensemble.ipynb)
