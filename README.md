# 🏦 Data Vault Bank Project

## 📌 Overview
This project demonstrates the implementation of a **Data Vault 2.0 architecture**  
on **bank transaction data** using **PySpark** for ETL processing and **Power BI** for visualization.  

The goal is to transform raw banking data into **actionable insights** while ensuring:
- **Scalability** for future growth,
- **Auditability** for compliance,
- **Flexibility** to adapt to business changes.

---

## 📊 Dataset
The dataset comes from Kaggle:  
👉 [Bank Transactions Dataset](https://www.kaggle.com/datasets/shivamb/bank-customer-segmentation)  

It contains customer demographics, account balances, and transaction details.  

---

## ⚙️ Methodology

This project follows the **Data Vault 2.0 methodology**, which separates **raw data ingestion** from **business logic**.

### 1. Raw Vault Layer
- **Hubs**: Unique business keys (e.g., CustomerID, TransactionID) with `SHA-256` hash keys.  
- **Links**: Relationships between hubs (e.g., which customer made which transaction).  
- **Satellites**: Descriptive attributes and history (e.g., DOB, gender, transaction amount).  
- **Features**: 
  - Use of **hash keys** to guarantee uniqueness,  
  - **Hash diff** to detect attribute changes,  
  - `load_date` and `record_source` for full traceability.

### 2. Business Vault Layer
- Enriched customer profiles (age, balance category, senior flag).  
- Enriched transactions (categories, suspicious flags).  
- Aggregates:
  - Monthly transaction statistics,  
  - Customer-level transaction summaries.  
- Segmentation of customers (Premium, Active, Occasional, LowValue).

### 3. Presentation Layer
- Star schema for BI:
  - **Dimensions**: Customers, Time, Locations, Segments.  
  - **Fact Table**: Transactions with foreign keys to dimensions.  
- Data exported to **CSV** for integration with Power BI.

### 4. Power BI Dashboard
- Imported the CSV exports into Power BI.  
- Built a dashboard showing:
  - Transaction trends over time,  
  - Customer segmentation,  
  - Suspicious transaction detection,  
  - Geographic distribution of customers.  

---



