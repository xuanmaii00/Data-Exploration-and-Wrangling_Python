# E Wallet Product and Transaction Analysis_Python
Analyzed e-wallet transactions to identify product performance trends, transaction behaviors, and optimize business decisions.

## I/ Introduction
### 1. Dataset 
The dataset comes from an e-wallet company, containing the following tables:
- payment_report.csv: Monthly payment volume for each product.
- product.csv: Product information, including product ID and team ownership.
- transactions.csv: Transaction details such as transaction type, merchant ID, and amount.
### 2. Objective

The company is facing challenges in understanding product performance and transaction behaviors across its e-wallet platform. As a Data Analyst, my task is to analyze the datasets to identify trends in payment volumes, ensure product ownership aligns with company rules, and categorize transaction types. 

The insights gathered will help pinpoint top-selling products, address potential issues in product management, and provide a clearer picture of how users engage with different types of transactions. This analysis will support more informed business decisions aimed at improving product strategies and operational efficiency.

## II/ Insights and Recommendations
### 1. EDA
#### 1.1. Payment and Product
a. **Missing Values**
   - The `category` column has 22 missing values (2.39%).
   - The `team_own` column also has 22 missing values (2.39%).

  → These are non-critical missing values, so no action is needed.

b. **Incorrect Data Types**
   - The `report_month` column has an inappropriate datatype (`object`).

   → Convert the `report_month` column to `datetime` format 

c. **Data Summary**
   - **Max, Min, and Median Values**
     - **Min volume**: 5,500 (relatively low).
     - **Max volume**: 13.83 billion (extremely high).
     - **Average volume**: 197.86 million (quite high).
     - **Median volume**: Significantly lower than the average, indicating a right-skewed distribution.
   
   → Analyzing customer behavior and transactional patterns may reveal the reasons behind the high variance in volume and opportunities for encouraging higher transaction volumes.

   - **Trend (Distribution)**
     - Data was reported from January 2023 to April 2023, with increasing frequency over time.
     - Most of the data involves successful payments, with very few involving refunds.
     - Product IDs are mostly below 3000, with a relatively normal distribution and a few outliers.
     - The majority of data comes from source 45, while very few are from sources 37, 38, and 39.
     - Three categories PXXXXXR, PXXXXXF and PXXXXXB have distinctively high count, occupying a large portion, while the remaining categories contribute relatively evenly and less compared to the top three.
   
   → Enhance marketing efforts, identify potential issues with product satisfaction or payment processes for refund types . 
  
   → Evaluate the performance of sources 37, 38, and 39 → Determine best practices that can be applied to improve their performance.

   - **Outliers**
     - A few products have significantly higher volumes than the rest.
     - Source IDs 37, 38, and 39 have much fewer records compared to source ID 45.
   → Conduct a deeper analysis of the outlier products → Ascertain whether they represent exceptional cases or require targeted marketing efforts.

d. **Team Distribution**
   - There are three teams: ASL accounts for the majority, followed by ASD, and lastly APS.
   → Impl
