# Rossman-Sales-Prediction-Regression
Summary:

Sales forecast is one of the most important weapons a retail company can possibly have in its arsenal. It helps a firm to manage its inventory, warehousing, and supply chain effectively and cut down costs significantly. 
Rossmann similarly, is a pharmaceutical store chain with over 3000 stores across 7 European countries, whose past sales data is been made available to us. We need to model a regression model that’d help Rossmann predict its sales for a horizon of 6 weeks. 


Objective: 

Given the past sales data, along with data about competitive stores, in its vicinity, I’m required to develop a machine learning regression model that can predict the sales for a forecast horizon of 6 weeks.


Approach:

Developing a machine learning model involves following steps:
1. Data Description: Understanding the characteristics of the dataset in hand.
2. Handling Null Values
3. Exploratory Data Analysis to understand the underlying patterns in the data.
4. Handling Outliers.
5. Feature Conditioning: Scaling and encoding (categorical features)
6. Feature Selection
7. Model Implementation and prediction 


Results:

1. Regression:
With the data filtered for multicollinearity and features trimmed down, we ran a number of
regression models on the features, of which Random Forest performed the best with a
regression score of 98.31 and adjusted R2 of 86.48% . But these models had an obvious
flaw to them, that is they depended on the feature ‘Customers’ in order to predict sales.
The number of customers in a real world scenario wouldn’t be something we’d have in
hand. And removing this one feature brought down the model performance by a huge
factor.

2. Regression with predicted customer values:
So the first solution to this problem was to create a model which predicts the number of
customers using the rest of the features in hand. I used the random forest regressor again
for this task. The resulting model scored 99.78% and adjusted R2 of 89.31%. Now we can
use these predicted values of footfall to go ahead and predict sales.
I again used the random forest regressor to predict sales using predicted customer value.
The model scored a regression score of 99.02% and adjusted R2 of 80.59%.
Yes the model performance has come down by a factor 5.89 %, but it remains a much more
practical approach.
