# 🧹 Transaction Data Cleaning & Analysis

## 📌 Project Overview

This project focuses on cleaning and analyzing a real-world transactional dataset (~100k rows) with multiple data quality issues.

The objective was not only to clean the data, but to apply **context-aware decisions** while preserving the integrity of the dataset.

---

## 🚨 Key Data Quality Issues

The raw dataset contained significant inconsistencies:

* ~33% missing values in **Price**
* ~33% missing **Customer IDs**
* ~16.7% missing **Transaction Status**
* Invalid dates (e.g. *2025-02-30*)
* Duplicate records
* Mixed formats in **Price** (€, $, commas, scientific notation)
* Noisy categorical data:

  * Transaction Status (*complete, Completed, carc Pending*)
  * Product Names (*Coff, Smar, Headp*)
  * Payment Methods inconsistencies
* Extreme outliers in **Quantity** (-10 to 800)

---

## 🛠️ Data Cleaning Approach

Instead of applying generic rules, cleaning decisions were based on context:

### 🔹 Identifiers

* Removed records with missing `Transaction_ID`

### 🔹 Dates

* Standardized formats
* Flagged invalid dates instead of forcing corrections

### 🔹 Price

* Removed currency symbols and unified formats
* Converted text to numeric values
* Excluded erroneous values (e.g. scientific notation)
* Preserved negative values as potential returns

### 🔹 Quantity

* Detected skewness and extreme outliers
* Applied **median imputation** (robust to outliers)

### 🔹 Categorical Features

* Standardized transaction status values
* Cleaned payment methods
* Reconstructed product names using pattern matching
* Assigned **"Unknown"** to ambiguous values

---

## 📊 Visual Analysis

### 1. Data Quality Overview

* Missing values by column

  <img width="634" height="405" alt="image" src="https://github.com/user-attachments/assets/cb302e7c-2bb3-4a6f-80a5-3177ab7f5506" />


### 2. Quantity Distribution

* Skewed distribution with outliers removed for visualization

  <img width="749" height="541" alt="image" src="https://github.com/user-attachments/assets/81f1d04f-c936-4ee3-b184-a12391e6e14c" />


### 3. Transaction Outcomes

* ~50% completed
* Remaining transactions distributed across pending, failed, and unknown

<img width="758" height="562" alt="image" src="https://github.com/user-attachments/assets/188327d6-647c-4f57-9200-85f7ff98ae2a" />

## Dashboard Preview

<img width="2493" height="1312" alt="image" src="https://github.com/user-attachments/assets/9728d010-afb0-462c-83ff-e57d79e6862f" />

---

## 💡 Key Insights

* ~50% of transactions are completed successfully
* ~17% of transactions remain **unknown**, indicating persistent data quality issues
* Transaction volume is stable over time
* Product categories show a balanced distribution (~18K each)
* Data quality issues are concentrated in **Price** and **Customer_ID**

---

## 📁 Data Source

Due to file size limitations, only a sample dataset is included.

👉 Full cleaning process (Google Sheets):
[https://docs.google.com/spreadsheets/d/1zB99hsAEu_oJI8xqXdgc-fkkvIcL2x2u/edit](https://docs.google.com/spreadsheets/d/1zB99hsAEu_oJI8xqXdgc-fkkvIcL2x2u/edit?usp=sharing&ouid=101706672073021986247&rtpof=true&sd=true)

👉 Dataset source (Kaggle):
https://www.kaggle.com/datasets/alfarisbachmid/dirty-financial-transactions-dataset

---

## 🚀 Tools Used

* Power BI
* DAX
* Google Sheets
* Data Cleaning Techniques

---

## 📌 Conclusion

Data cleaning is not about making data perfect —
it is about making **responsible, context-aware decisions** while preserving reality.


