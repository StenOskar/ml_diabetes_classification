# Questions

This document provides the group's answers to the questions proposed in the assignment.

1. Can survey questions asked from the CDC provide accurate predictions of whether an individual
has diabetes? Do you recommend additional features in the data?

**Survey questions**

Survey questions asked from the CDC can provide accurate predictions of whether an individual
**does not have** diabetes, but cannot accurately predicit if an individual **has** diabetes.

The three models tested on the full dataset made different predictions, which resulted in different
calucalted sensivities and specificities. For example, logistic regression got a specificity of 72%
while AdaBoost classifier got 97%. These are both high percentages, and the models got a total
accuracy of 73% and 87% respectively.

However, the calculated sensitivity for logistic regression was 78% while the sensitivity for
AdaBoost classifier was 20%. This is a low percentage, especially when you consider the importance
of the calculation, in addition to the fact that AdaBoost classifier performed best on the total
dataset.

With these considerations in mind, we cannot say that questions asked from the CDC provide accurate
predictions of whether an individual has diabetes or not. We can say however, that the questions
asked provide accurate predictions of whether an individual does not have diabetes.

**Additional features**

We do not recommend additional features in the data. We experimented with combining features in
order to obtain better predictions from the models. For example, we combined *HighBP* and
*HighCol* into *CardioRisk*, and *Stroke* and *HeartDiseaseorAttack* into *SevereCardioCondition*.

The new *CardioRisk* feature yielded no better correlation with the target attribute
*Diabetes_binary* than its original features. However, the *SevereCardioCondition* feature
correlated better with our target feature. We then tried training the models with the new feature,
and got little to no different results.

Because of this, we can say that the dataset is not really affected by additional features, or we
just did not create sufficient new features for the dataset.

2. What risk factors are most predictive of diabetes risk?

The risk factors most predicitve of diabetes risk can be derived from analyzing the correlations
between all features and our target feature *Diabetes_binary*. After taking a look at the
correlations, we find that *GenHlth*, *HighBP*, *DiffWalk*, *BMI* and *HighChol* are most
predicitve of diabetes risk.

3. Can we use a subset of the risk factors to accurately predict whether an individual has
diabetes?

We can use a subset of the risk factors to accurately predict whether an individual **has**
diabetes, but not to accurately predict whether an individual **does not have** diabetes.

This is very similar to the results discussed in question 1, however opposite, as one of the
machine learning models performed very differently on the subset.

The subset we used contained all the risk factors most predictive of diabetes risk, which were
discussed in question 2. When training the models on this dataset, logistic regression and AdaBoost
classifier performed similarly to when they were trained on the full dataset. However, the random
forest classifier model got different results.

When trained on the whole dataset, the random forest classifier got an accuracy of 86%, and when
trained on the subset it got a lower 71%. Even though the overall accuracy got lower, the
sensitivity increased considerably, from 16% to 77%.

Because of this, we can use the subset of the risk factors to accurately predict whether an
individual has diabetes, but not to accurately predict whether an individual does not have
diabetes.

4. What machine learning models are best for classifying the disease? Compare models and explain
why a model performed better based on the confusion matrix and minimizing false negatives.

The machine learning model best for classifying the disease is logistic regression.

As mentioned in question 1, we made calculations for accuracy, sensitivity and specificity for the
different machine learning models. When you analyze the ROC curve, you see that the AdaBoost
classifier model performed best overall. This fits well with the accuracy of 87%, which was the
highest among the models.

However, when you consider the domain you can say that false negatives are critical in our
situation. It really bad if our model predicts that an individual does not have diabetes, when in
reality the individual does. Because of this we should be more considerate about sensitivity.

The logisitic regression model had a sensitivity of 78%, while AdaBoost classifier had a 20%
sensitivity. Even though logistic regression only had a lower accuracy of 73%, it is the model with
the highest sensitivity. Because of this we might say that logistic regression performs better than
AdaBoost classifier, which is the completly opposite of what we derived earlier.

Therefore, when we consider the domain and the importance of false negatives, we can say that the
model best for classifying the disease is logistic regression.

We considered doing k-fold cross-validation on the logisitc regression model, but since it had a
lower accuracy percentage compared to the other models, we decided not to. We could however have
done cross-validation on the AdaBoost classifier model, but as we did not conclude this model to be
best for classifying the disease, we did not.
