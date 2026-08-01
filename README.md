# End-to-End Data Engineering Project using Databricks (FMCG Domain)

## Project Overview

This project demonstrates an end-to-end Data Engineering pipeline built using **Databricks Free Edition** for a real-world FMCG business scenario.

The business case simulates a large FMCG company acquiring a smaller (child) company. Since both companies maintain separate data systems, the objective is to consolidate data into a unified Lakehouse architecture for analytics and reporting.

The project follows the **Medallion Architecture (Bronze → Silver → Gold)** and implements ETL pipelines using **PySpark, SQL, Delta Lake, Amazon S3, Databricks Workflows, AI/BI Dashboard, and Genie**.

---

## Business Problem

A parent FMCG company acquires a child company.

- The parent company's data is available within Databricks.
- The child company's raw data is received as CSV files.
- The child company's data is uploaded to **Amazon S3**, which acts as the external data source.
- Databricks extracts the raw files from Amazon S3 and ingests them into the Lakehouse.
- The data is cleaned, transformed, validated, and integrated with the parent company's data to create a unified analytical platform.

The final output enables business users to analyze consolidated sales, customers, products, and stores through interactive dashboards.

---

## Technology Stack

- Databricks Free Edition
- Apache Spark (PySpark)
- SQL
- Delta Lake
- Unity Catalog
- Amazon S3
- Databricks Workflows
- AI/BI Dashboard
- Genie
- Git & GitHub

---

## Architecture

```
Child Company CSV Files
          │
          ▼
     Amazon S3 Bucket
          │
          ▼
Databricks Auto Ingestion
          │
          ▼
     Bronze Layer
          │
          ▼
     Silver Layer
          │
          ▼
      Gold Layer
          │
          ▼
AI/BI Dashboard & Genie
```

---

## ETL Workflow

### Step 1 – Data Ingestion

- Uploaded child company raw CSV datasets into Amazon S3.
- Established connection between Databricks and Amazon S3.
- Extracted the raw datasets from S3 into Databricks.
- Loaded raw data into Bronze Delta tables.

---

### Step 2 – Bronze Layer

- Stored raw source data without transformations.
- Maintained historical records.
- Preserved original schema.

---

### Step 3 – Silver Layer

Performed data transformation using PySpark.

Activities include:

- Data Cleaning
- Null Handling
- Duplicate Removal
- Schema Standardization
- Data Validation
- Business Rule Implementation
- Dimension Table Creation

---

### Step 4 – Gold Layer

Created business-ready reporting tables by joining fact and dimension tables.

The Gold layer supports:

- Sales Analysis
- Customer Insights
- Product Performance
- Store Performance
- Business KPIs

---

## Historical Load

Implemented an initial full load process that loads all historical transactional data into Delta tables.

---

## Incremental Load

Implemented incremental ETL using Delta Lake merge operations.

Only newly arrived records are processed, avoiding duplicate data while improving processing efficiency.

---

## Data Model

### Dimension Tables

- Customers
- Products
- Stores
- Dates

### Fact Table

- Sales Transactions

---

## Workflow Automation

Implemented Databricks Workflows to automate the complete ETL pipeline.

Workflow includes:

- Data Ingestion
- Bronze Processing
- Silver Processing
- Historical Load
- Incremental Load
- Gold Layer Refresh

---

## Dashboard

Built an AI/BI Dashboard in Databricks to visualize key business metrics.

Dashboard includes:

- Total Revenue
- Total Sales
- Sales Trend
- Product Performance
- Customer Insights
- Regional Performance

---

## Genie

Configured Databricks Genie to allow users to query business data using natural language.

Example:

> "Show total sales by region."

---

## Repository Structure

```
Databricks-FMCG-Data-Engineering-Project
│
├── notebooks/
│
├── sql/
│
├── screenshots/
│
├── datasets/
│
└── README.md
```

---

## Skills Demonstrated

- Data Engineering
- ETL Pipeline Development
- Medallion Architecture
- Delta Lake
- PySpark
- SQL
- Amazon S3 Integration
- Databricks Workflows
- Data Modeling
- Incremental Data Loading
- Dashboard Development
- GitHub Version Control

---

## Key Learnings

Through this project I gained hands-on experience in:

- Building scalable ETL pipelines
- Implementing Medallion Architecture
- Integrating Databricks with Amazon S3
- Performing historical and incremental data loading
- Creating Delta Lake tables
- Automating workflows
- Building AI/BI dashboards
- Using Genie for natural language analytics
- Managing project code using Git and GitHub

---

## Acknowledgements

This project was implemented as a hands-on learning exercise inspired by the Codebasics End-to-End Data Engineering Project using Databricks Free Edition. The implementation, project setup, code organization, GitHub repository, and documentation were completed independently for learning and portfolio purposes.
