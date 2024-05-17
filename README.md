# Term deposit subscriber predictor
## Background:
We are a small startup focusing mainly on providing machine learning solutions in the European banking market. We work on a variety of problems including fraud detection, sentiment classification and customer intention prediction and classification.

We are interested in developing a robust machine learning system that leverages information coming from call center data.

Ultimately, we are looking for ways to improve the success rate for calls made to customers for any product that our clients offer. Towards this goal we are working on designing an ever evolving machine learning product that offers high success outcomes while offering interpretability for our clients to make informed decisions.

## Data Description:
The data comes from direct marketing efforts of a European banking institution. The marketing campaign involves making a phone call to a customer, often multiple times to ensure a product subscription, in this case a term deposit. Term deposits are usually short-term deposits with maturities ranging from one month to a few years. The customer must understand when buying a term deposit that they can withdraw their funds only after the term ends. All customer information that might reveal personal information is removed due to privacy concerns.

## Attributes:
age : age of customer (numeric)

job : type of job (categorical)

marital : marital status (categorical)

education (categorical)

default: has credit in default? (binary)

balance: average yearly balance, in euros (numeric)

housing: has a housing loan? (binary)

loan: has personal loan? (binary)

contact: contact communication type (categorical)

day: last contact day of the month (numeric)

month: last contact month of year (categorical)

duration: last contact duration, in seconds (numeric)

campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)

Output (desired target):

y - has the client subscribed to a term deposit? (binary)

## Goal
Predict if the customer will subscribe (yes/no) to a term deposit (variable y)

## Methodology
In the exploratory data analysis all the features where examined to determine which one had the most predictive power. Applying feature engineering the selected features where transformed in order to maximize the performances. Four different classifier models were trained and tested with cross-validation: Support Virtual Machine (SVM), Decision Tree, Random Forest and XGBoost. The XGBoost classifier outperforms the other models and then was selected as the most suitable classifier for the task. The model reaches an accuracy of 80% with high precision and recall for the negative class (non-subscriber). For the positive class (subscriber) we have a very low precision and a recall of 77%. The results for the posive class can be improved collecting more samples.

## Conclusions
The unbalanced dataset make impossible create an accurate model to correctly identify positive samples. More samples of subscriber should be collected or synthetized. In order to partially balancing the dataset I used the weight matrix of the XGBoost classifier. From the feature importance analysis on the best model the duration of the call grater than 6 minutes and the age over 60 seems to be key feature in order to predict subscriber. This confirm the result of the data analysis where the retired people and over 60 are more incline to buy and people with negative balance and active loans are less incline to buy. Additionally From the data analysis the number of subscriber seems also to increase with the education grade and the students are more incline to subscribe.
