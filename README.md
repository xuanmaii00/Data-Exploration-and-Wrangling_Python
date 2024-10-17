# E-Wallet Product and Transaction Analysis (Python)
Analyzed e-wallet transactions to identify product performance trends, transaction behaviors, and optimize business decisions.

## I/ Introduction
### 1. Dataset 
The dataset comes from an e-wallet company, containing the following tables:
- **payment_report.csv**: Monthly payment volume for each product.
- **product.csv**: Product information, including product ID and team ownership.
- **transactions.csv**: Transaction details such as transaction type, merchant ID, and amount.

### 2. Objective
The company is facing challenges in understanding product performance and transaction behaviors across its e-wallet platform. As a Data Analyst, my task is to analyze the datasets to identify trends in payment volumes, ensure product ownership aligns with company rules, and categorize transaction types.

The insights gathered will help pinpoint top-selling products, address potential issues in product management, and provide a clearer picture of how users engage with different types of transactions. This analysis will support more informed business decisions aimed at improving product strategies and operational efficiency.

## II/ Insights and Recommendations
### 1. EDA
#### 1.1. Payment and Product

**a. Missing Values**

![image](https://github.com/user-attachments/assets/5e6c293b-9bee-4191-b5a8-0993c477cdeb)

- The `category` column has 22 missing values (2.39%).
- The `team_own` column also has 22 missing values (2.39%).

→ These are non-critical missing values, so no action is needed.

**b. Incorrect Data Types**

![image](https://github.com/user-attachments/assets/33fbfa25-a07b-4e8c-93ed-c2155b163e1a)

- The `report_month` column has an inappropriate datatype (`object`).

→ Convert the `report_month` column to `datetime` format.

**c. Volume Data Summary**

- **Min volume**: 5,500 (relatively low).
- **Max volume**: 13.83 billion (extremely high).
- **Average volume**: 197.86 million (quite high).
- **Median volume**: Significantly lower than the average, indicating a right-skewed distribution.

→ Analyzing customer behavior and transactional patterns may reveal the reasons behind the high variance in volume and opportunities for encouraging higher transaction volumes.

**d. Trend (Distribution)**

![image](https://github.com/user-attachments/assets/c47d2b80-5719-4db4-9b7d-77e115930c10)
![image](https://github.com/user-attachments/assets/f01c6879-ac10-41bb-83a0-532d53e48a5c)
![image](https://github.com/user-attachments/assets/3f6fa7df-2db1-4ffd-ace1-6505cc84ac20)
![image](https://github.com/user-attachments/assets/1cd9afb0-32ed-4d0e-b002-02461fd7195a)
![image](https://github.com/user-attachments/assets/59a201b4-7dad-4010-a45d-fa4b1100ea0b)
![image](https://github.com/user-attachments/assets/97589040-8ba8-425b-8ef0-99f07b814f02)
![image](https://github.com/user-attachments/assets/906f29d0-54b9-466a-b039-d3188b58ccbf)

- Data was reported from January 2023 to April 2023, with increasing frequency over time.
- Most of the data involves successful payments, with very few involving refunds.
- Product IDs are mostly below 3000, with a relatively normal distribution and a few outliers.
- The majority of data comes from source 45, while very few are from sources 37, 38, and 39.
- Three categories, PXXXXXR, PXXXXXF, and PXXXXXB, have distinctively high counts, occupying a large portion, while the remaining categories contribute relatively evenly and less compared to the top three.
- There are three teams: ASL accounts for the majority, followed by ASD, and lastly APS.

→ Enhance marketing efforts, identify potential issues with product satisfaction or payment processes for refund types.

→ Evaluate the performance of sources 37, 38, and 39, determine best practices that can be applied to improve their performance.

#### 1.2. Transaction

**a. Missing Values**

![image](https://github.com/user-attachments/assets/1d502add-376d-40b7-9b90-5957ec88b96d)

- The `sender_id` column has 49,058 (3.71%) missing values.
- The `receiver_id` column has 164,792 (12.45%) missing values.
- The `extra_info` column has 1,317,879 (99.54%) missing values.

→ These are non-critical columns, so no action is required.

**b. Incorrect Data Types**

![image](https://github.com/user-attachments/assets/9af94ef7-c2a3-4507-81e3-70f9d109da8b)

- The `timeStamp` column has the wrong datatype (`object`).

→ Convert the `timeStamp` column to `datetime` format.

**c. Volume Data Summary**

![image](https://github.com/user-attachments/assets/ca17c3f5-ac28-4a13-9ed7-6637ce9c2bbe)

- **Min transaction volume**: 1
- **Max transaction volume**: 78,691,477 (extremely high)
- **Mean transaction volume**: 238,805.88
- **Median transaction volume**: 30,000 (significantly lower than the mean)

→ The volume data is highly skewed to the right, with the mean being much larger than the median, indicating a few very large values pulling the mean upwards.

**d. Volume Trend (Distribution)**

- The distribution of `volume` is right-skewed, showing that most transactions are concentrated around lower values, with a few extremely large transactions distorting the mean.

**e. Volume Outliers**

- The maximum value of 78,691,477 is a significant outlier, much higher than the third quartile (100,000), indicating the presence of extreme outliers.

**f. Transaction Types**

![image](https://github.com/user-attachments/assets/b68f888d-4c0c-4fda-be3c-fd501fa6fae4)

- There are 7 distinct `transType` values, with most transactions concentrated around types 2, 8, and 22.

→ Focus can be given to these transaction types for deeper analysis and optimization.



