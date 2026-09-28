#  Data Warehouse & Analytics Project

Welcome to my **Data Warehouse & Analytics Project** repository.

This project demonstrates an end-to-end **data warehousing and analytics solution**, covering data ingestion, ETL, data cleansing, transformation, dimensional modeling, SQL analytics, and business reporting.

The project is designed as a practical portfolio project to demonstrate my skills in **Data Engineering, BI Development, SQL, ETL, Data Modeling, and Data Analytics**.

---

##  Data Architecture

The solution follows a **Medallion Architecture** consisting of three layers:

**Bronze → Silver → Gold**

```text
                 SOURCE SYSTEMS
                      │
          ┌───────────┴───────────┐
          │                       │
        ERP CSV                CRM CSV
          │                       │
          └───────────┬───────────┘
                      │
                      ▼
              ┌───────────────┐
              │ Bronze Layer  │
              │  Raw Data     │
              └───────┬───────┘
                      │
                Data Cleaning
                & Standardization
                      │
                      ▼
              ┌───────────────┐
              │ Silver Layer  │
              │ Cleansed Data │
              └───────┬───────┘
                      │
                Transformation
                & Data Modeling
                      │
                      ▼
              ┌───────────────┐
              │  Gold Layer   │
              │ Business Data │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ SQL Analytics │
              │ & BI Reports  │
              └───────────────┘
```

###  Bronze Layer

The Bronze layer stores data in its **raw form**, preserving the structure and values received from the source systems.

Data sources include:

* ERP CSV files
* CRM CSV files

Main activities:

* Source data ingestion
* Raw data loading
* Initial validation
* Source-to-target mapping
* Load monitoring

---

###  Silver Layer

The Silver layer contains **cleaned, standardized, and integrated data**.

Main activities:

* Data cleansing
* Data type standardization
* Handling NULL values
* Duplicate detection
* Data validation
* Standardizing business rules
* Integrating ERP and CRM datasets
* Resolving data quality issues

---

###  Gold Layer

The Gold layer contains **business-ready analytical data**.

The data is modeled using a **Star Schema** consisting of:

* Fact tables
* Dimension tables
* Business metrics
* Calculated measures

This layer is optimized for:

* Analytical SQL queries
* BI dashboards
* Reporting
* KPI analysis
* Business decision-making

---

#  Project Overview

The project covers the complete lifecycle of a modern data warehouse:

### 1️ Data Architecture

Designing a scalable warehouse architecture using the **Bronze, Silver, and Gold** approach.

### 2️ Data Engineering

Building ETL processes to extract data from source files, transform the data, and load it into SQL Server.

### 3️ Data Quality

Identifying and resolving issues such as:

* Missing values
* Duplicate records
* Invalid dates
* Incorrect data types
* Inconsistent naming
* Invalid customer/product references
* Data inconsistencies between source systems

### 4️ Data Integration

Combining ERP and CRM data into a unified analytical model.

### 5️ Data Modeling

Designing a dimensional model using:

* Fact tables
* Dimension tables
* Primary keys
* Foreign keys
* Business keys
* Surrogate keys

### 6️ Analytics & Reporting

Developing SQL-based analytical queries to generate insights into:

* Customer behavior
* Product performance
* Sales performance
* Sales trends
* Revenue
* Customer segmentation
* Product contribution

---

#  Project Objectives

The primary objective is to build a **modern SQL Server Data Warehouse** capable of consolidating sales information from multiple source systems and providing a reliable foundation for analytics and BI reporting.

### Key objectives

* Build an end-to-end data warehouse
* Implement Medallion Architecture
* Develop ETL pipelines
* Integrate ERP and CRM data
* Improve data quality
* Create a dimensional data model
* Develop reusable SQL transformations
* Build analytical datasets
* Generate business insights
* Document the complete data pipeline

---

#  Technology Stack

| Technology       | Purpose                               |
| ---------------- | ------------------------------------- |
| **SQL Server**   | Data warehouse & database             |
| **SSMS**         | Database development & administration |
| **SQL**          | ETL, transformation & analytics       |
| **Python**       | Data processing & automation          |
| **Pandas**       | Data cleansing & analysis             |
| **Azure**        | Cloud & data engineering concepts     |
| **Tableau**      | BI dashboards & visualization         |
| **Draw.io**      | Architecture & data modeling diagrams |
| **Git & GitHub** | Version control                       |
| **Excel / CSV**  | Source data                           |

