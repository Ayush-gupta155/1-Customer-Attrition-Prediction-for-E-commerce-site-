## Customer Churn/Attrition Prediction for E-Commerce Sites
### Predict the type of customer that has the potential to churn by identifying features to minimize customer churn rates and get the right business decisions.

Dataset: [Download](https://www.kaggle.com/datasets/ankitverma2010/ecommerce-customer-churn-analysis-and-prediction)

## Features Expanation
![image](https://user-images.githubusercontent.com/62954443/222766551-02155965-d534-4a76-8013-fe54cd869e18.png)

## Data Overview
![image](https://user-images.githubusercontent.com/62954443/222767941-8c027b03-c69a-4293-8bea-d0c3865a45b0.png)
## ML Workflow
![image](https://user-images.githubusercontent.com/62954443/222775609-3aa77195-fd13-40e9-a2fc-4d6a1cc81b8c.png)

Churn Prediction Analysis divided into several Stages which are as:

Stage 0: Problem Statements, Goal, & Objective Analysis
Stage 1: EDA, Insights & Visialization (Data Understanding)
Stage 2: Data Processing (Data Cleansing & Feature Engineering)
Stage 3: Machine Learning Modelling & Model Evaluation

## Stage 0:
### Ps 
Shoptify is an e-commerce site that recently recorded 16.8% client attrition. This incident prompted Shoptify to lose a large number of clients, which had an influence on Shoptify's income. Therefore, the cost of acquiring a new client is substantially higher than the cost of retaining an existing one. As a result, Shoptify must identify the sources of client turnover and propose remedies to those issues. Shoptify can evaluate which marketing plan is most matched to a customer's attributes by properly forecasting which consumers are most likely to churn.

### Goal
Forecasting the sort of consumers most likely to churn by detecting attributes in order to reduce customer churn and make the best business decisions.

### Objective
1.Developing a Machine Learning model to forecast possible churn and determine what characteristics lead customers to churn as well as features that might reduce potential churn.

2.Maximizing the company's income by removing users who have the potential to churn if given different treatment, resulting in a lower churn rate.

### Business Metric
1.The customer churn rate is a representation of consumers that discontinue their use of e-commerce.

2.In the e-commerce industry, revenue is the most important indicator.

## Stage 1:
### EDA & Insight Summary
1.There are 7 variables that have missing values.

2.On average, customers spend 3 hours a day using an e-commerce application.

3.There are still many customers who are not using coupons while shopping.

4.Customers with locations closer to warehouses (< 15 km) are more dominant.

5.The number of customers complaining is around 1000 people. Recently it should be taken into consideration in the development of the business.

6.Variable tenure is of concern because many customers churn on tenure < 2 months.

7.Variable Tenure & Complaints have shown fairly good results with variable target (Churn) ie -0.35 and 0.25.

8.The rate of customers who churn is higher than the customers who use a few coupons (1-2 only) or even the customers who do not use the coupon at all.

9.The business decision that can be done is to provide coupons every weekend or on a specific date.

10.There is no guarantee that the higher the satisfaction score, the lower the probability of churn.

## Stage 2:
### Preprocessing
1.From the overall data there are still differences in the data entered by the specified category, so that data is first replaced with one value to remove the redundancy, ie on the column PreferredLoginDevice and PreferredPaymentMode I replace Phone with Mobile Phone, then CC with Credit Card, then with Cash On Delivery becomes COD. To handle the value feature that is still empty, imputation is performed by inputting the median value from each featue because the value of the mean and the median does not jump far and the value of the median is absolute.

2.After dilating, the dataset does not show rows of data that have the same value for all features.

3.With the score method, outliers that will be removed are around 0.2%, ie 11 rows of data that will be dropped.

4.Data categorical which type data object/string need to be converted into numerical data type with feature encoding which is divided into two methods, for feature gender label encoding is done and for data which has more than 2 categories one hot encoding is done.

5.The initial stage of feature transformation is menclassification whether the feature has a normal or non-normal distribution based on value skew and kurtosis. After that, split data is done to make the entire train set equal to 70% and test set equal to 30%. Then, standardization is used to adjust the values between features. Data training then di-scaling using Standard Scaler then fit & transform, while pada data testing only transform.

6.Features that are less relevant in the modeling process will be dropped, ie feature Customer ID, so the total feature used is 5 numerical features, 13 categorical features and 1 target feature ie 'Churn'.

7.In the target feature (Churn) there is a significant imbalance of data with a false value of 83.12% and a true value of 16.84%. To handle this situation, the process of oversampling is performed to reduce the ratio on the training data using the SMOTE method, which is generated New values ​​for the variables based on the distribution data if the ratio data is balanced.

## Stage 3:
### Modeling
![image](https://user-images.githubusercontent.com/62954443/222785127-db85fabf-83d0-4b14-a373-1526de4beadf.png)


Used 5 alternatives in determining a model with precision and rock and cross train test as parameters. Used random forest as the model chosen because it has a minimum value of false positive and a gap of 0.01.


