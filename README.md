# Rossman-Sales-Prediction-Regression
# Introduction:

Sales forecast is one of the most important weapons a retail company can possibly have in its arsenal. It helps a firm to manage its inventory, warehousing, and supply chain effectively and cut down costs significantly. 
Rossmann similarly, is a pharmaceutical store chain with over 3000 stores across 7 European countries, whose past sales data is been made available to us. We need to model a regression model that’d help Rossmann predict its sales for a horizon of 6 weeks. 


# Objective: 

Given the past sales data, along with data about competitive stores, in its vicinity, I’m required to develop a machine learning regression model that can predict the sales for a forecast horizon of 6 weeks.


# Dataset:
We have a dataset containing daily sales entries of over 1115 Rossman stores over a period of two and a half years (2013-01-01 to 2015-07-31), along with supplemental data about the competitional stores as well. Few of the columns in the dataset: 
● Id - an Id that represents a (Store, Date) duple within the test set 

● Store - a unique Id for each store 

● Sales - the turnover for any given day (this is what you are predicting) ● Customers - the number of customers on a given day 

● Open - an indicator for whether the store was open: 0 = closed, 1 = open ● StateHoliday - indicates a state holiday. Normally all stores, with few exceptions, are closed on state holidays. Note that all schools are closed on public holidays and weekends. a = public holiday, b = Easter holiday, c = Christmas, 0 = None ● SchoolHoliday - indicates if the (Store, Date) was affected by the closure of public schools 

● StoreType - differentiates between 4 different store models: a, b, c, d ● Assortment - describes an assortment level: a = basic, b = extra, c = extended 

● CompetitionDistance - distance in meters to the nearest competitor store ● CompetitionOpenSince[Month/Year] - gives the approximate year and month of the time the nearest competitor was opened 

● Promo - indicates whether a store is running a promo on that day ● Promo2 - Promo2 is a continuing and consecutive promotion for some stores: 0 = store is not participating, 1 = store is participating 

● Promo2Since[Year/Week] - describes the year and calendar week when the store started participating in Promo2 

● PromoInterval - describes the consecutive intervals Promo2 is started, naming the months the promotion is started anew. E.g. "Feb,May,Aug,Nov" means each round starts in February, May, August, November of any given year for that store


# Approach:

Developing a machine learning model involves following steps:
1. Data Description: Understanding the characteristics of the dataset in hand.
2. Handling Null Values
3. Exploratory Data Analysis to understand the underlying patterns in the data.
4. Handling Outliers.
5. Feature Conditioning: Scaling and encoding (categorical features)
6. Feature Selection
7. Model Implementation and prediction 


# Results:

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
