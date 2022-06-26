# Credit-Card-Fraud-Detection
In this project fraudulent credit card transactions are detected with the help of Machine learning models and sampling techniques.

## Table of Contents
1. [Dataset](#p1)
2. [Requirements](#p2)
3. [Models](#p3)
4. [Cross Validation Techniques](#p4)
5. [Class Balancing Techniques](#p5)
6. [Results](#p6)
7. [Conclusion](#p7)
8. [References](#p8)

## <a name="p1">Dataset</a>
The dataset used is customer-level data that has been collected and analysed during a research collaboration of Worldline and the Machine Learning Group available on [Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud).<br>
The data set includes credit card transactions made by European cardholders over a period of two days in September 2013. Out of a total of 2,84,807 transactions, 492 were fraudulent. This data set is highly unbalanced, with the positive class (frauds) accounting for 0.172% of the total transactions. The data set has also been modified with Principal Component Analysis (PCA) to maintain confidentiality. Apart from ‘time’ and ‘amount’, all the other features (V1, V2, V3, up to V28) are the principal components obtained using PCA. The feature 'time' contains the seconds elapsed between the first transaction in the data set and the subsequent transactions. The feature 'amount' is the transaction amount. The feature 'class' represents class labelling, and it takes the value 1 in cases of fraud and 0 in others.

## <a name="p2">Requirements</a>
This project requires Python and the following Python libraries installed:
* numpy
* pandas
* xgboost
* scikit-learn
* matplotlib
* seaborn
* scipy
* statsmodels

## <a name="p3">Models</a>
1. Logistic Regression<br>
  a. L1 Regularisation<br>
  b. L2 Regularisation
2. K-Nearest Neighbors
3. Decision Trees<br>
  a. Gini Index Criterion<br>
  b. Entropy Criterion
4. Random Forest
5. XGBoost
6. Support Vector Machine with Sigmoid Kernel

## <a name="p4">Cross Validation Techniques</a>
- RepeatedKFold
- StratifiedKFold

## <a name="p5">Class Balancing Techniques</a>
- Random Oversampling
- SMOTE
- ADASYN

## <a name="p6">Results</a>
The Accuracy, ROC Value and Threshold of the the models trained are provided in [Results.csv](https://github.com/Marisha18/Credit-Card-Fraud-Detection/blob/main/Results.csv).
## <a name="p7">Conclusion</a>
We can see that the fraudulent transctions are mostly densed in the lower range of amount, whereas the non-fraudulent transctions are spreaded throughout low to high range of amount.

We do not see any specific pattern for the fraudulent and non-fraudulent transctions with respect to Time.

Given the class imbalance ratio, the accuracy is measured using the Area Under an ROC(Receiver operating characteristic) Curve (ROC) as confusion matrix accuracy is not meaningful for unbalanced classification.

In the oversample cases, of all the models we build found that the **XGBoost model with Random Oversampling with StratifiedKFold CV** gave us the best accuracy and ROC on oversampled data. Post that we performed hyperparameter tuning and achieved the following metrics : 

**XGboost roc_value: 0.9815403079438694<br>
XGBoost threshold: 0.01721232570707798**

However, of all the models we created we found **Logistic Regression with L2 Regularisation for StratifiedKFold cross validation** (without any oversampling or undersampling) gave us the best result.

## <a name="p8">References</a>
- Dataset: [Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
---
---
