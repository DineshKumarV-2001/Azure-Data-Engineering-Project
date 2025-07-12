# Azure-Data-Engineering-Project

📌 Project Overview

This project demonstrates an end-to-end ETL pipeline built on Azure, processing the Olist eCommerce dataset using Azure Data Factory, Azure Databricks (PySpark), and Azure Data Lake Storage Gen2. It follows a modern medallion architecture (Bronze, Silver, Gold) for layered data management.

⚙️ Tools & Technologies

Azure Data Factory (ADF)

Azure Databricks (PySpark)

Azure Data Lake Storage Gen2 (ADLS Gen2)

Delta Lake / Parquet

Python / PySpark


🧭 ETL Architecture

 Source (CSV) ──▶ ADF ──▶ ADLS Gen2 (Bronze Layer)
                           │
                           ▼
                   Azure Databricks (PySpark)
                           │
                           ▼
              ADLS Gen2 (Silver & Gold Layers)
              

              

Azure Data Factory (ADF) : Pipeline Overview: 

![image](https://github.com/user-attachments/assets/3d3c7666-ad47-43ad-b40d-5b07757e1269)

