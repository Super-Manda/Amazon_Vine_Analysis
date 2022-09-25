# :money_with_wings: Overview of the loan prediction risk analysis:
LendingClub is a peer-to-peer lending services company that has a credit card credit dataset.  This project uses various techniques of oversampling, undersampling, and combination-sampling (bias reduction) approaches to predict credit risk.  

## :credit_card: Purpose of this analysis:
The purpose is to evaluate the performance of these models and make recommendations on whether they should be used to predict credit risk.

## :moneybag: Results:

### Balanced accuracy score and the precision and recall scores of all six machine learning models

**1. Naive Random Oversampling**
- Accuracy: .6439
- Precision: .01
- Recall: .69

![1](https://github.com/Super-Manda/Credit-Risk/blob/main/Images/1Naive_Random_Oversampling.png)



**2. SMOTE Oversampling (Synthetic Minority Oversampling Technique)**
- Accuracy: .6629
- Precision: .01
- Recall: .63

![2](https://github.com/Super-Manda/Credit-Risk/blob/main/Images/2Smote_Oversampling.png)



**3. Cluster Centroids Undersampling**
- Accuracy: .5443
- Precision: .01
- Recall: .69

![3](https://github.com/Super-Manda/Credit-Risk/blob/main/Images/3Cluster_Centroids.png)



**4. SMOTEENN (Synthetic Minority Oversampling Technique with Edited Nearest Neighbor Undersampling)**
- Accuracy: .6748
- Precision: .01
- Recall: .76

![4](https://github.com/Super-Manda/Credit-Risk/blob/main/Images/4SMOTEENN.png)



**5. Balanced Random Forest Classifier**
- Accuracy: .7885
- Precision: .03
- Recall: .70

![5](https://github.com/Super-Manda/Credit-Risk/blob/main/Images/5Balanced_Random_Forest_Classifier.png)



**6. Easy Ensemble AdaBoost Classifier**
- Accuracy: .9317
- Precision: .09
- Recall: .92

![6](https://github.com/Super-Manda/Credit-Risk/blob/main/Images/6Easy_Ensemble_AdaBoost_Classifier.png)



## :heavy_dollar_sign: Summary of Six Models:
![Table1](https://github.com/Super-Manda/Credit-Risk/blob/main/Images/Table1.png)

### Results Summary:

## :chart: Recommendations:
- Out of these six models, the Easy Ensemble AdaBoost Classifier Model is the most successful.
