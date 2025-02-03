# pcmlai_bank

## Practical Application III: Comparing Classifiers

Goal: compare the performance of the classifiers K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines. Utilize a dataset related to marketing bank products over the telephone. 

## Link to codio for executing notebook (given permissions to anyone with link)
https://colab.research.google.com/drive/1nZ8cxw6q-71dFicQcsT2ZOKLOMEXbZhj#scrollTo=DIYJBbiAk8z4

## Link to ipynb code.
https://github.com/gputti/pcmlai_bank/blob/main/application_III.ipynb

## Observations
There are lot of observations and it may be difficult to list all. I am listing few important ones here. Please read comments in application for additional observations.
1. Data is skewed. TP(True Positive) are around 11% and TN 89%. So accuracy is not a good measure.
2. As explained in problem statement, we are dropping duration column.
3. Looking at correlation matrix for numerical columns, age and campaign has less influence on target column.
4. pdays column was renated as contacted and also values are changed to 0 or 1 (check comments for additional info)
5. LabelEncoding was done for all categorical columns except age.
6. If accuracy is considered, LogicalRegression has given highest accuracy. 


## Summary 
Target feature is highly skewed, so accuracy is not a good measure. True posiive is if a contact subscribed to term deposit. True negative is if a contact declines to term deposit prescription. As results are skewed, we simply can't depend on accuracy. 
Carefully considering negative cases, False Positive is harmful to business, i.e. model predicts a user is subscribed, where in reality not. so we stop following up. False Negative is annoying, but no harm. 
So target for highest FN. For comparing models, we better look at Recall. 

The true positive rate (TPR), or the proportion of all actual positives that were classified correctly as positives, is also known as recall.
Recall = TP/(TP+FN). So we need to look for highest FN i.e. lowest Recall. 
Comparing all we found DecisionTreeClassifier gives lowest Recall and gives 83%. 

