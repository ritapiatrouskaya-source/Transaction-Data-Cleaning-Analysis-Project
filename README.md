# 🧹 Transaction Data Cleaning & Analysis

This project focuses on cleaning and analyzing a transactional dataset (~100k rows) with multiple real-world data quality issues.

---

## 📊 Overview

The dataset contained a variety of inconsistencies, including missing values, invalid formats, and noisy categorical data.
The goal was not only to clean the data, but to make **informed decisions without distorting the underlying information**.

---

## 🚨 Data Quality Issues

The raw dataset included:

* ~33% missing values in **Price**
* ~33% missing **Customer IDs**
* ~16.7% missing **Transaction Status**
* Invalid dates (e.g. *2025-02-30*)
* Duplicate records
* Mixed formats in **Price** (€, $, commas, dots, scientific notation)
* Noisy categorical data:

  * Transaction Status (e.g. *complete, Completed, carc Pending*)
  * Product Names (e.g. *Coff, Smar, Headp*)
  * Payment Methods inconsistencies
* Extreme outliers in **Quantity** (-10 to 800)

---

## 🛠️ Data Cleaning Approach

Instead of applying generic fixes, decisions were made based on context:

### 🔹 Identifiers

* Removed records with missing `Transaction_ID`

### 🔹 Dates

* Standardized formats
* Flagged invalid dates instead of forcing correction

### 🔹 Price

* Removed currency symbols and standardized decimal formats
* Converted text to numeric values
* Identified and excluded erroneous values (e.g. scientific notation)
* Retained negative values as potential returns

### 🔹 Quantity

* Detected strong skewness and outliers
* Used **median imputation** instead of mean

### 🔹 Categorical Features

* Standardized `Transaction_Status` (e.g. complete → completed)
* Cleaned `Payment_Method`
* Reconstructed `Product_Name` using pattern matching
* Assigned **"Unknown"** to ambiguous values (e.g. "H", "S")

---

## 📈 Visual Analysis

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


---

## 💡 Key Insights

* Data quality issues were concentrated in **Price and Customer_ID**
* Categorical inconsistencies required structured normalization
* Quantity distribution confirmed the need for robust statistics (median)
* A noticeable share of data remains **unknown or invalid**, highlighting real-world data limitations

---

## 🔗 Data Source

Due to file size limitations, only a sample dataset is included.

👉 Full cleaning process (Google Sheets):

https://docs.google.com/spreadsheets/d/1zB99hsAEu_oJI8xqXdgc-fkkvIcL2x2u/edit?usp=sharing&ouid=101706672073021986247&rtpof=true&sd=true

---

## 🚀 Tools Used

* Google Sheets (data cleaning & transformation)
* Data visualization techniques

---

## 📌 Conclusion

Data cleaning is not about making data perfect —
it’s about making **responsible decisions while preserving reality**.



## Kaggle

https://www.kaggle.com/datasets/alfarisbachmid/dirty-financial-transactions-dataset?utm_source=chatgpt.com
