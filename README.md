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

## Results from Balanced Accuracy Scores, Confusion Matrixes and Imbalanced Classification Reports:

### RandomOverSampler model

![balance_accuracy_score](https://user-images.githubusercontent.com/96354508/165991147-d2162646-da39-4740-964c-3b025b14c034.png)

![imbalance_classification_report](https://user-images.githubusercontent.com/96354508/165991185-9e2c83bd-6a2f-4af2-ad62-37b3d5ecf404.png)

**Observations:**

* The balanced accuracy score is 64%.
* The high_risk precision is about 1% only with 62% sensitivity which makes a F1 of 2% only.
* Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 65%.

**SMOTE model**

![smote_balance_accuracy](https://user-images.githubusercontent.com/96354508/165993021-a1c5c84b-ca0b-4a0e-9e00-8cc59834ed60.png)

![smote_classification_report](https://user-images.githubusercontent.com/96354508/165993048-59cd84ca-f26d-454f-a174-e6f99fbf1d05.png)


**Observations:**
* The results are very similar to the previous model.
* The balanced accuracy score is 63%.
* The high_risk precision is 1% only with 62% sensitivity which makes a F1 of 2% only.
* Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 64%.

**ClusterCentroids model**

![cluster_centroid_balance_accuracy](https://user-images.githubusercontent.com/96354508/166119026-606f3804-c638-4863-bc38-3ff846b25fd0.png)

![cluster_centroid_classification_report](https://user-images.githubusercontent.com/96354508/166117660-1e7936c5-ff4a-4dbd-9756-5cd132b20502.png)

**Observations:**
* Balanced accuracy score is down to about 52%.
* The high_risk precision is still 1% only with 60% sensitivity which makes a F1 of 1%.
* Due to the high number of false positives, the low_risk sensitivity is only 43%.

**SMOTEENN model**

![smotten_balance_score](https://user-images.githubusercontent.com/96354508/166118079-ff813ed0-e500-4cba-9ac3-3480594bb691.png)

![smotten_classification_store](https://user-images.githubusercontent.com/96354508/166118089-f70ae2f6-b27a-400d-8d26-8668d36c7c70.png)

**Observations:**
* The balanced accuracy score is about 62%.
* The high_risk precision is 1% only with 71% sensitivity which makes a F1 of only 2%.
* Due to the high number of false positives, the low_risk sensitivity is 54%.

**BalancedRandomForestClassifier model**

![forest_classifier_balance_accuracy](https://user-images.githubusercontent.com/96354508/166119347-cbce8e1b-9b04-46d7-b138-ae36128cdd57.png)

![forest_classifier_classification_report](https://user-images.githubusercontent.com/96354508/166119351-79a4a6cc-49f6-4a97-9a3d-d7e9aa815075.png)

**Observations:**
* The balanced accuracy score improved to  79%.
* The high_risk precision is low at 4% only with 67% sensitivity which makes a F1 of only 7%.
* Due to a lower number of false positives, the low_risk sensitivity is now 91% with 100% presicion.

**EasyEnsembleClassifier model**

![easy_ensemble_balance_accuracy](https://user-images.githubusercontent.com/96354508/166119471-1b1e9f79-25a1-436f-bc1f-b73ea27d6d93.png)

![easy_ensemble_classification_report](https://user-images.githubusercontent.com/96354508/166119475-14a5af3c-c551-4193-85df-d16211c08ce3.png)

**Observations:**
* The balanced accuracy score is high to ~93%.
* The high_risk precision is still low at 7% with 91% sensitivity which makes a F1 of only 14%.
* Due to a lower number of false positives, the low_risk sensitivity is now 94% with 100% presicion.
## Summary
* All the above models utilized to perform the credit risk analysis display weak precision in determining if a credit risk is high.
* The Ensemble models brought a lot more accuracy on the sensitivity of the high risk credits.
* The EasyEnsembleClassifier model shows a recall of 92% so it detects almost all high risk credit. With a low precision, a lot of low risk credits are still falsely detected as high risk, which would penalize the bank's credit strategy.

**Recommendation:** I would recommend the bank to use EasyEnsembleClassifier model among all models used, because of improved accuracy.

