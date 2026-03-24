1. Project Overview
This project is an end-to-end data engineering solution built on Azure Cloud to process car sales data. It follows the Medallion Architecture (Bronze, Silver, and Gold layers) to transform raw, unstructured data into clean, business-ready datasets for advanced analytics and reporting.

2. Data Architecture (Architecture Diagram)
The following diagram illustrates the data flow and the integration of various Azure services used in this project:

3. Tech Stack
Azure Data Factory (ADF): Used for data ingestion from on-premises SQL sources to Azure Data Lake.

Azure Databricks (PySpark): The primary engine for data cleaning, complex transformations, and processing.

Azure Data Lake Gen2 (ADLS): Serves as the centralized storage layer, organized into Bronze, Silver, and Gold zones.

Delta Lake: Implemented to ensure ACID compliance and to perform efficient Merge (Upsert) operations.

GitHub: Used for source control, versioning of notebooks, and infrastructure-as-code (IaC).

4. Repository Structure
The project is organized into the following directory structure for better maintainability:

sql_scripts/: Contains the SQL DDL/Schema for the Fact and Dimension tables in the Gold layer.

adf_pipelines/: Contains the JSON definitions and ARM Templates for the Azure Data Factory infrastructure.

notebooks/: Contains the Databricks PySpark notebooks for Bronze, Silver, and Gold transformations.

5. Key Learnings & Implementations
Incremental Load: Designed a metadata-driven pipeline to process only the latest data, optimizing cost and performance.

Upsert Logic: Successfully implemented SCD Type 1 using the Delta Lake MERGE function to handle updates and inserts.

Data Quality: Ensured high data integrity by implementing deduplication logic using dropDuplicates() and Window functions.

Star Schema Modeling: Designed a curated Gold layer with a central Fact table and supporting Dimension tables for optimized BI reporting.# Azure-Data-Engineering-CarSaless-Project
