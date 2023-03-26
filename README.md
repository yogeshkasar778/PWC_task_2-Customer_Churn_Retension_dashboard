# PWC Power BI virtual work experience - Customer Churn Retention

![PwC Power BI Virtual Case Experience](https://user-images.githubusercontent.com/118357991/227788348-b988c4df-7923-46d6-8af7-102b8042f721.png)

## Problem Statement :

The purpose of this task is to:

- Define proper KPIs
- Create a dashboard for the retention manager reflecting the KPIs
- Write a short email to him (the engagement partner) explaining your findings, and include suggestions as to what needs to be changed
- Customers who left within the last month
- Services each customer has signed up for: phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies
- Customer account information: how long as a customer, contract, payment method, paperless billing, monthly charges, total charges and number of tickets opened in the categories administrative and technical
- Demographic info about customers – gender, age range, and if they have partners and dependents

## Datasource :

Dataset used for this task was presented by [Pwc](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) and customer churn Retention dataset:

Dataset: [Customer Churn Retention](https://github.com/yogeshkasar778/PWC_task_2---Customer_Churn_Retension_dashboard/blob/main/02%20Churn-Dataset.xlsx)

## Data Preparation:

Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Customer Churn dataset is give table named:

- `Customer churn dataset` which has `23 columns and 7043 rows` of observation

Data Cleaning for the dataset was done in the power query editor as follows:

- Replaced  the value is `SeniorCitizen` N coverted No and Y converted Yes

In the new table, one additional conditional columns were added using M-formula:

- loyalty = `SWITCH(TRUE(),'01 Churn-Dataset'[tenure]<=12,"< 1 year",'01 Churn-Dataset'[tenure]<=24,"< 2 years",'01 Churn-Dataset'[tenure]<=36,"< 3 years",'01 Churn-Dataset'[tenure]<=48,"< 4 years", '01 Churn-Dataset'[tenure]<=60,"< 5 years",'01 Churn-Dataset'[tenure]<=72,"< 6 years")`

- Removed Unnecessary columns 
- Removed Unnecessary rows
- Each of the columns in the table were validated to have the correct data type

## Data Modeling:

And then dataset was cleaned and transformed, it was ready to the data modeled.

- The `customer churn` tables as show below:

![Screenshot (39)](https://user-images.githubusercontent.com/118357991/227792100-51216842-8e72-4e48-b740-aab5d2f97541.png)

## Data Analysis (DAX):

Measures used in  all visualization are:

- Average MonthlyCharges = `AVERAGE('01 Churn-Dataset'[MonthlyCharges])`
- Average TotalCharges = `AVERAGE('01 Churn-Dataset'[TotalCharges])`
- churn count = `CALCULATE(COUNT('01 Churn-Dataset'[Churn]), ALLSELECTED('01 Churn-Dataset'[Churn]),'01 Churn-Dataset'[Churn] = "Yes")`
- churn rate % = `DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Churn]), '01 Churn-Dataset'[Churn] = "yes" ), COUNT('01 Churn-Dataset'[Churn]), 0)`
- Dependent in % = `DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Dependents]), '01 Churn-Dataset'[Dependents]="Yes",'01 Churn-Dataset'[Churn]="Yes"), CALCULATE(COUNT('01 Churn-Dataset'[Dependents]),'01 Churn-Dataset'[Churn]="Yes"), 0)`
- Dependent in % = `DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Dependents]), '01 Churn-Dataset'[Dependents]="Yes",'01 Churn-Dataset'[Churn]="Yes"), CALCULATE(COUNT('01 Churn-Dataset'[Dependents]),'01 Churn-Dataset'[Churn]="Yes"), 0)`
- Average MonthlyCharges = `AVERAGE('01 Churn-Dataset'[MonthlyCharges])`
- Average MonthlyCharges = `AVERAGE('01 Churn-Dataset'[MonthlyCharges])`
- Average MonthlyCharges = `AVERAGE('01 Churn-Dataset'[MonthlyCharges])`
- Average MonthlyCharges = `AVERAGE('01 Churn-Dataset'[MonthlyCharges])`
- Average MonthlyCharges = `AVERAGE('01 Churn-Dataset'[MonthlyCharges])`
- Average MonthlyCharges = `AVERAGE('01 Churn-Dataset'[MonthlyCharges])`



















