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
5. Balanced Random Forest Classifier
6. Easy Ensemble Classifier

The following model outputs were analyzed for all 6 models. 

* accuracy score
     *  measures how many observations in the testing set were correctly predicted by the model
* precision (i.e. positive predictive value)
     * measure of how reliable a positive classification is
     * Precision = TP / (TP + FP)
* recall/sensitivity (i.e. true positive rate)
     * ability of the classifier to find all the positive samples 
     * recall = TP / (TP + FN)
* F1
     * weighted average of the true positive rate (recall) and precision  
     * F1 = 2 ( precision * sensitivity ) / (precision + sensitivity)
     * a pronounced imbalance between sensitivity and precision will yield a low F1 score
* support (total number of actual occurrences in the dataset)


|                  | Predicted High Risk  |  Predicted Low Risk |
| -------------    | -------------       | -------------       |
| Actual High Risk  | True Positive (TP)  |  False Negative (FN)|
| Actual Low Risk  | False Positive (FP) | True Negative (TN)|

### Results

See image below for a summary of the results:
<p align="center">
  <img src = https://github.com/lauras521/Credit_Risk_Analysis/blob/d2946fa1b26111d5067930f40e93e83e9d1218a7/summary_of_all_tests.PNG>
</p>

The Easy Ensemble Classifier model has the highest accuracy score while the logistic regression undersampling model has the lowest balanced accuracy score.  

### Summary
For a credit card company there are many things to consider when reading the results of the models:

* Downside to a False Positive (i.e. actually low risk application but identified as high risk application)
    * you do not want a model that has a high rate of predicting low risk applications as high risk (i.e. false positive).  This would deny more people loans who would be good candidates for loans.
    * a model to minimize false positives will have a high precision
* Downside to a False Negative (i.e. actually high risk application but identified as low risk application)
   * you do not want a model that has a high rate of predicting high risk applications as low risk (i.e. false negative).  This could cost the company significantly since these people would not be able to pay off their debt.   
   * a model to minimize false negatives will have a high recall/sensitivity

Our first priority will be to pick a model to minimize false negatives (i.e. high recall) and then review the false positive rate to try and minimize that next (i.e. high precision).  The Easy Ensemble Classifier model has the highest recall of any model.  You can see only 8 high risk candidates were actually predicted as low risk out of 17,205 applications.  Additionally, 983 low risk applications were predicted as high risk which is the smallest number of applicants of any model.  This model optimizes both metrics to provide the fewest false positives and false negatives amongst all models.  As a result, I would recommend the company proceeds using this model.  The company might want to considered trying to further optimize the actually low risk applications who are being predicted as high risk from this model. 


## Resources
[link to code for over and undersampling models](https://github.com/lauras521/Credit_Risk_Analysis/blob/13d83effd92bd616b97250ea51257ed6a42cd04d/credit_risk_resampling.ipynb)

[link to code for BalancedRandomForestClassifier and EasyEnsembleClassifier models](https://github.com/lauras521/Credit_Risk_Analysis/blob/13d83effd92bd616b97250ea51257ed6a42cd04d/credit_risk_ensemble.ipynb)
