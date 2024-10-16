# Questions

This document provides the group's answers to the questions proposed in the assignment.

1. Can survey questions asked from the CDC provide accurate predictions of whether an individual
has diabetes? Do you recommend additional features in the data?

Yes based on the models in the dataset. It is possible to predict if an individual has diabetes.
The accuracy of the models is around 0.85. 
Additional features that could be added to the dataset are: 

2. What risk factors are most predictive of diabetes risk?

The risk factors most predicitve of diabetes risk can be derived from analyzing the correlations
between all features and our target feature *Diabetes_binary*. After taking a look at the
correlations, we find that *GenHlth*, *HighBP*, *DiffWalk*, *BMI* and *HighChol* are most
predicitve of diabetes risk.

3. Can we use a subset of the risk factors to accurately predict whether an individual has
diabetes?

4. What machine learning models are best for classifying the disease? Compare models and explain
why a model performed better based on the confusion matrix and minimizing false negatives.

The machine learning model to best classify if a person has diabetes is the adaBoost model.
This model has the lowest false negative rate and the highest accuracy.
the confusion matrix for the adaBoost model is as follows:
[TN, FP], [FN, TP] =
[42562, 1177], [5600,  1397]