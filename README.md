# PWC-Virtual-Job-Internship
![cutomer churn](https://github.com/Fey-Lajide/PWC-Virtual-Job-Internship/assets/124121752/3b7f8d18-815d-468d-9a94-9f4f2302d1ab)
This repository contains details of my project for Pwc. It includes the steps taken, the slides, and the result of the analysis. 
<hr1> TABLE OF CONTENTS </hr1>
1. Problem Statement 
2. Data Source 
3. Data Preparation
4. Data Modelling 
5. Data Analysis 
6. Data Visualization
7. Insights 
<h1> PROBLEM STATEMENT </h1>
This task has been undertaken so as to: 
- Define proper KPI's

- Create a dashboard for the retention manager reflecting the KPI's
  
- Write a short email to him (the engagement partner) explaining your findings, and include suggestions as to what needs to be changed
  
- Customers who left within the last month
  
- Services each customer has signed up for: phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies
  
- Customer account information: how long as a customer, contract, payment method, paperless billing, monthly charges, total charges and number of tickets opened in the categories administrative and technical
  
- Demographic info about customers – gender, age range, and if they have partners and dependents
  
<h1> DATA SOURCE </h1>
Here is a link to the dataset for this task: [02 Churn-Dataset (2).xlsx](https://github.com/Fey-Lajide/PWC-Virtual-Job-Internship/files/12803379/02.Churn-Dataset.2.xlsx)

<h1> DATA PREPARATION </h1>
- Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

- Customer Churn dataset is give table named:

- Customer churn dataset which has 23 columns and 7043 rows of observation
- 
- Data Cleaning for the dataset was done in the power query editor as follows:

- Replaced the value is SeniorCitizen N coverted No and Y converted Yes
- 
- In the new table, one additional conditional columns were added using M-formula:

loyalty = SWITCH(TRUE(),'01 Churn-Dataset'[tenure]<=12,"< 1 year",'01 Churn-Dataset'[tenure]<=24,"< 2 years",'01 Churn-Dataset'[tenure]<=36,"< 3 years",'01 Churn-Dataset'[tenure]<=48,"< 4 years", '01 Churn-Dataset'[tenure]<=60,"< 5 years",'01 Churn-Dataset'[tenure]<=72,"< 6 years")

- Removed Unnecessary columns

- Removed Unnecessary rows

- Each of the columns in the table were validated to have the correct data type

