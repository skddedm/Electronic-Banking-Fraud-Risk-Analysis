# Table of Content
* [1.0 Executive Summary](#executive-summary)
* [2.0 Methodology](https://github.com/skddedm/Electronic-Banking-Fraud-Risk-Analysis/blob/main/README.md#20-methodology)



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

# 3.0 Project Findings
After analysing the generated datasets, six (6) fraud risk areas were identified as follows: 
* 1,429 transactions were identified as unusual. The total value exposed with this risk is $10,701,598.31
* 1,357 transactions are identified at risk with the use of password or PIN only. $6,924,532.16 is value is at risk. 
* 1,421 transactions with 3 or more failed login attempts are a risk with $7,204,121.31 worth of transactions
* 1,505 transactions were identified as risky locations with $7,657,142.54 exposed. 
* 706 transactions and $3,544,286.50 have been identified to be at risk based on account type usage.
* 527 transactions and $2,763,645.81 are at risk based on merchant category.

A summary of the outcome is shown in the dash board  below:
<img width="828" height="350" alt="image" src="https://github.com/user-attachments/assets/e78a69a4-1fde-42ac-9b7e-fe234f424fd0" />

### 3.1 Root Causes of Vulnerabilities with Electronic Banking:
* Weak authentication and access controls. The electronic products of the bank work on different platforms connected over the internet. A weak password policy, weak multi-factor authentication and inadequate session management can cause some of these fraud risks to occur. 
* Inadequate transaction monitoring and fraud detection. Fraud events are dynamic with time, hence static rules and poor alert escalation will not help the bank adapt to and detect new fraud patterns.
* Vulnerabilities in applications and infrastructure security. Architectural weaknesses in applications and IT infrastructure security can occur with outdated software, unpatched systems, weak encryption implementation and insecure API connecting banking systems.
* Non-compliance with security standards. The bank may have improper network segregation, or weak logging and monitoring of card transactions as recommended by NIST SP-800r5, or inadequate protection of cardholder data as recommended by PCI-DSS.
* Limited user awareness and social engineering controls. The bank may not have created enough awareness for their customers about social engineering and security practices required to stay safe while using the bank’s electronic platforms. The staff of the bank may also not have adequate training or education regarding security and privacy trends to protecting customers. 

### 3.2 Risk Impact to the Bank
Related fraud with the use of electronic banking products could result in the following risks:
* Financial loss to the customers and bank. Unauthorized withdrawals could cause loss of customers while reimbursement and charge back will cost the bank’s in the fraud event.
* Regulatory and compliance risk. The fraud event could trigger regulatory findings for breach with consumer protection laws which may result in fines or stricter supervision conditions. 
* Customer experience and reputation risk. Customers may lose trust in the bank with their fraud experiences particularly, if the same fraud trend continues
* Operational disruption. To resolve fraud occurrences, emergency shutdowns and high volumes of customer complaints will increase workload for fraud and customer support teams taking up existing financial resources, IT resources, human resources and time.  
* Control breakdown and inefficiencies. The need to correct errors will result in increased human intervention which may result in more errors and dire impacts. 
* Legal and liability risk. Customers may embark on lawsuits. Unbearable numbers of such lawsuits could shut down the bank’s operations.

# 4.0 Details of Risk Areas Identified
### Unusual Transaction Amount 
The average transaction of each customer is compared to individual transactions performed by that same customer. Risk is identified where the actual transaction is greater than the average transaction amount for the same customer. It shows an unusual pattern traceable to the customer. 2836 transactions were identified as unusual. The total value exposed with this risk is $14,292,391.45

``` Excel
=IF([@Transaction_Amount]<=[@avg_transaction_amount],"usual transaction","unusual transaction")
```

|Row Labels         |Count of Transactios ID|Sum of Transaction Amount|
|-------------------|-----------------------|-------------------------|
|unusual transaction|2836                   |14,292,391.45            |
|usual trannsaction |14                     |82,338.22                |
|total              |2850                   |14,374,729.67            |

### 4.1 Risky Authentication Type
Biometric and OTP are more secure authentications than passwords or PIN because they involve a direct involvement of the actual customer to validate. 1,357 transactions are identified at risk with the use of password or PIN only because they can easily be acquired by unauthorized users. $6,924,532.16 is value is at risk. 
|Row Labels         |Count of Transactios ID|Sum of Transaction Amount|
|-------------------|-----------------------|-------------------------|
|biometric          |733                    |3,619,901.59             |
|OTP                |760                    |3,830,295.92             |
|password           |687                    |3,593,655.98             |
|PIN                |670                    |3,330,876.18             |
|total              |2,850                  |14,374,729.67            |

### 4.2 Failed Login Attempts
1,421 transactions with 3 or more failed login attempts are a risk because the actual customer is likely to recall their login credentials by the second attempt. $7,204,121.31 worth of transactions is at risk
|Row Labels         |Count of Transactios ID|Sum of Transaction Amount|
|-------------------|-----------------------|-------------------------|
|0                  |465                    |2,394,557.5              |
|1                  |468                    |2,326,748.99             |
|2                  |496                    |2,449,301.87             |
|3                  |449                    |2,384,244.24             |
|4                  |470                    |2,321,440.11             |
|5                  |502                    |2,498,436.96             |
|total              |2,850                  |14,374,729.67            |

### 4.3 Risky Location Transaction
Where the country of residence differs from the country of transaction and the authentication type is neither biometric nor OTP, the geographical location is risky with the transaction performed. Biometric and OTP give reasonable assurance that the customer is performing the transactions themselves away from where the bank knows them on record to reside. 1,505 transactions were identified as risky locations with $7,657,142.54 exposed. 
 
 ``` excel
=IF(AND([@Country_of_Residence]<>[@Country_of_Transaction],OR([@Authentication_Type]="Biometric",[@Authentication_Type]="OTP")),"safe location transaction","unsafe location transaction")
```

|Row Labels                |Count of Transactios ID|Sum of Transaction Amount|
|--------------------------|-----------------------|-------------------------|
|safe location transaction |1,345                  |6,717,587.13             |
|unsafe location           |1,505                  |7,657,142.54             |
|total                     |2,850                  |14,374,729.67            |

### 4.4 Account Type Usage Risk
Checking accounts, credit cards and debit cards are usually transactional in nature but an ATM or POS usage on savings accounts exposes risk with the inappropriate account usage which defeats the savings purpose of that account. 706 transactions and $3,544,286.50 have been identified to be at risk based on account type usage.
|Row Labels         |ATM   |Internet Banking |Mobile App |Online Banking |POS | Total |
|-------------------|------|-----------------|-----------|---------------|----|-------|
|checking           |373   |1                |376        |338            |330 |1,418  |
|credit card        |8     |8                |7          |-              |9   |32     |
|debit card         |10    |4                |4          |-              |5   |23     |
|savings            |364   |5                |355        |311            |342 |1,377  |
|total              |755   |18               |742        |649            |686 |2,850  |

### 4.5 Merchant Category Riskiness
If the country of residence differs from the country of transaction and the merchant category is either electronics or travel, risk is higher. A customer will highly plan purchases of an electronic or travel nature and will usually perform such transactions from their country of residence. When electronic or travel expenses are paid from outside the country of residence, there is some level of risk that it may not be the actual customer of the bank performing that transaction. $2,763,645.81 and 527 transactions are at risk based on merchant category.

```Excel
=IF(AND([@Country_of_Residence]<>[@Country_of_Transaction],OR([@Merchant_Category]="Electronics",[@Merchant_Category]="Travel")),"unsafe merchant transaction","safe merchant transaction")
```

|Row Labels                  |Count of Transactios ID|Sum of Transaction Amount|
|----------------------------|-----------------------|-------------------------|
|safe merchant transaction   |2,323                  |11,611,083.86            |
|unsafe merchant transaction |527                    |2,763,645.81             |
|total                       |2,850                  |14,374,729.67            |

# 5.0 Risk Metrics
The risk metrics is defined by the risk level rating, likelihood rating and impact rating. 

### 5.1 Risk Level
Risk level rating is defined by the likelihood rating and impact rating of each risk area.

| Risk Level | Rating    |
|------------|-----------|
|Low Risk	   |2 and below|
|Medium Risk |3 - 4      |
|High Risk   |5 and above|

### 5.2 Likelihood
Defined as the possibility of the risk area occurring. The number of the affected overdraft expressed as a percentage of the total number of overdraft approvals defines the likelihood.
|Likelihood   |Percentage         |Rating|
|-------------|-------------------|------|
|Unlikely     |Less than 5%       |1     |
|Likely       |Between 6% and 40% |2     |
|Very Likely  |Higher than 40%    |3     |

### 5.3 Impact
Defined as the overdraft amount value that can be affected in relation to the expressed likelihood. 
|Impact Severity |Financial Impacted               |Rating      |Investigation and Resolution Timeline|
|----------------|---------------------------------|------------|-------------------------------------|
|Minor           |Less than $1,000,000             |1           |Up to 2 months                       |
|Serious         |Between $1,000,001 and $3,000,000|2           |Up to 1 month                        |
|Major           |Higher than $3,000,000           |3           |Up to 1 week                         |

### 5.4 Fraud Risk Areas Assessment Summary
The six (6) weaknesses identified have been assessed in the table below:
|Risk Category                 |Likelihood Rating |Financial Impact Severity  | Risk Rating (likelihood rating + financial impact rating)|Risk Level|
|------------------------------|------------------|---------------------------|----------------------------------------------------------|----------|
|unusual transaction amount    |3                 |2                          |5                                                         |High      |
|risky authentication type     |3                 |3                          |6                                                         |High      |
|failed login attempts         |3                 |3                          |6                                                         |High      |
|risky location                |3                 |3                          |6                                                         |High      |
|account usage risk            |2                 |3                          |5                                                         |High      |
|merchant category risk        |2                 |2                          |4                                                         |Medium    |

# 6.0 Risk Areas and Required Strategies
Due to scarce resources and budget constraints, the assessed risk areas must be prioritized considering the overall risk rating and the impact severity amounts. Controls to assist prevent, detect and correct the identified risk areas using the NIST SP 800-53r5 have been recommended.
<img width="668" height="645" alt="image" src="https://github.com/user-attachments/assets/1e70155c-47a8-41b0-81b4-4d0294b2ad63" />



