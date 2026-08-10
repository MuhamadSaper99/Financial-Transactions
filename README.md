# Financial Transactions Data Warehouse & Fraud Analytics

An end-to-end **Data Engineering and Business Intelligence** project that builds a complete Data Warehouse for financial transactions and fraud analytics using the Microsoft BI Stack.

The project demonstrates the full data engineering lifecycle, starting from raw CSV/JSON files, followed by ETL processing using **SQL Server Integration Services (SSIS)**, data cleansing and transformation across multiple layers, building a **Star Schema Data Warehouse** in SQL Server, implementing **Full Load and Incremental Load** strategies, automating the ETL process through scheduled jobs, creating a semantic model using **SSAS Tabular**, and finally delivering interactive analytics through **Power BI**.

---

# 🏗️ Project Architecture

The project follows a layered Data Warehouse architecture:

```text
                    ┌──────────────────────┐
                    │     Source Files     │
                    │      CSV / JSON      │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │      ODS Layer       │
                    │    Raw Data Load     │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │      STG Layer       │
                    │ Cleansing & Transform│
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │    DWH / Gold Layer  │
                    │      Star Schema     │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │     SSAS Tabular     │
                    │    Semantic Model    │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │      Power BI        │
                    │ Dashboards & Analytics│
                    └──────────────────────┘

The project supports two main loading strategies:

Full Load – Used for the initial population of the Data Warehouse.
Incremental Load – Loads only newly arrived or required records during subsequent executions.

The incremental pipeline is implemented across the:

- ODS Layer
- STG Layer
- DWH Layer

The ETL process is also automated using scheduled jobs to support repeatable and reliable data processing.

📂 Data Sources

The project uses the following dataset:

Kaggle – Transactions Fraud Dataset

Source files:

- Users.csv
- Cards.csv
- Transactions.csv
- TrainFraudLabel.json
- MCC.json

The dataset contains:

- Customer information
- Payment card information
- Financial transactions
- Fraud labels
- Merchant Category Codes (MCC)
