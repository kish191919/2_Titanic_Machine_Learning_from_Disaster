# Titanic_Machine_Learning_from_Disaster

Predict survival on the Titanic and get familiar with ML basics

This project follows the instructions of a Kaggle competition since 2012.

The link of the competition is https://www.kaggle.com/c/titanic

### Data description
The sinking of the RMS Titanic is one of the most infamous shipwrecks in history.  On April 15, 1912, during her maiden voyage, the Titanic sank after colliding with an iceberg, killing 1502 out of 2224 passengers and crew. This sensational tragedy shocked the international community and led to better safety regulations for ships.

One of the reasons that the shipwreck led to such loss of life was that there were not enough lifeboats for the passengers and crew. Although there was some element of luck involved in surviving the sinking, some groups of people were more likely to survive than others, such as women, children, and the upper-class.

In this challenge, we ask you to complete the analysis of what sorts of people were likely to survive. In particular, we ask you to apply the tools of machine learning to predict which passengers survived the tragedy.

### Files
train.csv - The training set should be used to build your machine learning models. For the training set, we provide the outcome (also known as the “ground truth”) for each passenger. Your model will be based on “features” like passengers’ gender and class. You can also use feature engineering to create new features.

test.csv - The test set should be used to see how well your model performs on unseen data. For the test set, we do not provide the ground truth for each passenger. It is your job to predict these outcomes. For each passenger in the test set, use the model you trained to predict whether or not they survived the sinking of the Titanic

gender_submission.csv - A set of predictions that assume all and only female passengers survive, as an example of what a submission file should look like.


### Evaluation Method
Predict if a passenger survived the sinking of the Titanic or not. 
For each PassengerId in the test set, predict a 0 or 1 value for the Survived variable. 

Score is the percentage of passengers you correctly predict. This is known simply as "accuracy”.
Submit a csv file with exactly 418 entries plus a header row. 

The file should have exactly 2 columns:
 - PassengerId (sorted in any order)
 - Survived (contains your binary predictions: 1 for survived, 0 for deceased)

### Data fields
pclass: A proxy for socio-economic status (SES)
 - 1st = Upper
 - 2nd = Middle
 - 3rd = Lower

age: Age is fractional if less than 1. If the age is estimated, is it in the form of xx.5

sibsp: The dataset defines family relations in this way...
 - Sibling = brother, sister, stepbrother, stepsister
 - Spouse = husband, wife (mistresses and fiancés were ignored)

parch: The dataset defines family relations in this way...
 - Parent = mother, father
 - Child = daughter, son, stepdaughter, stepson
 - Some children travelled only with a nanny, therefore parch=0 for them.

### Evaluation:

Random Forest:
```
Training Score: 0.43107505964550397
Confusion Matrix:
 [[7844    2   54]
 [5459   98   78]
 [5301    3  740]]
 10-fold Cross Validation Report: 
              precision    recall  f1-score   support

          0       0.42      0.99      0.59      7900
          1       0.95      0.02      0.03      5635
          2       0.85      0.12      0.21      6044

avg / total       0.71      0.44      0.31     19579

```
AdaBoost:
```
Training Score : 0.6292977254067664
Confusion Matrix:
 [[7301  311  288]
 [2875 2627  133]
 [2858  203 2983]] 
 10-fold Cross Validation Report: 
              precision    recall  f1-score   support

          0       0.56      0.92      0.70      7900
          1       0.84      0.47      0.60      5635
          2       0.88      0.49      0.63      6044

avg / total       0.74      0.66      0.65     19579

```
Support Vector Machine:
```
Training Score : 0.40349420090683086
Confusion Matrix:
 [[7900    0    0]
 [5635    0    0]
 [6043    0    1]]
10-fold Cross Validation Report: 
              precision    recall  f1-score   support

          0       0.40      1.00      0.58      7900
          1       0.00      0.00      0.00      5635
          2       1.00      0.00      0.00      6044

avg / total       0.47      0.40      0.23     19579

```
Naive Bayes classification :
```
Training Score : 0.8329333739756135
Confusion Matrix:
 [[7414  110  376]
 [ 631 4764  240]
 [ 588   89 5367]] 
10-fold Cross Validation Report: 
              precision    recall  f1-score   support

          0       0.86      0.94      0.90      7900
          1       0.96      0.85      0.90      5635
          2       0.90      0.89      0.89      6044

avg / total       0.90      0.90      0.90     19579
```
### Prediction

Model : Naive Bayes classification

Kaggle Score : 0.48767

Kaggle rank : 793 / 1244 (63.7%) [2018.4.5] 


