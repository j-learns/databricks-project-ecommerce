# E-commerce Data Pipeline & Analytics Dashboard

## Project Overview
This project demonstrates an end-to-end data engineering and analytics workflow built on **Databricks**. Using e-commerce datasets provided by **codebasics.io**, I developed a scalable data pipeline following the **Medallion Architecture**. The project covers the full lifecycle of data—from landing raw files to performing complex PySpark transformations and building a final business intelligence dashboard.

## Technical Stack
* **Platform:** Databricks
* **Languages:** Python (PySpark), SQL
* **Architecture:** Medallion (Bronze, Silver, Gold)
* **Storage:** Delta Lake
* **Visualisation:** Databricks SQL Dashboards

## Data Pipeline & Architecture

### 1. Ingestion (Raw Layer)
The process begins with a raw "dumping ground" where external data is loaded in its original format. This landing zone acts as a permanent record, ensuring that original data is preserved before any modifications take place.

### 2. Medallion Workflow
I implemented a multi-stage pipeline to refine and structure the data as it moves through the Lakehouse:

* **Bronze Layer:** Data is ingested from the raw landing zone into Delta tables. This layer maintains the raw state of the data while enabling ACID transactions.
* **Silver Layer (Transformations):**
    * Used **PySpark** for data cleaning, handling null values, and deduplication.
    * Standardised schemas and performed data type casting to ensure consistency across the dataset.
* **Gold Layer (Dimension & Fact Modelling):**
    * Transformed refined data into a relational **Star Schema**.
    * Created **Dimension tables** (e.g., Customers, Products) and **Fact tables** (e.g., Sales) to optimise the environment for analytical queries and reporting.

### 3. Analytics & Insights
Once the data was structured into the Gold layer, I used **SQL** to query the Fact and Dimension tables. I then built a comprehensive **Sales Dashboard** within Databricks to visualise key performance indicators and business trends.
