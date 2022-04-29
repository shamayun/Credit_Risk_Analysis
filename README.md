# Credit Risk Analysis
## Overview:
I have  used Python to build and evaluate several machine learning models to predict credit risk.
I followed the steps below:

1. Oversample the data using the **RandomOverSampler** and **SMOTE** algorithms.
2. Undersample the data using the **ClusterCentroids** algorithm.
3. Use a combinatorial approach of over- and undersampling using the **SMOTEENN** algorithm.
4. Compare two machine learning models that reduce bias, **BalancedRandomForestClassifier** and **EasyEnsembleClassifier**.

I am going to evaluate performance of these models and make recommendations based on whether they should be used to predict credit risk.

### Resources:
* LoanStats_2019Q1.csv
* Jupyter Notebook
* Python

## Balanced Accuracy Scores, Confusion Matrixes and Imbalanced Classification Reports:

### RandomOverSampler model**

![balance_accuracy_score](https://user-images.githubusercontent.com/96354508/165991147-d2162646-da39-4740-964c-3b025b14c034.png)

![imbalance_classification_report](https://user-images.githubusercontent.com/96354508/165991185-9e2c83bd-6a2f-4af2-ad62-37b3d5ecf404.png)

**Observations:**

The balanced accuracy score is 64%.
The high_risk precision is about 1% only with 62% sensitivity which makes a F1 of 2% only.
Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 68%.

**SMOTE model**

![smote_balance_accuracy](https://user-images.githubusercontent.com/96354508/165993021-a1c5c84b-ca0b-4a0e-9e00-8cc59834ed60.png)

![smote_classification_report](https://user-images.githubusercontent.com/96354508/165993048-59cd84ca-f26d-454f-a174-e6f99fbf1d05.png)


The results are pretty similar to the previous model.
The balanced accuracy score is 63%.
The high_risk precision is 1% only with 62% sensitivity which makes a F1 of 2% only.
Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 66%.

**ClusterCentroids model**

Here the balanced accuracy score is down to about 52%.
The high_risk precision is still 1% only with 63% sensitivity which makes a F1 of 1%.
Due to the high number of false positives, the low_risk sensitivity is only 40%.

**SMOTEENN model**

The balanced accuracy score is about 62%.
The high_risk precision is still 1% only with 68% sensitivity which makes a F1 of only 2%.
Due to the high number of false positives, the low_risk sensitivity is 57%.

**BalancedRandomForestClassifier model**

The balanced accuracy score improved to about 79%.
The high_risk precision is still low at 4% only with 67% sensitivity which makes a F1 of only 7%.
Due to a lower number of false positives, the low_risk sensitivity is now 91% with 100% presicion.
**EasyEnsembleClassifier model**

Now, the balanced accuracy score is high to about 93%.
The high_risk precision is still low at 7% only with 91% sensitivity which makes a F1 of only 14%.
Due to a lower number of false positives, the low_risk sensitivity is now 94% with 100% presicion.
### Summary
All the models used to perform the credit risk analysis show weak precision in determining if a credit risk is high.
The Ensemble models brought a lot more improvment specially on the sensitivity of the high risk credits.
The EasyEnsembleClassifier model shows a recall of 92% so it detects almost all high risk credit. On another hand, with a low precision, a lot of low risk credits are still falsely detected as high risk which would penalize the bank's credit strategy and infer on its revenue by missing those business opportunities.
For those reasons I would not recommend the bank to use any of these models to predict credit risk.

