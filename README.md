# :money_with_wings: Overview of the loan prediction risk analysis:
LendingClub is a peer-to-peer lending services company that has a credit card credit dataset.  This project uses various techniques of oversampling, undersampling, and combination-sampling (bias reduction) approaches to predict credit risk.  

## :credit_card: Purpose and Definitions of this analysis:
The purpose is to evaluate the performance of these models and make recommendations on whether they should be used to predict credit risk.

- **True Positive (TP)** means that high risk is predicted, and the loan is truly high risk.
- **True Negative (TN)** means that low risk is predicted, and the loan is truly low risk.
- **False Positive (FP)** means that high risk is predicted, but the loan is actually low risk.
- **False Negative (FN)** means that low risk is predicted, but the loan is actually high risk.
 
**pre = Precision = TP/(TP+FP).**  
- When the ratio of correctly predicted high risk loans to the total number of high risk predictions is high, then precision should be high.  
- When there are too many false positives, precision will be low.  

**rec = Recall = TP/(TP+FN).**  
- It is also known as Sensitivity.  
- It reflects the ratio of correctly predicted high risk loans to the total actual high risk loans.  Thus, a low recall means a lot of false negatives, and a high recall means a lot of true positives.  
- False negatives are a concern because they are actually high risk loans that went undetected and marked as low risk.  The Lending Club would want to look carefully at this metric because in this case, it is better to err on the side of excluding qualified applications than to accidentally let in applications that are actually high risk.

**spe = Specificity = TN/(TN+FP).**  
- Specificity reflects the True Negative Rate.  
- It is the ratio of correctly predicted low risk loans to the total actual low risk loans.  
- This should be less of a concern to the Lending Club, given that most of what they have is low risk.

**f1 = F1 Score = (2 * Precision * Recall/(Precision + Recall)).**  
- This is essentially a weighted average of Precision and Recall, with 1.0 being the best true positive rate.

**geo = Geometric Mean = sqrt(Recall * Specificity).**  
- This may be useful to examine the square root of the product of both true positives and true negatives.

**iba = Index Balanced Accuracy =  (1 + alpha * (Recall - Specificity)) * (Recall * Specificity).**  
- It measures performance.  
- Alpha refers to the True Positive rate minus True Negative rate. 

**sup = Support**

Reference:
[Supplemental Source for Definitions](https://dev.to/amananandrai/performance-measures-for-imbalanced-classes-2ojj)


## :moneybag: Results:

### Balanced accuracy score and the precision and recall scores of all six machine learning models

**1. Naive Random Oversampling**
- Accuracy: .6439
- High Risk Precision: .01
- Recall: .69

![1](https://github.com/Super-Manda/Credit-Risk/blob/main/Images/1Naive_Random_Oversampling.png)



**2. SMOTE Oversampling (Synthetic Minority Oversampling Technique)**
- Accuracy: .6629
- High Risk Precision: .01
- Recall: .63

![2](https://github.com/Super-Manda/Credit-Risk/blob/main/Images/2Smote_Oversampling.png)



**3. Cluster Centroids Undersampling**
- Accuracy: .5443
- High Risk Precision: .01
- Recall: .69

![3](https://github.com/Super-Manda/Credit-Risk/blob/main/Images/3Cluster_Centroids.png)



**4. SMOTEENN (Synthetic Minority Oversampling Technique with Edited Nearest Neighbor Undersampling)**
- Accuracy: .6748
- High Risk Precision: .01
- Recall: .76

![4](https://github.com/Super-Manda/Credit-Risk/blob/main/Images/4SMOTEENN.png)



**5. Balanced Random Forest Classifier**
- Accuracy: .7885
- High Risk Precision: .03
- Recall: .70

![5](https://github.com/Super-Manda/Credit-Risk/blob/main/Images/5Balanced_Random_Forest_Classifier.png)



**6. Easy Ensemble AdaBoost Classifier**
- Accuracy: .9317
- High Risk Precision: .09
- Recall: .92

![6](https://github.com/Super-Manda/Credit-Risk/blob/main/Images/6Easy_Ensemble_AdaBoost_Classifier.png)



## :heavy_dollar_sign: Summary of Six Models:
![Table1](https://github.com/Super-Manda/Credit-Risk/blob/main/Images/Table1.png)

### Results Summary:
- For balanced accuracy score, the Easy Ensemble with Adaptive Boost is the highest at 0.9317, and no other model really comes close, because the next highest is the Balanced Random Forest at 0.7885.  

- For high risk precision, no model is truly recommendable in the sense that they range from 0.01 to 0.09, so all models are considered to have too many false positives, but of these, the one that is the most precise among them would be the Easy Ensemble with Adaptive Boost at 0.09.  

- Since precision is not a deal breaker in this industry, and recall is more important, it is noted that the Easy Ensemble with Adaptive Boost has the highest recall and that no other model comes close.   

- When looking at the weighted average of precision and recall (the F1 score), the Easy Ensemble with Adaptive Boost is the highest with a score of 0.16.       

## :chart: Recommendations:
- Out of these six models, the Easy Ensemble AdaBoost Classifier Model is the most successful.

- The least successful is the Cluster Centroids.  That model should definitely not be used because there is no metric for which it provides good results.