---

#  ETL Pipeline

The overall data pipeline follows:

```text
ERP CSV ─────┐
             │
             ▼
        Data Ingestion
             │
CRM CSV ─────┘
             │
             ▼
       ┌─────────────┐
       │ Bronze Layer│
       └──────┬──────┘
              │
              ▼
      Data Validation
              │
              ▼
       ┌─────────────┐
       │ Silver Layer│
       └──────┬──────┘
              │
              ▼
       Data Transformation
              │
              ▼
        Data Modeling
              │
              ▼
       ┌─────────────┐
       │  Gold Layer │
       └──────┬──────┘
              │
              ▼
       SQL Analytics
              │
              ▼
      BI Dashboard / Reports
```

---

#  Data Warehouse Design

The Gold layer follows a **Star Schema** approach.

Example:

```text
                    ┌─────────────────┐
                    │  Dim Customer   │
                    └────────┬────────┘
                             │
                             │
┌─────────────────┐    ┌─────▼──────┐    ┌─────────────────┐
│   Dim Product   │────│ Fact Sales │────│   Dim Date      │
└─────────────────┘    └─────┬──────┘    └─────────────────┘
                             │
                             │
                    ┌────────▼────────┐
                    │   Dim Store     │
                    └─────────────────┘
```

### Example Fact Table

`fact_sales`

Possible measures:

* Sales Amount
* Quantity
* Cost
* Profit
* Discount

### Example Dimensions

`dim_customer`

* Customer Key
* Customer ID
* Customer Name
* Gender
* Country
* City

`dim_product`

* Product Key
* Product ID
* Product Name
* Category
* Subcategory

`dim_date`

* Date Key
* Full Date
* Year
* Quarter
* Month
* Month Name
* Week

---

#  Analytics & Business Insights

The Gold layer enables analysis across multiple business areas.

##  Customer Analytics

Examples:

* Total customers
* New customers
* Repeat customers
* Customer purchase frequency
* Customer lifetime value
* Top customers by revenue
* Customer segmentation

##  Product Analytics

Examples:

* Best-selling products
* Product revenue
* Product profitability
* Category performance
* Product contribution
* Low-performing products

##  Sales Analytics

Examples:

* Total sales
* Total quantity sold
* Revenue trends
* Monthly sales
* Yearly sales
* Sales growth
* Average order value
* Top-performing periods

##  Time-Based Analysis

The Date dimension enables:

* Daily analysis
* Weekly analysis
* Monthly analysis
* Quarterly analysis
* Yearly analysis
* Year-over-year comparison
* Month-over-month comparison

---

#  Data Quality & Validation

Data quality checks are implemented throughout the pipeline.

Examples:

```text
✓ NULL value validation
✓ Duplicate record detection
✓ Primary key validation
✓ Foreign key validation
✓ Data type validation
✓ Date validation
✓ Referential integrity
✓ Invalid value detection
✓ Source-to-target reconciliation
✓ Record count validation
✓ Business rule validation
```

Example reconciliation:

```text
Source Records
      │
      ▼
Transformation
      │
      ▼
Target Records
      │
      ▼
Record Count Comparison
      │
      ▼
Data Validation
```

---

#  Repository Structure

```text
data-warehouse-project/
│
├── datasets/
│   ├── source_erp/
│   └── source_crm/
│
├── docs/
│   ├── data_architecture.drawio
│   ├── data_flow.drawio
│   ├── data_models.drawio
│   ├── etl.drawio
│   ├── data_catalog.md
│   ├── naming-conventions.md
│   └── requirements.md
│
├── scripts/
│   ├── bronze/
│   │   ├── ddl_bronze.sql
│   │   └── proc_load_bronze.sql
│   │
│   ├── silver/
│   │   ├── ddl_silver.sql
│   │   └── proc_load_silver.sql
│   │
│   └── gold/
│       ├── ddl_gold.sql
│       └── views.sql
│
├── tests/
│   ├── data_quality/
│   ├── validation/
│   └── reconciliation/
│
├── README.md
├── LICENSE
├── .gitignore
└── requirements.txt
```

