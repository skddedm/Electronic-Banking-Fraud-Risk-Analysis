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

# 2.0 Methodology
The following method was deployed:
* Sample datasets was acquired relating to fraud transactions in the use of electronic banking services. 2500 transactions were generated to include the columns: Transaction ID, Customer ID, Account type, Channel of transactions, Transaction date, Transaction amount, Device ID, Merchant category, Authentication type, Login failure counts, Country of residence, and Country of transaction. 
* The datasets were cleaned with Microsoft Power Query.
  <img width="828" height="384" alt="image" src="https://github.com/user-attachments/assets/0ab6902e-cad8-4bd8-835a-84836347c13b" />
  
* Some of the relationships that needed to exist to define some of the risk areas was calculated
For example: the average transaction amount of each customer was calculated and compared to the transaction 	value of the same customer to determine unusual transactions of each customer. Where the transaction value is 	greater than the average transaction amount of the same customer, possible risk 	may exist for investigation
* Pivot tables were generated into possible fraud risk areas for focus and further assessment
  <img width="821" height="354" alt="image" src="https://github.com/user-attachments/assets/3a641527-cf08-4022-837f-153c3a23ed55" />

* Risk metrics (the likelihood and impact) was defined
* The risk metrics was used to assess the risk areas to ascertain their likelihood and impact
* Microsoft Excel was used to create a dashboard summary of the findings
* Strategies were recommended to prevent, detect, and correct identified risk areas based on NIST SP 800-53r5

### 2.1 Data Limitations 
* Some fraud events may not be captured or incorrectly labeled in transaction logs. Some missing fields may include device ID, geographical location, and channels
* Fraudsters continuously change tactics to evade detection rules. Historical datasets may not reflect current or emerging fraud patterns.
* Strict privacy laws and internal policies limit access to sensitive data. Analysts may work with authorised datasets only.


