# PWC-Virtual-Job-Internship
![cutomer churn](https://github.com/Fey-Lajide/PWC-Virtual-Job-Internship/assets/124121752/3b7f8d18-815d-468d-9a94-9f4f2302d1ab)
![Customer Churn 1](https://github.com/Fey-Lajide/PWC-Virtual-Job-Internship/assets/124121752/db6651b9-ea2b-4f53-b66e-8e6643a808c9)

This repository contains details of my project for Pwc. It includes the steps taken, the slides, and insights.
<br/><br/>
<hr1> TABLE OF CONTENTS </hr1>
<br/>
1. Problem Statement 
2. Data Source 
3. Data Preparation
4. Data Modelling 
5. Data Analysis 
6. Data Visualization
7. Insights 
<h1> PROBLEM STATEMENT </h1>
This task has been undertaken so as to: 
<br/>
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
 
- Data Cleaning for the dataset was done in the power query editor as follows:

- Replaced the value is SeniorCitizen N coverted No and Y converted Yes
  
- In the new table, one additional conditional columns were added using M-formula:

  loyalty = SWITCH(TRUE(),'01 Churn-Dataset'[tenure]<=12,"< 1 year",'01 Churn-Dataset'[tenure]<=24,"< 2 years",'01 Churn-Dataset'[tenure]<=36,"< 3   
  years",'01 Churn-Dataset'[tenure]<=48,"< 4 years", '01 Churn-Dataset'[tenure]<=60,"< 5 years",'01 Churn-Dataset'[tenure]<=72,"< 6 years")

- Removed Unnecessary columns

- Removed Unnecessary rows

- Each of the columns in the table were validated to have the correct data type

<H1>DATA MODELLING</H1>
After the preliminary stages of Data Cleaning and Data Transformation, the Data was then modelled. The image below gives more insigts into this.
![dax](https://github.com/Fey-Lajide/PWC-Virtual-Job-Internship/assets/124121752/694bca4b-2b16-44ee-96a3-739900a7746f)
<h1>DATA ANALYSIS</h1>
The modelled data was then analyzed utilizing certain DAX functions and measures. 
Measures used in all visualization are:

- Average MonthlyCharges = AVERAGE('01 Churn-Dataset'[MonthlyCharges])

- Average TotalCharges = AVERAGE('01 Churn-Dataset'[TotalCharges])

- churn count = CALCULATE(COUNT('01 Churn-Dataset'[Churn]), ALLSELECTED('01 Churn-Dataset'[Churn]),'01 Churn-Dataset'[Churn] = "Yes")

- churn rate % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Churn]), '01 Churn-Dataset'[Churn] = "yes" ), COUNT('01 Churn-Dataset'[Churn]), 0)

- Dependent in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Dependents]), '01 Churn-Dataset'[Dependents]="Yes",'01 Churn-Dataset'[Churn]="Yes"), 
  CALCULATE(COUNT('01 Churn-Dataset'[Dependents]),'01 Churn-Dataset'[Churn]="Yes"), 0)

- Device protection in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]), '01 Churn-Dataset'[DeviceProtection] ="Yes", '01 Churn- 
  Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]),'01 Churn-Dataset'[Churn]="Yes"),0)

- Online backup in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]), '01 Churn-Dataset'[OnlineBackup] ="Yes", '01 Churn- 
  Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]),'01 Churn-Dataset'[Churn]="Yes"),0)

- Online security in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]), '01 Churn-Dataset'[OnlineSecurity] ="Yes", '01 Churn- 
  Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]),'01 Churn-Dataset'[Churn]="Yes"),0)

- Partner in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Partner]),'01 Churn-Dataset'[Partner]="Yes",'01 Churn-Dataset'[Churn]="Yes"), 
  CALCULATE(COUNT('01 Churn-Dataset'[Partner]), '01 Churn-Dataset'[Churn]="Yes"), 0)

- Phone service in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]), '01 Churn-Dataset'[PhoneService] ="Yes", '01 Churn- 
  Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]),'01 Churn-Dataset'[Churn]="Yes"),0)

- SenioCitizen in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[SeniorCitizen]=1,'01 Churn-Dataset'[Churn]="Yes"), 
  CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[Churn]="Yes"), 0)

- Streaming Movies in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]), '01 Churn-Dataset'[StreamingMovies] ="Yes", '01 Churn- 
  Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]),'01 Churn-Dataset'[Churn]="Yes"),0)

- Streaming TV in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]), '01 Churn-Dataset'[StreamingTV] ="Yes", '01 Churn- 
  Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]),'01 Churn-Dataset'[Churn]="Yes"),0)

- Tech Support in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]), '01 Churn-Dataset'[TechSupport] ="Yes", '01 Churn- 
  Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]),'01 Churn-Dataset'[Churn]="Yes"),0)

<h1> DATA VISUALIZATION </h1>
Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

Shows visualizations from Customer Retention analysis:


CUSTOMER CHURN 
<br/><br/>
![Customer Churn 2](https://github.com/Fey-Lajide/PWC-Virtual-Job-Internship/assets/124121752/8594cb92-381b-4860-bb96-e5a75029dc73)


CUSTOMER RISK 
<br/><br/>
![Customer Churn 3](https://github.com/Fey-Lajide/PWC-Virtual-Job-Internship/assets/124121752/6017313a-f28d-4713-bab6-ac42c61d23b1)

<H1> INSIGHTS </H1>
As shown the data Visualization, It can be deduced that:

- Customers on the Two-Year contract, have been with the company for long, while most of the customers on Month-to-Month contract joined the company.
  
- The company is at risk of losing recently joined customers. based on the results from analysis.. if they decided to month-to-month contract.
  
- 7043 customers are at the risk of churn. and The churn rate is 27% and yearly charges is $16.06M charges. and Monthly Charges is $456.12K monthly
  charges.
  
- 2955 tech tickets were opened and 3632 admin tickets were opened.
  
- CCMost of the churned customers did not sign up for Online Security and tech support and also did not sign up for Phone Services.
  
- It a lot of customers had an issue with Fiber Optic . Up to 42% of the customers churned were using Fiber Optic as their Internet Services.