---

#  Documentation

The `docs/` folder contains project documentation including:

### Data Architecture

Defines the overall architecture and interaction between source systems, warehouse layers, and reporting.

### Data Flow

Documents how data moves from source systems through Bronze, Silver, and Gold layers.

### Data Model

Documents the Star Schema and relationships between fact and dimension tables.

### Data Catalog

Provides:

* Table descriptions
* Column descriptions
* Data types
* Business definitions
* Source-to-target mappings

### Naming Conventions

Defines consistent naming standards for:

* Databases
* Schemas
* Tables
* Columns
* Stored procedures
* Views
* Files

---

#  Data Engineering Practices

This project follows several practical data engineering principles:

* Layered architecture
* Modular ETL scripts
* Reusable SQL procedures
* Data validation
* Error handling
* Source-to-target reconciliation
* Metadata-driven documentation
* Consistent naming conventions
* Version control
* Separation of raw and transformed data

---

#  Future Enhancements

The project can be extended with additional modern data engineering capabilities:

* Azure Data Factory pipelines
* Azure Data Lake Storage
* Azure SQL Database
* Incremental data loading
* Slowly Changing Dimensions
* Metadata-driven ETL
* Pipeline monitoring
* Automated data quality checks
* Python-based data processing
* Power BI / Tableau dashboards
* CI/CD for database deployments
* Cloud-based orchestration
* Automated documentation

---

#  Skills Demonstrated

This project demonstrates practical experience in:

### Data Engineering

* ETL/ELT
* Data pipelines
* Data integration
* Data cleansing
* Data validation
* Data warehouse development

### SQL Development

* Complex SQL queries
* Joins
* CTEs
* Window functions
* Aggregations
* Stored procedures
* Views
* Data transformations

### Data Modeling

* Star Schema
* Fact tables
* Dimension tables
* Surrogate keys
* Primary & foreign keys
* Dimensional modeling

### Business Intelligence

* KPI development
* Business metrics
* Analytical reporting
* Dashboard-ready datasets
* Sales analytics

### Tools & Platforms

* SQL Server
* SSMS
* PostgreSQL
* Python
* Pandas
* Azure
* Tableau
* Git & GitHub
* Draw.io

---

#  How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/data-warehouse-project.git
```

### 2. Open SQL Server

Use **SQL Server Management Studio (SSMS)** and create the required database.

### 3. Load the Bronze Layer

Execute the scripts located inside:

```text
scripts/bronze/
```

### 4. Process the Silver Layer

Run the transformation scripts:

```text
scripts/silver/
```

### 5. Build the Gold Layer

Execute:

```text
scripts/gold/
```

### 6. Run Analytics

Execute the SQL analytics queries against the Gold layer.

### 7. Connect BI Tool

Connect Tableau or another BI platform to the Gold layer and create dashboards.

---

#  Project Outcome

By completing this project, the raw ERP and CRM data is transformed into a structured analytical environment:

```text
Raw Data
   ↓
Bronze
   ↓
Clean & Standardize
   ↓
Silver
   ↓
Transform & Model
   ↓
Gold
   ↓
Analytics
   ↓
BI Dashboard
   ↓
Business Insights
```

The final solution provides a **single source of truth** for analytical reporting while maintaining a clear separation between raw, transformed, and business-ready data.

---

#  About Me

Hi, I'm **Abir Pal**, a **BI & Data Analytics Consultant** with experience in Business Intelligence, Data Analytics, SQL, Tableau, ETL, data modeling, and data engineering.

My interests include building scalable data solutions that transform raw business data into meaningful insights and decision-support systems.

### Core Areas

* Business Intelligence
* Data Analytics
* Data Engineering
* SQL Development
* Data Warehousing
* ETL & Data Integration
* Data Modeling
* Tableau
* Python
* Azure
* PostgreSQL
* SQL Server

---

##  Let's Connect

If you are interested in discussing **Data Engineering, BI, Analytics, SQL, Tableau, or modern data platforms**, feel free to connect with me.

 If you find this project useful, consider giving the repository a **star**!
