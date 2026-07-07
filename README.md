# End-to-End Data Engineering Pipeline: Online Retail Analytics

## Project Overview
This project aims to build an end-to-end data engineering pipeline to transform raw retail data into analytical insights using Power BI. The source data used is the original UK-based Online Retail Transaction CSV dataset consisting of 541,910 rows. This raw data has several issues such as duplicate records, missing values, and inconsistent transactions that need to be addressed before it can be used directly for sales and customer behavior analysis, as well as product performance monitoring.

## Tech Stack & Architecture
This project implements an ETL (Extract, Transform, Load) approach because data transformation is performed before loading it into MySQL, which is considered more suitable for retail analysis to ensure the data is more reliable, easily validated, and cleaner in structure.
*   **Data Source:** CSV file (raw data source).
*   **Preprocessing:** Python is used for initial preprocessing.
*   **ETL Orchestration:** Pentaho Data Integration is used to orchestrate the sequential execution of the ETL pipeline, from data ingestion and the creation of dimension tables to the fact table.
*   **Data Storage:** MySQL is used as a structured relational database to store the results of the ETL process.
*   **Data Visualization:** Power BI is used to build an interactive dashboard.

## Data Modeling
The data is modeled using a **Star Schema** approach. This schema was chosen because it is highly optimal for analytical needs, facilitates easier integration with Power BI, and accelerates the processing of reporting queries.
*   **Fact Table:** `fact_sales` (contains key metrics and calculations such as Quantity, UnitPrice, and TotalSales).
*   **Dimension Tables:** `dim_customer`, `dim_product`, and `dim_time`.

## Data Quality & Reliability Assurance
To ensure data quality and reliability (trustworthy data), this project applies the following strategies:
*   Cleaning the data by removing duplicate rows, handling null values, and validating data types.
*   Implementing strict validation rules: `quantity > 0` and `unit_price > 0`.
*   Maintaining reliability with a structured ETL workflow, controlled data transformations, consistency checks, and the detection of invalid transactions.

## Analytical Insights
The generated Power BI dashboard revealed several key business findings:
*   The company has 4,338 loyal customers, with transactions dominated by returning customers.
*   The majority of customers frequently check out transactions during lunch hours (12:00 PM - 1:00 PM).
*   There is a spike trend in transactions during October - November, indicating customers restock goods ahead of the year-end holidays (Christmas and New Year).
*   The company has a healthy revenue stream, reaching around £400K - £500K per month.
*   The largest sales come from the customer base in the United Kingdom, with the most frequently purchased product being *Paper Craft, Little Birdie*.

## Team & Responsibilities (Group 11)
This Data Engineering Project was collaboratively developed by:
*   **Raymond Widjaja** (2802474406): Power BI Dashboard & Project Documentation.
*   **Keisa Putri Alisa** (2802456662): Python Preprocessing, Pentaho ETL & MySQL Database.
*   **R. Divika Rathi** (2802535963): Python Preprocessing, Pentaho ETL & MySQL Database.
