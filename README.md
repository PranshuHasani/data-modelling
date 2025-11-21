# Data-Modelling-Project
A Databricks end-to-end ETL project using the Medallion Architecture (Bronze, Silver, Gold). It includes incremental loading, MERGE/UPSERT transformations, dimensional modeling, and SCD Type-1/Type-2 implementation to create clean, analytics-ready data.

## Dataset Description
The source dataset contains:
- Order details (order_id, order_date)
- Customer information
- Product information
- Country, payment type
- quantity & unit_price
- last_updated timestamp


## Project Structure
```
data-modeling/
├── notebooks/
│   ├── 01_source.py
│   ├── 02_bronze.py
│   ├── 03_silver.py
│   ├── 04_gold.py
│   └── 05_scd.py
```

## Medallion Architecture

### **Source Layer**
- Raw OLTP-style data  
- **Table:** `source_data`

### **Bronze Layer**
- Incremental ingestion  
- **Table:** `bronze_table`

### **Silver Layer**
- Data cleaning, standardization, and UPSERT (MERGE)  
- **Table:** `silver_table`

### **Gold Layer**
- Dimensional modeling (Star Schema)  
- **Tables:**  
  - **DimCustomers**  
  - **DimProducts**  
  - **DimPayments**  
  - **DimRegions**  
  - **DimSales**  
  - **FactSales**

### **SCD Layer**
- Type-1 and Type-2 dimension updates  
- **Tables:** `scdtyp1_table`, `scdtype2_table`

## Key Features Demonstrated
- Incremental data ingestion (Bronze Layer)  
- Data cleaning & standardization (Silver Layer)  
- MERGE-based UPSERT logic  
- Dimensional modeling (Gold Layer) 
- Star Schema (Dimensions + Fact)  
- Surrogate key generation  
- SCD Type-1 and Type-2
