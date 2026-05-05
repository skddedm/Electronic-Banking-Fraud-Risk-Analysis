# 1.0 Executive Summary
Banks deploy electronic banking services such as mobile applications, internet banking, debit/credit cards to increase convenience for customers and create value for the bank, but vulnerabilities and cyber threats can cause fraud to occur.

### 1.1 Problem Statement:
Possible fraud risks has reduced customer usage levels of electronic banking platforms

### 1.2 Project Objective:
The objective is broken into three (3) activities: 
* Identify and analyse risk areas of using electronic banking services with sample datasets generated
* Assess the likelihood and impact of each risk area to inform priority and resource allocation
* Recommend fraud risk prevention, detection, and correction controls guided by the NIST SP-800 53r5     

### 1.3 Project Scope:
* 2850 transactions of electronic banking nature were selected
* 50 customers were involved with the selected datasets
* 4 account types were involved: checking, savings, credit card and debit card
* 4 channels were deployed for customers: POS, ATM, mobile app and internet banking
* The transactions were performed between 1st January 2025 and 1st January 2026
* 6 merchant categories were the focus: food, service, electronic, entertainment, travel and retail
* 4 authentication types were the focus: biometric, OTP, password and PIN

### 1.4 Tools Deployed:
* Microsoft Excel Functions
* Power Query
* Pivot Tables
* Excel charts
* Semi-quantitative risk metrics
* NIST SP 800-53r5

### 1.5 Summary of Project Findings:
Generally, all the risk areas capture some form of irregularity that needs to be further investigated with strategies and additional controls put in place. There are 706 to 1505 transactions exposed and at transaction values at risk ranging from $2,763,645.81 to $10,701,598.31. Out of the 6 risk areas assessed, unusual transactions as defined by actual transaction amounts exceeding the average transaction amount of the same customer is the most exposed in terms of transaction value while transactions performed at risky locations defined as where the transaction country is different from the resident country of the customer and the authentication type is neither biometric or OTP. The risk level assessment is assigned to these areas based on their likelihood and impact. 5 high and 1 medium level risks were identified. Controls were initiated guided by NIST SP 800-53r5 to reduce the risk levels from average HIGH to estimated average LOW for each of the identified fraud risk categories. 

