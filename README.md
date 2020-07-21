
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

###  Variables:

<table>
    <thead>
        <tr>
            <th colspan="5">Bank Client Data</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>Variable</b></td>
            <td><b>Datatype</b></td>
            <td><b>Example</b></td>
        </tr>
        <tr>
            <td>age</td>
            <td>numeric</td>
            <td>27</td>
        </tr>
        <tr>
            <td>job</td>
            <td>categorical</td>
            <td>'admin','blue-collar','entrepreneur','housemaid'</td>
        </tr>
        <tr>
            <td>marital</td>
            <td>categorical</td>
            <td>'divorced','married','single','unknown'</td>
        </tr>
        <tr>
            <td>education</td>
            <td>categorical</td>
            <td>'basic.9y','high.school','illiterate','professional.course'</td>
        </tr>
        <tr>
            <td>credit_default</td>
            <td>categorical</td>
            <td>'yes','no', 'unknown'</td>
        </tr>
        <tr>
            <td>housing_loan</td>
            <td>categorical</td>
            <td>'yes','no','unknown'</td>
        </tr>
        <tr>
            <td>personal_loan</td>
            <td>categorical</td>
            <td>'yes','no','unknown'</td>
        </tr>
    </tbody>
</table>

<table>
    <thead>
        <tr>
            <th colspan="5">Campaign Data</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>Variable</b></td>
            <td><b>Datatype</b></td>
            <td><b>Example</b></td>
        </tr>
        <tr>
            <td>contact_type</td>
            <td>categrical</td>
            <td>'cellular','telephone'</td>
        </tr>
        <tr>
            <td>month</td>
            <td>categorical</td>
            <td>'jan','feb','mar'</td>
        </tr>
        <tr>
            <td>day_of_week</td>
            <td>categorical</td>
            <td>'mon','tues','wed'</td>
        </tr>
        <tr>
            <td>call_duration</td>
            <td>numeric</td>
            <td>seconds: 240</td>
        </tr>        
        <tr>
            <td>campaign</td>
            <td>numeric</td>
            <td>number of times customer called: 5</td>
        </tr>
        <tr>
            <td>p_days</td>
            <td>numeric</td>
            <td>6 (number of days that passed by after the client was last contacted from a previous campaign (999 means client was not previously contacted)</td>
        </tr>
        <tr>
            <td>poutcome</td>
            <td>categorical</td>
            <td>outcome of previous campaign: "failure","success","nonexistant"</td>
        </tr>      
    </tbody>
</table>

**Social and economic context attributes:**

<table>
    <thead>
        <tr>
            <th colspan="5">Social and Economic Context</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>Variable</b></td>
            <td><b>Datatype</b></td>
            <td><b>Example</b></td>
        </tr>
        <tr>
            <td>employment_variation_rate</td>
            <td>numeeric</td>
            <td>quarterly indicator of employement: 1.1</td>
        </tr>
        <tr>
            <td>consumer_price_index</td>
            <td>numeric</td>
            <td>monthly indicator of consumer prices: 93.99</td>
        </tr>
        <tr>
            <td>consumer_confidence_index</td>
            <td>numeric</td>
            <td>monthly indicator of consumer confidence: -36.4</td>
        </tr>
        <tr>
            <td>euribor_3-month_rate</td>
            <td>numeric</td>
            <td>daily indicator of EURO interback lending rate: 4.857</td>
        </tr>        
        <tr>
            <td>nr.employed</td>
            <td>numeric</td>
            <td>number of employees: 5191</td>
        </tr>
    </tbody>
</table>

**Output variable (desired target):**

**y** - has the client subscribed a term deposit? (binary: 'yes','no')


## Modeling

As this is a project for learning purposes, we're going to try out a lot of models. In this section we will work through:

* **Logistic Regression**
* **K-Nearest Neighbors**
* **Decision Trees and Random Forest**
* **XGBoost**
* **Support Vector Machines (SVM)**

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