# Titanic_Machine_Learning_from_Disaster

Predict survival on the Titanic and get familiar with ML basics
This project follows the instructions of a Kaggle competition since 2012.
The link of the competition is https://www.kaggle.com/c/titanic

### Data description
The sinking of the RMS Titanic is one of the most infamous shipwrecks in history.  On April 15, 1912, during her maiden voyage, the Titanic sank after colliding with an iceberg, killing 1502 out of 2224 passengers and crew. This sensational tragedy shocked the international community and led to better safety regulations for ships.

One of the reasons that the shipwreck led to such loss of life was that there were not enough lifeboats for the passengers and crew. Although there was some element of luck involved in surviving the sinking, some groups of people were more likely to survive than others, such as women, children, and the upper-class.

In this challenge, we ask you to complete the analysis of what sorts of people were likely to survive. In particular, we ask you to apply the tools of machine learning to predict which passengers survived the tragedy.

### Files
- train.csv - The training set should be used to build your machine learning models. For the training set, we provide the outcome (also known as the “ground truth”) for each passenger. Your model will be based on “features” like passengers’ gender and class. You can also use feature engineering to create new features.

- test.csv - The test set should be used to see how well your model performs on unseen data. For the test set, we do not provide the ground truth for each passenger. It is your job to predict these outcomes. For each passenger in the test set, use the model you trained to predict whether or not they survived the sinking of the Titanic

- gender_submission.csv - A set of predictions that assume all and only female passengers survive, as an example of what a submission file should look like.


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

DecisionTreeClassifier:
```
Training Score: 0.8183733401430031
Confusion Matrix:
 [[484  57]
 [ 93 247]] 

10-fold Cross Validation Report: 
              precision    recall  f1-score   support

          0       0.84      0.89      0.87       541
          1       0.81      0.73      0.77       340

avg / total       0.83      0.83      0.83       881

```
Randomforest:
```
Training Score : 0.8081588355464759
Confusion Matrix:
  [[483  58]
  [106 234]] 
 
10-fold Cross Validation Report: 
              precision    recall  f1-score   support

          0       0.82      0.89      0.85       541
          1       0.80      0.69      0.74       340

avg / total       0.81      0.81      0.81       881

```
AdaBoost
```
Training Score : 0.8103804902962205
Confusion Matrix:
[[539   2]
 [  5 335]] 
 
10-fold Cross Validation Report: 
              precision    recall  f1-score   support

          0       0.99      1.00      0.99       541
          1       0.99      0.99      0.99       340

avg / total       0.99      0.99      0.99       881

```
Support Vector Machine :
```
Training Score : 0.8161006128702757
Confusion Matrix:
 [[478  63]
 [ 83 257]] 
 
10-fold Cross Validation Report: 
              precision    recall  f1-score   support

          0       0.85      0.88      0.87       541
          1       0.80      0.76      0.78       340

avg / total       0.83      0.83      0.83       881

```
Naive Bayes classification :
```
Training Score : 0.7956716036772217
Confusion Matrix:
 [[431 110]
 [ 63 277]]
 
10-fold Cross Validation Report: 
              precision    recall  f1-score   support

          0       0.87      0.80      0.83       541
          1       0.72      0.81      0.76       340

avg / total       0.81      0.80      0.81       881
```
VotingClassifier
```
Training Score : 0.8308605720122575
Confusion Matrix:
  [[484  57]
  [ 84 256]] 
 
10-fold Cross Validation Report: 
              precision    recall  f1-score   support

          0       0.85      0.89      0.87       541
          1       0.82      0.75      0.78       340

avg / total       0.84      0.84      0.84       881
```
### Prediction

Model : VotingClassifier

Kaggle Score : 0.78468

Kaggle rank : 4304 / 10676 (40.3%) [2018.4.5] 


