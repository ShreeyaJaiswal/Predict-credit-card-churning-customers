# Description

<b>The problem statement was taken from Kaggle with the below problem description:-</b>

A manager at the bank is disturbed with more and more customers leaving their credit card services. They would really appreciate if one could predict for them who is gonna get churned so they can proactively go to the customer to provide them better services and turn customers' decisions in the opposite direction

The dataset consists of 10,127 customers mentioning their age, salary, marital_status, credit card limit, credit card category, etc. There are nearly 21 features.
We have only 16.07% of customers who have churned. Thus, it's a bit difficult to train our model to predict churning customers.

# Walkthrough 

The solution has been built over Python using Pandas and Machine Learning models.

<b>Performed:-</b>
- Divide the data into Train and Test
- Data Analysis
- Feature Selection
- Feature Engineering
- Model Building
- Best Model Selection
- Hypertuning the parameter of the best model to improve overall performance.

<b>Train Test Split:-</b>
- Divided the dataset into train and test with the ratio of 70:30.
- Training set comprised of 7088 entries whereas test set of 3039.

<b>Data Analysis:-</b>
- The dataset comprised of 21 features out of which, there were 5 categorical,and 15 numerical independent variables, and 1 categorical dependent variable "Atrrition_Flag".
- The dataset was highly imbalanced with 16% out of the total entries as Attrited Customer, and rest as Existing Customer.
- There weren't any missing values.
- Not all features followed the normal distribution and indicated the presence of the outlier.
- As outliers are playing the role in indentifying the churn customers. Hence, they were not corrected.

<b>Feature Selection:-</b>
- Correlation of the features were calculated and visualized using Heatmap to identifify highly correlated features.
- Variation Inflation Factor was calculated to identify multicolienarity.
- Highly correlated,unwanted features were dropped, leaving behind 14 independent variables.

<b>Feature Engineering:-</b>
- Normalized the numerical features.
- Encoded the categorical data.
- Handled Imbalance data using SMOTE and ensemble technique.

<b>Model Building:-</b>
- Ensemble Classification models were used, like for bagging RandomForest, and for boosting adaboost, xgboost.
- XGBClassifier outperformed with an F1 score of 80% and recall of 73%.
- The next best was RandomForestClassifier with F1 score of 76% and recall of 66%.

- Using SMOTE-NC performed minority oversampling to balance the dataset.
- Trained the dataset over the ensemble Classification models along with naive bayes and SVM.
- Here also xgboost and randomforest outperformed.

<b>Best Model Selection:-</b>
-  After minority oversampling using SMOTE-NC it was evident, the two model which performed well were XGBCLassifier and RandomForest.
-  RandomForest: False Positive is 99 and False Negative is 107
-  XGB: False Positive is 67 and False Negative is 168
-  It can be inferred, XGB False positive is less compared to RandomForest False Positive whereas vice versa for False Negative.
-   As we want to withold the customers who are likely to churn, so the best model is where the False Positive and False Negative is very less but if either of the two needs to be prioritized, I'll choose False Positive to be less.
-  Hence, I select XGBClassifier as my model as comparatively it's predicting 32 correct result of customers who are likely to be churn on risk of offering benefit plans to 61 existing customers. This will also increase the likelyhood of those existing 61 customers to be a life long holder of the service offered.

<b>Hypertuning:-</b>
-  Used RandomizedSearchCV to attain the best combaination of the hyperparameters of XGBClassifier to improve the learning of the model.
-  On hypertuning the model, I was able to increase the performance from f1 score of 78 to 84%  and overall accuracy to 95%.
