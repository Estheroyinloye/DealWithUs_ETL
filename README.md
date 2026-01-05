# DealWithUs - E-commerce ETL Pipeline

A scalable PySpark-based ETL pipeline built to replace manual Excel workflows with automated data processing.

## Project Overview

DealWithUs is a growing e-commerce platform connecting sellers and customers across multiple cities. This project builds an end-to-end ETL pipeline using PySpark to handle thousands of daily orders, clean scattered data sources, and load structured data into PostgreSQL for business intelligence.

## Business Problem

- **Manual Processing**: Excel-based reporting is slow and error-prone for large datasets
- **Data Quality Issues**: Missing values, inconsistent product names, duplicate customer records
- **Scattered Sources**: Data fragmented across multiple systems
- **Performance Bottleneck**: Cannot monitor sales trends, delivery delays, or customer behavior in real-time
- **Scalability Constraints**: Traditional tools cannot handle growing transaction volumes

## Tech Stack

- **PySpark**: Distributed data processing engine
- **Apache Spark**: Cluster computing framework
- **PostgreSQL**: Relational data warehouse
- **Parquet**: Optimized storage format
- **Python**: Core programming language


## Data Architecture

### Data Model Overview

**1. customers**
- `customer_id`, `full_name`, `email`, `country`, `signup_date`, `loyalty_status`
- Unique customer profiles and demographics

**2. products**
- `product_id`, `product_name`, `category`, `unit_price`, `brand`, `stock_count`
- Product catalog and pricing details

**3. orders**
- `order_id`, `customer_id`, `order_date`, `payment_method`, `order_status`, `shipping_cost`
- Purchase records linked to customers

**4. order_items**
- `order_item_id`, `order_id`, `product_id`, `quantity`, `unit_price`
- Line-level order breakdown for revenue analytics

## ETL Pipeline Workflow

### 1. Extract
Load CSV file from local into PySpark DataFrames

### 2. Clean
- Handle null values and missing data
- Remove duplicate records
- Standardize date formats and currency values
- Normalize dataset

### 3. Transform
- Create new columns
- Join datasets across customer, product, and order dimensions
- Aggregate metrics for reporting
  

### 4. Optimize
- Write data in Parquet format for compression and speed

### 5. Load
Save cleaned and transformed data into PostgreSQL tables for BI tools

