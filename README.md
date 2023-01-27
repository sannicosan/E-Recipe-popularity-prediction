# Summary
Title: E-Recipe-popularity-prediction

## Business Goal
The main objective of this business case is to be able to correctly predict popular recipes for the Tasty Byte web page i.e. which recipes will lead to high traffic, while trying to minimize the chance of showing unpopular recipes and be on target 80% of the times



## Methodology

We have treated the problem as a binary classification problem, with `high_traffic` as the target variable and the rest as the dependent variables, where we had both numeric and categorical variables.
We have converted all categorical to numeric ones (through One-Hot Encode technique) to fit all the data to a classification model suitable for the business case. 

We chose a **_Logistic Regression_** among all because of it's performance. With the model, we can make predictions about the popularity of the recipe displayed on the homepage with high precision*

*_Results will be presented in the following subsections_

## Metrics - KPI

The business criteria was to estimate which recipes will have have traffic 80% of the time. Since the exercise required a classification problem, the target classes were balanced and we also we wanted to minimize the chance of showing unpopular recipes (i.e. minimizing false positives), we have chosen **_precision_** as the main metric to evaulate model performance. 

With a model chosen, we can even now what the probability is for each recipe. If we choose a recipe that will be  popular with high probability, there will also a high chance of high traffic. Under this assumption, one extra thing we could do is measure the true traffic level (or the increase in traffic by default) and defined this number a the *_**KPI**_* for this use case. Unfortunately, since we don't have that information in our dataset, we will have to stick to _precision_ to decide between 'popular' and 'not popular' recipes.


Additionally, we supported our analysis on other concepts like the _confusion matrix_, _accuracy_, _recall_ and the _AUC-ROC score_ (Area under the ROC curve). 

At the end, we could report a **KPI/precision of  81%**  after the evaluation of our **_Logistic Regression model_**. 
The results will be summarized better in the next section.

## Conclusions:

* The three models (including the RandomForestClassifier) used for the classification problem perform well in general. However, we had to stick to the Logistic Regression for perfomance reasons. 
* We managed to achieved the required goal proposed (high precision, low number of False Positives)
* We have summamrized the results  in the following table (for all three models):
> _Note: All these results were from the evaluation on the test set._

| **Classifier**         | **Precision** | **Accuracy** | **Recall** | **AUC-ROC**  |
|------------------------|---------------|--------------|------------|--------------|
| **RandomForest**       | 0.75          | 0.68         | 0.73       | 0.7784019975 |
| **LightGBM**           | 0.81          | 0.74         | 0.76       | 0.785684561  |
| **LogisticRegression** | 0.81          | 0.76         | 0.79       | 0.8341656263 |

