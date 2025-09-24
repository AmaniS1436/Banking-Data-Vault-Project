# 🏦 Data Vault Bank Project

## 📌 Overview
This project demonstrates the implementation of a **Data Vault 2.0 architecture**  
on **bank transaction data**, using **PySpark** for ETL processing and **Power BI** for visualization.  

The objective is to transform raw banking data into **actionable business insights** while ensuring:
- **Scalability** → supports future growth and new data sources,  
- **Auditability** → compliance and full traceability from source to dashboard,  
- **Flexibility** → easily adapt to evolving business rules and analytics needs.  

---

## 📊 Dataset
The dataset is publicly available on Kaggle:  
👉 [Bank Transactions Dataset](https://www.kaggle.com/datasets/shivamb/bank-customer-segmentation)  

It contains customer demographics, account balances, and detailed transaction records.  

---

## ⚙️ Methodology
The project follows the **Data Vault 2.0 methodology**, which separates **raw data ingestion** from **business logic and reporting**.

### 🔹 1. Raw Vault Layer
- **Hubs** → Unique business keys (e.g., CustomerID, TransactionID) secured with `SHA-256` hash keys.  
- **Links** → Relationships between hubs (e.g., which customer made which transaction).  
- **Satellites** → Descriptive attributes with historical tracking (DOB, gender, balance, transaction details).  
- **Key techniques**:
  - **Hash keys** for uniqueness and distribution,  
  - **Hash diff** for change detection,  
  - `load_date` and `record_source` for auditability and lineage.  

### 🔹 2. Business Vault Layer
- Enriched **customer profiles** (age, senior flag, balance categories).  
- Enriched **transactions** (categories by amount, suspicious transaction flag).  
- Aggregations:
  - Monthly-level (total count, total/average transaction amount, active customers),  
  - Customer-level (total transactions, spending profile).  
- Segmentation into **Premium, Active, Occasional, and LowValue** customers.  

### 🔹 3. Presentation Layer
- Modeled as a **star schema** for BI reporting:  
  - **Dimensions**: Customer, Time, Location, Segments.  
  - **Fact Table**: Transactions referencing dimensions with amounts, categories, and flags.  
- Data exported as **CSV files**, ready for BI tools.  

### 🔹 4. Power BI Dashboard
- CSV files imported into **Power BI**.  
- Developed dashboards showcasing:  
  - Transaction trends over time,  
  - Customer segmentation insights,  
  - Detection of suspicious transactions,  
  - Geographic analysis of customer locations.  

---

## ✅ Results
- **Data Vault 2.0 applied** to banking data end-to-end.  
- **Business rules** integrated in the Business Vault.  
- **Star schema** ready for BI consumption.  
- **Power BI dashboard** delivering interactive insights.  

---

## 🎯 Business Impact
This project demonstrates the value of **Data Vault in banking analytics**:  
- **Scalability** → integrate new sources without redesigning the model.  
- **Auditability** → ensure compliance with full lineage tracking.  
- **Agility** → easily adjust to changing business rules.  
- **Better decision-making** → dashboards reveal trends, customer behavior, and anomalies.  

---

## 🌍 Importance of the Project
In the financial sector, **data-driven decision making** is essential. This project shows how:  
- **Modern data warehousing** techniques future-proof data pipelines,  
- Separating raw data from business logic enables **flexibility and compliance**,  
- Enriched insights can support **fraud detection, customer segmentation, and monitoring**,  
- A reproducible pipeline bridges the gap between **data engineering and business intelligence**.  

---

## 📝 Conclusion
This project provides a **complete end-to-end example** of applying **Data Vault 2.0** to banking transactions.  

By leveraging **PySpark, Data Vault modeling, and Power BI**, the pipeline achieves:  
- **Robust governance** → traceability and auditability,  
- **Actionable analytics** → segmentation and suspicious activity monitoring,  
- **Scalable architecture** → adaptable to future banking datasets.  

👉 Ultimately, this project highlights the **strategic importance of Data Vault** in transforming raw banking operations into **trusted, business-ready insights**.  




