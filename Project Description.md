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
- 

<b>Model Building:-</b>
<b>Best Model Selection:-</b>
<b>Hypertuning:-</b>
