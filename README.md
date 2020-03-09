
# Module 5 Final Project


##  Project Overview:
This project is designed to explore machine learning models and methods for the task of classification. We've been tasked with finding a dataset with labeled data with at least 40,000 rows of data and 20 columns. We will generally follow the OSEMN process for a data science project, which includes:

* Obtaining the data
* Scrubing (or cleaning) the data
* Exploring and visualizing the data
* Modeling
* INterpreting the results


**Project goal:** The data we will be using (more below) is a bank marketing data set. The goal for our project is to develop as model that predicts the success of a bank marketing campaign based on the features we have in out data. This model should therefore help us be better able to identify potential customers and refine our the focus of future campaigns.

## Dataset - Bank Marketing Data Set
###  Abstract:
The data is related with direct marketing campaigns (phone calls) of a Portuguese banking institution. The classification goal is to predict if the client will subscribe a term deposit (variable y).

###  Citation:
This dataset is publicly available for research. The details are described in [Moro et al., 2014]. Please include this citation if you plan to use this database:

[Moro et al., 2014] S. Moro, P. Cortez and P. Rita. A Data-Driven Approach to Predict the Success of Bank Telemarketing. Decision Support Systems, In press, http://dx.doi.org/10.1016/j.dss.2014.03.001

Available at: [pdf] http://dx.doi.org/10.1016/j.dss.2014.03.001 [bib] http://www3.dsi.uminho.pt/pcortez/bib/2014-dss.txt

Link to data: https://archive.ics.uci.edu/ml/datasets/Bank+Marketing

###  Input variables:

**Bank client data:**

age: (numeric)
job: type of job (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown')
marital: marital status (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed)
education: (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown')
default: has credit in default? (categorical: 'no','yes','unknown')
housing: has housing loan? (categorical: 'no','yes','unknown')
loan: has personal loan? (categorical: 'no','yes','unknown')

**Related with the last contact of the current campaign:**

contact: contact communication type (categorical: 'cellular','telephone')
month: last contact month of year (categorical: 'jan', 'feb', 'mar', ..., 'nov', 'dec')
day_of_week: last contact day of the week (categorical: 'mon','tue','wed','thu','fri')
duration: last contact duration, in seconds (numeric). Important note: this attribute highly affects the output target (e.g., if duration=0 then y='no'). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.

**Other attributes:**

campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)
pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)
previous: number of contacts performed before this campaign and for this client (numeric)
poutcome: outcome of the previous marketing campaign (categorical: 'failure','nonexistent','success')

**Social and economic context attributes:**

emp.var.rate: employment variation rate - quarterly indicator (numeric)
cons.price.idx: consumer price index - monthly indicator (numeric)
cons.conf.idx: consumer confidence index - monthly indicator (numeric)
euribor3m: euribor 3 month rate - daily indicator (numeric)
nr.employed: number of employees - quarterly indicator (numeric)
Output variable (desired target):

**y** - has the client subscribed a term deposit? (binary: 'yes','no')


## Modeling

As this is a project for learning purposes, we're going to try out a lot of models. In this section we will work through

**Logistic Regression
K-Nearest Neighbors
Decision Trees and Random Forest
XGBoost
Support Vector Machines (SVM)**

We'll also apply a grid search method to each to see if we can work through a range of hyper-parameters to find a what performs best. In short, we'll be doing a lot!

## Conclusions

At this time our models do not perform well enough to implement them in the way we have explored

Although on the high end our models may allow us to significantly reduce costs:

Our baseline campaign cost is as much as: $2,890,000
The logreg model could save up to: $1,629,550
The random forest model could save up to $1,758,475
However, the potential drop in revenue is not offset:

Baseline revenue expectations are as high as $35,200,000
The logreg model may allow us to miss up to: $-10,016,545
The random forest model may allow us to miss up to $-14,107,786
Due to it's better precision Random Forest was able to lower costs more significantly, but it also had a much higher False Negative rate, which given our scenario is ultimately more costly

Logistic Regression appears to be the method of choice for this problem. Although we do not have it as tuned as we would like it to be, it consistently had the highest recall and therefore lowest false negative rate

**Next Steps and Recommendations:**

The current method of calling customers relies on a high volume of unproductive calls, and we should continue to work to find a method that helps reduce those
We should look into the true cost of a campaign, if true costs are in fact 3-4 times higher, then many of our models may be in place to begin saving money now
We should attempt to stack models to gain greater efficiency and potentially improve recall and precision
greater data cleaning, feature transformation and feature engineering may help current models perform better on the margins