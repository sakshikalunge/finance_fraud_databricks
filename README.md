An end-to-end data engineering project built on Azure Databricks that processes batch and streaming financial data to generate fraud insights using a Medallion Architecture (Bronze → Silver → Gold) and a CI/CD deployment pipeline.

🚀 Project Overview

This project simulates a real-world financial fraud detection data platform.
It ingests raw financial data, cleans and transforms it, and produces a curated fraud analysis dataset.

The platform handles:

- Batch data → Customers, Accounts, Merchants
- Streaming data → Transactions

All pipelines are built using PySpark, orchestrated with Databricks Jobs, and deployed automatically using a GitHub CI/CD pipeline.

🏗️ Architecture
- Cloud Platform: Azure
- Processing Engine: Azure Databricks
- Storage: Azure Data Lake Storage (ADLS Gen2)
- Governance: Unity Catalog (External Locations, Storage Credentials, Grants)

Medallion Architecture
- 🥉 Bronze	Raw -                  unprocessed data from source systems (batch + streaming)
- 🥈 Silver	Cleaned -             standardized, and enriched data with CDC handling
- 🥇 Gold -	                        curated fraud analytics dataset with engineered fraud features

🔄 Data Engineering Features

✅ Batch + Streaming Pipelines

- Built using PySpark
- Used Structured Streaming for real-time transaction ingestion

✅ CDC & Dimension Handling
- Implemented Change Data Capture (CDC)
- Applied Slowly Changing Dimensions (SCD):
- Type 0 – No change tracking
- Type 1 – Overwrite with latest values

✅ Fraud Feature Engineering
Gold layer includes fraud-focused transformations such as:
- Transaction behavior patterns
- Account activity signals
- Derived fraud risk indicators
- Final Fraud Score dataset

⚙️ Orchestration

All pipelines are scheduled and executed using Databricks Job Workflows
Supports reliable, repeatable production-style runs

🔁 CI/CD Pipeline
This project includes a GitHub Actions CI/CD pipeline that:
- Connects securely to Databricks using secrets
- Automatically deploys notebooks to workspace folders:
1. /Shared/finance_fraud_project/bronze
2. /Shared/finance_fraud_project/silver
3. /Shared/finance_fraud_project/gold

Enables:
- Version control
- Automated deployments
- Reproducible environments

🎯 Outcome
This project demonstrates how to build a modern, governed, and production-ready data platform that:
- Handles batch and streaming data
- Applies data quality and transformation layers
- Implements CDC & dimensional modeling
- Produces fraud analytics datasets
- Uses CI/CD for automated cloud deployment
