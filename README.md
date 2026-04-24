# Transaction Data Cleaning & Analysis

This project focuses on cleaning and analyzing a transactional dataset (~100k rows) with significant data quality issues.

## 📊 Dataset Issues

The raw dataset contained multiple problems:

- ~33% missing values in Price
- ~33% missing Customer IDs
- ~16.7% missing Transaction Status
- Invalid dates (e.g. February 30)
- Duplicate records
- Quantity values with strong outliers (-10 to 800)

---

## 🛠️ Data Cleaning Steps

The following steps were applied:

- Removed records with missing Transaction_ID
- Identified and removed duplicates
- Standardized date formats and flagged invalid entries
- Replaced missing Customer_ID with "Unknown"
- Left Price missing values unchanged due to high missing rate
- Applied median imputation for Quantity
- Flagged invalid and missing values instead of blindly correcting them

---

## 📈 Visual Analysis

Key visualizations include:

- Missing Values by Column
- Quantity Distribution (after handling outliers)
  
<img width="392" height="242" alt="image" src="https://github.com/user-attachments/assets/9a1163ed-f784-4963-bb00-979d5419678a" />
---

## 💡 Key Insights

- Most data quality issues were concentrated in Price and Customer_ID
- Quantity distribution was highly skewed with significant outliers
- Median was more appropriate than average for imputation

---

## 📁 Project Structure


## 📊 Data Source & Cleaning Process

The full data cleaning process (including formulas) can be viewed here:

https://docs.google.com/spreadsheets/d/1zB99hsAEu_oJI8xqXdgc-fkkvIcL2x2u/edit?usp=sharing&ouid=101706672073021986247&rtpof=true&sd=true

## Kaggle

https://www.kaggle.com/datasets/alfarisbachmid/dirty-financial-transactions-dataset?utm_source=chatgpt.com
